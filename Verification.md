Verification
============

While the checksums included in the conf files provide verification of no
mutation between the time that Apcera Engineering saw a file and the time that
it is seen by a Stager building a package in Continuum, those checksums do not
in themselves verify that source was not already compromised by the time that
Apcera Engineering first viewed the file.

Unfortunately, it's uncommon for releases to be signed by PGP keys in the
strong set, with decent end-to-end assurances.  So this file records some
observances which at least let us provide for continuity and a degree of
implicit trust in a particular signing setup when a key is seen used across
multiple releases, so we at least can spot if something has _changed_.  If we
see one PGP key used for multiple years, with no cries of outrage, then that
particular key is probably legitimate.

If upstream use something as compromised as MD5, we can't do much about that,
except note it.

This file is stored in Git, which has a degree of backwards trust chaining, so
modifications to history and the contents of this file should result in
conflicts which are visible to every engineer who has this repository checked
out.

In an ideal world, we wouldn't have to rely upon software we can't
meaningfully or reasonably verify, but we're packaging up existing systems,
used by others, and the dependencies of those systems, so we don't get to
choose the software and apply market forces by selecting only software which
meets our criteria.


LibJPG
------

Release site at <http://www.ijg.org/>; HTTPS unrelated (accesses site-builder
default install setup).  Older releases also in index at
<http://www.ijg.org/files/>.  No fingerprints, no signatures.  Nada.

Using the older releases in index, we can pull back "latest" and "last one in
a package .conf" and if the latter verifies, hope that an attacker is
restricting themselves to only trojanning the latest.


FreeType
--------

<http://www.freetype.org/download.html> references
<http://download.savannah.gnu.org/releases/freetype/>.  Releases and detached
signatures are available there.

Signatures observed (as of 2.5.2) were with keyid 0xC1A60EACE707FDA5 which has
(very stale) signatures from 0x9710B89BCA57AD7C, the “PGP Global Directory
Verification Key”.  That service issues two-week signatures upon key
retrieval, but no longer has that key, or any other for <wl@gnu.org>.  The
last such signature dates from 2005.  So this ten-year-old 1024-bit key has
only signatures from an address verification signer, eight years ago.


LibPNG
------

Releases indexed at <http://www.libpng.org/pub/png/libpng.html>.  No HTTPS.
No cryptographic signatures.  MD5 checksums found in the web-page.  The
SourceForge git repo is a sequence of imports from the release tarballs.

Can't spot an OS bundling newer than 1.5.x.

In short: no meaningful verification is possible without a source audit and
ongoing delta audits.  It seems the general open source community is using
Ongoing Repeated Leaps Of Faith around libpng.


PHP
---

Software releases are indexed at <http://www.php.net/downloads.php>, HTTPS not
available.  There are different PGP keys used for each major.minor release
series; each release has a detached signature, and there's an MD5 signature on
the release-page.

As of 2013-12-15, the keys observed were:

 * PHP 5.5.7:  0xFE857D9A90D90EC1
 * PHP 5.4.23: 0x2F7956BC5DA04B5D

Neither key is in the strong set, I (Phil) have no trust path to them.  The
detached signatures validated, and the MD5 checksums of the files signed
matched those given on the unencrypted release page.

#EOF

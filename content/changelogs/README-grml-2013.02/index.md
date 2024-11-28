+++
title = 'Release Notes: Grml 2013.02 - Codename Grumpy Grinch'
+++

<p><a href="/screenshots/"><img align="right" style="margin-left: 20px;
border: 0" src="/screenshots/grml_2013.02.jpg" alt="*" /></a></p>

<h3>About</h3>

<p>This release brings the Grml tools towards the upcoming Debian stable
release (AKA wheezy), provides up2date hardware support and fixes known
bugs from the previous Grml release.</p>

<h3>New features</h3>

<ul>

<li>ssh boot option: display SSH server key fingerprints

<li>grml-hwinfo: added support for lsscsi, iscsiadm,
proxmox/libvirt/openvz/vserver information retrieval, swapon, mdadm,
LVM + dmsetup, now using 'lspci -nn' for lspci output

<li>grml-live: handling firmware related packages in GRMLBASE, added
uuid-runtime to GRMLBASE

<li>grml-network: netcardconfig provides support to scan for available
wireless networks

<li>grml-udev-config: Do not set mount options for NTFS partitions to
"ro" any longer

<li>grml2usb: verify that the bootflag is enabled

<li>grml2iso: ISOs are dd-able by default

<li>grml-debootstrap:

<ul>

<li>Use http.debian.net as default mirror
<li>Set wheezy as the new default release
<li>Add acpi-support-base + firmware-linux-free to default package selection

</ul>

</ul>

<h3>Important Changes</h3>

<ul>

<li>/etc/apt/sources.list.d/debian.list no longer uses cdn.debian.net
for the Debian repository, instead uses snapshot.debian.org with the
according release date. This should make installation of additional
software with regards to additional dependencies easier for users.

<li>Debian's live-boot changed the path from /live/image to
/lib/live/mount/medium. If you're using /live/image anywhere inside
your own custom scripts please adopt your code to use /lib/live/mount/medium
starting with Grml 2013.02.

<li>Debian's live-boot changed some persistency related settings.
Please visit <a href="https://github.com/grml/grml/wiki/persistency">
the persistency page in the Grml wiki</a> for further details.

</ul>

<h3>Bits &amp; bolts</h3>

<ul>
<li>Linux kernel is based on <b>3.7.9</b>. No additional modules are shipped.</li>
<li>Fixed several bugs from the <a href="http://bts.grml.org/grml/">bug tracking system</a>.</li>
</ul>

<h3>Packages</h3>

<p>Details about shipped packages and their versions on Grml are
available at the <a href="/files/#debian">Debian section</a>. Visit
<a href="/files/grml64-full_2013.02/dpkg.list">dpkg.list</a> for a
detailed list of packages shipped with Grml 2013.02.</p>

<h3>Updates</h3>

<p>Packages are taken from Debian testing, 26th of February
2013. 13 packages have been removed, and these 22 new packages
have been added (plus dependencies, excluding lib* and kernel image):</p>

<pre class="rahmen">
aptitude-common atmel-firmware bluez-firmware cpp-4.7 cryptsetup-bin epdfview
firmware-atheros firmware-bnx2 firmware-bnx2x firmware-intelwimax
firmware-libertas firmware-linux genisoimage ifenslave-2.6 insserv
libertas-firmware netsniff-ng ruby1.9.1 ssmping uuid-runtime virt-what
zd1211-firmware
</pre>

<p>These Grml packages have been removed/replaced (excluding lib* and kernel image):</p>

<pre class="rahmen">
arrayprobe consolekit cpp-4.6 fuse-utils gcc-4.5-base gcc-4.6-base
grub info linux-sound-base smbfs tasksel tasksel-data xorriso
</pre>

<h3>Known issues</h3>

<p>None at the time of the release!</p>

<p>Take a look at <a
href="/bugs/known/">the known bugs list</a>.
Please report problems using information on <a
href="/bugs/">grml.org/bugs/</a>.</p>


<h3>Download Grml 2013.02</h3>

<p>Grml 2013.02 can be downloaded from
<a href="http://grml.org/download/">grml.org/download/</a>.</p>

<h3>Feedback</h3>

<p>Your comments, bug reports, patches, and suggestions will help
fixing bugs and improving future releases. If you find a problem with
the release please check <a
href="/bugs/known/">the known bugs list</a> and report problems using information on <a
href="/bugs/">grml.org/bugs/</a>. Please send your feedback and
feature requests <a href="/contact/">to the Grml team</a>!</p>

<a name="thanks"></a>
<h3>Thanks</h3>

<p>Many thanks in this release go to (alphabetically)
Andras Korn,
Bernhard Tittelbach,
Charles A. Hewson,
Christian Hesse,
Christian Hofstaedtler,
Christoph Biedl,
Csillag Tamas,
Dominik Schips,
Evan Pitstick,
Florian Apolloner,
Florian Klien,
frenbu,
Gregor Herrmann,
Hendrik Jaeger,
Lukas Anzinger,
Pawel Sadkowski ,
Peter Palfrader,
Pierre Schmitz,
Raoul Raminder Andreas,
Thorsten Glaser and
Ulrich Dangel
for their contributions.</p>

<h3>More Information</h3>

<p>You can find out more about Grml on <a href="/">our website</a>, <a
href="/contact/#irc">IRC channel</a>, and <a
href="http://wiki.grml.org/">wiki</a>.

<p>To sign up for future Grml announcements, please subscribe to <a
href="http://ml.grml.org/mailman/listinfo/grml-announce">Grml's
announcement list</a>.</p>

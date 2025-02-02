+++
title = 'Release Notes: Grml 2014.03 - Codename Ponywagon'
+++

<p><a href="/screenshots/"><img align="right" style="margin-left: 20px;
border: 0" src="/screenshots/grml_2014.03.jpg" alt="*" /></a></p>

<h3>About</h3>

<p>This Grml release provides fresh software packages from Debian
testing (AKA jessie). As usual it also incorporates up2date hardware
support and fixes known bugs from the previous Grml release.</p>

<h3>New features</h3>

<ul>

<li>new boot option <em>vlan</em>: this provides
support for e.g. using something like
'ip=10.10.10.42::10.10.10.1:255.255.255.0:grml:eth0:off
vlan=301:eth0' to use VID 301 for device eth0 (development sponsored
by <a href="http://www.sipwise.com/">Sipwise
GmbH</a>)</li>

<li>grml-debootstrap:

<ul>
<li>Support FIXED_DISK_IDENTIFIERS option, useful for reproducible builds</li>
<li>install bridge-utils, cryptsetup, ifenslave and vlan packages by default</li>
<li>Support overriding configuration via environment variables</li>
</ul>

</li>

</ul>

<h3>Important Changes</h3>

<ul>

<li>forensic mode: the <em>readonly</em> boot option
was renamed to <em>read-only</em> (caused by change in
upstream's live-boot)</li>

</ul>

<h3>Bits &amp; bolts</h3>

<ul>
<li>Linux kernel is based on <b>3.13.6</b>.</li>
<li>Fixed several bugs from the <a href="http://bts.grml.org/grml/">bug tracking system</a>.</li>
</ul>

<h3>Packages</h3>

<p>Details about shipped packages and their versions on Grml are
available in the <a href="/files/#debian">Debian section</a>. Visit
<a href="/files/grml64-full_2014.03/dpkg.list">dpkg_list</a> for a
detailed list of packages shipped with Grml 2014.03).</p>

<h3>Updates</h3>

<p>Packages are taken from Debian testing, 30th of March
2014. 18 packages have been removed, and these 22 new packages
have been added (plus dependencies, excluding lib* and kernel image):</p>

<pre class="rahmen">
dump ifenslave nocache openssh-sftp-server python-crypto
python-dnspython python-ldb python-lockfile python-ntdb
python-samba python-talloc python-tdb qemu-system-common
qemu-system-x86 samba-common-bin samba-dsdb-modules
samba-libs sysvinit-core tcplay tdb-tools
xserver-xorg-video-modesetting xulrunner-24.0
</pre>

<p>These Debian packages have been removed/replaced (excluding lib* and kernel image):</p>

<pre class="rahmen">
ifenslave-2.6 recover ruby1.8 rubygems ttf-dejavu-core ufsutils
vgabios xserver-xorg-video-apm xserver-xorg-video-ark
xserver-xorg-video-chips xserver-xorg-video-i128
xserver-xorg-video-rendition xserver-xorg-video-s3
xserver-xorg-video-s3virge xserver-xorg-video-sis
xserver-xorg-video-tseng xserver-xorg-video-voodoo
xulrunner-17.0
</pre>

<h3>Known issues</h3>

<p>Please visit <a href="/bugs/known/">the known bugs webpage</a>.</p>

<h3>Download Grml 2014.03</h3>

<p>Grml 2014.03 can be downloaded from
<a href="/download/">grml.org/download/</a>.</p>

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
Andreas Gredler,
Axel Beckert,
Bernhard Tittelbach,
Christian Hofstaedtler,
Christoph Biedl,
Lukas Prokop,
Marc Haber,
Michael Schierl,
Patrick Schleizer,
Raoul and
Thilo Six
for their contributions.</p>

<h3>More Information</h3>

<p>You can find out more about Grml on <a href="/">our website</a>, <a
href="/contact/#irc">IRC channel</a>, and <a
href="http://wiki.grml.org/">wiki</a>.

<p>To sign up for future Grml announcements, please subscribe to <a
href="http://ml.grml.org/mailman/listinfo/grml-announce">Grml's
announcement list</a>.</p>

+++
title = 'Release Notes: Grml 2018.12-rc1 - codename Gnackwatschn'
+++

<p><strong>NOTE: the <a href="/changelogs/README-grml-2018.12/">stable release 2018.12</a> is already available!</strong></p>

<p><a href="/download/prerelease/">Download Now</a></p>

<h3>About</h3>

<p>Grml is a Debian based live system focusing on the needs of system administrators.
This Grml release provides fresh software packages from Debian testing (AKA buster).
As usual it also incorporates up to date hardware support and fixes known bugs from the previous Grml release.</p>

<h3>Important Changes</h3>

<ul>

<li>When using the `ssh` boot option Grml automatically starts haveged, an userspace entropy daemon which
uses HAVEGE (HArdware Volatile Entropy Gathering and Expansion).
If you should notice a slow boot and want to force the startup of the haveged service (independent of usage of ssh boot option)
you can start the service via boot option `services=haveged`.
See e.g. <a href="https://daniel-lange.com/archives/152-Openssh-taking-minutes-to-become-available,-booting-takes-half-an-hour-...-because-your-server-waits-for-a-few-bytes-of-randomness.html">Openssh
taking minutes to become available [...]</a> for further information.

<li>The cpufrequtils package with its loadcpufreq handling has been dropped. The cpufreq drivers are autoloaded and the powersave/ondemand driver is mature enough. The linux-cpupower tools provide the binaries as replacement for what cpufrequtils provided so far.

<li>If you're using Debian/stretch or newer and use the Grml repository on any of your systems, starting with version grml-debian-keyring (2018.06.02) of the grml-archive-keyring package you can use a
/etc/apt/sources.list.d/grml.sources setup like:

<pre>

Types: deb deb-src
URIs: http://deb.grml.org/
Suites: grml-stable grml-testing
Architectures: i386 amd64
Components: main
Signed-By: /usr/share/keyrings/grml-archive-keyring.gpg

</pre>

or you prefer the common sources.list setup you can use a /etc/apt/sources.list.d/grml.list like:

<pre>

deb [signed-by=/usr/share/keyrings/grml-archive-keyring.gpg] https://deb.grml.org/ grml-stable  main
deb [signed-by=/usr/share/keyrings/grml-archive-keyring.gpg] https://deb.grml.org/ grml-testing main

</pre>

<a href="https://wiki.debian.org/DebianRepository/UseThirdParty">https://wiki.debian.org/DebianRepository/UseThirdParty</a> provides more general documentation about this setup.

</ul>

<h3>New features</h3>

<p>Highlighting the most relevant changes only:</p>

<ul>

<li>Misc:

<ul>
<li>netcardconfig: added support for VLAN configuration + non-interactive mode
<li>grml-chroot: mount /dev/pts as devpts inside chroot
<li>grml2usb: added support for Secure Boot (if present with ISO only)
</ul>

</li>


<li><a href="/grml-live/">grml-live</a> (build system for creating Grml (based) Linux live systems):

<ul>
<li>Added support for EFI on 32-bit systems and increased EFI image size
<li>Switched from isohybrid to xorriso/isohybrid combination
<li>Several software additions/changes to GRML_SMALL and GRML_FULL classes
<li>Several changes, fixes and workarounds for systemd integration
<li>Added support for Debian/buster
<li>Dropped support for Debian/wheezy
<li>Added Secure Boot support (disabled by default though)
<li>Updated defaults and documention to use and assume Debian/stretch by default
<li>Replaced /etc/apt/grml.key with /etc/apt/trusted.gpg.d/grml-archive-keyring.gpg
<li>Updated cheatcodes to clarify hardware clock and timezone defaults
<li>Enable serial-getty with root autologin on every given device
</ul>

</li>

<li>grml-hwinfo (tool to collect hardware information):

<ul>
<li>Provide output of `efibootmgr -v` in file efibootmgr
<li>sysdump: ignore files inside /sys/kernel/debug + /sys/kernel/security/apparmor/revision to avoid hanging
<li>Redirect `ip mrule show` errors to ip_mrule.error
</ul>

</li>

<li><a href="/zsh/">grml-zshrc</a> (Zsh configuration):

<ul>
<li>grml-lang zsh completion: add dvorak, es, fr, it + jp to list of supported languages
<li>Use `apt` instead of `apt-get` in aliases when applicable (acp, acs, acsh, adg, ag, agi)
<li>Moved insert-datestamp to 'C-x d' (from 'Ctrl-e d'), to avoid defalys in the default Ctrl-e binding in emacs mode
</ul>

</li>

<li><a href="/grml-debootstrap/">grml-debootstrap</a> (wrapper around debootstrap for installing pure Debian):

<ul>
<li>Identify UUID of target system even if it's SWRAID or a mountpoint
<li>Travis CI integration (running automated VM installation tests)
<li>Switched default mirror from httpredir.debian.org to deb.debian.org
<li>Improved checks to make sure loop and dm-mod module are present
<li>Ensure /etc/timezone also includes the TIMEZONE setting
<li>Support skipping installation of GRUB bootloader using GRUB_INSTALL='no'
<li>Do not create target directory in /dev
<li>packer: added support for building Debian/buster + updated VirtualBox Guest Additions to 5.2.22
</ul>

</li>

</ul>

<h3>Bits &amp; bolts</h3>

<ul>
<li>Linux kernel is based on <b>4.19.8</b>.</li>
<li>Fixed several bugs from the <a href="https://github.com/grml/grml/issues/">issue tracking system</a>.</li>
</ul>

<h3>Packages</h3>

<p>Details about shipped packages and their versions in Grml are
available in the <a href="/files/#debian">Debian section</a>. Visit
<a href="/files/grml64-full_2018.12/dpkg.list">dpkg_list</a> for a
detailed list of packages shipped with Grml 2018.12(-rc1).</p>

<h3>Updates</h3>

<p>Packages are taken from Debian testing as of 19th of December 2018.
27 packages have been removed, and these 76 new packages
have been added (excluding lib* and kernel image):</p>

<pre class="rahmen">
bcache-tools binutils-common binutils-x86-64-linux-gnu cpp-8
cryptsetup-initramfs cryptsetup-run dbus-user-session dirmngr dislocker ed
fakeroot fdisk gcc-8-base gdbm-l10n gir1.2-glib-2.0 glusterfs-common
gnupg-l10n gnupg-utils gpg gpg-agent gpg-wks-client gpg-wks-server gpgconf
gpgsm iso-codes linux-libc-dev lm-sensors mcollective mcollective-common
ndisc6 nmap-common patchutils perl-modules-5.28 python-colorlog
python-fasteners python-humanize python-monotonic python-six python-talloc
python2 python2-minimal python3-certifi python3-chardet python3-configshell-fb
python3-gi python3-idna python3-jwt python3-pkg-resources python3-prettytable
python3-pyparsing python3-pyudev python3-requests python3-rtslib-fb
python3-six python3-urllib3 python3-urwid python3.7 python3.7-minimal
qemu-guest-agent qemu-system-data rdnssd restic ruby-stomp ruby-systemu
ruby-xmlrpc ruby2.5 stressant targetcli-fb tcl tcl8.6 thin-provisioning-tools
tk tk8.6 wdiff x11vnc x11vnc-data
</pre>

<p>These Debian packages have been removed/replaced (excluding lib* and kernel image):</p>

<pre class="rahmen">
apt-transport-https aptitude aptitude-common btrfs-tools cpp-6 cpufrequtils
dh-python e2fslibs gcc-6-base gnome-icon-theme gnupg-agent iproute lynx-cur
multiarch-support perl-modules-5.24 python-talloc python-urwid python3.5
python3.5-minimal qemu-kvm realpath ruby-nokogiri ruby-pkg-config ruby-rgen
ruby-safe-yaml ruby2.3 xdg-utils
</pre>

<h3>Known issues</h3>

<p>Please visit the <a href="/bugs/known/">known bugs</a> web page.</p>

<h3>Download Grml 2018.12-rc1</h3>

<p>Grml 2018.12-rc1 can be downloaded from
<a href="/download/prerelease/">grml.org/download/prerelease/</a>.</p>

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
András Korn,
Andreas Henriksson,
Antoine Beaupré,
Bernhard Tittelbach,
Bigo,
Chris Hofstaedtler,
David Prévot,
f0,
Grégoire Sutre,
Guillem Jover,
Helmut Grohne,
hex2a,
James Tocknell
joeran,
karlh1,
Leo Bergolth,
luke2261git,
Marc Haber,
Marcos Mello,
Markus Lindberg,
Martin Besser,
maximebuy,
Michael Biebl,
Michael Eischer,
Michael Schierl,
Moviuro,
Mykola Malkov,
Patrick Neumann,
Patrick Schleizer,
Paul Menzel,
Ralf Moll +
sl0n
for their contributions.</p>

<h3>More Information</h3>

<p>You can find out more about Grml on <a href="/">our website</a>, <a
href="/contact/#irc">IRC channel</a>, and <a
href="https://github.com/grml/grml/wiki">wiki</a>.

<p>To sign up for future Grml announcements, please subscribe to <a
href="http://ml.grml.org/mailman/listinfo/grml-announce">Grml's
announcement list</a>.</p>

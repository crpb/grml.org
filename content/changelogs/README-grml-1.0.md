+++
title = 'Release Notes: grml 1.0 Meilenschwein (20070518)'
url = '/changelogs/README-grml-1.0.html'
+++

<p><a href="/screenshots/"><img align="right" style="margin-left: 20px;
border: 0" src="/screenshots/grml_1.0_small.jpg" width="140" alt="*" /></a></p>

<h3>About</h3>

<p>grml is a Debian-based Live-CD. It includes a collection of GNU/Linux
software especially for users of texttools and system administrators.
grml provides automatic hardware detection. You can use grml for example
as a rescue system, for analyzing systems/networks or as a working
environment. It is not necessary to install anything to a harddisk, you
don't even need a harddisk to run it, unless you want to (use grml2hd
for this). Due to on-the-fly decompression grml includes about 2.1 GiB
of software and documentation on the CD.</p>

<h3>Bugfixes</h3>

<p>Fixed several bugs and issues reported on <a
href="https://github.com/grml/grml/wiki/grml_0.9">grml_0.9 @
grml-wiki</a>.</p>

<h3>New features</h3>

<p>Several improved, updated and extended configuration files.</p>

<h4>New grml-scripts (some selected ones):</h4>

<ul>

<li>alignmargins: adjust the margins and the position of the printed contents on the paper

<li>dirvish-setup: a simple script for setting up a basic configuration for the backup software dirvish

<li>grml2ram: copy compressed GRML image to RAM when running grml already (based on contribution by Michael Schierl)

<li>grml-quickconfig: get fast access to some basic grml-scripts (contributed by Michael Schierl)

<li>grml-setservices interface for basic configuration of system startup/shutdown via /etc/runlevel.conf

<li>gsuggest.pl: google suggest - ask google for keyword suggestions

<li>iso-term: wrapper script to run x-terminal-emulator in iso885915 mode

</ul>

<h4>New bootparameters/cheatcodes:</h4>

<ul>

<li>qemu: installs a default /etc/X11/xorg.conf (without having to run hardware detection)

<li>debian2hd: install plain Debian via <a href="/grml-debootstrap/">grml-debootstrap</a> in automatic mode

</ul>

<h4><a href="/grml2hd/">grml2hd</a> (install grml to harddisk):</h4>

<ul>

<li>support for Grub (now there's a dialog for selection between lilo and grub as bootloader)

<li>use of UUID and /dev/disk/by-uuid/ by default (provides stable booting devices, very important for installation on external usb/firewire
devices for example)

<li>use initrd/initramfs by default now

</ul>

<p>See <a href="/grml2hd/">grml.org/grml2hd/</a> for more
details regarding grml2hd.</p>

<h4><a href="/terminalserver/">grml-terminalserver</a> (boot
grml via network)</h4>

<ul>
<li>better module loading

<li>switch from tftpd-hpa to atftpd (resulting in big speedup)

</ul>

<p>See <a href="/terminalserver/">grml.org/terminalserver/</a>
for more details regarding grml-terminalserver.</p>

<h4><a href="/grml-debootstrap/">grml-debootstrap</a> (install plain
Debian fast and easy)</h4>

<ul>
<li>support full automatic installation via debian2hd
<li>use aptitude instead of apt-get in chroot-script
<li>use of DEBIAN_FRONTEND='noninteractive' to avoid unnecessary questions when installing
<li>support Debian release with codename 'lenny'
<li>support stages (improves cancel/resume of operations)
<li>support setting of some important variables via cmdline
<li>improved error handling
</ul>

<p>See <a href="/grml-debootstrap/">grml.org/grml-debootstrap/</a> for
more details regarding grml-debootstrap.</p>

<h4>Special new features:</h4>

<ul>

<li>updated to X.org 7.2 / Xserver 1.3</li>

<li>updated to libc6 2.5</li>

<li>use of <a href="#utf8">UTF-8</a> as default encoding</li>

<li>LaTeX: switch from tetex to texlive</li>

<li>grml-x: use of evdev (dropped options -nousb and -nops2, added
-ps2 and -usb instead), improved error handling and execution</li>

<li>grml-autoconfig: dropped userspace/powernowd stuff in
cpufrequeny scaling in favour of the ondemand-governor

<li>integrated grml-quickconfig within zsh-login

<li>got rid of grml-sysvinit, using plain sysvinit from Debian
without any hacks now

<li>support basic rescanning in live-cd initrd

<li>the grml team manages <a href="http://hg.grml.org/">all the Debian unique packages</a> with <a
href="http://www.selenic.com/mercurial/">mercurial</a> using <a
href="http://deb.grml.org/pool/main/g/grml-mercurial-utils/">grml-mercurial-utils</a>

</ul>

<h3>Kernel</h3>

<p>Based on vanilla kernel 2.6.20.11 including <a
href="/kernel/">several patches</a> (Speakup, Squashfs,...) and
additional modules:</p>

<pre class="rahmen">

acerhk, aufs, cowloop, drbd8, et131x, exmap, ipw3945, iscsitarget, ivtv, kqemu,
madwifi, misdn, ndiswrapper, nozomi, openafs, pcan, qc-usb, r1000, realtime-lsm,
rt2400, rt2500, rt2570, rt2x00, sdricoh_cs, sl-modem, snd-bt-sco, spca5xx,
sysprof, tidev, tpm_emulator, truecrypt, unionfs

</pre>

<p>Notice: some more modules
<!-- <a
href="https://github.com/grml/grml/wiki/ati">fglrx</a> and <a
href="https://github.com/grml/grml/wiki/nvidia">nvidia</a>)
-->
are not pre-installed but available through the <a href="http://deb.grml.org/">grml-repository</a>.</p>

<p>See <a href="/kernel/">grml.org/kernel/</a> for more details
regarding the grml-kernel.</p>

<h3>Important Changes</h3>

<p><a name="utf8"></a><strong>UTF-8:</strong> grml uses UTF8 as
default encoding. You can deactivate UTF-8 environment via
booting with bootoption lang=$LANG-iso.  Some software is not
yet UTF-8 aware (problem is located upstream, neither at Debian
or grml itself). More information about UTF-8 at grml can be
found at the <a
href="https://github.com/grml/grml/wiki/utf8">utf8 webpage in
the grml-wiki</a>.</p>

<p><strong>get_tw_cli / get_3ware:</strong> get_tw_cli has been
renamed into get_3ware as we support 3DM2 as well now.</p>

<p><strong>fluxbox:</strong> the keybindings have been restored to
their original (fluxbox upstream) behaviour. Now Alt+F# switches
between the desktops, Alt+Shift+F# sends an application to another
desktop. If you want to get the old behaviour back you can use the zsh
function fluxkey-change.</p>

<h3>Packages / Software</h3>

<p>Details about shipped packages and their versions on grml are
available at the <a href="/files/#debian">Debian section</a>. See <a
href="/files/release-1.0/dpkg_get_selections">dpkg_get_selections</a>
for a main package listing and <a
href="/files/release-1.0/dpkg_list">dpkg_list</a> for a more detailed
list of packages shipped with grml 1.0.</p>

<h3>Updates</h3>

<p>Updated all packages to Debian Unstable branch by 20070517.</p>

<p>Removed 90 packages [please notice that some of them are available under
different names/in different packages]:</p>

<pre class="rahmen">
*2.6.18-grml* lib*

aircrack aptconf bacula-client classpath classpath-common classpath-gtkpeer
convertfs cpp-3.3 ddd debpool debsig-verify doc-base emacspeak ethereal
ethereal-common fsh gcc-2.95 gcc-3.3 gcc-3.3-base glibc-doc grml-btnet
grml-kerneladdons-2.6.18 grml-sysvinit gs-gpl initrd-tools jamvm java-common
kdoc kenny kwtools-bin kwtools-common kwtools-graphic kwtools-net
kwtools-net-postfix kwtools-sys kwtools-sys-lvm kwtools-utils latex-ucs
linux-wlan-ng linux-wlan-ng-firmware lout lout-common lufs-utils lvm-common
lvm10 madwifi-doc misdn-utils mutt-ng muttprint nhfsstone nscd nxclient
olsrd-gui olsrd-plugin opie-server policycoreutils postgresql-client-8.1
prosper python-clamav python-jaxml python-selinux python2.3 raccess samdump
scapy securecgi simh synctree tclx8.3 tesseract-ocr tetex-base tetex-bin
tetex-extra tethereal tftp-hpa tftpd-hpa tk-brief transset ufsutils
unionfs-utils unzsplit valgrind vde wellenreiter wmi xcompmgr xen-tools
xen-utils-common xlibmesa-gl zsplit
</pre>

<p>Added 109 new packages (exluding lib* and *2.6.20-grml*):</p>

<pre class="rahmen">
4g8 advchk apwal arp-scan array-info ascii ascii2binary atftpd aufs-tools
blktrace bluetooth-alsa cbm clive concalc cryopid csstidy ctioga cups-pdf
dbus-x11 dnsproxy docbook2odf dpkg-ruby dvb-utils edbrowse espeak espeak-data
fakechroot fatresize funionfs fusedav gaffitter gatling gcolor2 gems
genisoimage grml-desktop grml-kerneladdons-2.6.20 grml-pylib hal-info icedax
ii imsniff ion3-mod-xinerama keyutils kqemu-common kvm lckdo mcabber mtp-tools
mtpaint ncc ncdu newsbeuter odt2txt olsrd-plugins ophcrack oss-compat
pamusb-tools pdfcube perl-tk pnputils podget postgresql-client-8.2 powertop
python-gobject python-pexpect python-scapy python-urwid rcov recordmydesktop
samdump2 scalpel screenie scrot sigit smbnetfs speedometer sucrack
texlive-base texlive-base-bin texlive-common texlive-doc-base
texlive-fonts-recommended texlive-lang-german texlive-latex-base
texlive-latex-recommended thc-ipv6 treil tss tweak uncrustify urlscan vde2
vim-addon-manager vinetto xjed xserver-xorg-input-aiptek
xserver-xorg-input-elo2300 xserver-xorg-input-elographics
xserver-xorg-input-evtouch xserver-xorg-input-hyperpen
xserver-xorg-input-joystick xserver-xorg-input-penmount
xserver-xorg-input-void xserver-xorg-video-intel xsteg xwatchwin zfs-fuse zzuf
</pre>

<h3>Upgrade notes</h3>

<p>As usual you can upgrade your grml harddisk system to the latest grml
version running 'apt-get update; apt-get install grml'. Take a look at <a
href="https://github.com/grml/grml/wiki/upgrading">the upgrading webpage in
the grml-wiki</a> as well. Notice: If you are using grml in a productive
environment and/or use a grml2hd installation we strongly recommend to
subscribe to <a href="/mailinglist/">the grml-user
mailinglist</a>!</p>

<h3>Changes since release 0.9 (20061206)</h3>

<ul>
  <li><a href="/grml2hd/gallery/">grml2hd screenshot gallery</a> available
  <li><a href="/user-survey/grml.txt">grml user survey</a> (results will be available soon)
  <li><a href="http://grml.supersized.org/archives/229-update-of-zsh-lovers-in-asciidoc-format.html">update of zsh-lovers</a>
  <li><a href="/team/">Frank Terbeck joined the grml-team</a>
</ul>

<h3>Known issues</h3>

<p>Take a look at <a
href="https://github.com/grml/grml/wiki/grml_1.0">grml_1.0 @ grml-wiki</a>.
Please report problems using information on <a
href="/bugs/">grml.org/bugs/</a>.</p>

<h3>Download grml 1.0</h3>

<p>grml 1.0 can be downloaded from mirrors listed on <a
href="/download/">grml.org/download/</a>.</p>

<h3>Feedback</h3>

<p>Your comments, bug reports, patches, and suggestions will help fix bugs
and improve future releases. If you find a problem with the release please
check <a href="https://github.com/grml/grml/wiki/grml_1.0">grml_1.0 @
grml-wiki</a> and report problems using information on <a
href="/bugs/">grml.org/bugs/</a>. Please send your feedback, feature
requests and bug reports to the grml-team!</p>

<ul>
  <li><a href="/contact/">grml.org/contact/</a>
  <li><a href="/irc/">#grml on irc.freenode.org</a>
</ul>

<h3>Thanks</h3>

<p>Many thanks in this release go to Michael Schierl, Jan-Pieter
Jacobs, Moritz Augsburger, Wolfgang Fuschlberger, Manuel Fuhr, Ronny
Plattner, Robert Giebel, Martin Ahammer, Matthias Diener and Josef
Teske for their contributions.  Many thanks to all of you who took part
in <a href="/user-survey/grml.txt">the grml user
survey</a>.  Many thanks also to the ones of you who <a
href="/donations/">donated something to the grml-team</a> and of course
to all those who have sent feedback since the last release!</p>

<h3>More Information</h3>

<p>You can find out more about grml on <a href="/">our website</a>, <a
href="/irc/">IRC channel</a>, and <a href="http://wiki.grml.org/">wiki</a>.

<p>To sign up for future grml announcements, please subscribe to <a
href="http://lists.mur.at/mailman/listinfo/grml-announce"> grml's
announcement list</a>.</p>


<p><a
href="http://www.spreadshirt.net/shop.php?article_id=3966156&view_id=4#top"><img
align="right" style="margin-left: 20px; border: 0"
src="/img/grmlshirt_0.9.jpg" alt="the grml 1.0 shirt" /></a></p>

<h3>Further Questions?</h3>

<p><a href="/contact/">Contact us.</a></p>

+++
title = 'FAQ for grml'
+++

<img style="float: right" src="/img/clanbomber.png" alt="*" />

<strong>Up2date:</strong> applies to Grml version 2024.02

<a name="toc"></a><strong>Index:</strong>

<p class="toc"><a href="#general">General:</a></p>
<ol>
    <li><a href="#whatis">What is Grml?</a></li>
    <li><a href="#flavours">What are grml32 / grml64 and grml96?</a></li>
    <li><a href="#grmlsmall">What is the difference between grml-full and grml-small?</a></li>
    <li><a href="#get">Where do I get Grml?</a></li>
    <li><a href="#whatmeans">What does Grml mean?</a></li>
    <li><a href="#releasename">What about the release name?</a></li>
    <li><a href="#requirements">Requirements for running Grml</a></li>
    <li><a href="#bootoptions">Which boot options does Grml support?</a></li>
    <li><a href="#systemd">Why is Grml using systemd?</a></li>
    <li><a href="#known_issues">Are there any known issues with this release? How about reporting bugs?</a></li>
</ol>

<p class="toc"><a href="#features">Features</a>:</p>
<ol>
    <li><a href="#usbboot">How do I boot Grml from a USB stick?</a></li>
    <li><a href="#persistency">Is it possible to store my settings?</a></li>
    <li><a href="#password">What are the passwords of users on Grml?</a></li>
    <li><a href="#version">How do I find out the version of Grml</a></li>
    <li><a href="#language">How do I change the language/keyboard settings?</a></li>
    <li><a href="#wms">Which window managers can I use?</a></li>
    <li><a href="#lvm">Where are my LVM devices?</a></li>
    <li><a href="#swraid">Where are my Software-RAID devices?</a></li>
    <li><a href="#booting">Which ways exist to boot Grml?</a></li>
    <li><a href="#timezone">How do I configure timezone on my Grml system?</a></li>
    <li><a href="#hdinstall">Is it possible to install Grml to harddisk?</a></li>
</ol>

<p class="toc"><a href="#software">Software:</a></p>
<ol>
    <li><a href="#sw_version">Which package(s) and which version is available?</a></li>
    <li><a href="#zsh">Why is Zsh the default shell?</a></li>
</ol>
</ol>

<p class="toc"><a href="#stuff">Support / Unanswered stuff:</a></p>
<ol>
    <li><a href="#questions">Further questions?</a></li>
    <li><a href="#support">Commercial Support</a></li>
</ol>

<h2><a name="general"></a><a href="#toc">General</a></h2>

<h3><a name="whatis"></a><a href="#toc">What is Grml?</a></h3>

<p>Grml is a bootable live system (Live-CD) based
on <a href="http://www.debian.org/">Debian</a>. It is not
necessary to install anything to a harddisk. Grml includes a
collection of GNU/Linux software especially for system
administrators. It specializes on administrative tasks like
installation, deployment and system rescue.</p>

<h3><a name="flavours"></a><a href="#toc">What are grml32 / grml64 and grml96?</a></h3>

<ul>
    <li>grml32-full: 32bit version (kernel and userspace)</li>
    <li>grml64-full: 64bit version (kernel and userspace)</li>
    <li>grml96-full: multi boot version (featuring the grml32-full and grml64-full ISOs combined on one ISO)</li>
</ul>

<p>Unless you've a good reason to really choose the 32bit flavour we
<em>strongly</em> encourage you to use either the grml64 or the grml96
flavour.</p>

<h3><a name="grmlsmall"></a><a href="#toc">What is the difference between grml-full and grml-small?</a></h3>

<p>grml-small provides a reduced set of available software compared to
grml-full.  It provides the same Linux kernel image as grml-full and is
fully binary compatible. Choose the grml-small flavour if size - for
whatever reason - really matters to you.</p>

<h3><a name="get"></a><a href="#toc">Where do I get Grml?</a></h3>

<p>Grml is open source, you can download it from the mirrors
listed at <a href="/download">grml.org/download/</a>.</p>

<h3><a name="whatmeans"></a><a href="#toc">What does Grml mean?</a></h3>

<p>Grml comes close to 'argl' or 'grrr' in English. People use
this when they want to express their dissatisfaction with
software (amongst other things).</p>

<h3><a name="releasename"></a><a href="#toc">What about the release name?</a></h3>

<p>Codename of Grml 2024.02 is &quot;Glumpad&quot;.
This is an austrian word for odds and ends, bits and pieces, useless stuff.
Related words in Austrian are &quot;Klumpert&quot; and &quot;Krimskrams&quot;, though the 'glum' and 'pad' might make the pronunciation more interesting.</p>

<h3><a name="requirements"></a><a href="#toc">Requirements for running Grml</a></h3>

<ul>

<li>Intel-compatible CPU (i686 or later, preferably Pentium class or higher; although some i586 processors e.g. the 'AMD Geode' are still supported)</li>

<li>&gt;=576MB of RAM (&gt;=1GB recommended)</p>

<li>either a bootable CD-/DVD-ROM drive,
a <a href="#usbboot">USB-boot capable system</a> or a
network card for booting via network/PXE (check
out <a href="#terminalserver">grml-terminalserver</a>)</li>

</ul>

<h3><a name="accessibility"></a><a href="#toc">What does accessibility at Grml mean?</a></h3>

<p>The Grml kernel includes support for speakup. For software,
brltty and espeakup are included.</p>

<h3><a name="bootoptions"></a><a href="#toc">Which boot options does Grml support?</a></h3>

<p>Check out the <a
href="https://git.grml.org/f/grml-live/templates/GRML/grml-cheatcodes.txt">grml-cheatcodes
file</a> (also available via <a href="/cheatcodes/">grml.org/cheatcodes/</a>). Of
course <a
href="https://www.kernel.org/doc/html/latest/admin-guide/kernel-parameters.html">the command-line parameters</a>
of the Linux kernel applies to Grml as well.</p>

<h3><a name="systemd"></a><a href="#toc">Why is Grml using systemd?</a></h3>

<p>The switch from file-rc to systemd happened for various reasons.
Grml used file-rc for many years, mainly because it provided a better
way to control startup behavior via its /etc/runlevel.conf configuration
than with using sysvinit. Though for us Grml developers this also meant
that whenever there have been any changes in Debian's startup
configuration we had to compare our /etc/runlevel.conf setup with what a
normal Debian system would give us. Users who wanted to remaster Grml
with a custom startup procedure as well had to practically fork
maintenance of the /etc/runlevel.conf file. This didn't only mean
tracking new features/services, but also solve any possible issues
around it - duplicating efforts and wasting developers time
unnecessarily. Lately we also started to see problems that no one else
seemed to have (or cared about enough), for example with multiple network
cards we ran into race-conditions with resolvconf. Problems like that
turned out to be release stoppers for us.</p>

<p>systemd on the other hand provides great documentation, service
supervision, takes care of parallel service startup and is the default
init system on most Linux distributions nowadays. This means more users,
better testing and integration. Logging, startup time investigation (to
get a fast boot procedure) and identifying failed service startups with
sysvinit/file-rc was always hard, unreliable or even impossible under
certain conditions. bootlogd was unreliable (while `journalctl -b` is
available out-of-the-box with systemd), bootchart was not nicely integrated
(while systemd-analyze blame/critical-chain works out-of-the-box) and we
aren't aware of any equivalence for e.g.
`systemctl --failed`.</p>

<p>It also turned out that it gives users who want to remaster Grml (or
build their very own ISOs from scratch using grml-live) more flexibility
and control
over the startup process. systemd's override.conf mechanism and preset
feature provides the flexibility to overwrite unwanted behavior, without
losing the option to use existing defaults.</p>

<p>We think it's good that systemd is actively
maintained and receives attention. The sysvinit/file-rc ecosystem was
stagnating/non-existent for too many years. Grml used its own initrd
implementation in its very beginnings, until a more broadly available
initramfs-tools / live-boot solution appeared, broadening the user base,
sharing goals amongst different (live) distributions. Back in the days
Grml - like many other live distributions - had to implement hardware
recognition on its own. While udev received lots of complaints back
then, its integration actually solved all the hardware recognition
problems for the good. systemd's vision of stateless systems is
something which helps building live systems like Grml.</p>

<p>While we don't claim that systemd is perfect and doesn't have its
issues and drawbacks (like any software), we're happy about its
existence and more than happy about development and support by Debian's
systemd folks.</p>

<a name="release"></a> <!-- old anchor -->
<a name="bugreport"></a> <!-- old anchor -->
<h3><a name="known_issues"></a><a href="#toc">Are there any known issues? How about reporting bugs?</a></h3>

<p>Please visit the <a href="/bugs/">bug webpage</a>.</p>

<h2><a name="features"></a><a href="#toc">Features</a></h2>

<!-- TODO: needs to be improved! -->
<h3><a name="usbboot"></a><a href="#toc">How do I boot Grml from a USB stick?</a></h3>

<p>Check out the <a href="/grml2usb/">grml2usb manpage</a>
and the grml-wiki page
&quot;<a href="https://github.com/grml/grml/wiki/usb">Boot Grml from usb-stick/firewire-device</a>&quot;.</p>

<h3><a name="store"></a><a name="persistency"></a><a href="#toc">Is it possible to store my settings?</a></h3>

<p>Yes, using the
<a href="https://github.com/grml/grml/wiki/persistency">persistency
feature</a>.</p>

<h3><a name="password"></a><a href="#toc">What are the passwords of users on Grml?</a></h3>

<p>There are no default passwords - all accounts are locked by
default for security reasons. Even local logins are not
possible (unless you set a password or create new user
accounts as root). You can create valid passwords using "sudo
passwd [username]" from the shell individually.
With the <a href="#bootoptions">boot option</a> 'ssh' a password for the
users 'root' and 'grml' is and SSH login is enabled.</p>

<h3><a name="version"></a><a href="#toc">How do I find out the version of Grml</a></h3>

<p>Run 'grml-version' or use the following command:</p>

<pre class="rahmen">
$ cat /etc/grml_version</pre>

<h3><a name="language"></a><a href="#toc">How do I change the language/keyboard layout?</a></h3>

<p>The default language of the Grml system is English (en_US.UTF-8).
All other locales are removed by default.
But it is possible to change the keyboard layout via either using 'grml-quickconfig',
the <a href="#bootoptions">boot option(s)</a> 'lang', 'keyboard' and 'xkeyboard'
or via executing grml-lang when Grml is already running.</p>

<p>Boot option examples:</p>

<pre class="rahmen">
grml lang=de      # enter this at the bootprompt and you will get
                  # german keyboard layout and german $LANG, $LC_ALL,
                  # $LANGUAGE...
grml keyboard=de xkeyboard=de lang=at # enter this at the bootprompt
                  # and you will get german keyboard and austrian
                  # language variables
</pre>

<p>'grml-lang' example:</p>

<pre class="rahmen">
% grml-lang de    # enter this in the shell to switch keyboard layout
</pre>

<p>Note: Run 'grml-setlang' to get a dialog based frontend for '/etc/default/locale'.</p>

<h3><a name="wms"></a><a href="#toc">Which window managers can I use?</a></h3>

<p>Starting with the 2011.12 release Grml provides <a
href="http://www.fluxbox.org/">Fluxbox</a> as window manager.</p>

<h3><a name="lvm"></a><a href="#toc">Where are my LVM devices?</a></h3>

<p>LVM (Logival Volumes) is <strong>not</strong> started by default to
avoid any possible damage to your data. To activate present LVM
devices execute (replace "$name" with the name of the PV):</p>

<pre class="rahmen">
# Start lvm2-pvscan@$name
</pre>

<p>or if you don't know its name and to enable all present ones, use:</p>

<pre class="rahmen">
# vgchange -ay
</pre>

<p>If you want to enable LVM by default just boot using the 'lvm'
<a href="#bootoptions">boot option</a> which automatically enables LVM.</p>

<h3><a name="swraid"></a><a href="#toc">Where are my Software-RAID devices?</a></h3>

<p>Software-RAID (usually known as the mdadm stuff) is
<strong>not</strong> started by default to avoid any possible damage to
your data. To get access to present SW-RAID devices just execute:</p>

<pre class="rahmen">
# mdadm --asssemble --scan
</pre>

<p>If you want to enable SW-RAID by default just boot using
the 'swraid' <a href="#bootoptions">boot option</a> which enables automatic assembling of
software raid arrays.</p>

<a name="terminalserver"></a>
<h3><a name="booting"></a><a href="#toc">Which ways exist to boot Grml?</a></h3>

<!-- TODO: needs rework -->

<p>Of course running from CD/DVD is a common way to boot
Grml. But Grml provides many more ways to boot:</p>

<p>It is possible to boot Grml via USB (e.g. USB stick or
harddisk), firewire, or running from a Compact Flash disk. It
works out of the box; you don't need to modify anything. Check
out <a href="https://github.com/grml/grml/wiki/usb">the usb
webpage in the grml-wiki</a> for more details.</p>

<p>Your computer can not boot from CD-ROM but provides a
floppy disk? Take a look
at <a href="http://btmgr.sourceforge.net/">btmgr</a>, <a href="http://ubcd4win.com/faq.htm#floppy">ubcd4win</a>
or <a href="http://linux.simple.be/tools/sbm">sbm</a>. They
provide support for booting from CD-ROM via a special floppy
disk.</p>

<p>grml-terminalserver makes it possible to boot your system
via network
using <a href="http://en.wikipedia.org/wiki/Preboot_Execution_Environment">PXE</a>
(Preboot Execution Environment). If your network card does not
provide support for booting via PXE you can still boot it
either using the provided grub image by grml-terminalserver
(for example via floppy drive) or
using <a href="http://etherboot.org/wiki/index.php">gPXE</a>.
For more information, refer to
the <a href="/terminalserver/">grml-terminalserver
webpage</a>.</p>

<h3><a name="timezone"></a><a href="#toc">How do I configure
timezone on my Grml system?</a></h3>

<p>Availabe boot options:</p>

<pre class="rahmen">
grml utc          # set UTC, if your system/hardware clock is set to UTC (Coordinated Universal Time)
grml localtime    # Hardware Clock is set to local time (LOCAL), this is the default
grml tz=$option   # set timezone to corresponding $option, usage example: tz=Europe/Vienna, defaults to UTC if unset
</pre>

<p>Further information: manpages hwclock(8), tzselect(1) and tzconfig(8); <a
href="http://www.debian.org/doc/manuals/system-administrator/ch-sysadmin-time.html">Debian
GNU/Linux System Administrator's Manual Chapter 16 - Time</a> and <a
href="http://wiki.debian.org/TimeZoneChanges">TimeZoneChanges in the
Debian-Wiki</a>.</p>

<h3><a name="hdinstall"></a><a href="#toc">Is it possible to install Grml to harddisk?</a></h3>

<p>No. If you want to get a Debian system take a look at <a
href="/grml-debootstrap/">grml-debootstrap</a> (or use the <a
href="https://www.debian.org/">Debian Installer</a> instead).</p>

<h2><a name="software"></a><a href="#toc">Software</a></h2>

<h3><a name="sw_version"></a><a href="#toc">Which package(s) and which
version is available?</a></h3>

<p>If you want to get details about the provided packages and the
package versions without booting the Grml ISO check out the dpkg_...
files in the <a href="/files/#debian">Debian-Information section on
grml.org/files/</a>.</p>

<h3><a name="zsh"></a><a href="#toc">Why is Zsh the default shell?</a></h3>

<p>Short answer: because <a href="/zsh/">Zsh rocks</a>, really!</p>

<p>Long(er) answer: If you don't know Zsh take a look the <a
href="/zsh/">Grml Zsh reference card</a>.</p>

<p>If you are a Bash user and don't know Zsh yet, don't be
afraid. Bash is largely a subset of Zsh and you don't have to
throw away your knowledge about shell stuff.</p>

<h2><a name="stuff"></a><a href="#toc">Support / Unanswered stuff</a></h2>

<h3><a name="questions"></a><a href="#toc">Further questions</a></h3>

<p>Do you have a question which is not answered in the FAQ or
in the provided <a href="/docs/">documentation</a> (execute
&quot;grml-info&quot; on your Grml system for offline
documentation)?  Also check out 'grml-tips $KEYWORD' on your
Grml system. Take a look at
<a href="/">the Grml website</a> and <a href="http://wiki.grml.org/">the
    grml-wiki</a>. A good place to become part of the community is the <a
    href="/mailinglist/">Grml mailinglist</a>.</p>

<h3><a name="support"></a><a href="#toc">Commercial Support</a></h3>

<p>You want to deploy Grml in your data center, use it as part of your
business or have an emergency case? You're happy with Grml but would
like to get your very own live system (providing your favourite software
selection, special configuration, setup and a custom bootsplash)?
Please get in <a href="/contact/">touch with us</a>.</p>

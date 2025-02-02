+++
title = 'Minutes of the Grml Developer Meeting 2010'
icon = 'info'
+++

<h3>Data</h3>

<ul>
    <li>What: Official Grml Developer Meeting</li>
    <li>Date: 4th and 5th of november 2010</li>
    <li>Place: <a href="https://metalab.at/">Metalab</a>, Vienna/Austria</li>
</ul>

<h3>Participants</h3>

<ul>
<li>Alexander 'formorer' Wirt</li>
<li>Andreas 'jimmy' Gredler</li>
<li>Christian 'ch' Hofstaedtler</li>
<li>Gerfried 'rhonda' Fuchs</li>
<li>Michael 'gebi' Gebetsroither</li>
<li>Michael 'mika' Prokop</li>
<li>Ulrich 'mru' Dangel</li>
</ul>

<h3>Some highlights</h3>

<ul>
    <li>formorer started to work on the new Grml Homepage and it looks great so far. Maybe it is finished for the new release</li>
    <li>ch organized the location and social event and closed many bugs</li>
    <li>jimmy implemented a special update-grub feature for integrating Grml ISOs in usual hd installations during the meeting and debugged several issues</li>
    <li>gebi designed and started to develop a framework for non free tools like Raid controller or truecrypt (yes truecrypt is non-free!)</li>
    <li>rhonda started to use Zsh and will be looking for fast mirrors outside of Europe.</li>
    <li>mika was just amazed about the donations and what was achieved during these two days. Thank you!</li>
</ul>

<h3>1st day</h3>

<p>Ch, Uli and Mika starting with installation and buildup of work place in Metalab's library at 9:45.
Gebi, Jimmy and formorer are joining at ~10:15, Rhonda joins in the afternoon. Official start at 10:35.</p>

<ul>
    <li>Starting with 98 open bugs, including 13 release stopper issues</li>
    <li>Small discussion about what is Grml and what should it be</li>
    <li>Artwork for upcoming release: different sizes of Tux</li>
    <li>Gebi will work on a framework for non-free tools for improved handling of hardware RAID controllers, truecrypt,...</li>
    <li>We decided to not invest any time in non-free firmware as our current system works pretty well out-of-the-box already and if there should be need for further discussions around inclusion of non-free firmware people should report it</li>
    <li>Acknowledgment regarding main programming languages used within Grml: Shell and Python are to be prefered unless there are good reasons against it, exceptions need good reasoning</li>
    <li>grml-etc-core should ship /etc/gitconfig in the future (instead of /etc/skel/.gitconfig for user-only config) to provide system wide configuration of some important defaults</li>
    <li>Detailed review of GRMLBASE software selection - the class is considered as base for any remastered ISOs and should provide software that either needs to be present because the live system wouldn't work otherwise or software we expect to get with every Grml based live system (lvm, madm, openssh,...)</li>
    <li>locales: /usr/share/locales shouldn't be removed overall but be made configurable (besides the already existing LOCALES class)&nbsp;</li>
    <li>We decided to not provide any translations of neither our programs nor our documentation, but reviews by native english speakers would be good</li>
    <li>To improve visibility we decided (as a first step) to provide more mirrors outside DACH -&gt; Rhonda will take care of it</li>
    <li>Discussed redesign of new Website (formorer started working on it already)</li>
    <li>Social Meeting in Vienna with two external guests with interesting and fulfilling discussions about Grml, Debian, Linux and the world.</li>
</ul>

<p>First day involved a lot and interesting discussions and it was really helpful to get all personal
ideas what Grml is and how we as a team can improve Grml.</p>

<h3>2nd day</h3>

<ul>
<li>Starting at 10:00 with 88 open bugs in the BTS</li>
<li>Work on update-grub for integration of a Grml-ISO in GRUB's bootmenu on harddisk installations, Jimmy takes care of it</li>
<li>Discussed and researched possible grml-api solutions. Currently grml-api is considered to not solve the real issues we're experiencing. Instead we decided to improve cooperation amongst the essential tools as everything can be located implicitly.</li>
<li>We need better documentation regarding Grml-remastering, especially remastering official Grml-ISOs with grml-live using release-chroots, Mika and Ch will take care of it.</li>
<li>We will work on a central shell library which provides the most important functions to be shared amongst different scripts without having to adjust new features on several places, e.g. like checkbootparams with its /cdrom/bootparams issue). The library should be /bin/bash &amp;&amp; /bin/zsh compatible and must work under non Grml-systems as well.</li>
<li>Mika introduces his Kantan testsuite. We want to test especially:
<ul>
    <li>grml2usb</li>
    <li>grml2hd</li>
    <li>grml-terminalserver</li>
    <li>forensic bootoption</li>
    <li>bootoptions:
    <ul>
        <li>findiso</li>
        <li>ssh</li>
        <li>grml2hd</li>
        <li>grml2ram (and using in combination with other bootoptions!)</li>
        <li>lang/keyboard</li>
        <li>check ttys for their running programs (e.g. the multi CPU race condition in GNU screen)</li>
    </ul>
    </li>
</ul>
</li>

<li>Remove "an unsupported"[1] program from grml-quickconfig and replace it with a supported one instead. The name is not provided by intention. :)&nbsp; [1] quote: formorer</li>
<li>Augeas -&gt; mru wants it, no one else likes it. Version in lenny is old, outdated and rusty, Version in squeeze has a problem with the apt lense. But the problem got fixed on Friday. Great upstream! Will be reconsidered after release of squeeze. #602703</li>
<li>The current beta tester program will be discontinued after the redesign of the new website. Did not provide any additional value and we have daily builds available since quite some time.</li>
<li>Check what is needed for a registered association. Would make live more easy in regard to donations, hardware, ... Mika will take care of it and would like to see this resolved until the next developer meeting.</li>
<li>We want to meet more often. Developer meetings are fun and we noticed we are <i>really</i> productive. -&gt; We would like to meet at least two times a year, especially for working together towards a new release. Preferable in remote, sunny locations like Hawaii. Maybe also a little bit longer then two days. If Hawaii does not work out maybe Realraum in Graz/Austria or LinuxHotel in Essen/Germany would be nice alternatives.</li>
<li>Talks about Grml: Mika would like to see other people talking about Grml as well, especially mru and formorer are volunteering to give talks</li>
<li>We want and need more testimonials. Currently we do not publish companies using Grml as most of them did not explicitly agree with publishing their names. We'll change that and will publish the name of all known companies and <i>if</i> they agree the logo. We want the name of your company if you are using Grml!</li>
<li>Polished and finalized a Grml User Survey which should go online soon.</li>
<li>Recruitment of new developers. We will provide documentation how to submit patches and best practices on our new website.</li>
<li>Discussed sponsoring solutions for Grml:
<ul>
  <li>CDs &amp; USB-Sticks</li>
  <li>Developer Meeting (if you like such reports, donate!)</li>
  <li>Server&amp;Housing</li>
  </ul>
  </li>
  <li>Google Summer of Code - try to get accepted: Possible projects:<ul><li>grml-live Webinterface/GUI</li>
  <li>Testing framework for arbitrary Linux distributions</li>
  <li>Integration of systemd in Debian (and Grml)</li>
</ul>
</li>
<li>Developer policy: what happens with inactive developers? If someone is inactive for a long time the project members decide about grading a core developer to contributor to avoid misusage of permissions within the project.</li>
<li>Gebi worked on a cdrecord version 3 package based on Mika's previous packaging work. It will be provided on the Grml mirror but <i>not</i> shipped on the CD by default.</li>
<li>Improve documentation of necessary tests for a Grml-Release and the Grml release process itself</li>
<li>We need to save some space as current grml-full ISOs are over 700MB. Started discussion about software packages in GRML_FULL. Ch provided a list of removal candidates for all packages within a-h. Ch already provided test ISOs under 700MB (without addons).</li>
<li>Xorg
<ul>
  <li>KMS is the future</li>
  <li>Don't ship xorg.conf configuration per default anymore, X auto configuration is quite good nowadays</li>
  <li>Ch already provided a new grml-x dealing with the new specification, WIP</li>
</ul>
</li>
<li>New Kernel 2.6.36 is out. Gebi and Mika will take care of it and unless there are release stoppers it will be provided with upcoming stable release.</li>
<li>We need information for the release notes:
<ul>
  <li>vnc_connect</li>
  <li>kms</li>
  <li>new kernel</li>
  <li>... further new features (in grml-etc-core, grml-etc, grml-live,...)</li>
</ul>
</li>
<li>Split grml-scripts in grml-scripts-core and grml-scripts. grml-scripts-core should only contain the software needed in grml-etc-core</li>
<li>Cleanup of grml-scripts and grml-network.</li>
<li>Reorganize grub templates for menus like the isolinux ones.</li>
<li>Change grml-rebuildfstab to only modify current device and do not scan whole system on every event.</li>
<li>Code reviews: we won't use an extra tool but push work in separate branches inside git and ask the according maintainer and/or other developers for feedback. The workflow with merge + signed-off will be documented accordingly</li>
<li>Workflow for Debian packaging/VCS: Mika presented his git-dch/git-buildpackage workflow - will be documented properly. As soon as the workflow is documented uploads for all core developers to grml-testing at deb.grml.org will be enabled.</li>
<li>Improve Grml page in german and english wikipedia, needs updates to reflect recent developement. Rhonda will take care of it.</li>
<li>Grml-Monster: we would like to get our own mascot with appropriate license for distribution</li>
<li>Would be nice to have a directory specific configuration for grml-live, Mika wants to take care of it.</li>
<li>Finished bug squashing with 84 open bugs, only 6 open release stoppers of which some are already pending.</li>
<li>Assigned main open tasks to each developer.</li>
<li>Official end of developer meeting at 19:30 and starting cleanup of used Metalab space.</li>
</ul>

<h3>Financial details</h3>

<p>Transportation, accommodation costs and the social event added up to 840 EUR. Thanks to generous private
donations as well as sponsoring by <a href="http://www.tarent.de/">Tarent</a> the full amount of
costs could be covered. Accounting is WIP these days, if any money should be left we will save the money for the
next upcoming Grml developer meeting. Thanks a lot to everyone of you who supported the Grml team through
donations!</p>

<h3>Thanks</h3>

<ul>
    <li>Thanks to generous sponsors for financially supporting the developer meeting</li>
    <li>Thanks to <a href="https://metalab.at/">Metalab</a> for their kindly hosting in their hacker space</li>
</ul>

<h3>Conclusion</h3>

<p>It was really amazing what we achieved during these two days and it was really helpful to meet
everyone in person. This event and this report would not be possible without many generous sponsors and the
friendly hosting by Metalab! We want to thank you all!</p>

<em>This document was prepared by Michael Prokop and Ulrich Dangel.<br />
Latest change: Mit Nov 10 23:23:44 CET 2010
</em>

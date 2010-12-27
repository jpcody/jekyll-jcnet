---
layout: blog_single
title: Making Site Backups to Your Local Machine
category: blog
permalink: blog/making_site_backups_to_your_local_machine
shortUrl: http://jpcody.in/1c
---
<p><strong>Warning:</strong> Here be nerdery and hackery that will be more valuable to future Googlers than most who would occasionally read these thoughts. Also, a Mac and <a href="http://panic.com/transmit">Transmit</a> by Panic are here used.<sup id="2010_01_02_fnlink1"><a href="#2010_01_02_fn1">1</a></sup></p>
<p>Recently, Jeff Atwood <a href="http://www.codinghorror.com/blog/archives/001315.html">ran into a problem</a>. His site, Coding Horror, suffered a catastrophic and complete data loss. Everything was lost&mdash;entries, photos, databases, you name it. For anyone who runs a site, this is a problem. He was able to recover most of his data from loyal readers, Google's cache, and his own, sparse backups.</p>
<p>But most of us don't have the benefit of devout followers making backups of our sites so they can read them offline, print copies to line their mattress with and save us in case of an emergency. So this is what I do, server side<sup id="2010_01_02_fnlink2"><a href="#2010_01_02_fn2">2</a></sup>:</p>
<ul>
    <li>Set up two folders at the root (one level above the document root, which is likely public_html) of my server: one for database backups and the other for entire site backups.</li>
    <li>Create two files at the root of my server: one with a script <a href="http://tips-scripts.com/site_backups">to back up my site</a> and another with a <a href="http://tips-scripts.com/sql_backups">script to back up my databases</a>.</li>
    <li>Run each of these via cron (so they'll run on their own, once per day, at a specified time) at odd times during off-peak hours&mdash;say, the first at 2:37am and the second at 3:06am.</li>
</ul>
<p>At this point, we've got a compressed file in the format of /backup/daynumber.tar.gz (i.e. /backup/30.tar.gz or /backup/14.tar.gz). So naturally, as we circle around to a new month, files are overwritten to save space. So you've got 30 days of backups for your entire site and for your databases, right there. But they're still on the server, which is vulnerable to spilled soup, mean people and the terrorists. So let's move them local.</p>
<ul>
    <li>Create two folders on my personal computer: one for database backups and the other for entire site backups. (Sound familiar?)</li>
    <li>Create a Transmit favorite to connect directly to each of the folders on your server, and name them something simple. ("DB Backups" and "Site Backups" for me.)</li>
    <li>Fire up Automator, and in Library > Internet, choose "Synchronize Files" next to the little Transmit icon.</li>
    <li>Choose my Transmit favorite of database backups, set the sync direction to "Download," sync method to "Update," and the appropriate local folder as my "Local path."</li>
    <li>Save the workflow as a file somewhere memorable and repeat the process for entire site backups.</li>
    <li>Create a new iCal event with an alarm sometime <em>after</em> your daily server backup mentioned above.</li>
    <li>For the alarm action, choose "Open file," and select your Automator workflow for database backups. Create a second event and alarm for entire site backups.</li>
</ul>
<p>Then, in 10 rather convoluted and confusing steps, you'll have an email alert each morning to let you know if you backed up successfully. I also changed the subject of the email it sends me to let me know whether it succeeded or failed, and I have Gmail automatically archive successes so only failures get through to my inbox.</p>
<p>So that's that. I'll open comments on this article as well so anyone can add, subtract or call me an idiot. Oh, also, I'd love to hear anything different you're doing with other setups.</p>
<ol>
	<li id="2010_01_02_fn1">Here is my setup: a <a href="http://site5.com">site5</a> server with PHP5 and a MySQL database. And locally, an iMac running Snow Leopard that stays on 24/7, backs up via Time Machine. Also, Automator (which you have if you're following so far) and Transmit. I don't know enough to know if your mileage will vary, so plan accordingly. <a href="#2010_01_02_fnlink2" class="small_caps">&nbsp;&nbsp;[Jump back]</a></li>
	<li id="2010_01_02_fn2">I'm extremely happy with site5 and trust them tremendously. But I do want myself, not them, to be accountable for things that belong to me&mdash;in this case, intellectual property. <a href="#2010_01_02_fnlink2" class="small_caps">&nbsp;&nbsp;[Jump back]</a></li>
</ol>
---
layout: blog_single
title: Archiving Twitter&mdash;Making My Data Mine
category: blog
permalink: blog/archiving_twitter_making_my_data_mine
shortUrl: http://jpcody.in/m
---
<a href="http://joshuacody.net/archive"><img src="/images/blog-img/twitter-archive.jpg" alt="Twitter Archive" width="380" height="245" class="main"/></a>
<p>Around a year ago, <a href="http://twitter.com/kevinhendricks">Kevin Hendricks</a> posted a simple question on Twitter asking for recommendations of methods to back up your Twitter updates. He wanted an automatic and local solution&mdash;a man wise enough to realize users don't make backups when they have to put thought into it (cf. Apple's <a href="http://en.wikipedia.org/wiki/Time_Machine_(Apple_software)">Time Machine</a>).</p>
<p>Aptly, I can't find his question today. And since I couldn't find that, <a href="http://joshuacody.net/archive">I built this</a>.</p>
<p>Essentially, it cycles through my Twitter updates every 10 minutes, stores any new information in a database, then displays that information in a searchable manner. Nothing too fancy. </p>
<p>But let's talk more about why.</p>
<h3>A slight rant on search and pagination</h3>
<p>Looking for Kevin's year-old update exposes the shortcomings of Twitter's history.</p>
<p>Twitter's <a href="http://search.twitter.com">own search function</a> has only a 10-day memory. Alternately, I could paginate through his last 3200 updates, which they allow access to. Twitter's AJAX pagination, however, makes this experience fall somewhere between a headache and a disaster. The feature [sic] means the page doesn't have to reload when you click "more," but it also means that the URL contains no clue to where in the search results you are.</p>
<p>For example's sake, navigate to a user's page. <a href="http://twitter.com/jpcody">Mine will do just fine</a>. Now say you have hit "more" 100 times, which means a single page holds 2,000 results. But the URL still reads as <em>http://twitter.com/jpcody</em>. And should you navigate away, experience a browser crash, or accidentally hit the "Back" button of your browser, all your clicking and scrolling is lost. When you return to the page, you only get the 20 most recent updates for said user.</p>
<p>Then you cuss, your children hear, they repeat the words at school, and Twitter has landed you back in the principal's office.</p>
<h3>So you built this just to search?</h3>
<p>Not completely, although that's certainly a part of it. It <strong>is</strong> nice to be able to simply search "allanwhite" when I'm looking for something I remember saying to him back in September.</p>
<p>More importantly, I built it because Twitter doesn't exactly have a <a href="http://en.wikipedia.org/wiki/Twitter#Outages">sparkling track record</a>. Not even <a href="http://www.techcrunch.com/2009/12/17/twitter-reportedly-hacked-by-iranian-cyber-army/">within the last week</a>. And I don't trust my data in their hands.</p>
<p>Jeff Atwood recently experienced a nearly entire loss of his site, Coding Horror, and <a href="http://www.codinghorror.com/blog/archives/001315.html">had this to say in its wake</a>:</p>
<blockquote>
    <p>Don't rely on your host or anyone else to back up your important data. Do it yourself. If you aren't personally responsible for your own backups, they are effectively not happening.</p>
</blockquote>
<p>Not to be a doomsayer, but Twitter could die. It's part of life for any service, bird, or application. There are malicious people out there with fast computers and an appetite for destruction. There are also brain farts, server errors, and lacks in foresight. It's just life on the internet.</p>
<p>Least of all, it's fun to be able to easily navigate to <a href="http://joshuacody.net/archive/index.php/archives/index/2450">my first musings</a> and see what I was saying back then. At this point, I haven't hit the magical number of 3200, so I could retrieve all of my updates (and still link to them on Twitter, should I choose). And now, my first 3200 will be stored on my own server, so even when I pass this upper-limit, I'll be able to access them at <em>http://joshuacody.net/twitter</em>.</p>
<p>(And, my server space and databases are backed up nightly to my personal machine, which is backed up to rotating hard drives, so I can really, really keep my data.)</p>
<h3>All this for some stupid Twitter updates?</h3>
<p>Yes, with a caveat.</p>
<p>Most people are guilty of a hasty generalization with Twitter. It's still commonly assumed that it's a place to "type what you ate for breakfast." (This fallacy comes in other packages as well, but it's the one tossed about most often.)</p>
<p>But I don't view it as such.</p>
<p class="big_quote">Twitter is a big corner of my online life where I store drafts of ideas, links to things I love, and snapshots of moments in time.</p>
<p>It's where I've learned the most about editing, the power of brevity, and the real-world value of sharing information. I can look back through my corner and see where I was a year ago&mdash;the things I was linking to, the way I was writing, or the pictures I was uploading. I can see where I was wrong and what I would do differently. And yeah, I've even said things that, to me, were wise enough or clever enough to keep.</p>
<h3>The future</h3>
<p>I'm thinking and brainstorming of ways to make this available to other folks. If it's something that'd be useful to you, then please follow me and retweet the following message:</p>
<p>I'm kidding. But let me know on Twitter or via email, and if it's something enough folks are interested in, I'll put some time and effort there.</p>
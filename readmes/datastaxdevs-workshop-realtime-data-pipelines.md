<h2><a class="anchor" aria-hidden="true" id="real-time-data-pipelines-with-apache-pulsartm-and-apache-cassandratm"> </a>🎓 Real-Time data pipelines with Apache Pulsar™ and Apache Cassandra™</h2>
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/badge.png?raw=true" width="150" align="right" />
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-realtime-data-pipelines" target="_blank"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod" alt="Gitpod ready-to-code" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p>Welcome to the <em>RealTime data pipeline with Apache Pulsar and Apache Cassandra</em>* workshop! In this two-hour workshop, we will show you a sample architecture making use of Apache Pulsar™ and Pulsar Functions for real-time, event-streaming-based data ingestion, cleaning and processing.</p>
<p>⏲️ <strong>Duration :</strong> 2 hours</p>
<p>🎓 <strong>Level</strong> Beginner to Intermediate</p>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/splash.png" alt="" /></p>
<blockquote>
<p><a href="#-start-hands-on" target="_blank">🔖 Accessing HANDS-ON</a></p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>📋 Table of contents</h2>
<ul>
<li><strong>HouseKeeping</strong>
<ul>
<li><a href="#objectives" target="_blank">Objectives</a></li>
<li><a href="#frequently-asked-questions" target="_blank">Frequently asked questions</a></li>
<li><a href="#materials-for-the-session" target="_blank">Materials for the Session</a></li>
</ul>
</li>
<li><strong>Architecture Design</strong>
<ul>
<li><a href="#architecture-overview" target="_blank">Architecture overview</a></li>
<li><a href="#injector-component" target="_blank">Injector Component</a></li>
<li><a href="#analyzer-component" target="_blank">Analyzer Component</a></li>
</ul>
</li>
<li><a href="#setup---initialize-your-environment" target="_blank">Setup - Initialize your environment</a></li>
<li><a href="#lab1---producer-and-consumer" target="_blank">LAB1 - Producer and Consumer</a></li>
<li><a href="#lab2---pulsar-functions" target="_blank">LAB2 - Pulsar functions</a></li>
<li><a href="#lab3---working-with-databases" target="_blank">LAB3 - Working with Database</a></li>
<li><a href="#lab4---pulsar-io" target="_blank">LAB4 - Pulsar I/O</a></li>
<li><a href="#Homework" target="_blank">Homework</a></li>
</ul>
<p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>
<p>🎯 Give you an understanding and how and where to position Apache Pulsar</p>
</li>
<li>
<p>🎯 Give an overview of  streaming and datascience ecosystem**</p>
</li>
<li>
<p>🎯 Give you an understanding of Apache Cassandra NoSQL Database</p>
</li>
<li>
<p>🎯 Create your first pipeline with streaming and database.</p>
</li>
<li>
<p>🚀 Have fun with an interactive session</p>
</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="frequently-asked-questions"> </a>Frequently asked questions</h2>
<p/>
<details>
<summary><b> 1️⃣ Can I run this workshop on my computer?</b></summary>
<hr>
<p>There is nothing preventing you from running the workshop on your own machine. If you do so, you will need the following:
<ol>
<li><b>git</b>
<li><b>Python 3.6+</b>
<li><b>Astra Cli</b>
<li><b>Pulsar Shell or Pulsar-Client</b>
</ol>
</p>
In this readme, we try to provide instructions for local development as well - but keep in mind that the main focus is development on Gitpod, hence <strong>we can't guarantee live support</strong> about local development in order to keep on track with the schedule. However, we will do our best to give you the info you need to succeed.
</details>
<p/>
<details>
<summary><b> 2️⃣ What other prerequisites are required?</b></summary>
<hr>
<ul>
<li>You will need enough *real estate* on screen, we will ask you to open a few windows and it would not fit on mobiles (tablets should be OK)
<li>You will need an Astra account: don't worry, we'll work through that in the following
<li>As "Intermediate level" we expect you to know what java and Spring are. 
</ul>
</p>
</details>
<p/>
<details>
<summary><b> 3️⃣ Do I need to pay for anything for this workshop?</b></summary>
<hr>
<b>No.</b> All tools and services we provide here are FREE. FREE not only during the session but also after.
</details>
<p/>
<details>
<summary><b> 4️⃣ Will I get a certificate if I attend this workshop?</b></summary>
<hr>
Attending the session is not enough. You need to complete the homework detailed below and you will get a nice badge that you can share on linkedin or anywhere else *(open badge specification)*
</details>
<p/>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to work at your own pace,<br />
we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="/slides/slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
<li><a href="https://www.twitch.tv/datastaxdevs" target="_blank">Twitch backup</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="architecture-design"> </a>Architecture Design</h2>
<p><em>Reviews of various venues (hotels/restaurants), written by various users, keep pouring in. We need a way to clean, normalize and filter them, removing trolls and flagging blatant outlier reviews, and make the running results available to the end user.</em></p>
<h4><a class="anchor" aria-hidden="true" id="architecture-overview"> </a>Architecture overview</h4>
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/./images/current_arch.png"/>
<details>
<summary><b> Show Detailed explanations</b></summary>
<ul>
<li>A stream of "events" (messages), some of which are reviews, is poured into a Pulsar topic for "raw reviews".
<li>A Pulsar function filters out malformed items and those that do not specify their target type (restaurant/hotel). This function takes care of normalizing the incoming reviews, since - as is often the case in real life - certain field names in the incoming reviews can have multiple forms. All reviews are encoded as JSON strings. The Pulsar function singles out hotel and restaurant reviews and routes them, after normalizing their structure, to two specific topics. 
<li>We happen to be interested in restaurants, so we have a long-running process ("analyzer") performing the actual analysis on these. Heavy artillery, such as AI/ML-based classifiers, code with fat dependencies and the like, would be placed here (i.e outside Pulsar).
<li>The analyzer keeps listening to the restaurant topic and ingests all incoming reviews: it keeps and update a state with key information, such as a rolling average score per each restaurant.
<li>As new items arrive, they are checked if they are "troll reviews" (review text in heavy disagreement with the numeric score) and, if so, discarded. Otherwise they enter the rolling average for the target restaurant.
<li>The analyzer periodically publishes an assessment for users and restaurants to a database, ready to be queried by any service that may need this data. (The output can also go to console if so desired). The destination DB also offers a ready-to-use REST API that allows to retrieve its data with simple HTTP requests, making it easy to build panels and UIs on top of this pipeline. The analyzer also reroutes "outlier reviews" (scores much different than the current rolling average) to another Pulsar topic, for a hypothetical manual inspection of such outliers.
</ul>
</p>
</details>
<h4><a class="anchor" aria-hidden="true" id="injector-component"> </a>Injector Component</h4>
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/./images/plots/02_reviews.png"  width="600px" />
<details>
<summary><b> Show Details</b></summary>
<p>
There is a pseudorandom procedure to generate reviews with features that fluctuate in a predictable
way: it is all in the <b>revGenerator</b> directory.
<p>There is no &quot;time&quot; in the generation: to keep things simple, we use a &quot;sequence index&quot; in place of<br />
time. Also, some of the &quot;reviews&quot; are not even valid JSON strings but contain gibberish instead,<br />
as is often the case in real-life data ingestion pipelines!</p>
<p>Each time a review is created, a venue (target) and a user (reviewer) are chosen at random: then,<br />
score and text are also created according to the following rules:</p>
<p>Each venue has a &quot;true&quot; quality that is slowly oscillating in time, see for example these two restaurants:</p>
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/./images/plots/01_real-values.png"  width="600px" />
<p>Each reviewer has an associate amplitude that dictates how widely the scores they produce<br />
may fluctuate away from the &quot;true&quot; value for that venue at that &quot;time&quot;: in this example, the individual<br />
scores emitted by two different reviewers, having a large and small associated amplitude, are plotted:</p>
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/./images/plots/02_reviews.png"  width="600px" />
<p>While reviews by Rita will presumably all fall in the &quot;expected&quot; region around the current average,<br />
a large fraction of the reviews by Anne will be too far away from<br />
it and thus be flagged as &quot;outlier reviews&quot;.</p>
<p>Each review comes with an associated text, which in this toy<br />
example is simply a bunch of words strung together, some positive (&quot;delicious&quot;) and some negative (&quot;disgusting&quot;).<br />
Each reviewer, however, has a Boolean &quot;trolliness&quot; flag: if true, then this text is built in strong<br />
disagreement with the numeric score in the review.</p>
</p>
</details>
<h4><a class="anchor" aria-hidden="true" id="analyzer-component"> </a>Analyzer Component</h4>
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/./images/plots/03_moving-average.png" width="600px"/>
<details>
<summary><b> Show Details</b></summary>
<p>
On the <b>analyzer side</b>, the reconstructed rolling average roughly follows the "true" quality for
a venue, and is used to detect "outliers": each review that differs too much from the current rolling
average is deemed an outlier. Here the rolling average corresponding to the above restaurant is plotted:
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/./images/plots/03_moving-average.png"  width="600px"/>
<p>The analyzer also discards troll reviews and keeps a running<br />
counter of them, both per-user and per-restaurant, ready to be exposed with the other data. To do so, a toy version of a sentiment analysis is implemented (simply based on some words with positive<br />
and negative connotation) and used to compare with the numeric<br />
score given in the review.</p>
</p>
</details>
<hr />
<h1><a class="anchor" aria-hidden="true" id="start-hands-on"> </a>🏁 Start Hands-on</h1>
<h2><a class="anchor" aria-hidden="true" id="setup-initialize-your-environment"> </a>Setup - Initialize your environment</h2>
<h4><a class="anchor" aria-hidden="true" id="code-setup-01-code-open-gitpod"> </a><code>✅.setup-01</code>- Open Gitpod</h4>
<p>Gitpod is an IDE based on VSCode deployed in the cloud.</p>
<blockquote>
<p>↗️ <em>Right Click and select open as a new Tab...</em></p>
</blockquote>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-realtime-data-pipelines" target="_blank"><img src="https://dabuttonfactory.com/button.png?t=Open+Gitpod&f=Open+Sans-Bold&ts=16&tc=fff&hp=20&vp=10&c=11&bgt=unicolored&bgc=0b5394" /></a></p>
<h4><a class="anchor" aria-hidden="true" id="code-setup-02-code-create-your-astra-account-following-web-page-opened-by-gitpod-or-follow-this-link"> </a><code>✅.setup-02</code>- Create your Astra Account: Following web page opened by gitpod or follow this link</h4>
<p><em><strong><code>ASTRA</code></strong> is the simplest way to run both Cassandra and Pulsar with zero operations at all - just push the button and get your clusters. No credit card required</em></p>
<p>Leveraging <a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/#c-procedure" target="_blank">Database creation guide</a> create a database. <em>Right-Click the button</em> with <em>Open in a new TAB.</em></p>
<p>The Astra registration page should have opened with Gitpod, if not use <a href="https://astra.dev/yt-9-14" target="_blank">this link</a>.</p>
<h4><a class="anchor" aria-hidden="true" id="code-setup-03-code-create-astra-credentials-token-create-an-application-token-by-following-a-href-https-awesome-astra-github-io-docs-pages-astra-create-token-target-blank-these-instructions-a"> </a><code>✅.setup-03</code>- Create Astra Credentials (token): Create an application token by following <a href="https://awesome-astra.github.io/docs/pages/astra/create-token/" target="_blank" target="_blank">these instructions</a>.</h4>
<p>Skip this step is you already have a token. You can reuse the same token in our other workshops, too.</p>
<blockquote>
<p>Your token should look like: <code>AstraCS:....</code></p>
</blockquote>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token 
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-setup-04-code-setup-astra-cli"> </a><code>✅.setup-04</code>- Setup Astra CLI</h4>
<p>Go back to your gitpod terminal waiting for your token. Make sure you select the <code>1_producer</code> shell in the bottom-right panel and provide the value where it is asked.</p>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/pic-astratoken.png" alt="pic" /></p>
<blockquote>
<p>🖥️ <code>setup-04 output</code></p>
<pre><code>[cedrick.lunven@gmail.com]
ASTRA_DB_APPLICATION_TOKEN=AstraCS:AAAAAAAA

[What's NEXT ?]
You are all set.(configuration is stored in ~/.astrarc) You can now:
   • Use any command, 'astra help' will get you the list
   • Try with 'astra db list'
   • Enter interactive mode using 'astra'

Happy Coding !
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-setup-05-code-list-your-existing-users"> </a><code>✅.setup-05</code>- List your existing Users.</h4>
<pre lang="bash"><code>astra user list
</code></pre>
<blockquote>
<p>🖥️ <code>setup-05 output</code></p>
<pre><code>+--------------------------------------+-----------------------------+---------------------+
| User Id                              | User Email                  | Status              |
+--------------------------------------+-----------------------------+---------------------+
| b665658a-ae6a-4f30-a740-2342a7fb469c | cedrick.lunven@datastax.com | active              |
+--------------------------------------+-----------------------------+---------------------+
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-setup-06-code-create-database-code-workshops-code-and-keyspace-code-trollsquad-code-if-they-do-not-exist"> </a><code>✅.setup-06</code>- Create database <code>workshops</code> and keyspace <code>trollsquad</code> if they do not exist:</h4>
<pre lang="bash"><code>astra db create workshops -k trollsquad --if-not-exist --wait
</code></pre>
<p>Let's analyze the command:</p>
<table>
<thead>
<tr>
<th>Chunk</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>db create</code></td>
<td>Operation executed <code>create</code> in group <code>db</code></td>
</tr>
<tr>
<td><code>workshops</code></td>
<td>Name of the database, our argument</td>
</tr>
<tr>
<td><code>-k trollsquad</code></td>
<td>Name of the keyspace, a db can contains multiple keyspaces</td>
</tr>
<tr>
<td><code>--if-not-exist</code></td>
<td>Flag for itempotency creating only what if needed</td>
</tr>
<tr>
<td><code>--wait</code></td>
<td>Make the command blocking until all expected operations are executed (timeout is 180s)</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>Note</strong>: If the database already exist but has not been used for while the status will be <code>HIBERNATED</code>. The previous command will resume the db an create the new keyspace but it can take about a minute to execute.</p>
</blockquote>
<blockquote>
<p>🖥️ <code>setup-06 output</code></p>
<pre><code>[ INFO ] - Database 'workshops' already exist. Connecting to database.
[ INFO ] - Database 'workshops' has status 'MAINTENANCE' waiting to be 'ACTIVE' ...
[ INFO ] - Database 'workshops' has status 'ACTIVE' (took 7983 millis)
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-setup-07-code-check-the-status-of-database-code-workshops-code"> </a><code>✅.setup-07</code>- Check the status of database <code>workshops</code></h4>
<pre lang="bash"><code>astra db status workshops
</code></pre>
<blockquote>
<p>🖥️ <code>setup-07 output</code></p>
<pre><code>[ INFO ] - Database 'workshops' has status 'ACTIVE'
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-setup-08-code-get-the-informations-for-your-database-including-the-keyspace-list"> </a><code>✅.setup-08</code>- Get the informations for your database including the keyspace list</h4>
<pre lang="bash"><code>astra db get workshops
</code></pre>
<blockquote>
<p>🖥️ <code>setup-08 output</code></p>
<pre><code>+------------------------+-----------------------------------------+
| Attribute              | Value                                   |
+------------------------+-----------------------------------------+
| Name                   | workshops                               |
| id                     | bb61cfd6-2702-4b19-97b6-3b89a04c9be7    |
| Status                 | ACTIVE                                  |
| Default Cloud Provider | AWS                                     |
| Default Region         | us-east-1                               |
| Default Keyspace       | trollsquad                              |
| Creation Time          | 2022-08-29T06:13:06Z                    |
|                        |                                         |
| Keyspaces              | [0] trollsquad                          |
|                        |                                         |
|                        |                                         |
| Regions                | [0] us-east-1                           |
|                        |                                         |
+------------------------+-----------------------------------------+
</code></pre>
</blockquote>
<p><em>Congratulations your environment is all set, let's start the labs !</em></p>
<h2><a class="anchor" aria-hidden="true" id="lab1-producer-and-consumer"> </a>LAB1 - Producer and Consumer</h2>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-01-code-generate-an-unique-tenant-name"> </a><code>✅.lab1-01</code>- Generate an unique tenant name</h4>
<blockquote>
<p><strong>Note</strong>: Your tenant name must start with a lowercase alphabetic character. It can only contain lowercase alphanumeric characters, and hyphens (kebab-case), and the maximum length is 25.</p>
</blockquote>
<p>A tenant name should BE UNIQUE IN ALL CLUSTER. So to get a unique name let's generate one randomly.</p>
<pre lang="bash"><code>export TENANT=&quot;trollsquad-$(tr -dc a-z0-9 &lt;/dev/urandom | head -c 9 ; echo '')&quot;
echo $TENANT
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-01 output</code></p>
<pre><code>trollsquad-abcdefghi
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-02-code-create-the-tenant-using-the-generated-name"> </a><code>✅.lab1-02</code>- Create the tenant using the generated name</h4>
<p>You can create a tenant from the user interface using <a href="https://docs.datastax.com/en/astra-streaming/docs/astream-quick-start.html#create-a-tenant" target="_blank">this tutorial</a> but we will not use this today.</p>
<p>We will use the CLI for everyone to share the same values for regions and cloud provider. We will default all values for simplicity and because they are harcoded in the configuration file.</p>
<pre lang="bash"><code>astra streaming create ${TENANT}
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-02 output</code></p>
<pre><code>[ INFO ] - Tenant 'trollsquad-abcdefghi' has being created.
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-03-code-list-your-tenants"> </a><code>✅.lab1-03</code>- List your tenants</h4>
<pre lang="bash"><code>astra streaming list
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-03 output</code></p>
<pre><code>+---------------------+-----------+----------------+----------------+
| name                | cloud     | region         | Status         |
+---------------------+-----------+----------------+----------------+
| trollsquad-abcdefghi| aws       | useast2        | active         |
+---------------------+-----------+----------------+----------------+
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-04-code-start-code-pulsar-shell-code"> </a><code>✅.lab1-04</code>- Start <code>Pulsar-shell</code></h4>
<blockquote>
<p><strong>Note</strong> Pulsar shell is a fast and flexible shell for Pulsar cluster management, messaging, and more. It's great for quickly switching between different clusters, and can modify cluster or tenant configurations in an instant.</p>
</blockquote>
<p>Astra CLI will download and install the software if needed. Then it will generate a <code>client.conf</code> based on the tenant name you provide.</p>
<pre lang="bash"><code>astra streaming pulsar-shell ${TENANT}
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-04 output</code></p>
<pre><code>[ INFO ] - pulsar-shell first launch, downloading (~ 60MB), please wait...
[ INFO ] - pulsar-shell has been installed
/home/gitpod/.astra/lunastreaming-shell-2.10.1.1/conf/client-aws-useast2-trollsquad-pk6oztya8.conf
Pulsar-shell is starting please wait for connection establishment...
Using directory: /home/gitpod/.pulsar-shell
Welcome to Pulsar shell!
  Service URL: pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651
  Admin URL: https://pulsar-aws-useast2.api.streaming.datastax.com

Type help to get started or try the autocompletion (TAB button).
Type exit or quit to end the shell session.

default(pulsar-aws-useast2.streaming.datastax.com)&gt; 
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-05-code-show-namespaces-in-code-pulsar-shell-code"> </a><code>✅.lab1-05</code>- Show namespaces in <code>pulsar-shell</code></h4>
<pre lang="bash"><code>admin namespaces list ${TENANT}
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-05 output</code></p>
<pre><code>trollsquad-abcdefghi/default
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-06-code-show-topics-in-code-pulsar-shell-code-empty"> </a><code>✅.lab1-06</code>- Show topics in <code>pulsar-shell</code> (empty)</h4>
<pre lang="bash"><code>admin topics list ${TENANT}/default
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-06 output</code></p>
<pre><code>&lt;empty&gt;
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-07-code-create-our-4-working-topics-one-command-after-the-other"> </a><code>✅.lab1-07</code>- Create our 4 working topics, one command after the other.</h4>
<ul>
<li><code>rr-raw-in</code></li>
</ul>
<pre lang="bash"><code>admin topics create persistent://${TENANT}/default/rr-raw-in
</code></pre>
<ul>
<li><code>rr-hotel-reviews</code></li>
</ul>
<pre><code>admin topics create persistent://${TENANT}/default/rr-hotel-reviews
</code></pre>
<ul>
<li><code>rr-restaurant-reviews</code></li>
</ul>
<pre><code>admin topics create persistent://${TENANT}/default/rr-restaurant-reviews
</code></pre>
<ul>
<li><code>rr-restaurant-anomalies</code></li>
</ul>
<pre><code>admin topics create persistent://${TENANT}/default/rr-restaurant-anomalies
</code></pre>
<ul>
<li>List the topics</li>
</ul>
<pre><code>admin topics list ${TENANT}/default
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-07 output</code></p>
<pre><code>persistent://trollsquad-abcdefghi/default/rr-raw-in
persistent://trollsquad-abcdefghi/default/rr-restaurant-anomalies
persistent://trollsquad-abcdefghi/default/rr-hotel-reviews
persistent://trollsquad-abcdefghi/default/rr-restaurant-reviews
</code></pre>
</blockquote>
<p>Let's dig into what those topics are used for. The will be populated one after this other moving across the labs.</p>
<table>
<thead>
<tr>
<th>Title</th>
<th>description</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>rr-raw-in</code></td>
<td>Will get inputs from injector</td>
</tr>
<tr>
<td><code>rr-hotel-reviews</code></td>
<td>Pulsar function router will put hotels reviews there</td>
</tr>
<tr>
<td><code>rr-restaurant-reviews</code></td>
<td>Pulsar function router will put restaurants reviews there</td>
</tr>
<tr>
<td><code>rr-restaurant-anomalies</code></td>
<td>The analyzer will reject reviews there</td>
</tr>
</tbody>
</table>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-08-code-exit-code-pulsar-shell-code"> </a><code>✅.lab1-08</code> -  Exit <code>pulsar-shell</code></h4>
<pre lang="bash"><code>exit
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-09-code-create-code-env-code-as-configuration-file"> </a><code>✅.lab1-09</code>- Create <code>.env</code> as configuration file</h4>
<pre><code>cp .env.sample .env
ASTRA_DB_ID=`astra db get workshops --key id`
echo &quot;ASTRA_DB_ID=\&quot;${ASTRA_DB_ID}\&quot;&quot; &gt;&gt; .env
ASTRA_DB_APP_TOKEN=`astra config get default --key ASTRA_DB_APPLICATION_TOKEN`
echo &quot;ASTRA_DB_APP_TOKEN=\&quot;${ASTRA_DB_APP_TOKEN}\&quot;&quot; &gt;&gt; .env
echo &quot;TENANT=\&quot;${TENANT}\&quot;&quot; &gt;&gt; .env
PULSAR_TOKEN=`astra streaming pulsar-token ${TENANT}`
echo &quot;PULSAR_TOKEN=\&quot;${PULSAR_TOKEN}\&quot;&quot; &gt;&gt; .env
ORGID=`astra org id`
echo &quot;ORGID=\&quot;${ORGID}\&quot;&quot; &gt;&gt; .env
set -a
source .env
set +a
tail -5 .env
</code></pre>
<blockquote>
<p><strong>Note</strong>: If your DB <code>workshops</code> existed before this session and was not started on region <code>us-east-1</code> you will have to edit <code>.env</code> changing the key <code>ASTRA_DB_REGION</code></p>
</blockquote>
<blockquote>
<p>🖥️ <code>lab1-09 output</code></p>
<pre><code>gitpod /workspace/workshop-realtime-data-pipelines (main) $ tail -5 .env
ASTRA_DB_ID=&quot;3ed83de7-d97f-4fb6-bf9f-82e9f7eafa23&quot;
ASTRA_DB_APP_TOKEN=&quot;AstraCS:gdZaqzmFZ************&quot;
TENANT=&quot;trollsquad-abcdefghi&quot;
PULSAR_TOKEN=&quot;eyJhbGciOiJSUzI1**********&quot;
ORGID=&quot;f9460f14-9879-4ebe-83f2-48d3f3dce13c&quot;
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-10-code-show-your-topics-on-the-user-interface"> </a><code>✅.lab1-10</code>- Show your topics on the user interface</h4>
<blockquote>
<p><strong>Note</strong>: <em>You need to be logged in to Astra&quot;. Make sure you have not being autologout before issueing the command</em></p>
</blockquote>
<pre><code>gp preview --external https://astra.datastax.com/org/${ORGID}/streaming/pulsar-aws-useast2/tenants/${TENANT}/topics/namespaces/default/topics/
</code></pre>
<p>Sometimes you have to hard refresh or click <code>topics</code> tab again. Notice the ellipsis to expand the list of topics if not present.</p>
<blockquote>
<p>🖥️ <code>lab1-10 output</code></p>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/pic-topics.png" alt="pic" /></p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-11-code-show-your-topic-code-rr-raw-in-code-in-astra-user-interface"> </a><code>✅.lab1-11</code>- Show your topic <code>rr-raw-in</code> in Astra User Interface:</h4>
<pre><code>gp preview --external https://astra.datastax.com/org/${ORGID}/streaming/pulsar-aws-useast2/tenants/${TENANT}/topics/namespaces/default/topics/rr-raw-in/1/0/overview
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-011 output</code></p>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/pic-rr-raw-in.png" alt="pic" /></p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-12-code-start-the-generator"> </a><code>✅.lab1-12</code>- Start the generator</h4>
<pre lang="bash"><code>/workspace/workshop-realtime-data-pipelines/revGenerator/review_generator.py -r 10
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-012 output</code></p>
<pre><code>2022-09-13 10:36:24.243 INFO  [140097656701568] ClientConnection:189 | [&lt;none&gt; -&gt; pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651] Create ClientConnection, timeout=10000
2022-09-13 10:36:24.249 INFO  [140097656701568] ConnectionPool:96 | Created connection for pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651
2022-09-13 10:36:24.349 INFO  [140097629259520] ClientConnection:375 | [10.0.5.2:49564 -&gt; 3.138.177.230:6651] Connected to broker
2022-09-13 10:36:24.818 INFO  [140097629259520] HandlerBase:64 | [persistent://trollsquad-pk6oztya8/default/rr-raw-in, ] Getting connection from pool
2022-09-13 10:36:24.910 INFO  [140097629259520] ClientConnection:189 | [&lt;none&gt; -&gt; pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651] Create ClientConnection, timeout=10000
2022-09-13 10:36:24.915 INFO  [140097629259520] ConnectionPool:96 | Created connection for pulsar://192.168.69.127:6650
2022-09-13 10:36:25.016 INFO  [140097629259520] ClientConnection:377 | [10.0.5.2:56960 -&gt; 18.223.216.1:6651] Connected to broker through proxy. Logical broker: pulsar://192.168.69.127:6650
2022-09-13 10:36:25.482 INFO  [140097629259520] ProducerImpl:189 | [persistent://trollsquad-pk6oztya8/default/rr-raw-in, ] Created producer on broker [10.0.5.2:56960 -&gt; 18.223.216.1:6651] 
* 0 ... [{&quot;u_id&quot;: &quot;geri&quot;, &quot;score&quot;: 9.3, &quot;review_type&quot;: &quot;hotel&quot;, &quot;item_id&quot;: &quot;slpsnd&quot;, &quot;item_name&quot;: &quot;SleepSound&quot;, &quot;text&quot;: &quot;we terrible disgusting unsatisfactory cooked terrible&quot;, &quot;idx&quot;: 0}]
* 1 ... [a5VH40D^L625Z98b1BKTN@N2aCEQN=VXQTD0IaYPK[RXbZVOQZJGP2`Y;^5OZ@:EE]
* 2 ... [{&quot;u_id&quot;: &quot;botz&quot;, &quot;score&quot;: 9.600000000000001, &quot;review_type&quot;: &quot;hotel&quot;, &quot;item_id&quot;: &quot;slpsnd&quot;, &quot;item_name&quot;: &quot;SleepSound&quot;, &quot;text&quot;: &quot;excellent excellent delicious ordinary dish with is tasty&quot;, &quot;idx&quot;: 2}]
* 3 ... [{&quot;u_id&quot;: &quot;botz&quot;, &quot;score&quot;: 9.1, &quot;item_id&quot;: &quot;eat_st&quot;, &quot;item_name&quot;: &quot;EatNStay&quot;, &quot;text&quot;: &quot;excellent the is excellent ordinary ordinary eating&quot;, &quot;idx&quot;: 3}]
....
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-13-code-start-code-pulsar-shell-code"> </a><code>✅.lab1-13</code>- Start <code>pulsar-shell</code></h4>
<p>For now on the first terminal will be busy with the generator. As such move to the second terminal called <code>2_consumer</code></p>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/pic-bash2.png" alt="" /></p>
<pre><code>set -a
source .env
set +a
source /home/gitpod/.astra/cli/astra-init.sh
astra streaming  pulsar-shell ${TENANT}
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-013 output</code></p>
<pre><code>/home/gitpod/.astra/lunastreaming-shell-2.10.1.1/conf/client-aws-useast2-trollsquad-pk6oztya8.conf
Pulsar-shell is starting please wait for connection establishment...
Using directory: /home/gitpod/.pulsar-shell
Welcome to Pulsar shell!
  Service URL: pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651
  Admin URL: https://pulsar-aws-useast2.api.streaming.datastax.com

Type help to get started or try the autocompletion (TAB button).
Type exit or quit to end the shell session.

default(pulsar-aws-useast2.streaming.datastax.com)&gt; 
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab1-14-code-visualize-messages-with-a-consumer-using-code-client-code"> </a><code>✅.lab1-14</code>- Visualize messages with a consumer using <code>client</code></h4>
<pre lang="bash"><code>client consume persistent://${TENANT}/default/rr-raw-in -s consume_log -n 0
</code></pre>
<blockquote>
<p>🖥️ <code>lab1-014 output</code></p>
<pre><code>2022-09-13T10:49:04,150+0000 [pulsar-client-io-1-1] INFO  org.apache.pulsar.client.impl.ConnectionPool - [[id: 0xf990e737, L:/10.0.5.2:54496 - R:pulsar-aws-useast2.streaming.datastax.com/3.16.119.226:6651]] Connected to server
2022-09-13T10:49:04,709+0000 [pulsar-client-io-1-1] INFO  org.apache.pulsar.client.impl.ConsumerStatsRecorderImpl - Starting Pulsar consumer status recorder with config: {&quot;topicNames&quot;:[&quot;persistent://trollsquad-pk6oztya8/default/rr-raw-in&quot;],&quot;topicsPattern&quot;:null,&quot;subscriptionName&quot;:&quot;consume_log&quot;,&quot;subscriptionType&quot;:&quot;Exclusive&quot;,&quot;subscriptionProperties&quot;:null,&quot;subscriptionMode&quot;:&quot;Durable&quot;,&quot;receiverQueueSize&quot;:1000,&quot;acknowledgementsGroupTimeMicros&quot;:100000,&quot;negativeAckRedeliveryDelayMicros&quot;:60000000,&quot;maxTotalReceiverQueueSizeAcrossPartitions&quot;:50000,&quot;consumerName&quot;:null,&quot;ackTimeoutMillis&quot;:0,&quot;tickDurationMillis&quot;:1000,&quot;priorityLevel&quot;:0,&quot;maxPendingChunkedMessage&quot;:10,&quot;autoAckOldestChunkedMessageOnQueueFull&quot;:false,&quot;expireTimeOfIncompleteChunkedMessageMillis&quot;:60000,&quot;cryptoFailureAction&quot;:&quot;FAIL&quot;,&quot;properties&quot;:{},&quot;readCompacted&quot;:false,&quot;subscriptionInitialPosition&quot;:&quot;Latest&quot;,&quot;patternAutoDiscoveryPeriod&quot;:60,&quot;regexSubscriptionMode&quot;:&quot;PersistentOnly&quot;,&quot;deadLetterPolicy&quot;:null,&quot;retryEnable&quot;:false,&quot;autoUpdatePartitions&quot;:true,&quot;autoUpdatePartitionsIntervalSeconds&quot;:60,&quot;replicateSubscriptionState&quot;:false,&quot;resetIncludeHead&quot;:false,&quot;keySharedPolicy&quot;:null,&quot;batchIndexAckEnabled&quot;:false,&quot;ackReceiptEnabled&quot;:false,&quot;poolMessages&quot;:true,&quot;startPaused&quot;:false,&quot;maxPendingChuckedMessage&quot;:10}
...
2022-09-13T10:49:59,192+0000 [pulsar-client-io-1-1] INFO  org.apache.pulsar.client.impl.ConsumerImpl - [persistent://trollsquad-pk6oztya8/default/rr-raw-in][consume_log] Subscribing to topic on cnx [id: 0x797d8d1d, L:/10.0.5.2:50876 - R:pulsar-aws-useast2.streaming.datastax.com/3.138.177.230:6651], consumerId 0
2022-09-13T10:49:59,288+0000 [pulsar-client-io-1-1] INFO  org.apache.pulsar.client.impl.ConsumerImpl - [persistent://trollsquad-pk6oztya8/default/rr-raw-in][consume_log] Subscribed to topic on pulsar-aws-useast2.streaming.datastax.com/3.138.177.230:6651 -- consumer: 0
2022-09-13T10:49:59,395+0000 [pulsar-client-io-1-1] INFO  com.scurrilous.circe.checksum.Crc32cIntChecksum - SSE4.2 CRC32C provider initialized
----- got message -----
key:[null], properties:[], content:{&quot;user_id&quot;: &quot;geri&quot;, &quot;score&quot;: 5.0, &quot;review_type&quot;: &quot;restaurant&quot;, &quot;item_id&quot;: &quot;vegg00&quot;, &quot;item_name&quot;: &quot;VeggieParadise&quot;, &quot;text&quot;: &quot;roast risotto risotto eating for for dish&quot;, &quot;idx&quot;: 1171}
----- got message -----
key:[null], properties:[], content:{&quot;user_id&quot;: &quot;botz&quot;, &quot;score&quot;: 7.300000000000001, &quot;review_type&quot;: &quot;restaurant&quot;, &quot;item_id&quot;: &quot;gold_f&quot;, &quot;item_name&quot;: &quot;Golden Fork&quot;, &quot;text&quot;: &quot;with we ordinary we with cooked we ordinary&quot;, &quot;idx&quot;: 1172}
</code></pre>
</blockquote>
<p>We can kill this consumer with <code>CTRL + C</code>.</p>
<h2><a class="anchor" aria-hidden="true" id="lab2-pulsar-functions"> </a>LAB2 - Pulsar functions</h2>
<p>For now both terminal will 1 and 2 be busy with the generator. As such move to the second terminal called <code>3_analyzer</code></p>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/pic-bash3.png" alt="" /></p>
<h4><a class="anchor" aria-hidden="true" id="code-lab2-01-code-locate-and-setup-the-function"> </a><code>✅.lab2-01</code>- Locate and setup the function</h4>
<pre lang="bash"><code>set -a
source .env
set +a
gp open /workspace/workshop-realtime-data-pipelines/pulsar_routing_function/review_router.py
sed -i &quot;s/___TENANT___/${TENANT}/&quot; /workspace/workshop-realtime-data-pipelines/pulsar_routing_function/review_router.py
</code></pre>
<blockquote>
<p>🖥️ <code>lab2-01 output</code></p>
<p>Before <code>sed</code>:<br />
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/sed-before.png" alt="pic" /></p>
<p>After <code>sed</code>:<br />
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/sed-after.png" alt="" /></p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab2-02-code-start-pulsar-shell-again"> </a><code>✅.lab2-02</code>- Start Pulsar Shell (again)</h4>
<pre lang="bash"><code>source /home/gitpod/.astra/cli/astra-init.sh
astra streaming pulsar-shell ${TENANT}
</code></pre>
<blockquote>
<p>🖥️ <code>lab2-02 output</code></p>
<pre><code>/home/gitpod/.astra/lunastreaming-shell-2.10.1.1/conf/client-aws-useast2-trollsquad-abcdefghi.conf
Pulsar-shell is starting please wait for connection establishment...
Using directory: /home/gitpod/.pulsar-shell
Welcome to Pulsar shell!
  Service URL: pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651
 Admin URL: https://pulsar-aws-useast2.api.streaming.datastax.com

Type help to get started or try the autocompletion (TAB button).
Type exit or quit to end the shell session.

default(pulsar-aws-useast2.streaming.datastax.com)&gt; 
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab2-03-code-list-functions-in-code-pulsar-shell-code"> </a><code>✅.lab2-03</code>- List functions in <code>pulsar-shell</code></h4>
<pre lang="bash"><code>admin functions list --tenant=${TENANT} --namespace=default
</code></pre>
<blockquote>
<p>🖥️ <code>lab2-03 output</code></p>
<pre><code>&lt;empty&gt;
</code></pre>
</blockquote>
<blockquote>
<p><strong>Note</strong>:<em>If you need to delete a function you can also leverage on the <code>admin</code> command to do so:</em></p>
<pre lang="bash"><code>admin functions delete
    --name rrouter-function 
    --tenant=${TENANT} 
    --namespace=default
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab2-04-code-create-the-pulsar-function"> </a><code>✅.lab2-04</code>- Create the Pulsar-function</h4>
<pre lang="bash"><code>admin functions create
  --py /workspace/workshop-realtime-data-pipelines/pulsar_routing_function/review_router.py
  --classname review_router.ReviewRouter
  --tenant ${TENANT}
  --namespace default
  --name rrouter-function
  --inputs persistent://${TENANT}/default/rr-raw-in
</code></pre>
<blockquote>
<p>🖥️ <code>lab2-04 output</code></p>
<pre><code>Created successfully
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab2-05-code-list-functions-in-code-pulsar-shell-code"> </a><code>✅.lab2-05</code>- List functions in <code>pulsar-shell</code></h4>
<pre lang="bash"><code>admin functions list --tenant=${TENANT} --namespace=default
exit
</code></pre>
<blockquote>
<p>🖥️ <code>lab2-05 output</code></p>
<pre><code>rrouter-function
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab2-06-code-check-on-topics-code-rr-hotel-reviews-code-and-code-rr-restaurant-reviews-code"> </a><code>✅.lab2-06</code>- Check on topics <code>rr-hotel-reviews</code> and <code>rr-restaurant-reviews</code></h4>
<ul>
<li>Hotels</li>
</ul>
<pre lang="bash"><code>gp preview --external https://astra.datastax.com/org/${ORGID}/streaming/pulsar-aws-useast2/tenants/${TENANT}/topics/namespaces/default/topics/rr-hotel-reviews/1/0
</code></pre>
<blockquote>
<p>🖥️ <code>lab2-06 output-1</code></p>
<p>Hotels:<br />
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/pic-hotel-reviews.png" alt="" /></p>
</blockquote>
<ul>
<li>Restaurants</li>
</ul>
<pre><code>gp preview --external https://astra.datastax.com/org/${ORGID}/streaming/pulsar-aws-useast2/tenants/${TENANT}/topics/namespaces/default/topics/rr-restaurant-reviews/1/0
</code></pre>
<blockquote>
<p>🖥️ <code>lab2-06 output-2</code></p>
<p>Restaurants:<br />
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/pic-restaurant-reviews.png" alt="" /></p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab2-07-code-consume-5-message-in-topics-content-with-code-pulsar-shell-code"> </a><code>✅.lab2-07</code>- Consume 5 message in topics content with <code>pulsar-shell</code></h4>
<ul>
<li>Start Shell:</li>
</ul>
<pre><code>astra streaming pulsar-shell ${TENANT}
</code></pre>
<ul>
<li>Execute command:</li>
</ul>
<pre><code>client consume persistent://${TENANT}/default/rr-restaurant-reviews -s consume_log -n 5
</code></pre>
<blockquote>
<p>🖥️ <code>lab2-07 output</code></p>
<p>After initialization you see messages:<br />
[...]<br />
----- got message -----<br />
key:[null], properties:[], content:{&quot;user_id&quot;: &quot;rita&quot;, &quot;r_score&quot;: 3.9000000000000004, &quot;tgt_name&quot;: &quot;VeggieParadise&quot;, &quot;tgt_id&quot;: &quot;vegg00&quot;, &quot;r_text&quot;: &quot;we ordinary roast with is for for is&quot;, &quot;idx&quot;: 9619}<br />
[...]</p>
<p>If we format a sample message it looks like:</p>
<pre lang="json"><code>{ 
  &quot;user_id&quot;: &quot;geri&quot;, 
   &quot;r_score&quot;: 1.5, 
   &quot;tgt_name&quot;: &quot;Pizza Smile&quot;, 
   &quot;tgt_id&quot;: &quot;pizzas&quot;, 
   &quot;r_text&quot;: &quot;delicious with for eating stellar excellent is&quot;, 
   &quot;idx&quot;: 20179
 }
</code></pre>
</blockquote>
<ul>
<li>Exit <code>pulsar-shell</code></li>
</ul>
<pre lang="bash"><code>exit
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-lab2-08-code-run-analyzer"> </a><code>✅.lab2-08</code>- Run Analyzer</h4>
<p>revAnalyzer is a standalone batch to evaluate which reviews are relevant and which are not.</p>
<pre lang="bash"><code>set -a
source .env
set +a
/workspace/workshop-realtime-data-pipelines/revAnalyzer/review_analyzer.py -r -o -t -f 200
</code></pre>
<blockquote>
<p>🖥️ <code>lab2-08 output</code></p>
<pre><code>Checking &quot;known_ids_per_type&quot; ... done.
Checking &quot;restaurants_by_id&quot; ... done.
Checking &quot;restaurants_by_id_time&quot; ... done.
Checking &quot;reviewers_by_id&quot; ... done.
2022-09-13 12:46:30.012 INFO  [140019973255808] Client:88 | Subscribing on Topic :persistent://trollsquad-pk6oztya8/default/rr-restaurant-reviews
2022-09-13 12:46:30.012 INFO  [140019973255808] ClientConnection:189 | [&lt;none&gt; -&gt; pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651] Create ClientConnection, timeout=10000
2022-09-13 12:46:30.019 INFO  [140019973255808] ConnectionPool:96 | Created connection for pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651
2022-09-13 12:46:30.121 INFO  [140019938682624] ClientConnection:375 | [10.0.5.2:33432 -&gt; 18.223.216.1:6651] Connected to broker
2022-09-13 12:46:30.593 INFO  [140019938682624] HandlerBase:64 | [persistent://trollsquad-pk6oztya8/default/rr-restaurant-reviews, review-analyzer, 0] Getting connection from pool
2022-09-13 12:46:30.688 INFO  [140019938682624] ClientConnection:189 | [&lt;none&gt; -&gt; pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651] Create ClientConnection, timeout=10000
2022-09-13 12:46:30.696 INFO  [140019938682624] ConnectionPool:96 | Created connection for pulsar://192.168.50.226:6650
2022-09-13 12:46:30.798 INFO  [140019938682624] ClientConnection:377 | [10.0.5.2:49968 -&gt; 3.138.177.230:6651] Connected to broker through proxy. Logical broker: pulsar://192.168.50.226:6650
2022-09-13 12:46:31.263 INFO  [140019938682624] ConsumerImpl:224 | [persistent://trollsquad-pk6oztya8/default/rr-restaurant-reviews, review-analyzer, 0] Created consumer on broker [10.0.5.2:49968 -&gt; 3.138.177.230:6651] 
2022-09-13 12:46:31.358 INFO  [140019938682624] HandlerBase:64 | [persistent://trollsquad-pk6oztya8/default/rr-restaurant-anomalies, ] Getting connection from pool
2022-09-13 12:46:31.453 INFO  [140019938682624] ClientConnection:189 | [&lt;none&gt; -&gt; pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651] Create ClientConnection, timeout=10000
2022-09-13 12:46:31.460 INFO  [140019938682624] ConnectionPool:96 | Created connection for pulsar://192.168.7.141:6650
2022-09-13 12:46:31.558 INFO  [140019938682624] ClientConnection:377 | [10.0.5.2:41468 -&gt; 3.16.119.226:6651] Connected to broker through proxy. Logical broker: pulsar://192.168.7.141:6650
2022-09-13 12:46:32.032 INFO  [140019938682624] ProducerImpl:189 | [persistent://trollsquad-pk6oztya8/default/rr-restaurant-anomalies, ] Created producer on broker [10.0.5.2:41468 -&gt; 3.16.119.226:6651] 
[ 20827] Outlier detected: &quot;anne&quot; on &quot;Golden Fork&quot; (rev 7.40 != avg 3.47)
[ 24252] Outlier detected: &quot;anne&quot; on &quot;Golden Fork&quot; (rev 7.90 != avg 4.63)
[ 24256] Outlier detected: &quot;botz&quot; on &quot;Golden Fork&quot; (rev 0.40 != avg 4.21)
[ 24616] Outlier detected: &quot;botz&quot; on &quot;Golden Fork&quot; (rev 0.60 != avg 3.97)
[ 25239] Restaurant Score Summary:
                 [gold_f  25239]   &quot;Golden Fork&quot;      : 3.66   (outliers:      4/    64)
                 [pizzas  25239]   &quot;Pizza Smile&quot;      : 0.67   (outliers:      0/    55)
                 [vegg00  25239]   &quot;VeggieParadise&quot;   : 1.93   (outliers:      0/    57)
[ 25239] Reviewer Summary:
                   &quot;anne&quot;  25239 : troll-score = 0.00 (outliers:      2 /     42). Visits: gold_f(18), pizzas(12), vegg00(12)
                   &quot;botz&quot;  25239 : troll-score = 0.00 (outliers:      2 /     43). Visits: gold_f(13), pizzas(14), vegg00(16)
                   &quot;geri&quot;  25239 : troll-score = 0.66 (outliers:      0 /     41). Visits: gold_f(12), vegg00(2)
                   &quot;john&quot;  25239 : troll-score = 0.00 (outliers:      0 /     35). Visits: gold_f(13), pizzas(10), vegg00(12)
                   &quot;rita&quot;  25239 : troll-score = 0.00 (outliers:      0 /     39). Visits: gold_f(7), pizzas(18), vegg00(14)
[ 25239] Writing to DB ... done.
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab2-09-code-change-terminal"> </a><code>✅.lab2-09</code>- Change Terminal</h4>
<p>All terminal are busy. Let us move to the terminal called <code>4_reader</code></p>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/pic-bash4.png" alt="" /></p>
<h4><a class="anchor" aria-hidden="true" id="code-lab2-010-code-start-reader-to-log-anomalies-in-shell-code-reader-code"> </a><code>✅.lab2-010</code>- Start reader to log anomalies in shell <code>reader</code></h4>
<pre lang="bash"><code>set -a
source .env
set +a
/workspace/workshop-realtime-data-pipelines/tools/reader.py -t rr-restaurant-anomalies
</code></pre>
<blockquote>
<p>🖥️ <code>lab2-10 output</code></p>
<pre><code>2022-09-13 12:52:16.261 INFO  [139762389439104] Client:88 | Subscribing on Topic :persistent://trollsquad-pk6oztya8/default/rr-restaurant-anomalies
2022-09-13 12:52:16.262 INFO  [139762389439104] ClientConnection:189 | [&lt;none&gt; -&gt; pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651] Create ClientConnection, timeout=10000
2022-09-13 12:52:16.267 INFO  [139762389439104] ConnectionPool:96 | Created connection for pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651
2022-09-13 12:52:16.380 INFO  [139762369062656] ClientConnection:375 | [10.0.5.2:40472 -&gt; 3.16.119.226:6651] Connected to broker
2022-09-13 12:52:16.852 INFO  [139762369062656] HandlerBase:64 | [persistent://trollsquad-pk6oztya8/default/rr-restaurant-anomalies, my-sub, 0] Getting connection from pool
2022-09-13 12:52:16.945 INFO  [139762369062656] ClientConnection:189 | [&lt;none&gt; -&gt; pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651] Create ClientConnection, timeout=10000
2022-09-13 12:52:16.951 INFO  [139762369062656] ConnectionPool:96 | Created connection for pulsar://192.168.7.141:6650
...
[2022-09-13T12:52:40] Received message 217:
    Type = JSON
        {
            &quot;detected_by&quot;: &quot;review_analyzer.py&quot;,
            &quot;idx&quot;: 22650,
            &quot;r_score&quot;: 9.4,
            &quot;r_text&quot;: &quot;roast superb roast ordinary superb superb stellar we&quot;,
            &quot;tgt_id&quot;: &quot;gold_f&quot;,
            &quot;tgt_name&quot;: &quot;Golden Fork&quot;,
            &quot;user_id&quot;: &quot;botz&quot;
        }
...
</code></pre>
</blockquote>
<blockquote>
<p><strong>Note</strong>: <em>you can customize the behaviour of those commands - try passing <code>-h</code>to the scripts to see what is available</em>.</p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="lab3-working-with-databases"> </a>LAB3 - Working with databases</h2>
<p>All terminal are busy. Let us move to the terminal called <code>5_database</code></p>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/pic-bash5.png" alt="" /></p>
<p>The only missing piece at this point are direct database queries. You can access the tables in any way you want, for instance using the provided <a href="https://github.com/datastaxdevs/awesome-astra/wiki/Cql-Shell" target="_blank">CQL shell on the Astra DB UI</a>: just inspect the <code>trollsquad</code> keyspace and try to <code>SELECT</code> rows from the tables you find there.</p>
<h4><a class="anchor" aria-hidden="true" id="code-lab3-01-code-display-schema"> </a><code>✅.lab3-01</code>- Display schema</h4>
<p>You will notice that the restaurant reviews are written in <em>two</em> tables:</p>
<ul>
<li>one will simply contain the latest average score for each restaurant</li>
</ul>
<pre lang="bash"><code>set -a
source .env
set +a
source /home/gitpod/.astra/cli/astra-init.sh
astra db cqlsh workshops -e &quot;describe table trollsquad.restaurants_by_id;&quot;
</code></pre>
<blockquote>
<p>🖥️ <code>lab3-01 output (1)</code></p>
<pre lang="sql"><code>[ INFO ] - Cqlsh has been installed

Cqlsh is starting please wait for connection establishment...

CREATE TABLE trollsquad.restaurants_by_id (
    id text PRIMARY KEY,
    average float,
    hits int,
    name text,
    num_outliers int
)
</code></pre>
</blockquote>
<blockquote>
<p><strong>Note</strong>:<em>Sometimes you can hit a timeout error, it that is the case reexcute the same command.</em></p>
</blockquote>
<ul>
<li>the other is structured to offer historical data for e.g. a plotting client application (there is some built-in eviction of old results to avoid unbound growth of the table).</li>
</ul>
<pre lang="bash"><code>source /home/gitpod/.astra/cli/astra-init.sh
astra db cqlsh workshops -e &quot;describe table trollsquad.restaurants_by_id_time;&quot;
</code></pre>
<blockquote>
<p>🖥️ <code>lab3-01 output (2)</code></p>
<pre lang="sql"><code>CREATE TABLE trollsquad.restaurants_by_id_time (
    id text,
    time timestamp,
    average float,
    name text,
    PRIMARY KEY (id, time)
) WITH CLUSTERING ORDER BY (time ASC)
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab3-02-code-what-restaurants-can-be-queried"> </a><code>✅.lab3-02</code>- What restaurants can be queried?</h4>
<pre lang="bash"><code>astra db cqlsh workshops \
   -e &quot;select * from trollsquad.known_ids_per_type where id_type='restaurant'&quot;
</code></pre>
<blockquote>
<p>🖥️ <code>lab3-02 output</code></p>
<pre lang="sql"><code> id_type    | ids
------------+--------------------------------
 restaurant | {'gold_f', 'pizzas', 'vegg00'}
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab3-03-code-what-reviewers-can-be-queried"> </a><code>✅.lab3-03</code>- What reviewers can be queried?</h4>
<pre lang="bash"><code>astra db cqlsh workshops \
   -e &quot;select * from trollsquad.known_ids_per_type where id_type='reviewer'&quot;
</code></pre>
<blockquote>
<p>🖥️ <code>lab3-03 output</code></p>
<pre lang="sql"><code> id_type    | ids
------------+--------------------------------
 reviewer | {'anne', 'botz', 'geri', 'john', 'rita'}
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab3-04-code-what-s-the-current-status-of-a-restaurant"> </a><code>✅.lab3-04</code>- What's the current status of a restaurant?</h4>
<pre lang="bash"><code>astra db cqlsh workshops \
   -e &quot;select * from trollsquad.restaurants_by_id where id='vegg00'&quot;
</code></pre>
<blockquote>
<p>🖥️ <code>lab3-04 output</code></p>
<pre lang="sql"><code>id     | average | hits | name           | num_outliers
--------+---------+------+----------------+--------------
 vegg00 | 1.93489 |   57 | VeggieParadise |            0

</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab3-05-code-what-s-the-current-status-of-a-reviewer"> </a><code>✅.lab3-05</code>- What's the current status of a reviewer?</h4>
<pre lang="bash"><code>astra db cqlsh workshops \
   -e &quot;select * from trollsquad.reviewers_by_id where id='geri'&quot;
</code></pre>
<blockquote>
<p>🖥️ <code>lab3-05 output</code></p>
<pre lang="sql"><code> id   | hits | num_outliers | target_map                  | trollings
------+------+--------------+-----------------------------+-----------
geri |   83 |            0 | {'gold_f': 16, 'vegg00': 4} |        63

</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-lab3-06-code-what-is-the-timeline-of-reviews-for-a-restaurant"> </a><code>✅.lab3-06</code>- What is the timeline of reviews for a restaurant?</h4>
<pre lang="bash"><code>astra db cqlsh workshops \
   -e &quot;select * from trollsquad.restaurants_by_id_time where id='gold_f'&quot;
</code></pre>
<blockquote>
<p>🖥️ <code>lab3-05 output</code></p>
<pre lang="sql"><code>id     | time                            | average | name
--------+---------------------------------+---------+-------------
 gold_f | 2022-09-13 00:48:51.481000+0000 | 5.14027 | Golden Fork
 gold_f | 2022-09-13 00:48:52.782000+0000 | 4.02716 | Golden Fork
 gold_f | 2022-09-13 00:48:59.465000+0000 |  2.9716 | Golden Fork
 gold_f | 2022-09-13 00:49:01.645000+0000 | 4.91724 | Golden Fork
 gold_f | 2022-09-13 00:49:03.377000+0000 | 4.09476 | Golden Fork
 gold_f | 2022-09-13 00:49:05.156000+0000 | 3.31554 | Golden Fork
 gold_f | 2022-09-13 00:49:06.902000+0000 | 4.79082 | Golden Fork
 gold_f | 2022-09-13 00:49:08.588000+0000 | 3.13101 | Golden Fork
 gold_f | 2022-09-13 00:49:10.141000+0000 | 4.96983 | Golden Fork
 gold_f | 2022-09-13 00:49:12.284000+0000 | 4.87864 | Golden Fork
 gold_f | 2022-09-13 00:49:13.722000+0000 | 4.18713 | Golden Fork
 gold_f | 2022-09-13 00:49:15.501000+0000 |  2.9564 | Golden Fork
</code></pre>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="lab4-pulsar-i-o"> </a>LAB4 - Pulsar I/O</h2>
<p>We used a standalone analyzer to create the tables and populate values. What if, each time a data is inserted in a topic it is also copied in the db.</p>
<h4><a class="anchor" aria-hidden="true" id="code-lab4-01-code-analyzing-message-syntax-in-code-rr-restaurant-anomalies-code"> </a><code>✅.lab4-01</code>- Analyzing message syntax in <code>rr-restaurant-anomalies</code></h4>
<ul>
<li>Start Pulsar-shell again</li>
</ul>
<pre lang="bash"><code>astra streaming pulsar-shell ${TENANT}
</code></pre>
<ul>
<li>Consume a couple of messages in <code>rr-restaurant-anomalies</code> (the analyzer should be running)</li>
</ul>
<pre lang="bash"><code>client consume persistent://${TENANT}/default/rr-restaurant-anomalies -s log -n 5
</code></pre>
<ul>
<li>Looking at message structure, the output look like</li>
</ul>
<pre lang="bashing"><code>
[...]
key:[null], properties:[], content:{&quot;user_id&quot;: &quot;botz&quot;, &quot;r_score&quot;: 6.4, &quot;tgt_name&quot;: &quot;Pizza Smile&quot;, &quot;tgt_id&quot;: &quot;pizzas&quot;, &quot;r_text&quot;: &quot;eating is for ordinary is&quot;, &quot;idx&quot;: 17261, &quot;detected_by&quot;: &quot;review_analyzer.py&quot;}
----- got message -----
[...]
</code></pre>
<ul>
<li>Extracting one message and formatting as <code>JSON</code>:</li>
</ul>
<pre lang="json"><code>{ 
  &quot;user_id&quot;: &quot;geri&quot;, 
  &quot;r_score&quot;: 5.7, 
  &quot;tgt_name&quot;: &quot;Golden Fork&quot;, 
  &quot;tgt_id&quot;: &quot;gold_f&quot;, 
  &quot;r_text&quot;: &quot;dish the the is dish with we&quot;, 
  &quot;idx&quot;: 17845,  
  &quot;detected_by&quot;: &quot;review_analyzer.py&quot;
}
</code></pre>
<p>Let us do a couple of assumptions:</p>
<ul>
<li>idx ensures unicity of a record</li>
<li>we want to search by user</li>
</ul>
<pre lang="sql"><code>CREATE TABLE IF NOT EXISTS trollsquad.msg_rr_restaurant_anomalies (
     user_id  text,
     idx      int,
     r_score  double,
     tgt_name text,
     tgt_id   text,
     r_text   text,
     detected_by text,
     PRIMARY KEY (user_id, idx)
) WITH CLUSTERING ORDER BY (idx ASC);
</code></pre>
<ul>
<li>Exit the <code>pulsar-shell</code></li>
</ul>
<pre lang="bash"><code>exit
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-lab4-02-code-create-the-associated-table"> </a><code>✅.lab4-02</code>- Create the associated Table</h4>
<ul>
<li>Create the table through CQL</li>
</ul>
<pre lang="bash"><code>astra db cqlsh workshops -e &quot;CREATE TABLE IF NOT EXISTS trollsquad.msg_rr_restaurant_anomalies ( \
      user_id  text, \
      idx      int, \
      r_score  double, 
      tgt_name text,\
      tgt_id   text,\
      r_text   text,\
      detected_by text,\
      PRIMARY KEY (user_id, idx)\
  ) WITH CLUSTERING ORDER BY (idx ASC);&quot;
</code></pre>
<ul>
<li>Check table now exist</li>
</ul>
<pre lang="bash"><code>astra db cqlsh workshops -e &quot;describe table trollsquad.msg_rr_restaurant_anomalies;&quot;
</code></pre>
<ul>
<li>Check content of the table</li>
</ul>
<pre lang="bash"><code>astra db cqlsh workshops -e &quot;select * FROM trollsquad.msg_rr_restaurant_anomalies LIMIT 10;&quot;
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-lab4-03-code-create-a-sink-with-the-user-interface"> </a><code>✅.lab4-03</code>- Create a Sink with the user interface</h4>
<blockquote>
<p><strong>Note</strong>:<a href="https://docs.datastax.com/en/astra-streaming/docs/astream-astradb-sink.html" target="_blank">Reference Documentation</a></p>
</blockquote>
<ul>
<li>In the dashboard of your tenant, locate the tab <code>Sinks</code> and select button <code>[Create Sink]</code>.</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/create-sink-01.png" alt="" /></p>
<ul>
<li>Enter General attributes (part 1)</li>
</ul>
<table>
<thead>
<tr>
<th>Attribute</th>
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Namespace</td>
<td><code>default</code></td>
<td>The namespace we work with from the beginning</td>
</tr>
<tr>
<td>Sink Type</td>
<td><code>Astra DB</code></td>
<td>You can define external systems but here we stay in Astra</td>
</tr>
<tr>
<td>Name</td>
<td><code>sink-anomalies</code></td>
<td>Pick anything unique, here reminding the source topic</td>
</tr>
<tr>
<td>Topic</td>
<td><code>rr-restaurant-anomalies</code></td>
<td>The one we decided to save</td>
</tr>
</tbody>
</table>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/create-sink-02.png" alt="" /></p>
<ul>
<li>Get your token value. You need to remind the token we used today, the first entry your provided:</li>
</ul>
<pre lang="bash"><code>astra config get default --key ASTRA_DB_APPLICATION_TOKEN
</code></pre>
<ul>
<li>Enter Database attributes (part 2)</li>
</ul>
<table>
<thead>
<tr>
<th>Attribute</th>
<th>Value</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>Database</td>
<td><code>workshops</code></td>
<td>db created it in the beginning</td>
</tr>
<tr>
<td>Keyspace</td>
<td><code>trollsquad</code></td>
<td>keyspace we created in the beginning</td>
</tr>
<tr>
<td>TableName</td>
<td><code>msg_rr_restaurant_anomalies</code></td>
<td>Table we created before</td>
</tr>
<tr>
<td>Token</td>
<td><code>&lt;your_token&gt;</code></td>
<td>Do not copy-paste the value but use YOUR token.</td>
</tr>
</tbody>
</table>
<p>And for Mapping. It is a mapping 1 to 1 from message attributes to db columns.</p>
<pre lang="csv"><code>user_id=value.user_id,idx=value.idx,r_score=value.r_score,tgt_name=value.tgt_name,tgt_id=value.tgt_id,r_text=value.r_text,detected_by=value.detected_by
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/create-sink-03.png" alt="" /></p>
<ul>
<li>These were the last entries you can now click the <code>[Create]</code> button</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/create-sink-04.png" alt="" /></p>
<ul>
<li>The sink will take about a minute to initialize and start:</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/create-sink-05.png" alt="" /></p>
<ul>
<li>When it is ready the status will switch to <code>running</code></li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/create-sink-06.png" alt="" /></p>
<ul>
<li>You can get the details by clicking on the sink name in the table</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/create-sink-07.png" alt="" /></p>
<h4><a class="anchor" aria-hidden="true" id="code-lab4-04-code-query-the-destination-table"> </a><code>✅.lab4-04</code>- Query the destination table</h4>
<pre lang="bash"><code>astra db cqlsh workshops -e &quot;select * FROM trollsquad.msg_rr_restaurant_anomalies LIMIT 10;&quot;
</code></pre>
<blockquote>
<p>🖥️ <code>lab4-04 output</code></p>
<p><code>YOUR_HOMEWORK</code></p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h2>
<p>To submit the <strong>homework</strong>, please take a screenshot in gitpod with the result of lab <code>✅.lab4-04</code>, you will have different values than the ones showed during the live.</p>
<p>Don't forget to <a href="https://dtsx.io/homework-realtime-data-pipelines" target="_blank">submit your homework</a> and be awarded a nice verified badge!</p>
<h2><a class="anchor" aria-hidden="true" id="what-s-next"> </a>What's NEXT ?</h2>
<p>We've just scratched the surface of what you can do using Astra DB, built on Apache Pulsar and Cassandra.</p>
<p>Go take a look at <a href="https://www.datastax.com/dev" target="_blank">DataStax for Developers</a> to see what else is possible.</p>
<p>There's plenty to dig into!</p>
<p>Congratulations: you made to the end of today's workshop.</p>
<p>Don't forget to <a href="https://dtsx.io/homework-realtime-data-pipelines" target="_blank">submit your homework</a> and be awarded a nice verified badge!</p>
<img src="https://github.com/datastaxdevs/workshop-realtime-data-pipelines/raw/master/images/badge.png?raw=true" width="350" />
<p><strong>... and see you at our next workshop!</strong></p>

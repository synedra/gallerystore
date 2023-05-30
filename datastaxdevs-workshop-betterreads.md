<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="workshops-better-reads"> </a>Workshops 📘 Better Reads 📘 !</h1>
<img src="https://github.com/datastaxdevs/workshop-betterreads/raw/master/img/badge.png?raw=true" width="150" align="right" />
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-goodreads-clone" target="_blank"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod" alt="Gitpod ready-to-code" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<blockquote>
<p>⚠️ Difficulty: <strong><code>Intermediate</code>, we expect you to already know Java and Spring.</strong></p>
</blockquote>
<p>Learn how to build an app end-to-end application with Spring ecosystem <em>(boot, mvc, security, data, test, thymeleaf)</em> and Apache Cassandra™.</p>
<h2><a class="anchor" aria-hidden="true" id="table-of-content"> </a>📋 Table of content</h2>
<img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/screenshot.png?raw=true" align="right" width="400px"/>
<p><strong>HOUSEKEEPING</strong></p>
<ul>
<li><a href="#objectives" target="_blank">Objectives</a></li>
<li><a href="#acknowledgements" target="_blank">Acknowledgements</a></li>
<li><a href="#frequently-asked-questions" target="_blank">Frequently asked questions</a></li>
<li><a href="#materials-for-the-session" target="_blank">Materials for the Session</a></li>
</ul>
<p><a href="#1-database-initialization" target="_blank"><strong>LAB1 - Database Initialization</strong></a></p>
<ul>
<li><a href="#11---create-an-astra-account" target="_blank">1.1 - Create Astra Account</a></li>
<li><a href="#12---create-an-astra-token" target="_blank">1.2 - Create Astra Token</a></li>
<li><a href="#13---open-your-environment" target="_blank">1.3 - Open your environment</a></li>
<li><a href="#14---setup-astra-cli" target="_blank">1.4 - Setup Astra CLI</a></li>
<li><a href="#15---create-database" target="_blank">1.5 - Create Database</a></li>
<li><a href="#16---create-schema" target="_blank">1.6 - Create Schema</a></li>
<li><a href="#17---load-data" target="_blank">1.7 - Load Data</a></li>
</ul>
<p><a href="#2-application-implementation" target="_blank"><strong>LAB2 - Application Implementation</strong></a></p>
<ul>
<li><a href="#21---configuration" target="_blank">2.1 - Configuration</a></li>
<li><a href="#22---start-application-and-first-use" target="_blank">2.2 - Start application and first use</a></li>
<li><a href="#23---setup-authentication-for-google" target="_blank">2.3 - Setup authentication for Google</a></li>
<li><a href="#24---setup-authentication-for-github" target="_blank">2.4 - Setup authentication for Github</a></li>
<li><a href="#25---authentication-with-oauth2" target="_blank">2.5 - Authentication with OAuth 2</a></li>
</ul>
<p><a href="#homeworks" target="_blank"><strong>Homeworks</strong></a></p>
<h2><a class="anchor" aria-hidden="true" id="housekeeping"> </a>HouseKeeping</h2>
<h3><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h3>
<ul>
<li>Discover how to use the following technologies:
<ul>
<li><strong>Spring Data:</strong> the Object Mapping layer of Spring</li>
<li><strong>Spring Data Cassandra:</strong> what traps to avoid</li>
<li><strong>Spring Security:</strong> how to handle authentication with OAuth2</li>
<li><strong>Spring MVC:</strong> how to expose REST API and controllers</li>
<li><strong>Spring Webflux:</strong> how to use the new <code>WebClient</code></li>
<li><strong>Thymeleaf:</strong> how to build a user interface with Spring</li>
<li><strong>Spring Test:</strong> How to run tests</li>
<li><strong>Astra DB</strong> (a Database-as-a-service built on Apache Cassandra)</li>
</ul>
</li>
<li>Han fun with an interactive session</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="acknowledgements"> </a>Acknowledgements</h3>
<p>This application has been built based on the work of <a href="https://www.youtube.com/channel/UCYt1sfh5464XaDBH0oH_o7Q" target="_blank"><strong>Java Brains</strong></a>, a famous youtuber <em>(500k+ subscribers)</em>. On his channel you can find the full <a href="https://www.youtube.com/watch?v=LxVGFBRpEFM"><em>Code with me Series</em></a>, 16 episodes for building this application step-by-step. The link to each episode is provided at the end of this readme.</p>
<h3><a class="anchor" aria-hidden="true" id="frequently-asked-questions"> </a>Frequently asked questions</h3>
<p/>
<details>
<summary><b> 1️⃣ Can I run this workshop on my computer?</b></summary>
<hr>
<p>There is nothing preventing you from running the workshop on your own machine, If you do so, you will need the following
<ol>
<li><b>git</b> installed on your local system
<li><b>JDK 8+</b> installed on your local system
<li><b>Maven 3.6+</b> installed on your local system
</ol>
</p>
In this readme, we try to provide instructions for local development as well - but keep in mind that the main focus is development on Gitpod, hence <strong>We can't guarantee live support</strong> about local development in order to keep on track with the schedule. However, we will do our best to give you the info you need to succeed.
</details>
<p/>
<details>
<summary><b> 2️⃣ What other prerequisites are required?</b></summary>
<hr>
<ul>
<li>You will need an enough *real estate* on screen, we will ask you to open a few windows and it does not file mobiles (tablets should be OK)
<li>You will need a GitHub account eventually a google account for the Google Authentication (optional)
<li>You will need an Astra account: don't worry, we'll work through that in the following
<li>As Intermediate level we expect you to know what java and Spring are. 
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
Attending the session is not enough. You need to complete the homeworks detailed below and you will get a nice badge that you can share on linkedin or anywhere else *(open api badge)*
</details>
<p/>
<blockquote>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h3>
<p>It doesn't matter if you join our workshop live or you prefer to work at your own pace,<br />
we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="/slides/slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
<li><a href="https://www.twitch.tv/datastaxdevs" target="_blank">Twitch backup</a></li>
</ul>
<hr />
<h2><a class="anchor" aria-hidden="true" id="1-database-initialization"> </a>1. Database Initialization</h2>
<h3><a class="anchor" aria-hidden="true" id="1-1-create-an-astra-account"> </a>1.1 - Create an Astra Account</h3>
<blockquote>
<p><strong>Note</strong>: <strong>Datastax Astra</strong> is a cloud-native, fully managed database-as-a-service (DBaaS) based on Apache Cassandra. It provides a scalable, performant and highly available database solution without the operational overhead of managing Cassandra clusters. Astra supports both SQL and NoSQL APIs, and includes features like backup and restore, monitoring and alerting, and access control. It enables developers to focus on application development while the database infrastructure is managed by Datastax.</p>
</blockquote>
<ul>
<li><code>✅ 1.1.a</code> - Access <a href="https://astra.datastax.com" target="_blank">https://astra.datastax.com</a> and register with <code>Google</code> or <code>Github</code> account</li>
</ul>
<p><img src="https://github.com/DataStax-Academy/cassandra-for-data-engineers/blob/main/images/setup-astra-1.png?raw=true" alt="" /></p>
<h3><a class="anchor" aria-hidden="true" id="1-2-create-an-astra-token"> </a>1.2 - Create an Astra Token</h3>
<ul>
<li>
<p><code>✅ 1.2.a</code> Locate <code>Settings</code> (#1) in the menu on the left, then <code>Token Management</code> (#2)</p>
</li>
<li>
<p><code>✅ 1.2.b</code>Select the role <code>Organization Administrator</code> before clicking <code>[Generate Token]</code></p>
</li>
</ul>
<p><img src="https://github.com/DataStax-Academy/cassandra-for-data-engineers/blob/main/images/setup-astra-2.png?raw=true" alt="" /></p>
<ul>
<li><code>✅ 1.2.c</code> - Copy your token in the clipboard. With this token we will now create what is needed for the training.</li>
</ul>
<p><img src="https://github.com/DataStax-Academy/cassandra-for-data-engineers/blob/main/images/setup-astra-3.png?raw=true" alt="" /></p>
<h3><a class="anchor" aria-hidden="true" id="1-3-open-your-environment"> </a>1.3 - Open your Environment</h3>
<blockquote>
<p><strong>Note</strong>: <strong>Gitpod</strong> is a cloud-based integrated development environment (IDE) that allows developers to build, test and run applications directly in their web browser. It provides preconfigured dev environments for GitHub projects, so developers can start coding immediately without setting up local environment. Gitpod saves time and streamlines the development process.</p>
</blockquote>
<blockquote>
<p><code>✅ 1.3.a</code> ↗️ <em>Right Click and select open as a new Tab...</em></p>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-betterreads" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="1-4-setup-astra-cli"> </a>1.4 - Setup Astra CLI</h3>
<blockquote>
<p><strong>Note</strong>:  The <strong>Astra CLI</strong> is a command-line interface (CLI) tool for managing Apache Cassandra databases hosted on Datastax Astra. It allows developers to perform tasks like creating and managing databases, executing Cassandra queries, and managing security and access control. The Astra CLI simplifies database management and provides an alternative to the Astra web interface, enabling automation and integration with other tools and workflows.</p>
</blockquote>
<ul>
<li><code>✅ 1.4.a</code> <strong>Locate the terminal called <code>setup</code> and check that the CLI is available</strong></li>
</ul>
<pre><code>astra --version
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>$ astra --version
0.2.1
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.4.b</code> <strong>Trigger the setup command</strong></li>
</ul>
<pre><code>astra setup
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>    _____            __                  
   /  _  \   _______/  |_____________    
  /  /_\  \ /  ___/\   __\_  __ \__  \  
 /    |    \\___ \  |  |  |  | \// __ \_ 
 \____|__  /____  &gt; |__|  |__|  (____  /
         \/     \/                   \/ 
           Version: 0.2.1

 -----------------------
 ---      SETUP      ---
 -----------------------

$ Enter an Astra token:
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.4.c</code> <strong>Provide your token as asked (starting witg AstraCS:..)</strong></li>
</ul>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>[OK]    Configuration has been saved.
[OK]    Enter 'astra help' to list available commands.
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.4.d</code> <strong>List your existing Users.</strong></li>
</ul>
<pre lang="bash"><code>astra user list
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>+--------------------------------------+-----------------------------+---------------------+
| User Id                              | User Email                  | Status              |
+--------------------------------------+-----------------------------+---------------------+
| b665658a-ae6a-4f30-a740-2342a7fb469c | cedrick.lunven@datastax.com | active              |
+--------------------------------------+-----------------------------+---------------------+
</code></pre>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="1-5-create-database"> </a>1.5 - Create database</h3>
<ul>
<li><code>✅ 1.5.a</code> <strong>Create database <code>workshops</code> with keyspace <code>better_reads</code></strong></li>
</ul>
<pre lang="bash"><code>astra db create workshops -k better_reads --if-not-exist
</code></pre>
<blockquote>
<p>🖥️ <code>Output</code></p>
<pre><code>[ INFO ] - Database 'workshops' already exist. Connecting to database.
[ INFO ] - Database 'workshops' has status 'MAINTENANCE' waiting to be 'ACTIVE' ...
[ INFO ] - Database 'workshops' has status 'ACTIVE' (took 7983 millis)
</code></pre>
</blockquote>
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
<td><code>-k better_reads</code></td>
<td>Name of the keyspace, a db can contains multiple keyspaces</td>
</tr>
<tr>
<td><code>--if-not-exist</code></td>
<td>Flag for itempotency creating only what if needed</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>Note</strong>: If the database already exist but has not been used for while the status will be <code>HIBERNATED</code>. The previous command will resume the db an create the new keyspace but it can take about a minute to execute.</p>
<pre><code>[OK]    Resuming Database 'com.dtsx.astra.sdk.db.domain.Database@406005b3' ...
[INFO]  Database 'workshops' has status 'RESUMING' waiting to be 'ACTIVE' ...
[INFO]  Database 'workshops' has status 'ACTIVE' (took 41466 millis)
[INFO]  Keyspace  'workshops' already exists. Connecting to keyspace.
[OK]    Database 'workshops' is ready.
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.5.b</code> <strong>Check the status of database <code>workshops</code></strong></li>
</ul>
<pre lang="bash"><code>astra db status workshops
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>[ INFO ] - Database 'workshops' has status 'ACTIVE'
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.5.c</code> <strong>Get the informations for your database including the keyspace list</strong></li>
</ul>
<pre lang="bash"><code>astra db get workshops
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>+------------------------+-----------------------------------------+
| Attribute              | Value                                   |
+------------------------+-----------------------------------------+
| Name                   | workshops                               |
| id                     | 906ef2f2-07d0-472c-add6-fe719cf61d02    |
| Status                 | ACTIVE                                  |
| Default Cloud Provider | GCP                                     |
| Default Region         | us-east1                                |
| Default Keyspace       | better_reads                            |
| Creation Time          | 2023-02-20T12:06:21Z                    |
|                        |                                         |
| Keyspaces              | [0] better_reads                        |
|                        |                                         |
| Regions                | [0] us-east1                            |
+------------------------+-----------------------------------------+
</code></pre>
</blockquote>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h3><a class="anchor" aria-hidden="true" id="1-6-create-schema"> </a>1.6 - Create Schema</h3>
<ul>
<li><code>✅ 1.6.a</code> <strong>Check tables list leveraging <code>cqlsh</code></strong></li>
</ul>
<pre lang="bash"><code>astra db cqlsh workshops -k better_reads -e &quot;describe tables;&quot;
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>[INFO]  Downloading Cqlshell, please wait...
[INFO]  Installing  archive, please wait...
[INFO]  Secure connect bundles have been downloaded.
[INFO]  Cqlsh is starting, please wait for connection establishment...

&lt;empty&gt;
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.6.b</code> <strong>Create tables</strong></li>
</ul>
<pre lang="bash"><code>astra db cqlsh workshops \
   -k better_reads \
   -f /workspace/workshop-betterreads/dataset/schema-ddl.cql
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>[INFO] Secure connect bundles have been downloaded.
[INFO] Cqlsh is starting, please wait for connection establishment...
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.6.c</code> <strong>List tables</strong></li>
</ul>
<pre lang="bash"><code>astra db cqlsh workshops -k better_reads -e &quot;describe tables;&quot;
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>[INFO] Secure connect bundles have been downloaded.
[INFO] Cqlsh is starting, please wait for connection establishment...

author_by_id  book_by_id  book_by_user_and_bookid  books_by_user
</code></pre>
</blockquote>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h3><a class="anchor" aria-hidden="true" id="1-7-load-data"> </a>1.7 - Load Data</h3>
<ul>
<li><code>✅ 1.7.a</code> <strong>Show content of the CSV File</strong></li>
</ul>
<pre><code>head -n 10 /workspace/workshop-betterreads/dataset/book_by_id_0.csv 
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>id,author_id,author_names,book_description,book_name,cover_ids,published_date
OL10000049W,&quot;[\&quot;OL3964979A\&quot;]&quot;,&quot;[]&quot;,,&quot;Le crime organise/quatre films exemplaires&quot;,&quot;[\&quot;3140091\&quot;]&quot;,2009-12-11
OL10000394W,&quot;[\&quot;OL3965434A\&quot;]&quot;,&quot;[]&quot;,,&quot;Portraits of Illusions&quot;,&quot;[\&quot;3140733\&quot;]&quot;,2009-12-11
OL10000415W,&quot;[\&quot;OL3965461A\&quot;]&quot;,&quot;[]&quot;,,&quot;Le Berceau du monde&quot;,&quot;[\&quot;3140790\&quot;]&quot;,2009-12-11
OL10000427W,&quot;[\&quot;OL3965478A\&quot;]&quot;,&quot;[]&quot;,,&quot;La fracture identitaire&quot;,&quot;[]&quot;,2009-12-11
OL10000471W,&quot;[\&quot;OL3965508A\&quot;]&quot;,&quot;[]&quot;,,&quot;Jamiroquaï de A à Z&quot;,&quot;[\&quot;3140910\&quot;]&quot;,2009-12-11
OL10001081W,&quot;[\&quot;OL3966201A\&quot;]&quot;,&quot;[]&quot;,,&quot;Contes soufis, tome 1&quot;,&quot;[\&quot;3142335\&quot;]&quot;,2009-12-11
OL10001150W,&quot;[\&quot;OL3966289A\&quot;]&quot;,&quot;[]&quot;,,&quot;Le prix de la terre&quot;,&quot;[\&quot;3142514\&quot;]&quot;,2009-12-11
OL10001271W,&quot;[\&quot;OL3966392A\&quot;]&quot;,&quot;[]&quot;,,&quot;Balzac&quot;,&quot;[\&quot;3142712\&quot;]&quot;,2009-12-11
OL10001538W,&quot;[\&quot;OL3966709A\&quot;]&quot;,&quot;[]&quot;,,&quot;D'affectueuses révérences&quot;,&quot;[]&quot;,2009-12-11
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.7.b</code> <strong>Check how many rows. It should have more than 250k</strong></li>
</ul>
<pre><code>wc -l /workspace/workshop-betterreads/dataset/book_by_id_0.csv
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>250437 ./dataset/book_by_id_0.csv
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.7.c</code> <strong>Populate table <code>book_by_id</code> from the csv <code>book_by_id_0</code></strong></li>
</ul>
<pre><code>astra db load workshops \
     -k better_reads \
     -t book_by_id \
     -maxErrors -1 \
     -url /workspace/workshop-betterreads/dataset/book_by_id_0.csv
</code></pre>
<ul>
<li>The batch is running and should be able to see the throughput at ~3k records per second.</li>
</ul>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>[INFO]  Downloading Dsbulk, please wait...
[INFO]  Installing  archive, please wait...
[INFO] Secure connect bundles have been downloaded.
[INFO] RUNNING: dsbulk load -u token -p xxxxb -b /yyy1.zip -k better_reads -t book_by_id -logDir ./logs --log.verbosity normal --schema.allowMissingFields true -maxConcurrentQueries AUTO -delim , -url ./dataset/book_by_id_0.csv -header true -encoding UTF-8 -skipRecords 0 -maxErrors -1
[INFO] DSBulk is starting please wait ...
Username and password provided but auth provider not specified, inferring PlainTextAuthProvider
A cloud secure connect bundle was provided: ignoring all explicit contact points.
A cloud secure connect bundle was provided and selected operation performs writes: changing default consistency level to LOCAL_QUORUM.
...
 total | failed | rows/s |  p50ms |  p99ms | p999ms | batches
18,944 |      0 |  1,706 | 107.08 | 134.22 | 182.45 |    1.00
...
</code></pre>
</blockquote>
<ul>
<li>The operation should take about 1 minute to complete. The file can have some errors like invalid title with special characters. IT IS NOT A PROBLEM the dataset is not perfect we will have some failed rows.</li>
</ul>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code> total | failed | rows/s | p50ms | p99ms | p999ms | batches
250,000 |    183 |  3,684 | 21.44 | 56.10 |  66.32 |    1.00
Operation LOAD_20220214-185449-001328 completed with 183 &gt; errors in 1 minute and 7 seconds.
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.7.d</code> <strong>Populate table <code>book_by_id</code> from the csv <code>book_by_id_1</code></strong></li>
</ul>
<pre><code>astra db load workshops \
     -k better_reads \
     -t book_by_id \
     -maxErrors -1 \
     -url /workspace/workshop-betterreads/dataset/book_by_id_1.csv
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code> total | failed | rows/s |  p50ms |  p99ms | p999ms | batches
250,000 |    138 |  1,787 | 106.92 | 136.31 | 398.46 |    1.00
Operation LOAD_20230220-153154-071483 completed with 138 errors in 2 minutes and 19 seconds.
</code></pre>
</blockquote>
<ul>
<li><code>✅ 1.7.e</code> <strong>Count Records in the table <code>book_by_id</code></strong></li>
</ul>
<pre><code>astra db count workshops \
     -k better_reads \
     -t book_by_id
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>Picked up JAVA_TOOL_OPTIONS:  -Xmx2576m
 total | failed | rows/s |  p50ms |    p99ms |   p999ms
499,679 |      0 | 57,806 | 210.15 | 6,207.57 | 6,207.57
</code></pre>
</blockquote>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="2-application-implementation"> </a>2. Application Implementation</h2>
<h3><a class="anchor" aria-hidden="true" id="2-1-configuration"> </a>2.1 - Configuration</h3>
<ul>
<li><code>✅ 2.1.a</code> <strong>Generate <code>.env</code> file</strong></li>
</ul>
<pre><code>cd /workspace/workshop-betterreads/better-reads-webapp
astra db create-dotenv workshops -k better_reads
cat .env
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<p><em>Values have been omitted in this guide for security reason</em></p>
<pre><code>ASTRA_DB_APPLICATION_TOKEN=...
ASTRA_DB_GRAPHQL_URL=...
ASTRA_DB_GRAPHQL_URL_ADMIN=...
ASTRA_DB_GRAPHQL_URL_PLAYGROUND=...
ASTRA_DB_GRAPHQL_URL_SCHEMA=...
ASTRA_DB_ID=...
ASTRA_DB_KEYSPACE=&quot;better_reads&quot;
ASTRA_DB_REGION=&quot;us-east1&quot;
ASTRA_DB_REST_URL=...
ASTRA_DB_REST_URL_SWAGGER=...
ASTRA_DB_SECURE_BUNDLE_PATH=...
ASTRA_DB_SECURE_BUNDLE_URL=...
ASTRA_ORG_ID=...
ASTRA_ORG_NAME=...
ASTRA_ORG_TOKEN=...
</code></pre>
</blockquote>
<ul>
<li><code>✅ 2.1.b</code> <strong>Load <code>.env</code> as environment variables</strong></li>
</ul>
<pre><code>set -a
source .env
set +a
env | grep ASTRA_DB_
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<p><em>Values have been omitted in this guide for security reason</em></p>
<pre><code>ASTRA_DB_APPLICATION_TOKEN=...
ASTRA_DB_GRAPHQL_URL=...
ASTRA_DB_GRAPHQL_URL_ADMIN=...
ASTRA_DB_GRAPHQL_URL_PLAYGROUND=...
ASTRA_DB_GRAPHQL_URL_SCHEMA=...
ASTRA_DB_ID=...
ASTRA_DB_KEYSPACE=&quot;better_reads&quot;
ASTRA_DB_REGION=&quot;us-east1&quot;
ASTRA_DB_REST_URL=...
ASTRA_DB_REST_URL_SWAGGER=...
ASTRA_DB_SECURE_BUNDLE_PATH=...
ASTRA_DB_SECURE_BUNDLE_URL=...
</code></pre>
</blockquote>
<ul>
<li>
<p><code>✅ 2.1.c</code> <strong>Open configuration file</strong></p>
</li>
<li>
<p>Open project configuration</p>
</li>
</ul>
<pre><code>gp open /workspace/workshop-betterreads/better-reads-webapp/pom.xml
</code></pre>
<ul>
<li>Locate the declaration of the <code>spring-boot-starter</code></li>
</ul>
<pre lang="xml"><code>&lt;dependency&gt;
  &lt;groupId&gt;com.datastax.astra&lt;/groupId&gt;
  &lt;artifactId&gt;astra-spring-boot-starter&lt;/artifactId&gt;
  &lt;version&gt;${astra-sdk.version}&lt;/version&gt;
&lt;/dependency&gt;
</code></pre>
<ul>
<li><code>✅ 2.1.d</code> <strong>Study <code>application.yaml</code> file</strong></li>
</ul>
<pre><code>gp open /workspace/workshop-betterreads/better-reads-webapp/src/main/resources/application.yml
</code></pre>
<ul>
<li>Notice how the variables are used</li>
</ul>
<pre lang="yaml"><code>astra:
  api:
    application-token: ${ASTRA_ORG_TOKEN}
    database-id: ${ASTRA_DB_ID}
    database-region: ${ASTRA_DB_REGION}
</code></pre>
<ul>
<li>We could have let Spring Data generate the tables for us based on the entities but it is a bad practice</li>
</ul>
<pre lang="yaml"><code>spring:
  application:
    name: betterreads
  data:
    cassandra:
      schema-action: create-if-not-exists
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="2-2-start-application-and-first-use"> </a>2.2 - Start Application and first use</h3>
<ul>
<li>
<p><code>✅ 2.2.a</code> <strong>Known the URL of the application</strong></p>
</li>
<li>
<p>It would be handy to know the URL of the application</p>
</li>
</ul>
<pre><code>gp url 8080
</code></pre>
<ul>
<li><code>✅ 2.2.b</code> <strong>Start the Application</strong></li>
</ul>
<pre><code>cd /workspace/workshop-betterreads/better-reads-webapp
mvn spring-boot:run
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>BetterReads with Spring Boot, String Data, Spring NVC, Spring security
An application by JabaBrains.
The application will start at http://localhost:8080
13:37:20.276 INFO  com.datastax.astra.sdk.AstraClient              : Setup of AstraClient from application.yml
13:37:20.280 INFO  com.datastax.astra.sdk.config.AstraClientConfig : Initializing [AstraClient]
13:37:20.459 INFO  com.datastax.astra.sdk.AstraClient              : + API(s) Devops     [ENABLED]
13:37:20.459 INFO  com.datastax.astra.sdk.AstraClient              : + Db: id &gt; [3ed83de7-d97f-4fb6-bf9f-82e9f7eafa23] and region [eu-west-1]
13:37:20.460 INFO  com.datastax.astra.sdk.AstraClient              : + Downloading bundles in: [/home/gitpod/.astra]
13:37:21.124 INFO  com.datastax.astra.sdk.databases.DatabaseClient : + SecureBundle found : scb_3ed83de7-d97f-4fb6-bf9f-82e9f7eafa23_eu-west-1.zip
13:37:21.124 INFO  com.datastax.astra.sdk.databases.DatabaseClient : + SecureBundle found : scb_3ed83de7-d97f-4fb6-bf9f-82e9f7eafa23_eu-central-1.zip
13:37:23.041 INFO  com.datastax.astra.sdk.AstraClient              : [AstraClient] has been initialized.
</code></pre>
</blockquote>
<p>A new tab should have opened in your browser. You can also open a new terminal and enter the command.</p>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/new_terminal.png?raw=true" alt="new_terminal" /></p>
<pre><code>gp preview $(gp url 8080)
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/app1.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.2.c</code>- <strong>Show Book details</strong></li>
</ul>
<p>In the search item look for <code>Glimpses of ancient Sowams</code> you can search to whatever you want it will request open library ut during this workshop you only imported a subset of books, let us pick one you imported.</p>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/app2.png?raw=true" alt="new_terminal" /></p>
<p>Select the first item, if you select the second you will hit the page book not found as this book is not in the DB.</p>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/app3.png?raw=true" alt="new_terminal" /></p>
<p>This is only what we can do at this point. To mark the book as read we will need to authenticate with <code>Google</code> or <code>Github</code>.</p>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h3><a class="anchor" aria-hidden="true" id="2-3-setup-authentication-for-google"> </a>2.3 - Setup Authentication for Google</h3>
<ul>
<li>
<p><code>✅ 2.3.a</code> - Connect to <a href="https://console.cloud.google.com" target="_blank">Google Cloud Platform</a></p>
</li>
<li>
<p><code>✅ 2.3.b</code> - Create a new project if needed, on the screens i put <code>BetterReadsDemoApps</code> and click <code>[CREATE]]</code></p>
</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp1.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.c</code> - Select <code>Api and Services</code> on the project home page</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp_welcome.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.c</code> - Select <code>[ENABLE APIS AND SERVICES]</code> in menu</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp2.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.d</code> - Search for <code>Gmail Apis</code> and add them to your project.</li>
</ul>
<p><strong>Look For API</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gmail_2.png?raw=true" alt="new_terminal" /></p>
<p><strong>Select API</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp3.png?raw=true" alt="new_terminal" /></p>
<p><strong>Output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gmail_3.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.e</code> - Search for <code>Google Analytics Apis</code> and add them to your project.</li>
</ul>
<p><strong>Look For API</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/googleanalytics_1.png?raw=true" alt="new_terminal" /></p>
<p><strong>Select API</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp4.png?raw=true" alt="new_terminal" /></p>
<p><strong>Output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/googleanalytics_2.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.f</code> - Check <code>External</code> (or internal as you prefer to limit scope). Then select <code>CREATE</code></li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp6.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.g</code> - Select <code>[OAuth consent screen]</code> in the menu on the left. Provide your application name, a support email and the application logo. Go to the bottom of the page and also provide an email. You can then <code>[Save and continue]</code>.</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcpoauth1.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.h</code> - On menu in the left select <em>Credentials</em> and use the button on top <code>[CREATE CREDENTIALS]</code>/ OAuth ClientID.</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp7.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.i</code> - Select <code>Web Application</code> and provide it a name</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp8.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.j</code> - For <code>Authorized JavaScript origins</code> use the output of :</li>
</ul>
<pre><code>gp url 8080
</code></pre>
<ul>
<li><code>✅ 2.3.k</code> - For <code>Authorized redirect URIs</code> use the output  and then <code>[Create]</code></li>
</ul>
<pre><code>echo $(gp url 8080)/login/oauth2/code/google | sed -r  &quot;s/https/http/&quot;
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp9.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.l</code> - A new page will open with your <code>clientId</code> and <code>client Secret</code>. Make sure you copy them locally you will need to setup your application with it.</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp10.png?raw=true" alt="new_terminal" /></p>
<pre><code>You are now doomed we will now mine cryptos with your google account.

Just kidding ^_^
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/gcp11.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.3.m</code> - Open file <code>src/main/resources/application.yml</code> in your project</li>
</ul>
<pre><code>gp open /workspace/workshop-betterreads/better-reads-webapp/src/main/resources/application.yml
</code></pre>
<ul>
<li><code>✅ 2.3.n</code> - Changes keys <code>client-id</code> and <code>client-secret</code> with your values for the provider <code>Google</code>.</li>
</ul>
<pre lang="yaml"><code>  security:
    oauth2:
      client:
        registration:
          google:
            client-id: change
            client-secret: change
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="2-4-setup-authentication-for-github"> </a>2.4 - Setup Authentication for Github</h3>
<p>As each attendee has a different URL in gitpod, you will have to create your own github `OAuth Apps - Let's do this together. For github settings we will have to enter a callback URL. To know which one enter use the following command</p>
<pre><code>clear
echo $(gp url 8080)/login/oauth2/code/github | sed -r  &quot;s/https/http/&quot; 
</code></pre>
<ul>
<li><code>✅ 2.4.a</code> - Login to your github account and go to <code>Organizations</code></li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/githubapps1.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.4.b</code> - There scroll down to locate the last item of the menu <code>Developer Settings</code> <em>(hopefully you have not as many organizations as me)</em>, There pick <code>OAuth Apps</code> (we are using OAuth)</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/githubapps2.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.4.c</code> - Click button <code>[New OAuth Apps]</code> on the page</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/githubapps3.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.4.d</code> - You will be asked to login again for security reasons, then fill the form to register a new Github App. Thre Register your application</li>
</ul>
<table>
<thead>
<tr>
<th>Name</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Application name</code></td>
<td>The application name shown to user</td>
</tr>
<tr>
<td><code>Homepage URL</code></td>
<td>Can be anything, just the app (gp url 8080)</td>
</tr>
<tr>
<td><code>Authorization Callback URL</code></td>
<td>Call back url the one listed above <code>${homepage}/login/oauth2/code/github</code></td>
</tr>
</tbody>
</table>
<ul>
<li><code>✅ 2.4.e</code> - Click <code>[Register Application]</code></li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/githubapps4.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.4.f</code> - The application is created. You got your clientId. You will have to generate a clientSecret now. Once you get both save them on a text file in your machine we will need them later</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/githubapps5.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.4.h</code> - When everything is set you can upload am image for your application and save the change with <code>[Update Application]</code>.</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/githubapps6.png?raw=true" alt="new_terminal" /></p>
<ul>
<li><code>✅ 2.4.i</code> - Open file <code>src/main/resources/application.yml</code> in your project</li>
</ul>
<pre><code>gp open /workspace/workshop-betterreads/better-reads-webapp/src/main/resources/application.yml
</code></pre>
<ul>
<li><code>✅ 2.4.j</code> - Changes keys <code>client-id</code> and <code>client-secret</code> with your values for the provider <code>Github</code>.</li>
</ul>
<pre lang="yaml"><code>  security:
    oauth2:
      client:
        registration:
          github:
            client-id: change
            client-secret: change
</code></pre>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h3><a class="anchor" aria-hidden="true" id="2-5-authenticate-with-oauth2"> </a>2.5 - Authenticate with Oauth2</h3>
<ul>
<li><code>✅ 2.5.a</code> - After setting up the connection you can now start the application again :</li>
</ul>
<pre><code>cd /workspace/workshop-betterreads/better-reads-webapp
mvn spring-boot:run
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-2-5-b-code-authenticate-with-github"> </a><code>✅ 2.5.b</code> - Authenticate with Github</h4>
<ul>
<li>On homepage click on <code>Authenticate with Github</code></li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/githubapps7.png?raw=true" alt="new_terminal" /></p>
<ul>
<li>Eventually you get the SSO screen for you organization</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/githubapps8.png?raw=true" alt="new_terminal" /></p>
<ul>
<li>Then you authorize the application again</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/githubapps9.png?raw=true" alt="new_terminal" /></p>
<pre><code>HAHAHA EVIL LAUGH 

YOU ARE DOOMED AGAIN WE ALSO HAVE YOUR GITHUB ACCOUNT NOW
WE WILL FEED OUR TROLLS AND CODEX.AI WITH IT.
</code></pre>
<ul>
<li>More seriously, Your are in !</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/githubapps10.png?raw=true" alt="new_terminal" /></p>
<h4><a class="anchor" aria-hidden="true" id="code-2-5-c-code-authenticate-with-github"> </a><code>✅ 2.5.c</code> Authenticate with Github</h4>
<ul>
<li>Use the button <code>[Login via Google]</code></li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/google1.png?raw=true" alt="new_terminal" /></p>
<ul>
<li>Validate with the familiar Google Screen</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/google2.png?raw=true" alt="new_terminal" /></p>
<ul>
<li>You are in !</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-betterreads/blob/master/img/google3.png?raw=true" alt="new_terminal" /></p>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="homeworks"> </a>Homeworks</h2>
<img src="https://github.com/datastaxdevs/workshop-betterreads/raw/master/img/badge.png?raw=true" width="200" align="right" />
<p>Don't forget to complete your assignment and get your verified skill badge! Finish and submit your homework!</p>
<ol>
<li>
<p>Complete the practice steps as described below until you have your own app running in Gitpod. (up to step 11)</p>
</li>
<li>
<p>Answer the technical questions in the form (We promise, it is NOT difficult if you follow the workshop).</p>
</li>
<li>
<p>Take a screenshot of you authenticated in the app with a few books</p>
</li>
<li>
<p>Submit your homework <a href="https://dtsx.io/homework-betterreads" target="_blank">here</a></p>
</li>
<li>
<p><em>(totally optional)</em> Watch the full course on Javabrains.io</p>
</li>
</ol>
<ul>
<li><a href="https://www.youtube.com/watch?v=LxVGFBRpEFM" target="_blank">01 - Introduction to the series</a></li>
<li><a href="https://www.youtube.com/watch?v=HAiCwq4jfn8" target="_blank">02 - About the app</a></li>
<li><a href="https://www.youtube.com/watch?v=SnQXdvFkq4U" target="_blank">03 - System Design</a></li>
<li><a href="https://www.youtube.com/watch?v=106jIBE9XSc" target="_blank">04 - Cassandra Schema</a></li>
<li><a href="https://www.youtube.com/watch?v=waLSHx-VN08" target="_blank">05 - Setting up hosted</a></li>
<li><a href="https://www.youtube.com/watch?v=d28t_QySyzs" target="_blank">06 - Creating the Data Loader</a></li>
<li><a href="https://www.youtube.com/watch?v=7I37-awpaGg" target="_blank">07 - Connecting Spring Boot app to DataStax Astra</a></li>
<li><a href="https://www.youtube.com/watch?v=uezZIPK8kPk" target="_blank">08 - Using Repository pattern with Spring Data</a></li>
<li><a href="https://www.youtube.com/watch?v=24NrLl8EhDM" target="_blank">09 - Saving all the authors in the world to Cassandra</a></li>
<li><a href="https://www.youtube.com/watch?v=Fm-XrOTgOto" target="_blank">10 - Setting up books by ID </a></li>
<li><a href="https://www.youtube.com/watch?v=nwyf_4aSkqM" target="_blank">11 - Starting with Spring boot and security</a></li>
<li><a href="https://www.youtube.com/watch?v=-IuafzgS3fU" target="_blank">12 - Implementing the Book view flow</a></li>
<li><a href="https://www.youtube.com/watch?v=6K0im9vcoCk" target="_blank">13 - Building book search feature</a></li>
<li><a href="https://www.youtube.com/watch?v=NEZGCpN1J6M" target="_blank">14 - Tracking user interactions with books</a></li>
<li><a href="https://www.youtube.com/watch?v=ZIGImCqRr1I" target="_blank">15 - Building the My Books feature</a></li>
<li><a href="https://www.youtube.com/watch?v=hJLtsn2aSr4" target="_blank">16 - Wrapping Up</a></li>
</ul>
<hr />

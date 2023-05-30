<h1><a class="anchor" aria-hidden="true" id="graph-streaming-with-astra-and-quine"> </a>🎓 Graph Streaming with Astra and Quine</h1>
<p>Welcome to the real-time graph ETL for modern data pipelines with <strong>Quine and Apache Cassandra</strong> workshop! In this two-hour workshop, we show how to combine a scalable database, <code>Apache Cassandra™</code>, with a powerful real-time streaming graph processor, <code>Quine</code>.</p>
<p>⏲️ <strong>Duration :</strong> 2 hours</p>
<p>🎓 <strong>Level :</strong> Intermediate</p>
<p><img src="https://github.com/datastaxdevs/workshop-streaming-graph-quine/raw/master/data/img/splash.png" alt="" /></p>
<p>Using <strong>Astra DB</strong>, the cloud-based <em>Cassandra-as-a-Service</em> platform delivered by DataStax, we will cover the very first steps for every developer who wants to try to learn a new database: creating tables and CRUD operations.</p>
<p>Quine, from the team at thatDot, is a real-time streaming graph interpreter. A server-side program that consumes data, builds a graph structure, and runs live computation on that graph to answer questions or compute results, and then stream them out.</p>
<p>It doesn't matter if you join our workshop live or you prefer to do it at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<blockquote>
<p><a href="#-start-hands-on" target="_blank">🔖 Accessing HANDS-ON</a></p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>📋 Table of contents</h2>
<ol>
<li><a href="#objectives" target="_blank">Objectives</a></li>
<li><a href="#frequently-asked-questions" target="_blank">Frequently asked questions</a></li>
<li><a href="#materials-for-the-session" target="_blank">Materials for the Session</a></li>
<li><a href="#create-your-astra-db-instance" target="_blank">Create your Database</a></li>
<li><a href="#setup-quine" target="_blank">Setup Quine</a></li>
<li><a href="#graph-exploration" target="_blank">Graph Exploration</a></li>
<li><a href="#homework" target="_blank">Homework</a></li>
<li><a href="#whats-next-" target="_blank">What's NEXT</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<p>1️⃣ <strong>Give you an understanding of Quine streaming graph</strong></p>
<p>2️⃣ <strong>Show how to configure Quine to use Cassandra or Astra DB</strong></p>
<p>3️⃣ <strong>Provide an overview of Quine's Architecture</strong></p>
<p>4️⃣ <strong>Have you run a streaming scenario to detect an anomaly in the graph</strong></p>
<p>🚀 <strong>Have fun with an interactive session!</strong></p>
<h2><a class="anchor" aria-hidden="true" id="frequently-asked-questions"> </a>Frequently asked questions</h2>
<p/>
<details>
<summary><b> 1️⃣ Can I run this workshop on my computer?</b></summary>
<hr>
<p>There is nothing preventing you from running the workshop on your own machine. If you do so, you will need the following installed on your local system:
<ol>
<li><b>git</b>
<li><b>Java 11</b>
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
<li>As "Intermediate level" we expect you to know what Java is.  If you don't know what a streaming graph is, or haven't used a graph system before, that's ok...we'll cover that.
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
<summary><b> 4️⃣ Will I get a certificate or badge if I attend this workshop?</b></summary>
<hr>
Attending the session is not enough. You need to complete the homework detailed below and you will get a nice badge that you can share on LinkedIn or anywhere else *(open badge specification)*
</details>
<p/>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to work at your own pace,<br />
we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="./slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">Discord chat</a></li>
<li><a href="https://stackoverflow.com/questions/tagged/cassandra/" target="_blank">Questions and Answers</a></li>
<li><a href="https://www.twitch.tv/datastaxdevs" target="_blank">Twitch backup</a></li>
</ul>
<hr />
<h1><a class="anchor" aria-hidden="true" id="start-hands-on"> </a>🏁 Start Hands-on</h1>
<h2><a class="anchor" aria-hidden="true" id="create-your-astra-db-instance"> </a>Create your Astra DB instance</h2>
<p><em><strong><code>ASTRA DB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, 40M read/write operations and about 80GB storage monthly for free - sufficient to run small production workloads. If you end your credits the databases will pause, no charge</em></p>
<p>Leveraging the <a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/#c-procedure" target="_blank">database creation guide</a>, create a database. <em>Right-Click the button</em> with <em>Open in a new TAB.</em></p>
<p><a href="https://astra.dev/2-16" target="_blank"><img src="data/img/create_astra_db.png?raw=true" /></a></p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Database Name</strong></td>
<td><code>workshops</code></td>
</tr>
<tr>
<td><strong>Keyspace Name</strong></td>
<td><code>quine</code></td>
</tr>
<tr>
<td><strong>Regions</strong></td>
<td>Select <code>GOOGLE CLOUD</code>, then Moncks Corner (us-east1) OR an Area close to you, then a region with no LOCK 🔒 icons, those are the region you can use for free.</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>ℹ️ Note:</strong> If you already have a database <code>workshops</code>, simply add a keyspace <code>quine</code> using the <code>Add Keyspace</code> button on the bottom right hand corner of db dashboard page.</p>
</blockquote>
<p>While the database is being created, you will also get a <strong>Security token</strong>:<br />
save it somewhere safe, as it will be needed later in other workshops (In particular the string starting with <code>AstraCS:...</code>.)</p>
<p>The status will change from <code>Pending</code> to <code>Active</code> when the database is ready, this will only take 2-3 minutes. You will also receive an email when it is ready.</p>
<h4><a class="anchor" aria-hidden="true" id="token"> </a>Token</h4>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="setup-quine"> </a>Setup Quine</h2>
<p>These instructions were written using Java 11.10.  To run Quine locally, follow the steps below.  Or, you can run it in GitPod:</p>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-streaming-graph-quine" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<h3><a class="anchor" aria-hidden="true" id="setup-astra-shell-in-gitpod"> </a>Setup Astra Shell in GitPod</h3>
<p>The Astra Shell tool will be included in the GitPod build.  Once the environment has completed its initial build, you should see the following at the bottom of the terminal:</p>
<pre lang="bash"><code>Open A NEW TERMINAL and run: astra setup
</code></pre>
<p>Open a new terminal by clicking the plus ( + ) icon on the upper-right corner of the current terminal window.  Then run:</p>
<pre lang="bash"><code>astra setup
</code></pre>
<p>You will be prompted to enter (paste) your token.</p>
<pre lang="bash"><code>• Enter your token (starting with AstraCS) :
</code></pre>
<p>Once you it <kbd>enter</kbd>, you should see output similar to below:</p>
<pre><code>[rags@acm.org]
&gt; ASTRA_DB_APPLICATION_TOKEN=AstraCS:AAAAAAAA
&gt;
&gt; [What's NEXT ?]
&gt; You are all set.(configuration is stored in ~/.astrarc) You can now:
&gt;    • Use any command, 'astra help' will get you the list
&gt;    • Try with 'astra db list'
&gt;    • Enter interactive mode using 'astra'
&gt;
&gt; Happy Coding!
</code></pre>
<p>Verify the setup with the following command which should list all the databases:</p>
<pre><code>astra db list
</code></pre>
<p>Open a new terminal window and run Quine by executing:</p>
<pre lang="bash"><code>./start.sh
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="download-quine-local"> </a>Download Quine - Local</h3>
<p>Follow the <a href="https://quine.io/download" target="_blank">Download Quine page</a> to download the JAR. Choose/create a directory for Quine, and copy the JAR to another location:</p>
<pre lang="bash"><code>mkdir -p ~/local/quine
cp quine-1.3.2.jar ~/local/quine/
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="configure-quine-local"> </a>Configure Quine - Local</h3>
<p>Create a <code>quine.conf</code> file inside the quine directory:</p>
<pre lang="bash"><code>cd ~/local/quine
touch quine.conf
</code></pre>
<p>Edit the <code>quine.conf</code> file:</p>
<pre><code>quine.store {
  # store data in an Apache Cassandra instance
  type = cassandra
  # the keyspace to use
  keyspace = quine
  should-create-keyspace = false
  should-create-tables = true
  replication-factor = 3
  write-consistency = LOCAL_QUORUM
  read-consistency = LOCAL_QUORUM
  local-datacenter = ${ASTRA_DB_REGION}
  write-timeout = &quot;10s&quot;
  read-timeout = &quot;10s&quot;
}
datastax-java-driver {
  advanced {
    auth-provider {
      class = PlainTextAuthProvider
      username = &quot;token&quot;
      password = ${ASTRA_DB_APP_TOKEN}&quot;
    }
  }
  basic {
    cloud {
      secure-connect-bundle = &quot;/workspace/workshop-streaming-graph-quine/secure-connect-workshops.zip&quot;
    }
  }
}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="astra-specific-settings"> </a>Astra-Specific Settings:</h4>
<p><code>type = cassandra</code> - If the type is not specified, Quine defaults to use RocksDB.</p>
<p><code>should-create-keyspace = false</code> - Remember keyspaces can only be created in Astra via the dashboard.</p>
<p><code>replication-factor = 3</code> - Defaults to 1 if not set, which will not work with Astra DB.</p>
<p><code>write-consistency = LOCAL_QUORUM</code> - Minimum consistency level required by Astra.</p>
<p><code>read-consistency = LOCAL_QUORUM</code> - Minimum consistency level required by Astra.</p>
<p><code>local-datacenter = &quot;us-east1&quot;</code> - Set your Astra DB cloud region as the local DC.</p>
<p><code>username = &quot;token&quot;</code> - No need to mess with this. Just leave it as the literal word &quot;token.&quot;</p>
<p><code>password</code> - A valid token for an Astra DB cluster.</p>
<p><code>secure-connect-bundle</code> - A valid, local file location of a downloaded Astra secure connect bundle. The driver gets the Astra DB hostname from the secure bundle, so there is no need to specify endpoints separately.</p>
<h3><a class="anchor" aria-hidden="true" id="download-the-recipe-and-sample-data-local"> </a>Download the recipe and sample data - Local</h3>
<p>Download the &quot;Password Spraying&quot; <a href="https://raw.githubusercontent.com/datastaxdevs/workshop-streaming-graph-quine/main/password-spraying-workshop.yml" target="_blank">recipe</a> from Github. Move the resulting YAML file to your <code>quine</code> directory.</p>
<pre lang="bash"><code>mkdir ~/local/quine
cp password-spraying-workshop.yml ~/local/quine/
</code></pre>
<p>Then, download the <a href="https://that.re/attempts" target="_blank">sample data file</a>&quot; and move the JSON file to your <code>quine</code> directory.</p>
<pre lang="bash"><code>mkdir ~/local/quine
cp attempts.json ~/local/quine/
</code></pre>
<p>Alternatively, if you have cloned this repository and are working in the repo directory locally, you can run the <code>get_quine.sh</code> script. If successful, the script will download the latest version of Quine and the sample data for this workshop, and the script will output something similar to what you see below.</p>
<pre lang="shell"><code>❯ ./get_quine.sh

HTTP request sent, awaiting response... 200 OK
Length: 220704180 (210M) [application/octet-stream]
Saving to: ‘quine-1.3.2.jar’

quine-1.3.2.jar        100%[=========================================================&gt;] 210.48M  20.5MB/s    in 22s     

2022-10-06 11:13:39 (9.78 MB/s) - ‘quine-1.3.2.jar’ saved [220704180/220704180]

HTTP request sent, awaiting response... 200 OK
Length: 82243423 (78M) [application/json]
Saving to: ‘attempts.json’

attempts.json          100%[=========================================================&gt;]  78.43M  15.4MB/s    in 5.0s    

2022-10-06 11:13:49 (15.8 MB/s) - ‘attempts.json’ saved [82243423/82243423]
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="starting-quine-local"> </a>Starting Quine - Local</h3>
<p>To run Quine using the Password Spray recipe, invoke the JAR with Java, while passing the <code>quine.conf</code> as a <code>config.file</code> JVM parameter, while also specifying the recipe, like this:</p>
<pre lang="bash"><code>cd ~/local/quine
java -Dconfig.file=quine.conf -jar quine-1.3.2.jar -r password-spraying-workshop.yml --force-config
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="troubleshooting"> </a>Troubleshooting</h3>
<p>If Quine starts correctly, it should produce output similar to below:</p>
<pre lang="bash"><code>2022-06-15 15:11:52,666 WARN [NotFromActor] [s0-io-4] com.datastax.oss.driver.internal.core.cql.CqlRequestHandler - Query '[0 values] CREATE TABLE IF NOT EXISTS journals (quine_id blob,timestamp bigint,data blob,PRIMARY KEY(quine_id,timestamp)) WITH CLUSTERING ORDER BY (timestamp ASC) AND compaction={'class':'TimeWindowCompactionStrategy'}' generated server side warning(s): Ignoring provided values [compaction] as they are not supported for Table Properties (ignored values are: [additional_write_policy, bloom_filter_fp_chance, caching, cdc, compaction, compression, crc_check_chance, dclocal_read_repair_chance, extensions, gc_grace_seconds, id, max_index_interval, memtable_flush_period_in_ms, min_index_interval, nodesync, read_repair, read_repair_chance, speculative_retry])
Graph is ready!
Application state loaded.
Quine app web server available at http://0.0.0.0:8080
</code></pre>
<p>Quine should then start ingesting the data stream automatically, displaying its progress as it moves along.</p>
<p>If the output does not read:</p>
<pre><code>Graph is ready!
Application state loaded.
Quine app web server available at http://locahost:8080
</code></pre>
<p>Then look for exceptions.</p>
<h4><a class="anchor" aria-hidden="true" id="incorrect-database-name"> </a>Incorrect database name</h4>
<p>If you see this error:</p>
<pre lang="bash"><code>Downloading Astra secure connect bundle...
Picked up JAVA_TOOL_OPTIONS:  -Xmx3489m
[WARN ] - Database workshops has not been found
[WARN ] - Database 'workshops' has not been found.
[ERROR] - NOT_FOUND: Database 'workshops' has not been found.
Download of SCB failed!
</code></pre>
<p>...this means that your token is not associated with a database named 'workshops'.  Edit the <code>.env</code> file with the following GitPod command:</p>
<pre lang="bash"><code>gp open .env
</code></pre>
<p>Enter the correct name for your database, and rerun <code>start.sh</code>.</p>
<h4><a class="anchor" aria-hidden="true" id="snapshots-table-fails-to-create"> </a>Snapshots table fails to CREATE</h4>
<p>If you see an error:</p>
<pre><code>com.datastax.oss.driver.api.core.servererrors.InvalidQueryException: Clustering key columns must exactly match columns in CLUSTERING ORDER BY directive
</code></pre>
<p>...this means that one of tables (likely the <code>snapshots</code> table) failed to CREATE properly.  From GitPod, you can fix this by using the Astra Shell.  If your DB name is different from &quot;workshops,&quot; replace it as appropriate.</p>
<pre lang="bash"><code>astra db cqlsh workshops
</code></pre>
<p>Check to ensure the <code>snapshots</code> table exists:</p>
<pre><code>cqlsh&gt; use quine;
cqlsh&gt; desc quine;
</code></pre>
<p>If not, execute this CQL in Astra Shell (or cqlsh if you're running locally) to create it:</p>
<pre><code>CREATE TABLE quine.snapshots (
    quine_id blob,
    timestamp bigint,
    multipart_index int,
    data blob,
    multipart_count int,
    PRIMARY KEY (quine_id, timestamp, multipart_index)
) WITH CLUSTERING ORDER BY (timestamp DESC, multipart_index ASC)
    AND additional_write_policy = '99PERCENTILE'
    AND bloom_filter_fp_chance = 0.01
    AND caching = {'keys': 'ALL', 'rows_per_partition': 'NONE'}
    AND comment = ''
    AND compaction = {'class': 'org.apache.cassandra.db.compaction.UnifiedCompactionStrategy'}
    AND compression = {'chunk_length_in_kb': '64', 'class': 'org.apache.cassandra.io.compress.LZ4Compressor'}
    AND crc_check_chance = 1.0
    AND default_time_to_live = 0
    AND gc_grace_seconds = 864000
    AND max_index_interval = 2048
    AND memtable_flush_period_in_ms = 0
    AND min_index_interval = 128
    AND read_repair = 'BLOCKING'
    AND speculative_retry = '99PERCENTILE';
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="clearing-quine-data"> </a>Clearing Quine Data</h4>
<p>If Quine starts, but you see a message which looks like this:</p>
<pre lang="bash"><code>Standing Query STANDING-1 already exists
Standing Query STANDING-2 already exists
Ingest Stream INGEST-1 already exists
</code></pre>
<p>...that means that you'll need to clear the existing data before proceeding.  You can do this by running the <code>truncate_tables.sh</code> script from within GitPod.</p>
<h4><a class="anchor" aria-hidden="true" id="extra-double-quote-on-standing-2-link"> </a>Extra Double Quote on STANDING-2 Link</h4>
<p>Once you seen the message indicating that an anomaly has been found, you should be able to <kbd>Ctrl</kbd>+click or <kbd>Command</kbd> click to open the Quine Graph Explorer with a query for that pattern match.  However, sometimes the new tab will open and the page load will fail due to an extra double-quote on the end of the query.  Simply click on the query text well, and press <kbd>End</kbd> to go to the end of the line.  If you see a double quote there, <kbd>backspace</kbd> over it.</p>
<h3><a class="anchor" aria-hidden="true" id="quine-graph-explorer"> </a>Quine Graph Explorer</h3>
<p>You can now use Quine's visual graph explorer in a web browser, and create/traverse data with either Gremlin or Cypher: <a href="http://localhost:8080/" target="_blank">http://localhost:8080/</a></p>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="graph-exploration"> </a>Graph Exploration</h2>
<p>The <code>attempts.json</code> contains the pattern for one password spraying attack. Quine will produce an alert in the console when the standing query matches the pattern. The alert will look similar to this:</p>
<pre lang="shell"><code>2022-10-07 09:37:46,255 Standing query `alert` match: {&quot;meta&quot;:{&quot;isPositiveMatch&quot;:true,&quot;resultId&quot;:&quot;7242b979-03c2-2bc3-9879-13661e8359b5&quot;},&quot;data&quot;:{&quot;QuineUILink&quot;:&quot;Password Spraying Attack: http://localhost:8080/#MATCH%20(user)-[:ORIGINATED]-%3E(attempt1%20%7BoutcomeResult:%22FAILURE%22%7D)-[:NEXT]-%3E(attempt2%20%7BoutcomeResult:%22FAILURE%22%7D)-[:NEXT]-%3E(attempt3%20%7BoutcomeResult:%22FAILURE%22%7D)-[:NEXT]-%3E(attempt4%20%7BoutcomeResult:%22FAILURE%22%7D)-[:NEXT]-%3E(attempt5%20%7BoutcomeResult:%22SUCCESS%22%7D)%20WHERE%20id(attempt1)=%22cb73fb14-4686-3913-8cd8-7d4d608b53d5%22%20RETURN%20DISTINCT%20user%2Cattempt1%2Cattempt2%2Cattempt3%2Cattempt4%2Cattempt5&quot;}}
</code></pre>
<p>When the alert arrives, hold down the command key on a MAC and right-click the link to open Quine.</p>
<p>You should be able to arrange the graph in your browser into a shape similar to this:</p>
<p><img src="https://github.com/datastaxdevs/workshop-streaming-graph-quine/raw/master/data/img/quine-exploration-ui.png" alt="quine exploration ui" /></p>
<p>Explore the graph using the <a href="https://docs.quine.io/getting-started/exploration-ui.html" target="_blank">Exploration UI</a> to follow the path of the attack in the event stream.</p>
<h2><a class="anchor" aria-hidden="true" id="stopping-quine"> </a>Stopping Quine</h2>
<p>To stop Quine, you can simply hit <kbd>Ctrl</kbd>+<kbd>c</kbd>.  Or, you can run the <code>stop.sh</code> file from a terminal (locally or from within GitPod).</p>
<h2><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h2>
<p>To submit the <strong>homework</strong>,</p>
<ul>
<li>Write a new recipe or extend an existing one and take SCREENSHOT(s).
<ul>
<li>Visit the Quine <a href="https://docs.quine.io/docs.html" target="_blank">documentation</a> site</li>
<li>Go through the Getting Started -&gt; <a href="https://docs.quine.io/getting-started/recipes-tutorial.html" target="_blank">Quine Recipes</a> tutorial</li>
<li>Create a new recipe from scratch, or...</li>
<li>Modify an <a href="https://quine.io/recipes" target="_blank">existing recipe</a> to do something new</li>
<li>Email the SCREENSHOT(s) of Quine running your recipe in the browser and the recipe YAML file</li>
</ul>
</li>
</ul>
<p>EMAIL:</p>
<pre lang="text"><code>To: aaron.ploetz@datastax.com, michael@thatdot.com
Subject: Quine Homework
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="what-s-next"> </a>What's NEXT ?</h2>
<p>We've just scratched the surface of what you can do using Astra DB, built on Apache Cassandra.<br />
Go take a look at <a href="https://www.datastax.com/dev" target="_blank">DataStax for Developers</a> to see what else is possible.<br />
There's plenty to dig into!</p>
<p>Congratulations: you made to the end of today's workshop.</p>
<p><strong>... and see you at our next workshop!</strong></p>
<blockquote>
<p>Sincerely yours, The DataStax Developers</p>
</blockquote>

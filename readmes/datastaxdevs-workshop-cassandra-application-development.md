<h1><a class="anchor" aria-hidden="true" id="workshop-application-development-with-cassandra"> </a>Workshop - Application Development with Cassandra</h1>
<p>Learn about drivers, connectivity and requests by running a simple API with<br />
Apache Cassandra/Astra DB as its data backend. The steps are available in <em>several languages</em>.</p>
<p>Click here for the workshop <a href="slides/slides.pdf" target="_blank">slide deck</a>.</p>
<h3><a class="anchor" aria-hidden="true" id="pre-requisites"> </a>Pre-requisites</h3>
<p>This workshop, the third in a series, builds on the same example used in the two previous episodes (an IoT application to access temperature measurements collected from a network of sensors).</p>
<p>Besides some knowledge of the <a href="https://www.datastax.com/learn/data-modeling-by-example/sensor-data-model" target="_blank">example domain</a> used in this workshop, it is desirable to have familiarity with the concepts explored in the two previous installments of the series:</p>
<ul>
<li><a href="https://github.com/datastaxdevs/workshop-cassandra-fundamentals" target="_blank">Cassandra Fundamentals</a></li>
<li><a href="https://github.com/datastaxdevs/workshop-cassandra-data-modeling" target="_blank">Data Modeling with Cassandra</a></li>
</ul>
<h4><a class="anchor" aria-hidden="true" id="database-pre-requisites"> </a>Database pre-requisites</h4>
<p>It is assumed in the following that you already have created your <a href="https://github.com/datastaxdevs/workshop-cassandra-fundamentals#4-create-your-astra-db-instance" target="_blank">Astra DB instance</a> as instructed in the first episode, and that you have a valid &quot;DB Administrator&quot; Token.<br />
<strong>Note</strong>: the Token that is created with the database does not have all permissions we need, so you <em>need</em> to manually <a href="https://awesome-astra.github.io/docs/pages/astra/create-token/" target="_blank">create a Token</a> with the higher &quot;DB Administrator&quot; permission and use it in what comes next.</p>
<p><em>In case you haven't your Astra DB yet, go ahead and create it now for free by clicking here:</em></p>
<p><a href="https://astra.dev/yt-01-25-23" target="_blank"><img src="images/create_astra_db_button.png?raw=true" /></a></p>
<blockquote>
<p><em>Tip</em>: call the database <code>workshops</code> and the keyspace <code>sensor_data</code>.</p>
</blockquote>
<p><em>In case you already have a database <code>workshops</code> but no <code>sensor_data</code> keyspace, simply add it using the &quot;Add Keyspace&quot; button on the bottom right hand corner of your DB dashboard: please do so, avoiding the creation of another database with the same name. (Also, on the free tier you have to &quot;Resume&quot; the database if it is &quot;Hibernated&quot; for prolonged inactivity.)</em></p>
<h2><a class="anchor" aria-hidden="true" id="1-setup"> </a>1. Setup</h2>
<h3><a class="anchor" aria-hidden="true" id="astra-db-administrator-token"> </a>Astra DB &quot;Administrator&quot; token</h3>
<p>If you don't have a &quot;DB Administrator&quot; token yet, log in to your Astra DB<br />
and create a token with this role.<br />
To create the token, click on the &quot;...&quot; menu next to your database in the main<br />
Astra dashboard and choose &quot;Generate token&quot;. Then make sure you select the &quot;DB Administrator&quot; role.<br />
<em>Download or note down all components of the token before navigating away:<br />
these will not be shown again.</em><br />
<a href="https://awesome-astra.github.io/docs/pages/astra/create-token/" target="_blank">See here</a><br />
for more on token creation.</p>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show the token creation on screen,
but will then destroy it immediately for security reasons.
</code></pre>
</blockquote>
<p>Mind that, as mentioned already, <em>the default Token auto-created for you when<br />
creating the database is not powerful enough for us today.</em></p>
<h3><a class="anchor" aria-hidden="true" id="gitpod"> </a>Gitpod</h3>
<p>First, open this repo in Gitpod by right-clicking the following button (&quot;open in new tab&quot;):</p>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-cassandra-application-development" target="_blank"><img src="images/open_in_gitpod.svg?raw=true" /></a></p>
<p>In a couple of minutes you will have your Gitpod IDE up and running, with this repo cloned, ready and waiting for you (you may have to authorize the Gitpod single-sign-on to continue).</p>
<blockquote>
<p>You may see a dialog about &quot;opening this workspace in VS Code Desktop&quot;: you can safely dismiss it.</p>
</blockquote>
<p><em>Note</em>: The next steps are to be executed <em>within the Gitpod IDE.</em></p>
<h3><a class="anchor" aria-hidden="true" id="configure-the-astra-cli"> </a>Configure the Astra CLI</h3>
<p>Astra CLI is preinstalled: configure it by providing your<br />
<code>AstraCS:...</code> database token when prompted:</p>
<pre lang="bash"><code>astra setup
</code></pre>
<p>(<em>Optional)</em> Now you can use the CLI to get some info on your database(s):</p>
<pre lang="bash"><code>astra db list
astra db get workshops
</code></pre>
<details><summary>Click here if you have <strong>multiple databases</strong> called "workshops"</summary>
<p>DB names are not required to be unique: what <em>is</em> unique is the <a href="https://awesome-astra.github.io/docs/pages/astra/faq/#where-should-i-find-a-database-identifier" target="_blank">&quot;Database ID&quot;</a>.</p>
<p>In case you find yourself having more than one &quot;workshops&quot; database, you can provide the ID instead of the name to the CLI commands<br />
and, being able to unambiguously determine the target, it will work flawlessly.</p>
</details>
<h3><a class="anchor" aria-hidden="true" id="create-and-populate-tables"> </a>Create and populate tables</h3>
<p>The Astra CLI can also launch a <code>cqlsh</code> session for you, automatically connected to your database. Use this feature to execute a <code>cql</code> script that resets the contents of the <code>sensor_data</code> keyspace, creating the right tables and writing representative data on them:</p>
<pre lang="bash"><code># Make sure the DB exists (resuming it if hibernated)
astra db create workshops -k sensor_data --if-not-exist --wait

# Launch the initialization script
astra db cqlsh workshops -f initialize.cql
</code></pre>
<p>You are encouraged to peek at the contents of the script to see what it does.</p>
<p><em>(Optional)</em> Interactively run some test queries on the newly-populated keyspace</p>
<details><summary>Click to show test queries</summary>
<p>Open an interactive <code>cqlsh</code> shell with:</p>
<pre lang="bash"><code>astra db cqlsh workshops -k sensor_data
</code></pre>
<p>Now you can copy-paste any of the queries below and execute them with the <kbd>Enter</kbd> key:</p>
<pre lang="sql"><code>-- Q1 (note 'all' is the only partition key in this table)
SELECT  name, description, region, num_sensors
FROM    networks
WHERE   bucket = 'all';

-- Q2
SELECT  date_hour, avg_temperature, latitude, longitude, sensor
FROM    temperatures_by_network
WHERE   network    = 'forest-net'
  AND   week       = '2020-07-05'
  AND   date_hour &gt;= '2020-07-05'
  AND   date_hour  &lt; '2020-07-07';

-- Q3
SELECT  *
FROM    sensors_by_network
WHERE   network = 'forest-net';

-- Q4
SELECT  timestamp, value
FROM    temperatures_by_sensor
WHERE   sensor = 's1003'
  AND   date   = '2020-07-06';

</code></pre>
<p>To close <code>cqlsh</code> and get back to the shell prompt, execute the <code>EXIT</code> command.</p>
</details>
<h3><a class="anchor" aria-hidden="true" id="prepare-connection-settings"> </a>Prepare connection settings</h3>
<p>You can use the Astra CLI to prepare a dotenv file which defines all connection<br />
parameters and secrets needed for your application to run:</p>
<pre lang="bash"><code>astra db create-dotenv workshops -k sensor_data
</code></pre>
<p>A <code>.env</code> file will be created (you can peek at it with Gitpod's file editor, e.g. running <code>gp open .env</code>).</p>
<p>You can now source it with:</p>
<pre lang="bash"><code>source .env
</code></pre>
<blockquote>
<p><strong>Note</strong>: The <code>.env</code> is handled differently in each implementation (Java, Python, Javascript), as will be shown later.</p>
<p><strong>Note</strong>: While creating the <code>.env</code>, the database's <a href="https://awesome-astra.github.io/docs/pages/astra/download-scb/" target="_blank">Secure Connect Bundle</a><br />
has also been downloaded for you: you may want to check that the file<br />
is about 12-13 KiB in size with <code>ls $ASTRA_DB_SECURE_BUNDLE_PATH -lh</code>.</p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="2-3-now-to-the-exercises"> </a>2 &amp; 3. Now to the exercises!</h2>
<p><em>Note: it is suggested to check the <a href="https://www.datastax.com/learn/data-modeling-by-example/sensor-data-model" target="_blank">sensor data model</a> in order to be better prepared for what follows. Keep it open in another tab.</em></p>
<p>Choose your path:</p>
<ul>
<li><a href="python/Python_README.md" target="_blank">Python</a></li>
<li><a href="java/Java_README.md" target="_blank">Java</a></li>
<li><a href="javascript/Javascript_README.md" target="_blank">Javascript</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="homework-instructions"> </a>Homework instructions</h2>
<img src="https://github.com/datastaxdevs/workshop-cassandra-application-development/raw/master/images/api-micro.png?raw=true" width="150" align="left" />
<p>In order to get a badge of completion for this workshop, complete the following assignment:</p>
<blockquote>
<p>Add a GET endpoint to your API corresponding to query <code>Q1</code><br />
(<em>&quot;Find information about all networks; order by name (asc)&quot;</em>).<br />
<strong>Tip</strong>: remember the data-modeling optimization of having inserted the <code>bucket</code> column.</p>
</blockquote>
<p>Take a <em>screenshot</em> of the relevant code block and of a successful request to that endpoint and head over to <a href="https://dtsx.io/homework-appdev" target="_blank">this form</a>. Answer a couple of &quot;theory&quot; questions, attach your screenshot, and hit &quot;Submit&quot;.</p>
<p>That's it! Expect to be awarded your badge in the next week or so!</p>
<h2><a class="anchor" aria-hidden="true" id="conclusion"> </a>Conclusion</h2>
<p>This is not the end of your journey, rather the start: come visit us for more cool content, and learn how to succeed using Cassandra and Astra DB in your applications!</p>
<p>Congratulations and see you at our next workshop!</p>
<blockquote>
<p>Sincerely yours, the DataStax Developers</p>
</blockquote>

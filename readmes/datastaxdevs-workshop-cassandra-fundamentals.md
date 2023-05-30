<h1><a class="anchor" aria-hidden="true" id="apache-cassandratm-fundamentals"> </a>🎓 Apache Cassandra™ Fundamentals</h1>
<p>Welcome to the <strong>Apache Cassandra™ Fundamentals</strong> workshop! In this two-hour workshop, we shows the most important fundamentals and basics of the powerful distributed <code>NoSQL database Apache Cassandra™</code>.</p>
<p>Using <strong>Astra DB</strong>, the cloud based <em>Cassandra-as-a-Service</em> platform delivered by DataStax, we will cover the very first steps for every developer who wants to try to learn a new database: creating tables and CRUD operations.</p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-fundamentals/raw/master/images/splash.png" alt="" /></p>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<blockquote>
<p><a href="#-start-hands-on" target="_blank">🔖 Accessing HANDS-ON</a></p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>📋 Table of contents</h2>
<img src="https://github.com/datastaxdevs/workshop-cassandra-fundamentals/blob/main/images/cassandra_fundamentals.png?raw=true" align="right" width="300px"/>
<ol>
<li><a href="#1-objectives" target="_blank">Objectives</a></li>
<li><a href="#2-frequently-asked-questions" target="_blank">Frequently asked questions</a></li>
<li><a href="#3-materials-for-the-session" target="_blank">Materials for the Session</a></li>
<li><a href="#4-create-your-astra-db-instance" target="_blank">Create your Database</a></li>
<li><a href="#5-create-tables" target="_blank">Create tables</a></li>
<li><a href="#6-execute-crud-operations" target="_blank">Execute CRUD operations</a></li>
<li><a href="#7-homework" target="_blank">Homework</a></li>
<li><a href="#8-whats-next-" target="_blank">What's NEXT </a></li>
</ol>
<p><br/>
<h2><a class="anchor" aria-hidden="true" id="1-objectives"> </a>1. Objectives</h2>
<p>1️⃣ <strong>Give you an understanding and how and where to position Apache Cassandra™</strong></p>
<p>2️⃣ <strong>Give an overview of the NoSQL ecosystem and its rationale</strong></p>
<p>3️⃣ <strong>Provide an overview of Cassandra Architecture</strong></p>
<p>4️⃣ <strong>Make you create your first tables and run your first statements</strong></p>
<p>🚀 <strong>Have fun with an interactive session</strong></p>
<h2><a class="anchor" aria-hidden="true" id="2-frequently-asked-questions"> </a>2. Frequently asked questions</h2>
<p/>
<details>
<summary><b> 1️⃣ Can I run this workshop on my computer?</b></summary>
<hr>
<p>There is nothing preventing you from running the workshop on your own machine. If you do so, you will need the following:
<ol>
<li><b>git</b> installed on your local system
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
<h2><a class="anchor" aria-hidden="true" id="3-materials-for-the-session"> </a>3. Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to work at your own pace,<br />
we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="/slides/slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
<li><a href="https://www.twitch.tv/datastaxdevs" target="_blank">Twitch backup</a></li>
</ul>
<hr />
<h1><a class="anchor" aria-hidden="true" id="start-hands-on"> </a>🏁 Start Hands-on</h1>
<h2><a class="anchor" aria-hidden="true" id="4-create-your-astra-db-instance"> </a>4. Create your Astra DB instance</h2>
<p><em><strong><code>ASTRA DB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, 40M read/write operations and about 80GB storage monthly for free - sufficient to run small production workloads. If you end your credits the databases will pause, no charge</em></p>
<p>Leveraging <a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/#c-procedure" target="_blank">Database creation guide</a> create a database. <em>Right-Click the button</em> with <em>Open in a new TAB.</em></p>
<p><a href="https://astra.dev/yt-01-11-23" target="_blank"><img src="images/create_astra_db_button.png?raw=true" /></a></p>
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
<td><code>sensor_data</code></td>
</tr>
<tr>
<td><strong>Regions</strong></td>
<td>Select <code>GOOGLE CLOUD</code>, then an Area close to you, then a region with no LOCKER 🔒 icons, those are the region you can use for free.</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>ℹ️ Note:</strong> If you already have a database <code>workshops</code>, simply add a keyspace <code>sensor_data</code> using the <code>Add Keyspace</code> button on the bottom right hand corner of db dashboard page.</p>
</blockquote>
<p>While the database is being created, you will also get a <strong>Security token</strong>:<br />
save it somewhere safe, as it will be needed to later in other workshop (In particular the string starting with <code>AstraCS:...</code>.)</p>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show the token creation on screen,
but will then destroy it immediately for security reasons.
</code></pre>
</blockquote>
<p>The status will change from <code>Pending</code> to <code>Active</code> when the database is ready, this will only take 2-3 minutes. You will also receive an email when it is ready.</p>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="5-create-tables"> </a>5. Create tables</h2>
<p>Ok, now that you have a database created the next step is to create tables to work with.</p>
<p><em>General Methodology Notes</em>: We'll work with a (rather simplified) <em>Internet of things</em> application where we'll be recording temperatures coming from a network of sensors.</p>
<ul>
<li><code>networks</code> identified by a unique name represent a region, an area where you find related infrastructure.</li>
</ul>
<h4><a class="anchor" aria-hidden="true" id="step-5a-navigate-to-the-cql-console-and-login-to-the-database"> </a>✅ Step 5a. Navigate to the CQL Console and login to the database</h4>
<p>In the Summary screen for your database, select <strong><em>CQL Console</em></strong> from the top menu in the main window. This will take you to the CQL Console and automatically log you in.</p>
<details>
    <summary>Show me! </summary>
    <img src="https://github.com/datastaxdevs/workshop-cassandra-fundamentals/raw/master/images/astra-cql-console.gif" />
</details>
<blockquote>
<p><em>Note</em>: if you are working with your own Cassandra cluster (other than Astra DB), you will reach the CQL Console differently.<br />
Moreover, in that case you have to manually create the keyspace once in the CQL Console: this is done with a command similar to<br />
<code>CREATE KEYSPACE sensor_data WITH REPLICATION = {'class': 'NetworkTopologyStrategy', 'replication_factor': 3};</code>.<br />
See the Cassandra documentation for more details on this.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="step-5b-describe-keyspaces-and-use-one-of-them"> </a>✅ Step 5b. Describe keyspaces and USE one of them</h4>
<p>Ok, now we're ready to rock. Creating tables is quite easy, but before we create one we need to tell the database which keyspace we are working with.</p>
<p>First, let's <strong><em>DESCRIBE</em></strong> all of the keyspaces that are in the database. This will give us a list of the available keyspaces.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>DESC KEYSPACES;
</code></pre>
<p><em>&quot;desc&quot; is short for &quot;describe&quot;, either is valid.</em></p>
<blockquote>
<p>CQL commands usually end with a semicolon <code>;</code>. If you hit Enter and nothing happens -- you don't even get your prompt back -- most likely it's because you have not ended the command with <code>;</code>. If in trouble, you can always get back to the prompt with <code>Ctrl-C</code> and start typing the command anew.</p>
</blockquote>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-fundamentals/raw/master/images/cql/01_desc_keyspaces.png" alt="Keyspaces in CQL" /></p>
<blockquote>
<p>ℹ️ Depending on your setup you might see a different set of keyspaces than in the image. The one we care about for now is <strong><em>sensor_data</em></strong>. From here, execute the <strong><em>USE</em></strong> command with the <strong><em>sensor_data</em></strong> keyspace to tell the database our context is within <strong><em>sensor_data</em></strong>.</p>
</blockquote>
<blockquote>
<p>Take advantage of the TAB-completion in the CQL Console. Try typing <code>use sens</code> and then pressing TAB, for example.</p>
</blockquote>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>USE sensor_data;
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-fundamentals/raw/master/images/cql/02_use_sensor_data.png" alt="USE keyspace" /></p>
<p>Notice how the prompt displays <code>&lt;username&gt;@cqlsh:sensor_data&gt;</code> informing us we are <strong>using</strong> the <strong><em>sensor_data</em></strong> keyspace. Now we are ready to create our tables.</p>
<h4><a class="anchor" aria-hidden="true" id="step-5c-create-the-code-networks-code-table"> </a>✅ Step 5c. Create the <code>networks</code> table</h4>
<p>At this point we can execute a command to create the <strong>networks</strong> table.<br />
Just copy/paste the following command into your CQL console at the prompt.<br />
Try to identify the primary key, the partition key and the clustering columns<br />
(if any) for this table in the command:</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>CREATE TABLE IF NOT EXISTS networks (
  name        TEXT,
  description TEXT,
  region      TEXT,
  PRIMARY KEY ((name))
);
</code></pre>
<p>Then <strong><em>DESCRIBE</em></strong> your keyspace tables to ensure it is there.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>DESC TABLES;
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-fundamentals/raw/master/images/cql/03_networks_table_created.png" alt="A table created" /></p>
<p>Aaaand <strong>BOOM</strong>, you created a table in your database. That's it.<br />
Now let's go ahead and create a couple more tables before we do<br />
something interesting with the data.</p>
<h4><a class="anchor" aria-hidden="true" id="step-5d-create-the-tables-for-code-sensors-code-and-code-temperatures-code"> </a>✅ Step 5d. Create the tables for <code>sensors</code> and <code>temperatures</code></h4>
<ul>
<li>
<p>A network will contain several <code>sensors</code>. Sensors are uniquely identified by their name, such as <code>s1001</code>. The design of our application is such that we need to be able to <em>retrieve all <code>sensors</code> for a given <code>network</code>, sorted by the sensor name</em>.</p>
</li>
<li>
<p>Next, for each sensor you want to be able to retrieve <code>temperatures</code> sorted by descending date.</p>
</li>
</ul>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>CREATE TABLE IF NOT EXISTS sensors_by_network (
  network         TEXT,
  sensor          TEXT,
  latitude        DECIMAL,
  longitude       DECIMAL,
  characteristics MAP&lt;TEXT,TEXT&gt;,
  PRIMARY KEY ((network),sensor)
);

CREATE TABLE IF NOT EXISTS temperatures_by_sensor_bad (
  sensor TEXT,
  timestamp TIMESTAMP,
  value FLOAT,
  PRIMARY KEY ((sensor),timestamp)
) WITH CLUSTERING ORDER BY (timestamp DESC);
</code></pre>
<ul>
<li>
<p><code>networks</code> to <code>sensors</code> is a one-to-many relationship yet there is no integrity constraint. This is on you, at application level to ensure the coherence.</p>
</li>
<li>
<p>You should notice than sensors are grouped by network (as the name stated. The partition key <code>network</code> groups all sensors for a given network on the same Cassandra node meaning a request with network in the where clause will access a single node.</p>
</li>
<li>
<p><code>sensors</code> to <code>temperatures</code> is a also a one-to-many relation. Every temperature for a sensor will be saved in the same partition.</p>
</li>
</ul>
<p/>
<details>
<summary><b>This table has a major issue... can you guess what it is?</b></summary>
<hr>
The SIZE. The more the sensors capture information the bigger the partitions become. There is a good practice rule stating that the upper limit for a partition is 100MB or 100k records. You need to split values across multiple partitions. This technique is called <i>bucketing.</i>
</details>
<p/>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>DROP TABLE  temperatures_by_sensor_bad;

CREATE TABLE temperatures_by_sensor (
  sensor TEXT,
  date DATE,
  timestamp TIMESTAMP,
  value FLOAT,
  PRIMARY KEY ((sensor, date),timestamp)
) WITH CLUSTERING ORDER BY (timestamp DESC);
</code></pre>
<blockquote>
<p>ℹ️ <em>Dropping a table can lead to a timeout in the user interface, do not worry, it is not harmful: the table is effectively deleted under the hood.</em></p>
</blockquote>
<p><strong><em>DESCRIBE</em></strong> your keyspace tables: you should see all three listed.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>DESC TABLES;
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-fundamentals/raw/master/images/cql/04_post_tables_created.png" alt="A table created" /></p>
<p>And tables list:</p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-fundamentals/raw/master/images/cql/04_post_tables_created_2.png" alt="A table created" /></p>
<p>You may wonder, how did we arrive at this particular structure for the <code>sensors_by_network</code> and <code>temperatures_by_sensors</code> tables ?</p>
<p>The answer lies in the methodology for data modeling<br />
with Cassandra, which, at its very core, states: <strong>first look at application's needs, determine the required workflows, then map them to a number of queries, finally design a table around each query</strong>.</p>
<ul>
<li>
<p>We create table <code>sensors_by_network</code> to support a query such as <em>&quot;get all sensors for a network <code>X</code>&quot;</em></p>
</li>
<li>
<p>We create table <code>temperatures_by_sensors</code> to support a query such as <em>&quot;get all temperatures for a sensor <code>Y</code>&quot;</em></p>
</li>
</ul>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="6-execute-crud-operations"> </a>6. Execute CRUD operations</h2>
<p>CRUD stands for &quot;<strong>create, read, update, and delete</strong>&quot;. Simply put, they are the basic types of commands you need to work with ANY database in order to maintain data for your applications.</p>
<h4><a class="anchor" aria-hidden="true" id="step-6a-c-rud-create-insert-data-users"> </a>✅ Step 6a. (C)RUD = create = insert data, users</h4>
<p>Our tables are in place so let's put some data in them. This is done with the <strong>INSERT</strong> statement. We'll start by inserting 2 rows into the <strong><em>networks</em></strong> table.</p>
<p>Copy and paste the following in your CQL Console:<br />
<em>(Once you have carefully examined the first of the following <strong>INSERT</strong> statements below, you can simply copy/paste the others which are very similar.)</em></p>
<p>📘 <strong>Commands to execute</strong></p>
<pre lang="sql"><code>INSERT INTO networks (name,description,region)
VALUES ('forest-net',
        'forest fire detection network',
        'south');

INSERT INTO networks (name,description,region)
VALUES ('volcano-net',
        'volcano monitoring network',
        'north');   
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="step-6b-c-rud-create-insert-data-posts"> </a>✅ Step 6b. (C)RUD = create = insert data, posts</h4>
<p>Let's run some more <strong>INSERT</strong> statements, this time for <strong>sensors</strong>. We'll insert data into the <strong><em>sensors_by_network</em></strong> table.</p>
<p><em>(Once you have carefully examined the first of the following <strong>INSERT</strong> statements below, you can simply copy/paste the others which are very similar.)</em></p>
<blockquote>
<p><em>Note</em>: in the following, we are using <code>MAP&lt;&gt;</code> which lets you define you our key/value mapping, thereby adding a bit of flexibility -- Cassandra Data models are strongly typed.</p>
</blockquote>
<p>📘 <strong>Commands to execute</strong></p>
<pre lang="sql"><code>INSERT INTO sensors_by_network 
(network,sensor,latitude,longitude,characteristics)
VALUES ('forest-net','s1001',30.526503,-95.582815,
       {'accuracy':'medium','sensitivity':'high'});
INSERT INTO sensors_by_network 
(network,sensor,latitude,longitude,characteristics)
VALUES ('forest-net','s1002',30.518650,-95.583585,
       {'accuracy':'medium','sensitivity':'high'});     
INSERT INTO sensors_by_network 
(network,sensor,latitude,longitude,characteristics)
VALUES ('forest-net','s1003',30.515056,-95.556225,
       {'accuracy':'medium','sensitivity':'high'});     
INSERT INTO sensors_by_network 
(network,sensor,latitude,longitude,characteristics)
VALUES ('volcano-net','s2001',44.460321,-110.828151,
       {'accuracy':'high','sensitivity':'medium'});    
INSERT INTO sensors_by_network 
(network,sensor,latitude,longitude,characteristics)
VALUES ('volcano-net','s2002',44.463195,-110.830124,
       {'accuracy':'high','sensitivity':'medium'});    
</code></pre>
<p>Ok, we have a lovely bunch of sensors in our application.</p>
<p>Now let's add temperature measurements in table <strong><em>temperatures_by_sensors</em></strong> as well! Let's do it with the following command (please note that the <code>INSERT</code> statements are similar to the ones seen above, with different columns and table name):</p>
<blockquote>
<p><em>Note</em>: In a relational database you may have use a join on 3 tables <code>Networks &gt; Sensors &gt; Temperatures</code>. In the following, we are putting back the network name in temperature table and this is because it will be required in the where clause.</p>
</blockquote>
<p>📘 <strong>Commands to execute</strong></p>
<pre lang="sql"><code>INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-04','2020-07-04 00:00:01',80);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-04','2020-07-04 00:59:59',79);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-04','2020-07-04 12:00:01',97);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-04','2020-07-04 12:59:59',98);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-04','2020-07-04 00:00:01',82);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-04','2020-07-04 00:59:59',80);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-04','2020-07-04 12:00:01',100);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-04','2020-07-04 12:59:59',100);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-04','2020-07-04 00:00:01',81);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-04','2020-07-04 00:59:59',80);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-04','2020-07-04 12:00:01',99);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-04','2020-07-04 12:59:59',98);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-05','2020-07-05 00:00:01',81);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-05','2020-07-05 00:59:59',80);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-05','2020-07-05 12:00:01',98);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-05','2020-07-05 12:59:59',99);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-05','2020-07-05 00:00:01',82);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-05','2020-07-05 00:59:59',82);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-05','2020-07-05 12:00:01',100);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-05','2020-07-05 12:59:59',99);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-05','2020-07-05 00:00:01',83);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-05','2020-07-05 00:59:59',82);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-05','2020-07-05 12:00:01',101);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-05','2020-07-05 12:59:59',102);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-06','2020-07-06 00:00:01',90);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-06','2020-07-06 00:59:59',90);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-06','2020-07-06 12:00:01',106);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1001','2020-07-06','2020-07-06 12:59:59',107);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-06','2020-07-06 00:00:01',90);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-06','2020-07-06 00:59:59',90);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-06','2020-07-06 12:00:01',108);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-06','2020-07-06 12:59:59',110);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-06','2020-07-06 00:00:01',90);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-06','2020-07-06 00:59:59',90);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-06','2020-07-06 12:00:01',1315);
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1003','2020-07-06','2020-07-06 12:59:59',1429);
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="step-6c-c-r-ud-read-read-data"> </a>✅ Step 6c. C(R)UD = read = read data</h4>
<p>Now that we've inserted a set of rows (two sets, to be precise), let's take a look at how to read the data back out. This is done with a <strong>SELECT</strong> statement. In its simplest form we could just execute a statement like the following <strong><em>**cough</em></strong> <strong><em>**cough</em></strong>:</p>
<pre lang="sql"><code>SELECT * FROM networks;
</code></pre>
<pre><code> name        | description                   | region
-------------+-------------------------------+--------
  forest-net | forest fire detection network |  south
 volcano-net |    volcano monitoring network |  north
</code></pre>
<p>or</p>
<pre lang="sql"><code>SELECT * FROM sensors_by_network;
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<pre><code>token@cqlsh:sensor_data&gt; SELECT * FROM sensors_by_network;

 network     | sensor | characteristics                               | latitude  | longitude
-------------+--------+-----------------------------------------------+-----------+-------------
  forest-net |  s1001 | {'accuracy': 'medium', 'sensitivity': 'high'} | 30.526503 |  -95.582815
  forest-net |  s1002 | {'accuracy': 'medium', 'sensitivity': 'high'} | 30.518650 |  -95.583585
  forest-net |  s1003 | {'accuracy': 'medium', 'sensitivity': 'high'} | 30.515056 |  -95.556225
 volcano-net |  s2001 | {'accuracy': 'high', 'sensitivity': 'medium'} | 44.460321 | -110.828151
 volcano-net |  s2002 | {'accuracy': 'high', 'sensitivity': 'medium'} | 44.463195 | -110.830124
</code></pre>
<p>You may have noticed my coughing fit a moment ago. Even though you can execute a <strong>SELECT</strong> statement with no partition key defined, this is NOT something you should do when using Apache Cassandra. We are doing it here for illustration purposes only and because our whole dataset is just a handful of values.</p>
<p>Given the data we inserted earlier, a more proper statement would be something like (while we are at it, we also explicitly specify which columns we want back):</p>
<pre lang="sql"><code>SELECT sensor, characteristics, latitude, longitude 
FROM sensors_by_network
WHERE network = 'forest-net';
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<pre><code>token@cqlsh:sensor_data&gt; SELECT sensor, characteristics, latitude, longitude
               ... FROM sensors_by_network
               ... WHERE network = 'forest-net';

 sensor | characteristics                               | latitude  | longitude
--------+-----------------------------------------------+-----------+------------
  s1001 | {'accuracy': 'medium', 'sensitivity': 'high'} | 30.526503 | -95.582815
  s1002 | {'accuracy': 'medium', 'sensitivity': 'high'} | 30.518650 | -95.583585
  s1003 | {'accuracy': 'medium', 'sensitivity': 'high'} | 30.515056 | -95.556225
</code></pre>
<p>The key is to ensure we are <strong>always selecting by some partition key</strong> at a minimum, so to avoid the dreaded <em>full-cluster scans</em> which yield performances that are generally unacceptable in production.</p>
<p>Ok, with that out of the way we can <strong>READ</strong> the data from the other table as well - remember we <strong>INSERT</strong>ed on both tables?</p>
<p>📘 <strong>Commands to execute</strong></p>
<pre lang="sql"><code>SELECT * FROM temperatures_by_sensor;

SELECT timestamp, value 
FROM temperatures_by_sensor
WHERE sensor='s1002' 
AND date='2020-07-05';
</code></pre>
<p>(again, in the second <strong>SELECT</strong> we specify some columns - it is something we may want to do in most cases).</p>
<p>📗 <strong>Expected output</strong></p>
<pre><code>token@cqlsh:sensor_data&gt; select timestamp, value from temperatures_by_sensor where sensor='s1002' and DATE='2020-07-05';

 timestamp                       | value
---------------------------------+-------
 2020-07-05 12:59:59.000000+0000 |    99
 2020-07-05 12:00:01.000000+0000 |   100
 2020-07-05 00:59:59.000000+0000 |    82
 2020-07-05 00:00:01.000000+0000 |    82
</code></pre>
<p>Once you execute the above <strong>SELECT</strong> statements you should see something like the expected output above. We have now <strong>READ</strong> the data we <strong>INSERTED</strong> earlier. Awesome job!</p>
<p>📘 <strong>Commands to execute</strong></p>
<pre lang="sql"><code>SELECT * FROM temperatures_by_sensor
WHERE sensor='s1002';
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p>This is a surprise.</p>
<p/>
<details>
<summary><b> Can you explain the error message ?</b></summary>
As you did not provide the full partition key (2 columns) Cassandra needs to perform a full scan of your cluster (request on every node).
<p>It will be bad, it will be ugly, it will be your fault. Always code your applications as if the DBA was a serial killer and he knows your address.</p>
</p>
</details>
<p/>
<h4><a class="anchor" aria-hidden="true" id="step-6d-cr-u-d-update-update-data"> </a>✅ Step 6d. CR(U)D = update = update data</h4>
<p>At this point we've <strong><em>CREATED</em></strong> and <strong><em>READ</em></strong> some data, but what happens when you want to change some existing data to some new value? That's where <strong>UPDATE</strong> comes into play.</p>
<p><em>The use case is as follows: We notice the sensor was not correctly calibrated and the data needs to be updated.</em></p>
<p>Let's take one of the records we created earlier and modify it. Recall that we <strong><em>INSERTED</em></strong> the following record in the <strong><em>temperatures_by_sensors</em></strong> table.</p>
<pre lang="sql"><code>// For reference
INSERT INTO temperatures_by_sensor 
(sensor,date,timestamp,value)
VALUES ('s1002','2020-07-05','2020-07-05 00:00:01', 82);
</code></pre>
<blockquote>
<p>Let's say that at this particular moment the temperature was not 82 but 92 (Climate change ...).</p>
</blockquote>
<p>Looking at <code>PRIMARY KEY ((sensor, date), timestamp)</code>, we know that  <strong>sensor</strong>, <strong>date</strong> and <strong>timestamp</strong> are used to define uniqueness of the row. We'll need all of them to update our record (plus, of course, some of the data columns, otherwise we are not changing anything in that row!).</p>
<p>📘 <strong>Commands to execute</strong></p>
<pre lang="sql"><code>UPDATE temperatures_by_sensor 
SET value = 92
WHERE sensor = 's1002'
AND date = '2020-07-05'
AND timestamp = '2020-07-05 00:00:01';

SELECT *
FROM temperatures_by_sensor 
WHERE sensor='s1002' 
AND DATE='2020-07-05';
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<pre><code>token@cqlsh:sensor_data&gt; select *  from temperatures_by_sensor where sensor='s1002' and DATE='2020-07-05';

 sensor | date       | timestamp                       | value
--------+------------+---------------------------------+-------
  s1002 | 2020-07-05 | 2020-07-05 12:59:59.000000+0000 |    99
  s1002 | 2020-07-05 | 2020-07-05 12:00:01.000000+0000 |   100
  s1002 | 2020-07-05 | 2020-07-05 00:59:59.000000+0000 |    82
  s1002 | 2020-07-05 | 2020-07-05 00:00:01.000000+0000 |    92

(4 rows)
token@cqlsh:sensor_data&gt; 
</code></pre>
<blockquote>
<p><em>Note</em>: you could also achieve the same result with another <code>INSERT</code> statement,<br />
which will simply overwrite the previous values if the partition key is the same.<br />
This is because Cassandra <em>does not read before writing</em>, i.e. updates are inserts!</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="step-6e-cru-d-delete-remove-data"> </a>✅ Step 6e. CRU(D) = delete = remove data</h4>
<p>The final operation from our <strong>CRUD</strong> acronym is <strong>DELETE</strong>. This is the operation we use when we want to remove data from the database.<br />
In Apache Cassandra you can <strong>DELETE</strong> from the cell level all the way up to the partition<br />
<em>(meaning I could remove a single column in a single row or I could remove a whole partition)</em> using the same <strong>DELETE</strong> command.</p>
<p><em>Generally speaking, it's best to perform as few delete operations as possible on the largest amount of data. Think of it this way, if you want to delete ALL data in a table, don't delete each individual cell, just <strong>TRUNCATE</strong> the table. If you need to delete all the rows in a partition, don't delete each row, <strong>DELETE</strong> the partition, and so on.</em></p>
<p>When deleting a row on a given table, we have to specify the values of the primary key for that table. <em>(And don't forget<br />
that, if your data model has the same information stored twice in different tables, it will be up to you to<br />
issue two different <strong>DELETE</strong> operations!)</em></p>
<p>📘 <strong>Commands to execute</strong></p>
<ul>
<li>Partition level delete</li>
</ul>
<pre lang="sql"><code>// Get a partition
SELECT *  FROM temperatures_by_sensor 
WHERE sensor='s1002' 
AND date='2020-07-05';

// Delete at Partition level
DELETE FROM temperatures_by_sensor
WHERE sensor='s1002' 
AND date='2020-07-05';

// Read again
SELECT *  from temperatures_by_sensor 
WHERE sensor='s1002' 
AND date='2020-07-05';
</code></pre>
<ul>
<li>Row-level delete</li>
</ul>
<pre lang="sql"><code>// Get a partition
SELECT *  from temperatures_by_sensor 
WHERE sensor='s1002' 
AND date='2020-07-04';

// Delete at Row level
DELETE FROM temperatures_by_sensor
where sensor='s1002' 
AND date='2020-07-04' 
AND timestamp='2020-07-04 00:00:01.000000+0000';

// Read again
SELECT *  from temperatures_by_sensor 
WHERE sensor='s1002' 
AND date='2020-07-04';
</code></pre>
<p>(Notice in the above, for your convenience, we read the tables, then delete the rows, then read them again).</p>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-fundamentals/raw/master/images/cql/07_deleting.png" alt="Deleting in CQL" /></p>
<p>Notice the rows are now removed from both tables: it is as simple as that.</p>
<h4><a class="anchor" aria-hidden="true" id="step-6f-design"> </a>✅ Step 6f. Design</h4>
<pre><code>What is the table we need in order to:
  - find hourly average temperatures ...
  - for every sensor ...
  - in a specified network ...
  - for a given date range ?
How can you do that?
</code></pre>
<p>Maybe you select every sensors...</p>
<ul>
<li>
<p>...then for every sensors you select the list of temperatures...</p>
</li>
<li>
<p>...but you could do the latest queries in parallel doing map reduce</p>
</li>
</ul>
<p>Maybe you can query all temperatures and then filter by network...</p>
<ul>
<li>
<p>... but you will need to add this column network....</p>
</li>
<li>
<p>....</p>
</li>
<li>
<p>....</p>
</li>
</ul>
<p><code>STOP IT !!!!</code></p>
<p>With Cassandra for a new request, you create a new table, even if its mean duplicating the data. I think you got it <code>^_^</code></p>
<p/>
<details>
<summary><b> Can you find what the table looks like ?</b></summary>
<hr>
<p>
<pre>
CREATE TABLE temperatures_by_network (
  network TEXT,
  week DATE,
  date_hour TIMESTAMP,
  sensor TEXT,
  avg_temperature FLOAT,
  latitude DECIMAL,
  longitude DECIMAL,
  PRIMARY KEY ((network,week),date_hour,sensor)
) WITH CLUSTERING ORDER BY (date_hour DESC, sensor ASC);
</pre>
</details>
<p/>
<h2><a class="anchor" aria-hidden="true" id="7-homework"> </a>7. Homework</h2>
<p>To submit the <strong>homework</strong>, please take a screenshot of the CQL Console showing the rows in tables<br />
<code>temperatures_by_sensor</code> and <code>sensors_by_network</code> before <em>and</em> after executing the DELETE statements.</p>
<p>You should also complete two mini-courses (a few minutes each) about using CQL and designing tables:</p>
<ul>
<li>Complete the mini-course <a href="https://www.datastax.com/learn/cassandra-fundamentals/cql" target="_blank">Cassandra Query Language</a> and take a screenshot of the final screen (&quot;Congratulations!&quot; on the left + console output on the right).</li>
<li>Complete the mini-course <a href="https://www.datastax.com/learn/data-modeling-by-example/digital-library-data-model" target="_blank">&quot;Cassandra Data Modeling / Digital Library&quot;</a> (link for hands-on at the bottom of the lessons). Take a screenshot of the final screen (&quot;Congratulations!&quot; on the left + console output on the right).</li>
</ul>
<p>Don't forget to <a href="https://dtsx.io/homework-intro-to-cassandra" target="_blank">submit your homework</a> and be awarded a nice verified badge!</p>
<h2><a class="anchor" aria-hidden="true" id="8-what-s-next"> </a>8. What's NEXT ?</h2>
<p>We've just scratched the surface of what you can do using Astra DB, built on Apache Cassandra.<br />
Go take a look at <a href="https://www.datastax.com/dev" target="_blank">DataStax for Developers</a> to see what else is possible.<br />
There's plenty to dig into!</p>
<p>Congratulations: you made to the end of today's workshop.</p>
<p>Don't forget to <a href="https://dtsx.io/homework-intro-to-cassandra" target="_blank">submit your homework</a> and be awarded a nice verified badge!</p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-fundamentals/raw/master/images/badge/intro-to-cassandra.png" alt="Badge" /></p>
<p><strong>... and see you at our next workshop!</strong></p>
<blockquote>
<p>Sincerely yours, The DataStax Developers</p>
</blockquote>

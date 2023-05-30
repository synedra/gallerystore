<h1><a class="anchor" aria-hidden="true" id="apache-cassandra-r-data-modelling"> </a>🎓🎓 Apache Cassandra® Data Modelling</h1>
<p>Welcome to the <strong>Apache Cassandra® Data Modelling</strong> workshop! In this two-hour workshop, we show the methodology to build an effective data model with the distributed <code>NoSQL database Apache Cassandra™</code>.</p>
<p>Using <strong>Astra DB</strong>, the cloud based <em>Cassandra-as-a-Service</em> platform delivered by DataStax, we will cover the process for every developer who wants to build an application: list the use cases and build an effective data model.</p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-data-modeling/raw/master/images/splash.png" alt="" /></p>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<blockquote>
<p><a href="#-start-hands-on" target="_blank">🔖 Accessing HANDS-ON</a></p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="table-of-content"> </a>📋 Table of content</h2>
<img src="https://github.com/datastaxdevs/workshop-cassandra-data-modeling/raw/master/images/illustrations.png?raw=true" align="right" width="300px"/>
<ol>
<li><a href="#1-objectives" target="_blank">Objectives</a></li>
<li><a href="#2-frequently-asked-questions" target="_blank">Frequently Asked Questions</a></li>
<li><a href="#3-materials-for-the-session" target="_blank">Materials for the Session</a></li>
<li><a href="#4-create-your-astra-db-instance" target="_blank">Create Your Astra DB Instance</a></li>
<li><a href="#5-tables-with-single-row-and-multi-row-partitions" target="_blank">Tables with Single-Row and Multi-Row Partitions</a></li>
<li><a href="#6-dynamic-bucketing" target="_blank">Dynamic Bucketing</a></li>
<li><a href="#7-working-with-data-types" target="_blank">Working with Data Types</a></li>
<li><a href="#8-kdm-data-modeling-tool" target="_blank">KDM Data Modeling Tool</a></li>
<li><a href="#9-sensor-data-modeling" target="_blank">Sensor Data Modeling</a></li>
<li><a href="#10-homework" target="_blank">Homework</a></li>
<li><a href="#11-whats-next-" target="_blank">What's NEXT </a></li>
</ol>
<p><br/>
<h2><a class="anchor" aria-hidden="true" id="1-objectives"> </a>1. Objectives</h2>
<p>1️⃣ <strong>Understand how data is distributed and organized in Apache Cassandra®</strong></p>
<p>2️⃣ <strong>Learn how primary, partition, and clustering keys are defined in Apache Cassandra®</strong></p>
<p>3️⃣ <strong>Become familiar with CQL data types in Apache Cassandra®</strong></p>
<p>4️⃣ <strong>Learn about the data modeling methodology for Apache Cassandra®</strong></p>
<p>🚀 <strong>Have fun with an interactive session</strong></p>
<h2><a class="anchor" aria-hidden="true" id="2-frequently-asked-questions"> </a>2. Frequently Asked Questions</h2>
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
<li>You will need enough "real estate" on screen, we will ask you to open a few windows and it would not fit on mobiles (tablets should be OK)
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
Attending the session is not enough. You need to complete the homework detailed below and you will get a nice badge that you can share on LinkedIn or anywhere else.
</details>
<p/>
<h2><a class="anchor" aria-hidden="true" id="3-materials-for-the-session"> </a>3. Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to work at your own pace,<br />
we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="/slides/slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
</ul>
<hr />
<h1><a class="anchor" aria-hidden="true" id="start-hands-on"> </a>🏁 Start Hands-on</h1>
<h2><a class="anchor" aria-hidden="true" id="4-create-your-astra-db-instance"> </a>4. Create Your Astra DB Instance</h2>
<p><em><strong><code>ASTRA DB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, 40M read/write operations and about 80GB storage monthly for free - sufficient to run small production workloads. If you end your credits the databases will pause, no charge</em></p>
<p>Leveraging <a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/#c-procedure" target="_blank">Database creation guide</a> create a database. <em>Right-Click the button</em> with <em>Open in a new TAB.</em></p>
<p><a href="https://astra.dev/yt-7-27" target="_blank"><img src="images/create_astra_db_button.png?raw=true" /></a></p>
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
save it somewhere safe, as it will be needed to later in other workshops (In particular the string starting with <code>AstraCS:...</code>.)</p>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<p>The status will change from <code>Pending</code> to <code>Active</code> when the database is ready, this will only take 2-3 minutes. You will also receive an email when it is ready.</p>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="5-tables-with-single-row-and-multi-row-partitions"> </a>5. Tables with Single-Row and Multi-Row Partitions</h2>
<p>A <a href="https://github.com" target="_blank">GitHub</a> account may be required to run this hands-on lab in Gitpod.</p>
<h3><a class="anchor" aria-hidden="true" id="part-1-a-href-https-gitpod-io-https-github-com-datastax-academy-workshop-cassandra-data-modeling-tables-single-row-partitions-tables-with-single-row-partitions-a"> </a>✅ Part 1: <a href="https://gitpod.io/#https://github.com/DataStax-Academy/workshop-cassandra-data-modeling-tables-single-row-partitions/" target="_blank">Tables with Single-Row Partitions</a></h3>
<h3><a class="anchor" aria-hidden="true" id="part-2-a-href-https-gitpod-io-https-github-com-datastax-academy-workshop-cassandra-data-modeling-tables-multi-row-partitions-tables-with-multi-row-partitions-a"> </a>✅ Part 2: <a href="https://gitpod.io/#https://github.com/DataStax-Academy/workshop-cassandra-data-modeling-tables-multi-row-partitions/" target="_blank">Tables with Multi-Row Partitions</a></h3>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="6-dynamic-bucketing"> </a>6. Dynamic Bucketing</h2>
<details>
  <summary> <h3><a class="anchor" aria-hidden="true" id="homework-1"> </a>📌 Homework 1</h3></summary>
<p>Consider the table that supports query <code>Find all sensors in a specified network</code>:</p>
<pre lang="sql"><code>CREATE TABLE sensors_by_network_2 (
  network TEXT,
  sensor TEXT,
  PRIMARY KEY ((network), sensor)
);
</code></pre>
<p>Assume that a network may have none to millions of sensors. With dynamic bucketing, we can introduce artificial buckets to store sensors. A network with a few sensors may only need one bucket. A network with many sensors may need many buckets. Once buckets belonging to a particular network get filled with sensors, we can dynamically assign new buckets to store new sensors of this network.</p>
<p>📘 <strong>Implement dynamic bucketing in Astra DB</strong></p>
<pre lang="sql"><code>-- Table to manage buckets
CREATE TABLE buckets_by_network (
  network TEXT,
  bucket TIMEUUID,
  PRIMARY KEY ((network), bucket)
) WITH CLUSTERING ORDER BY (bucket DESC);

-- Table to store sensors
CREATE TABLE sensors_by_bucket (
  bucket TIMEUUID,
  sensor TEXT,
  PRIMARY KEY ((bucket), sensor)
);


-- Sample data
INSERT INTO buckets_by_network (network, bucket) VALUES ('forest-net', 49171ffe-0d12-11ed-861d-0242ac120002);
INSERT INTO buckets_by_network (network, bucket) VALUES ('forest-net', 74a13ede-0d12-11ed-861d-0242ac120002);

INSERT INTO sensors_by_bucket (bucket, sensor) VALUES (49171ffe-0d12-11ed-861d-0242ac120002, 's1001');
INSERT INTO sensors_by_bucket (bucket, sensor) VALUES (49171ffe-0d12-11ed-861d-0242ac120002, 's1002');

INSERT INTO sensors_by_bucket (bucket, sensor) VALUES (74a13ede-0d12-11ed-861d-0242ac120002, 's1003');
</code></pre>
<p>📘 <strong>Add a new sensor to a network</strong></p>
<ol>
<li>Get the latest bucket.</li>
</ol>
<pre lang="sql"><code>SELECT bucket FROM buckets_by_network WHERE network = 'forest-net' LIMIT 1;
</code></pre>
<ol start="2">
<li>Check the number of sensors in the bucket.</li>
</ol>
<pre lang="sql"><code>SELECT COUNT(*) AS sensors
FROM sensors_by_bucket WHERE bucket = 74a13ede-0d12-11ed-861d-0242ac120002;
</code></pre>
<ol start="3">
<li>Depending on the sensors-per-bucket threshold, insert a new sensor into the existing bucket, or create a new bucket and insert into the new bucket.</li>
</ol>
<pre lang="sql"><code>INSERT INTO sensors_by_bucket (bucket, sensor) VALUES (74a13ede-0d12-11ed-861d-0242ac120002, 's1004');
</code></pre>
<p>📘 <strong>Retrieve sensors in a specified network</strong></p>
<ol>
<li>Retrieve the buckets</li>
</ol>
<pre lang="sql"><code>SELECT bucket FROM buckets_by_network WHERE network = 'forest-net';
</code></pre>
<ol start="2">
<li>Retrieve the sensors</li>
</ol>
<pre lang="sql"><code>SELECT sensor
FROM sensors_by_bucket
WHERE bucket IN (74a13ede-0d12-11ed-861d-0242ac120002, 49171ffe-0d12-11ed-861d-0242ac120002);
</code></pre>
</details>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="7-working-with-data-types"> </a>7. Working with Data Types</h2>
<details>
  <summary> <h3><a class="anchor" aria-hidden="true" id="homework-2"> </a>📌 Homework 2</h3></summary>
<h3><a class="anchor" aria-hidden="true" id="step-7a-code-list-code-collections"> </a>✅ Step 7a. <code>List</code> Collections</h3>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>// Definition
CREATE TABLE IF NOT EXISTS table_with_list (
  uid      uuid,
  items    list&lt;text&gt;,
  PRIMARY KEY (uid)
);

// Insert
INSERT INTO table_with_list(uid,items)
VALUES (c7133017-6409-4d7a-9479-07a5c1e79306, ['a', 'b', 'c']);

// Replace
UPDATE table_with_list SET items = ['d', 'e']
WHERE uid = c7133017-6409-4d7a-9479-07a5c1e79306;

// Show result
SELECT * FROM table_with_list ;

// Append to list
UPDATE table_with_list SET items = items + ['f']
WHERE uid = c7133017-6409-4d7a-9479-07a5c1e79306;

// Replace an element (not available in Astra because read before write)
UPDATE table_with_list SET items[0] = ['g']
WHERE uid = c7133017-6409-4d7a-9479-07a5c1e79306;
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="step-7b-code-set-code-collections"> </a>✅ Step 7b. <code>Set</code> Collections</h3>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>// Definition
CREATE TABLE IF NOT EXISTS table_with_set (
  uid      uuid,
  animals  set&lt;text&gt;,
  PRIMARY KEY (uid)
);

// Insert
INSERT INTO table_with_set(uid,animals)
VALUES (87fad746-4adf-4107-9858-df8643564186, {'spider', 'cat', 'dog'});

// Replace
UPDATE table_with_set SET animals = {'pangolin', 'bat'}
WHERE uid = 87fad746-4adf-4107-9858-df8643564186;

// Show result
SELECT * FROM table_with_set;

// Append to Set
UPDATE table_with_set SET animals = animals + {'sheep'}
WHERE uid = 87fad746-4adf-4107-9858-df8643564186;
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="step-7c-code-map-code-collections"> </a>✅ Step 7c. <code>Map</code> Collections</h3>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>// Definition
CREATE TABLE IF NOT EXISTS table_with_map (
  uid         text,
  dictionary  map&lt;text, text&gt;,
  PRIMARY KEY (uid)
);

// Insert
INSERT INTO table_with_map(uid, dictionary)
VALUES ('fr_en', {'fromage':'cheese', 'vin':'wine', 'pain':'bread'});

// Replace
UPDATE table_with_map SET dictionary = {'saucisse': 'sausage'}
WHERE uid = 'fr_en';

// Show result
SELECT * FROM table_with_map;

// Append to Map
UPDATE table_with_map SET dictionary = dictionary + {'frites':'fries'}
WHERE uid = 'fr_en';
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="step-7d-user-defined-types"> </a>✅ Step 7d. User-Defined Types</h3>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>// Definition
CREATE TYPE IF NOT EXISTS udt_address (
  street text,
  city text,
  state text,
);

// Use the UDT in a table
CREATE TABLE IF NOT EXISTS table_with_udt (
  uid      text,
  address   udt_address,
  PRIMARY KEY (uid)
);

// INSERT (not quote on field names like street)
INSERT INTO table_with_udt(uid, address)
VALUES ('superman', {street:'daily planet',city:'metropolis',state:'CA'});

// Replace
UPDATE table_with_udt
SET address = {street:'pingouin alley',city:'antarctica',state:'melting'}
WHERE uid = 'superman';

// Replace a single field
UPDATE table_with_udt
SET address.state = 'melt'
WHERE uid = 'superman';
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="step-7e-counters"> </a>✅ Step 7e. Counters</h3>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>// Definition
CREATE TABLE IF NOT EXISTS table_with_counters (
  handle        text,
  following     counter,
  followers     counter,
  notifications counter,
  PRIMARY KEY (handle)
);

// You have a new follower
UPDATE table_with_counters SET followers = followers + 1
WHERE  handle = 'clunven';

// Some counters are... null
SELECT * from table_with_counters;

// Set to 0... but set is not valid
UPDATE table_with_counters
SET following = following + 0, notifications = notifications + 0
WHERE handle = 'clunven';

// Following someone
UPDATE table_with_counters SET following = following + 1
WHERE handle = 'clunven';

// You have a new message
UPDATE table_with_counters SET notifications = notifications + 1
WHERE handle = 'clunven';

</code></pre>
</details>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="8-kdm-data-modeling-tool"> </a>8. KDM Data Modeling Tool</h2>
<details>
  <summary> <h3><a class="anchor" aria-hidden="true" id="demo"> </a>🍿 Demo</h3></summary>
<h3><a class="anchor" aria-hidden="true" id="download-a-href-https-raw-githubusercontent-com-datastaxdevs-workshop-cassandra-data-modeling-main-materials-kdm-sensor-data-xml-the-project-xml-file-a"> </a>✅ Download <a href="https://raw.githubusercontent.com/datastaxdevs/workshop-cassandra-data-modeling/main/materials/kdm_sensor_data.xml" target="_blank">the project XML file</a>.</h3>
<h3><a class="anchor" aria-hidden="true" id="open-a-href-http-kdm-kashliev-com-the-kdm-tool-a"> </a>✅ Open <a href="http://kdm.kashliev.com/" target="_blank">the KDM tool</a>.</h3>
<h3><a class="anchor" aria-hidden="true" id="import-the-project-by-selecting-code-import-project-code-from-the-menu-and-specifying-file-code-kdm-sensor-data-xml-code"> </a>✅ Import the project by selecting <code>Import Project</code> from the menu and specifying file <code>kdm_sensor_data.xml</code>.</h3>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-data-modeling/raw/master/images/kdm_01.png" alt="" /></p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-data-modeling/raw/master/images/kdm_02.png" alt="" /></p>
<h3><a class="anchor" aria-hidden="true" id="explore-the-five-data-modeling-steps-supported-by-kdm-note-that-the-conceptual-data-model-in-step-1-and-queries-in-step-2-are-already-defined"> </a>✅ Explore the five data modeling steps supported by KDM. Note that the conceptual data model in Step 1 and queries in Step 2 are already defined.</h3>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-data-modeling/raw/master/images/kdm_03.png" alt="" /></p>
</details>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="9-sensor-data-modeling"> </a>9. Sensor Data Modeling</h2>
<p>A <a href="https://github.com" target="_blank">GitHub</a> account may be required to run this hands-on lab in Gitpod.</p>
<h3><a class="anchor" aria-hidden="true" id="a-href-https-gitpod-io-https-github-com-datastax-academy-workshop-cassandra-data-modeling-sensor-data-sensor-data-modeling-a"> </a>✅ <a href="https://gitpod.io/#https://github.com/DataStax-Academy/workshop-cassandra-data-modeling-sensor-data/" target="_blank">Sensor Data Modeling</a></h3>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="10-homework"> </a>10. Homework</h2>
<ol>
<li>
<p>Complete <a href="#7-working-with-data-types" target="_blank">Working with Data Types</a>. Take a screenshot of the CQL Console showing the rows in tables<br />
<code>table_with_udt</code> and <code>table_with_counters</code> before <em>and</em> after executing the DELETE statements.</p>
</li>
<li>
<p>Complete the mini-course <a href="https://www.datastax.com/learn/data-modeling-by-example/time-series-model" target="_blank">Time Series Data Modeling</a>. Take a screenshot of the final screen of the practice lab, with the console output at the right.</p>
</li>
<li>
<p><a href="https://forms.gle/Z69y4MM3SpEDg7nt5" target="_blank">Submit your homework</a> and be awarded a nice verifiable badge!</p>
</li>
</ol>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="11-what-s-next"> </a>11. What's NEXT ?</h2>
<p>We've just scratched the surface of what you can do using Astra DB, built on Apache Cassandra.</p>
<p>Go take a look at <a href="https://www.datastax.com/dev" target="_blank">DataStax for Developers</a> to see what else is possible.<br />
There's plenty to dig into!</p>
<p>Congratulations: you made to the end of today's workshop.</p>
<p><img src="https://github.com/datastaxdevs/workshop-cassandra-data-modeling/raw/master/images/badge_data_modeling.png" alt="Badge" /></p>
<p><strong>... and see you at our next workshop!</strong></p>
<blockquote>
<p>Sincerely yours, The DataStax Developers</p>
</blockquote>

<h2><a class="anchor" aria-hidden="true" id="scalable-indexing-for-cassandra-using-datastax-astra"> </a>🎓🔥 Scalable Indexing for Cassandra using DataStax Astra 🔥🎓</h2>
<p><a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p><img src="https://user-images.githubusercontent.com/23346205/96910093-f5ee7100-146c-11eb-9cfb-06ea3732c2bd.png" alt="Storage Attached Index Workshop" /></p>
<p>Welcome to the 'Scalable Indexing for Cassandra using DataStax Astra' workshop! In this two-hour workshop, the Developer Advocate team of DataStax will explain the new Storage Attached Indexing (SAI) feature using Astra, the cloud based Cassandra-as-a-Service platform delivered by DataStax, to demonstrate how you can use them to add some much wanted flexibility to your Cassandra data model by querying outside of primary key fields.</p>
<p><strong>To date, SAI is currently supported on DataStax Astra and DataStax Enterprise 6.8.3+. There is a currently a <a href="https://cwiki.apache.org/confluence/display/CASSANDRA/CEP-7%3A+Storage+Attached+Index" target="_blank">CEP</a> to bring this functionality into Open Source Apache Cassandra.</strong></p>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li>Materials used during presentations</li>
<li>Hands-on exercises</li>
<li>Workshop videos
<ul>
<li><a href="https://www.youtube.com/watch?v=GLJc1Uz9dqw" target="_blank">First workshop</a> [NAM Time]</li>
<li><a href="https://www.youtube.com/watch?v=yNQYQjXtV30" target="_blank">Second workshop</a> [IST Time]</li>
</ul>
</li>
<li><a href="https://bit.ly/cassandra-workshop" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>Table of Contents</h2>
<table>
<thead>
<tr>
<th>Title</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Slide deck</strong></td>
<td><a href="slides/Presentation.pdf" target="_blank">Slide deck for the workshop</a></td>
</tr>
<tr>
<td><strong>Exercise Notebook</strong></td>
<td><a href="SA_Index_Workshop.tar" target="_blank">Exercises in Studio Notebook for Astra</a></td>
</tr>
<tr>
<td><strong>SAI Documentation</strong></td>
<td><a href="https://docs.datastax.com/en/storage-attached-index/6.8/sai/saiQuickStart.html" target="_blank">SAI Documentation</a></td>
</tr>
<tr>
<td><strong>1. Create your Astra instance</strong></td>
<td><a href="#1-create-your-astra-instance" target="_blank">Create your Astra instance</a></td>
</tr>
<tr>
<td><strong>2. Getting started with SAI</strong></td>
<td><a href="#2-getting-started-with-sai-storage-attached-index" target="_blank">Getting started with SAI</a></td>
</tr>
<tr>
<td><strong>3. IoT sensor data model use case</strong></td>
<td><a href="#3-iot-sensor-data-model-use-case" target="_blank">IoT sensor data model use case</a></td>
</tr>
</tbody>
</table>
<h2><a class="anchor" aria-hidden="true" id="1-create-your-astra-instance"> </a>1. Create your Astra instance</h2>
<p><code>ASTRA</code> service is available at url <a href="https://dtsx.io/workshop" target="_blank">https://astra.datastax.com</a>. <code>ASTRA</code> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. <code>Astra</code> offers <strong>5 Gb Tier Free Forever</strong> and you <strong>don't need a credit card</strong> or anything to sign-up and use it.</p>
<p><strong>✅ Step 1a. Register (if needed) and Sign In to Astra</strong> : You can use your <code>Github</code>, <code>Google</code> accounts or register with an <code>email</code>.</p>
<p>Make sure to chose a password with minimum 8 characters, containing upper and lowercase letters, at least one number and special character</p>
<ul>
<li><a href="https://dtsx.io/workshop" target="_blank">Registration Page</a></li>
</ul>
<p><img src="https://github.com/datastaxdevs/shared-assets/blob/master/astra/login-1000.png?raw=true" alt="Registration Image" /></p>
<ul>
<li><a href="https://dtsx.io/workshop" target="_blank">Authentication Page</a></li>
</ul>
<p><img src="https://github.com/datastaxdevs/shared-assets/blob/master/astra/signin-raw.png?raw=true" alt="Login Image" /></p>
<p><strong>✅ Step 1b. Choose the free plan and select your region</strong></p>
<p><img src="https://github.com/datastaxdevs/shared-assets/blob/master/astra/choose-a-plan-1000-annotated.png?raw=true" alt="my-pic" /></p>
<ul>
<li>
<p><strong>Select the free tier</strong>: 5GB storage, no obligation</p>
</li>
<li>
<p><strong>Select the region</strong>: This is the region where your database will reside physically (choose one close to you or your users). For people in EMEA please use <code>europe-west-1</code> idea here is to reduce latency.</p>
</li>
</ul>
<p><strong>✅ Step 1c. Configure and create your database</strong></p>
<p>You will find below which values to enter for each field.</p>
<p><img src="https://github.com/datastaxdevs/shared-assets/blob/master/astra/create-and-configure-annotated-1000.png?raw=true" alt="my-pic" /></p>
<ul>
<li>
<p><strong>Fill in the database name</strong> - <code>sa_index_workshop_db.</code> While Astra allows you to fill in these fields with values of your own choosing, please follow our reccomendations to make the rest of the exercises easier to follow. If you don't, you are on your own! :)</p>
</li>
<li>
<p><strong>Fill in the keyspace name</strong> - <code>sa_index</code>. It's really important that you use the name sa_index here in order for all the exercises to work well. We realize you want to be creative, but please just roll with this one today.</p>
</li>
<li>
<p><strong>Fill in the Database User name</strong> - <code>index_user</code>. Note the user name is case-sensitive. Please use the case we suggest here.</p>
</li>
<li>
<p><strong>Fill in the password</strong> - <code>index_password1</code>. Fill in both the password and the confirmation fields. Note that the password is also case-sensitive. Please use the case we suggest here.</p>
</li>
<li>
<p><strong>Create the database</strong>. Review all the fields to make sure they are as shown, and click the <code>Create Database</code> button.</p>
</li>
</ul>
<p>You will see your new database <code>pending</code> in the Dashboard.</p>
<p><img src="https://github.com/datastaxdevs/shared-assets/blob/master/astra/dashboard-pending-1000.png?raw=true" alt="my-pic" /></p>
<p>The status will change to <code>Active</code> when the database is ready, this will only take 2-3 minutes. You will also receive an email address when it is ready.</p>
<p><strong>✅ Step 1d. View your Database and connect</strong></p>
<p>Let’s review the database you have configured. Select your new database in the lefthand column.</p>
<p>Now you can select to connect, to park the database, to access CQL console or Studio.</p>
<p><img src="https://github.com/datastaxdevs/shared-assets/blob/master/astra/summary-1000.png?raw=true" alt="my-pic" /></p>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="2-getting-started-with-sai-storage-attached-index"> </a>2. Getting started with SAI (Storage Attached Index)</h2>
<p><strong>SAI</strong> is short for <strong>Storage Attached Indexes</strong>, it allows us to build indexes on Cassandra tables that dramatically improve the flexibility of Cassandra queries.</p>
<p>For a <strong>non-technical introduction</strong> to <strong>SAI</strong>, have a look at this <a href="https://www.datastax.com/blog/get-your-head-clouds-part-1-3-build-cloud-native-apps-datastax-astra-dbaas-now-aws-gcp" target="_blank">recent blog post</a>.</p>
<p>To learn more about <strong>SAI</strong> from a <strong>technical perspective</strong>, have a look at our <a href="https://docs.datastax.com/en/storage-attached-index/6.8/sai/saiQuickStart.html" target="_blank">docs on SAI</a>. Honestly, these docs are pretty great IMO especially the <a href="https://docs.datastax.com/en/storage-attached-index/6.8/sai/saiFaqs.html">SAI FAQ</a>. Definitely take a moment to read through these to get a better understanding of how all of this works and even more examples on top of what we are presenting in this repo.</p>
<p>Now, let's get into some examples. The first thing we'll need is a table and some data to work with. For that we need to talk about my dentist, or really, a contrived example of a client data model a dentist might need to use.</p>
<p><strong>✅ Step 2a. Navigate to the CQL Console and login to the database</strong></p>
<p>In the Summary screen for your database, select <strong><em>CQL Console</em></strong> from the top menu in the main window. This will take you to the CQL Console with a login prompt.</p>
<p><img src="https://user-images.githubusercontent.com/23346205/97186856-35bc9d80-1778-11eb-80fd-df1a2f264a25.png" alt="astra cqlsh console" /></p>
<p>Once you click the <em><code>CQL Console</code></em> tab it will automatically log you in and present you with a <code>token@cqlsh&gt;</code> prompt.</p>
<p><strong>✅ Step 2b. Describe keyspaces and USE <code>sa_index</code></strong></p>
<p>Ok, you're logged in, and now we're ready to rock. Creating tables is quite easy, but before we create one we need to tell the database which keyspace we are working with.</p>
<p>First, let's <strong><em>DESCRIBE</em></strong> all of the keyspaces that are in the database. This will give us a list of the available keyspaces.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre><code>desc KEYSPACES;
</code></pre>
<p><em>&quot;desc&quot; is short for &quot;describe&quot;, either is valid</em></p>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/97188152-939db500-1779-11eb-8e47-0d6b4ebea74b.png" alt="desc keyspace output" /></p>
<p>Depending on your setup you might see a different set of keyspaces then in the image. The one we care about for now is <strong><em>sa_index</em></strong>. From here, execute the <strong><em>USE</em></strong> command with the <strong><em>sa_index</em></strong> keyspace to tell the database our context is within <strong><em>sa_index</em></strong>.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre><code>use sa_index;
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/97188451-e4151280-1779-11eb-98a2-f7292621f6ac.png" alt="use sa_index output" /></p>
<p>Notice how the prompt displays <code>token@cqlsh:sa_index&gt;</code> informing us we are <strong>using</strong> the <strong><em>sa_index</em></strong> keyspace. Now we are ready to create our tables.</p>
<p><strong>✅ Step 2c. Create a <em><code>clients</code></em> table and insert some data</strong></p>
<p>Create the table.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>CREATE TABLE IF NOT EXISTS clients (
    uniqueid uuid primary key,
    firstname text,
    lastname text,
    birthday date,
    nextappt timestamp,
    newpatient boolean,
    photo text
);
</code></pre>
<p>Insert some data into the table.</p>
<p><em>We don't have real image URLs, so we're just using a placeholder string.</em></p>
<p>📘 <strong>Commands to execute</strong></p>
<pre lang="SQL"><code>INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (D85745B1-4BEC-43D7-8B77-DD164CB9D1B8, 'Alice', 'Apple', '1984-01-24', '2020-10-20 12:00:00', true, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (2A4F139F-0BBF-4A6F-B982-5400F11D2F2B, 'Zeke', 'Apple', '1961-12-30', '2020-10-20 12:30:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (DF649261-89CB-446B-9998-FFA2D17506F9, 'Lorenzo', 'Banana', '1963-09-03', '2020-10-20 13:00:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (808E6BBF-A0F4-4E4C-9C97-E36751D51A8B, 'Miley', 'Banana', '1969-02-06', '2020-10-20 13:30:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (3D458A4D-2F54-4271-BEDC-1FC316B3CC96, 'Cheryl', 'Banana', '1970-07-11', '2020-10-20 14:00:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (287AB6B4-1AA6-45DF-B6F8-2BE253B9AACE, 'Red', 'Currant', '1974-02-18', '2020-10-20 15:00:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (AB49D151-CC04-40DC-AEEA-0A4E5F59D69A, 'Matthew', 'Durian', '1976-11-11', '2020-10-19 12:30:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (783CE790-16B4-4645-B27C-4FDF3994A755, 'Vanessa', 'Elderberry', '1977-12-03', '2020-10-20 15:30:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (D23997E4-CCCB-46BB-B92F-0D4582A68809, 'Elaine', 'Elderberry', '1979-11-16', '2020-10-20 10:00:00', true, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (36C386C1-3C3B-49FC-81B1-391D5537453D, 'Phoebe', 'Fig', '1986-01-27', '2020-10-21 11:00:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (00FEE7EE-8F93-4C2E-A8BE-3ADD81235822, 'Patricia', 'Grape', '1986-06-24', '2020-10-21 12:00:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (B9DB7E99-AD1C-49B1-97C6-87154663AEF4, 'Herb', 'Huckleberry', '1990-07-09', '2020-10-21 13:00:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (F4DB7673-CA4E-4382-BDCD-2C1704363590, 'John-Henry', 'Huckleberry', '1979-11-16', '2020-10-21 14:00:00', false, 'imageurl');

INSERT INTO clients (uniqueid, firstname, lastname, birthday, nextappt, newpatient, photo) 
VALUES (F4DB7673-CA4E-4382-BDCD-2C1704363595, 'Sven', 'Åskådare', '1967-11-07', '2020-10-21 14:00:00', false, 'imageurl');
</code></pre>
<p><strong>✅ Step 2d. Verify data exists</strong></p>
<p>Now let's take a look at the data we just inserted.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre><code>SELECT * FROM clients;
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/97189410-f2176300-177a-11eb-90ca-3604f113520f.png" alt="select from client table" /></p>
<p><strong>✅ Step 2e. Create some indexes</strong></p>
<p>Ok great, we have data in our table, but remember we used <strong><em><code>uniqueid</code></em></strong> as our <strong>primary key</strong> when we created the table. If we want to query a single patient, we'd have to do that by the <strong><em><code>uniqueid</code></em></strong> column because that's our <strong>partition key</strong> <em>(don't forget, a single value in the primary key is always the partition key)</em>.</p>
<p>As a matter of fact, let's try an example. Let's say I want to find a user by their lastname.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>SELECT * FROM clients WHERE lastname = 'Apple';
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/97208146-33b30880-1791-11eb-8470-13b6381de70e.png" alt="clients where lastname allow filtering" /></p>
<p>Right, the database is telling me here I <strong>CANNOT</strong> query against the <strong>lastname</strong> column because it is NOT in my primary key <strong><em><code>uniqueid</code></em></strong>.</p>
<p>But how would we search for users outside of using their unique ID's? We need to look for clients based on information they give us when they walk in the office. Namely, information like first and last name, or birthdate. Maybe a combination of those. Let's set up some indexes to do that.</p>
<p><em>Don't worry about options in the below statements just yet. We'll get to that. For now, just execute the commands to create your indexes.</em></p>
<p>📘 <strong>Commands to execute</strong></p>
<pre lang="SQL"><code>CREATE CUSTOM INDEX IF NOT EXISTS ON clients(firstname) USING 'StorageAttachedIndex' 
WITH OPTIONS = {'case_sensitive': false, 'normalize': true };

CREATE CUSTOM INDEX IF NOT EXISTS ON clients(lastname) USING 'StorageAttachedIndex' 
WITH OPTIONS = {'case_sensitive': false, 'normalize': true };

CREATE CUSTOM INDEX IF NOT EXISTS ON clients(birthday) USING 'StorageAttachedIndex';
</code></pre>
<p><strong>✅ Step 2f. Execute queries that use firstname, lastname, and birthday using our indexes</strong></p>
<p>Remember, the <strong><code>clients</code></strong> table data model only includes <strong><code>uniqueid</code></strong> in the primary key. In the traditional Cassandra sense I can only query against the <strong><code>uniqueid</code></strong> column in the <strong>WHERE</strong> clause. However, with our <strong>SAIndexes</strong> now added we can do a lot more.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>// Look for a client by ONLY their lastname. Notice the case used.
SELECT * FROM clients WHERE lastname = 'Apple';
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/97198417-25f78600-1785-11eb-8632-9a7d30456ec4.png" alt="clients where lastname" /></p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>// Look for a client by their lastname and firstname. Notice the case used.
SELECT * FROM clients WHERE lastname = 'apple' AND firstname = 'alice';
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/97198713-871f5980-1785-11eb-8416-bd595a70bf6d.png" alt="clients where firstname and lastname" /></p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>// Look for a client by an exact match to their birthday.
SELECT * FROM clients WHERE birthday = '1984-01-24';
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/97198969-d9607a80-1785-11eb-8a5a-f754995634f1.png" alt="clients where birthday" /></p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>// Look for a client by a range match for the year of their birthday.
SELECT * FROM clients WHERE birthday &gt; '1984-01-01' AND birthday &lt; '1985-01-01';
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/97199744-baaeb380-1786-11eb-829d-5e05d99d4ba5.png" alt="clients where birthday range" /></p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>// Look for a client by their firstname 
// and a range match for the year of their birthday. Again, notice the case used.
SELECT * FROM clients 
WHERE firstname = 'aLicE'
AND birthday &gt; '1984-01-01' AND birthday &lt; '1985-01-01';
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/97200012-0f522e80-1787-11eb-8aa9-d3c22049dd4b.png" alt="clients where name and birthday range" /></p>
<p><strong>✅ Step 2g. Digest everything we just did there</strong></p>
<p>Ok, so let's break that all down. I said earlier when we created the indexes I would explain the options included with some of the indexes.</p>
<pre lang="SQL"><code>WITH OPTIONS = {'case_sensitive': false, 'normalize': true };
</code></pre>
<p>So what does the <strong>“WITH OPTIONS”</strong> part mean?</p>
<p>Well, <a href="https://docs.datastax.com/en/dse/6.8/cql/cql/cql_reference/cql_commands/cqlCreateCustomIndex.html#cqlCreateCustomIndex__cqlCreateCustomIndexOptions" target="_blank">case_sensitive</a> is fairly straightforward. Setting this <strong>false</strong> allows us to match any combination of case for the terms we are querying against, <strong>firstname</strong> or <strong>lastname</strong> fields according to the indexes we created.</p>
<p>This is why I kept varying the case used in our queries above. You could <strong>NOT</strong> have done does this with a traditional Cassandra query.</p>
<p>How about <a href="https://docs.datastax.com/en/dse/6.8/cql/cql/cql_reference/cql_commands/cqlCreateCustomIndex.html#cqlCreateCustomIndex__cqlCreateCustomIndexOptions" target="_blank">normalize</a>? Basically, this means that special characters, like vowels with diacritics can be represented by multiple binary representations for the same character, which also makes things easier to match.</p>
<p>An example would be a row with a column value that contained the character <code>Å (U+212B)</code>.  With <strong>normalize</strong> enabled a query that used the character <code>Å (U+00C5)</code> would find that row. This saves from the need to find all unicode variations for a single character.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>SELECT * FROM clients WHERE lastname = 'Åskådare';
</code></pre>
<p><em>To be clear, this is not Ascii folding where I might insert code that uses <code>é</code> and a select using <code>e</code>. This is coming as a future feature.</em></p>
<p>To sum up, we queried against a combination of string and date fields using exact matches, multiple string cases, and date ranges. Just by adding an index on 3 fields we significantly expanded the flexibility of our data model.</p>
<p>Let's do more.</p>
<p><strong>✅ Step 2h. Add another index to support a new data model requirement</strong></p>
<p>Imagine a case where we now have a requirement to find clients based off of their next appointment.</p>
<p>Prior to <strong>SAI</strong>, if I wanted to accomplish this same thing in Cassandra, I would set up a new table using the <strong>date</strong> as the <strong>partition key</strong>, and I'd probably have the <strong>appointment</strong> slots as a <strong>clustering column</strong>, along with the <strong><code>uniqueid</code></strong> rounding out the primary key.</p>
<p>Then, I would retrieve the days partition to get a list of the appointments for the day. Now, I have <strong>two tables</strong> that I need to worry about to support that query.</p>
<p>Let's see what this looks like with <strong>SAI</strong>.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>CREATE CUSTOM INDEX IF NOT EXISTS ON clients(nextappt) USING 'StorageAttachedIndex';
</code></pre>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>SELECT * FROM clients WHERE nextappt &gt; '2020-10-20 09:00:00';
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/97206362-01081080-178f-11eb-8b7d-6b002da6f9fb.png" alt="clients where nextappt" /></p>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="3-iot-sensor-data-model-use-case"> </a>3. IoT sensor data model use case</h2>
<p>Time to swtich gears to a real IoT data model use case.</p>
<p>In the following case, an organization recieved a feed of sensor data that always included all of the fields that the sensor kept track of, even if those fields hadn't changed since the last reading.</p>
<p><strong>All of the data was sent whenever a single field changed values.</strong></p>
<p>Now, this isn't necessarily something that has to be difficult to deal with, if all of the key fields are the same, <strong>we can easily overwrite redundant data without doing a read-before-write</strong> and all of that non-changing, redundant data will just compact away.</p>
<p>But, a <strong>problem arises</strong> if we need to <strong>query</strong> based on <strong>something other than the primary key</strong>.</p>
<p>If this table is instead organized to be physically efficient for querying, then I may not be able to easily upsert the data from the sensor without 1) creating a lot of unnecessary records, or 2) being forced to do a read-before-write to check if a record already exists.</p>
<p>In this case, the <strong>user was stuck with option 1</strong>, because <strong>it was cheaper to store more data than it was to have the compute resources for all of that extra query power for the 20x read workload that was required just to check to see if a sensor reading was already in the database.</strong></p>
<p>For this section we will continue by using <a href="SA_Index_Workshop.tar" target="_blank">this Studio notebook</a> in Astra. Please right-click on the link provided and choose <strong>Copy Link Address</strong>. From there, follow the instructions to import into Astra.</p>
<p>Click on the <strong><code>Studio</code></strong> tab within your Astra console.<br />
<img src="https://user-images.githubusercontent.com/23346205/97359835-c3c97e80-1873-11eb-82a7-2d6ce63d04f3.png" alt="astra use studio" /></p>
<p>This will launch <strong>Studio</strong> in a new tab.</p>
<p>Click the <strong><code>+</code></strong> icon to import a notebook.<br />
<img src="https://user-images.githubusercontent.com/23346205/97360192-3c303f80-1874-11eb-97c1-10d610c93f8c.png" alt="studio import notebooks" /></p>
<p>Choose <strong><code>IMPORT FROM URL</code></strong>.<br />
<img src="https://user-images.githubusercontent.com/23346205/97360504-ae088900-1874-11eb-94ca-1157295169de.png" alt="import from url" /></p>
<p>Paste in the link address you copied and click <strong><code>Import</code></strong>.<br />
<img src="https://user-images.githubusercontent.com/23346205/97360803-0dff2f80-1875-11eb-87a4-eb365d951969.png" alt="import from url with link" /></p>
<p>From there the notebook will be imported and opened automatically. Navigate down to Section <strong>3. IoT sensor data model use case</strong> to continue on.<br />
<img src="https://user-images.githubusercontent.com/23346205/97361093-74844d80-1875-11eb-9d11-ceecc64dd1f7.png" alt="view studio notebook" /></p>
<!--
**✅ Step 3a. Create our `sensordata` table**

- This table will create a partition for every hour of every day for each location.
- In this case, we have between 1,000 and 10,000 locations, and there are potentially dozens of devices per location.
- The **`updated`** **STATIC** column will show the last time that the values in **`payload`** were updated that hour.
- As hours go by, we will naturally create a snapshot of the last hour.
- This might be undesirable if I didn't know that 
- I get at least one sensor payload per hour unless a device is offline.

📘 **Command to execute**
```SQL
CREATE TABLE sensordata (
    location text,
    dayhour timestamp,
    device_id text,
    device_name text,
    updated timestamp STATIC,
    payload map<text,text>,
    PRIMARY KEY ((location, dayhour), device_id)
) WITH CLUSTERING ORDER BY (device_id ASC);
```

**✅ Step 3b. Create indexes to address query needs outside of our primary key**

OK, so this table organizes the data the way we want it to be space efficient, and it gets rid of redundant records by virtue of the physical organziation that it creates on disk. 

We get the snapshot view that we want each hour, and if most of the values in “payload” don't change over the course an hour, then we avoid both having to do a read before write, and we avoid storing extra copies of that data. 

Where does **SAI** come into the picture? Well, the trick is that queries against this data use the non-unique **`device_name`** field along with the **`dayhour`** that we're looking for, but we also sometimes need to query by the key in the **`payload`** map. 

Being able to query with those inputs, and also organize the data as efficiently as we can is nearly impossible without **SAI**. 

Let's look at the indexes we need to make as well as load some sample data that we can query.

📘 **Commands to execute**
```SQL
CREATE CUSTOM INDEX IF NOT EXISTS ON sensordata(device_name) USING 'StorageAttachedIndex'
WITH OPTIONS = {'case_sensitive': false, 'normalize': true };

CREATE CUSTOM INDEX IF NOT EXISTS ON sensordata(dayhour) USING 'StorageAttachedIndex';

CREATE CUSTOM INDEX IF NOT EXISTS ON sensordata(keys(payload)) USING 'StorageAttachedIndex' 
WITH OPTIONS = {'case_sensitive': false, 'normalize': true };
```

_That last **CREATE CUSTOM INDEX** command uses the [keys()](https://docs.datastax.com/en/storage-attached-index/6.8/sai/saiUsing.html#SAIcollectionmapexampleswithkeys,values,andentries) function to index only the map keys in the **payload** map. That lets us **search for entries** with a **specific key name**, which in this case allows us to query for a particular sensor reading._ 

So, now that we have our table structure, let's load some data and query it.

**✅ Step 3c. Insert data**

_Note that the UUIDs here are only increasing by one because it's an expedient thing to do when manually generating data, in the real world, don't do that._

📘 **Commands to execute**
```SQL
INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('ABC','2020-10-20 01:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB78','device1','2020-10-20 01:30:00',{'temp':'freezing!', 'humidity':'low'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('ABC','2020-10-20 01:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB79','device1','2020-10-20 01:31:00',{'temp':'freezing!', 'humidity':'low', 'mood':'hungry'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('ABC','2020-10-20 01:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB79','device1','2020-10-20 01:32:00',{'temp':'freezing!', 'humidity':'low', 'mood':'full'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('ABC','2020-10-20 02:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB80','device2','2020-10-20 02:30:00',{'speed':'stopped', 'color':'blue'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('ABC','2020-10-20 03:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB81','device2','2020-10-20 03:30:00',{'speed':'slow', 'color':'blue'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('DEF','2020-10-20 00:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB82','dev1','2020-10-20 00:30:00',{'temp':'hot!', 'humidity':'sticky'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('DEF','2020-10-20 01:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB83','dev2','2020-10-20 01:30:00',{'temp':'warm', 'humidity':'muggy'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('DEF','2020-10-20 02:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB84','dev3','2020-10-20 02:30:00',{'temp':'freezing!', 'humidity':'my beard is growing icicles'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('GHI','2020-10-20 00:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB85','doohickey','2020-10-20 00:30:00',{'temp':'hot!', 'humidity':'dry', 'orientation':'rightside up'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('GHI','2020-10-20 01:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB86','doohickey','2020-10-20 01:30:00',{'temp':'hot!', 'humidity':'dry', 'orientation':'upside down'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('GHI','2020-10-20 02:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB87','doohickey','2020-10-20 02:30:00',{'temp':'hot!', 'humidity':'dry', 'orientation':'forwards'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('GHI','2020-10-20 03:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB85','doohickey','2020-10-20 03:30:00',{'temp':'hot!', 'humidity':'dry', 'orientation':'backwards'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('ABC','2020-10-20 03:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB78','device1','2020-10-20 03:31:00',{'temp':'freezing!', 'humidity':'low', 'mood':'hungry again'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('ABC','2020-10-20 03:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB78','device1','2020-10-20 03:35:00',{'temp':'freezing!', 'humidity':'low', 'mood':'full'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('ABC','2020-10-20 03:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB78','device1','2020-10-20 03:40:00',{'temp':'freezing!', 'humidity':'low', 'mood':'no, still peckish'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('DEF','2020-10-20 03:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB93','dev4','2020-10-20 03:30:00',{'temp':'/tmp', 'speed':'low'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('DEF','2020-10-20 03:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB93','dev4','2020-10-20 03:40:00',{'temp':'/var/lib/tmp', 'speed':'low', 'color':'green'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('DEF','2020-10-20 03:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB94','dev5','2020-10-20 03:45:00',{'temp':'freezing!', 'humidity':'low', 'mood':'hungry'});

INSERT INTO sensordata(location, dayhour, device_id, device_name, updated, payload)
VALUES('DEF','2020-10-20 03:00:00','87C5EFE5-1849-4C0B-BBCD-F4FB84F6FB95','dev6','2020-10-20 03:50:00',{'temp':'freezing!', 'humidity':'low', 'mood':'hungry'});
```

_It is worth pointing out that doing an **INSERT** on a **Map** column like this will **always replace the full map**. In this case, I know that's OK for my use case because I always get a full input file that has all the sensor readings in it. Sometimes, this isn't what you want, and you'll need to use the **SET** keyword to **set a specific value in the map**._

**✅ Step 3d. Execute queries that use device_name, dayhour, and payload map keys using our indexes**

📘 **Command to execute**
```SQL
SELECT * FROM sensordata WHERE device_name='doohickey';
```

📗 **Expected output**

![sensordata where device_name](https://user-images.githubusercontent.com/23346205/97318153-f2c6fc80-1841-11eb-8c77-9aefed902d61.png)

📘 **Command to execute**
```SQL
SELECT * FROM sensordata 
WHERE device_name = 'device1' 
AND dayhour = '2020-10-20 01:00:00';
```

📗 **Expected output**

![sensordata where device_name](https://user-images.githubusercontent.com/23346205/97318153-f2c6fc80-1841-11eb-8c77-9aefed902d61.png)

-->

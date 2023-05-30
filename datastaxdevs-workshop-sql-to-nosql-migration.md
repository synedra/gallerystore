<h2><a class="anchor" aria-hidden="true" id="from-sql-to-nosql-a-migration-path"> </a>🎓🔥 From SQL to NoSQL, a migration path</h2>
<p><a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p><img src="https://user-images.githubusercontent.com/23346205/113427767-9f824880-93a3-11eb-8461-3689a13882a6.jpeg?raw=true" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="https://youtu.be/tNvBjY8izSk" target="_blank">Workshop video</a></li>
<li><a href="./slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://bit.ly/cassandra-workshop" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h2>
<img src="https://user-images.githubusercontent.com/1742301/113891771-aeaf2f00-97c5-11eb-844e-c4df5d7c4cc9.png" width="200" align="right" />
<p>Don't forget to complete your upgrade and get your verified skill badge! Finish and submit your homework!</p>
<ol>
<li>Complete the practice steps 1-4 from this repository as described below. Make screenshots of the last step (load data with DSBulk)</li>
<li>Complete scenario <a href="https://www.datastax.com/dev/scenario/try-it-out-cassandra-data-modeling" target="_blank">Cassandra Data Modeling</a> and make a screenshot of the &quot;congratulations&quot; page.</li>
<li>Submit your homework <a href="https://github.com/datastaxdevs/workshop-sql-to-nosql-migration/issues/new?assignees=HadesArchitect&amp;labels=homework%2C+pending&amp;template=homework-assignment.md&amp;title=%5BHW%5D+%3CNAME%3E" target="_blank">here</a></li>
</ol>
<p>That's it, you are done! Expect an email next week!</p>
<h2><a class="anchor" aria-hidden="true" id="table-of-content"> </a>Table of content</h2>
<ol>
<li><a href="#1-create-your-astra-db-instance" target="_blank">Create your Astra DB Instance</a></li>
<li><a href="#2-create-petclinic-nosql-data-model" target="_blank">Create petclinic NoSQL data model</a></li>
<li><a href="#3-generate-your-astra-application-token-and-service-account" target="_blank">Generate your Astra application token and service account</a></li>
<li><a href="#4-transform-and-load-data-with-dsbulk" target="_blank">Load data into Astra DB with DSBulk</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="1-create-your-astra-db-instance"> </a>1. Create your Astra DB instance</h2>
<p><code>ASTRA</code> service is available at url <a href="https://dtsx.io/workshop" target="_blank">https://astra.datastax.com</a>. <code>ASTRA</code> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. <strong>No credit card or any payment required</strong>, $25.00 USD credit every month, roughly 5M writes, 30M reads, 40GB storage monthly - <strong>sufficient to run small production workloads</strong>.</p>
<h3><a class="anchor" aria-hidden="true" id="step-1a-register-if-needed-and-sign-in-to-astra-db-you-can-use-your-code-github-code-code-google-code-accounts-or-register-with-an-code-email-code"> </a>✅ Step 1a. Register (if needed) and Sign In to Astra DB : You can use your <code>Github</code>, <code>Google</code> accounts or register with an <code>email</code>.</h3>
<p>Make sure to chose a password with minimum 8 characters, containing upper and lowercase letters, at least one number and special character</p>
<ul>
<li><a href="https://dtsx.io/workshop" target="_blank">Registration Page</a></li>
</ul>
<p><img src="https://user-images.githubusercontent.com/23346205/113758960-84387580-96e2-11eb-96dc-27448cf0d55f.png" alt="Registration Image" /></p>
<ul>
<li><a href="https://dtsx.io/workshop" target="_blank">Authentication Page</a></li>
</ul>
<p><img src="https://user-images.githubusercontent.com/23346205/113758903-6ec34b80-96e2-11eb-990d-49e8a381cb6d.png" alt="Login Image" /></p>
<h3><a class="anchor" aria-hidden="true" id="step-1b-create-a-pay-as-you-go-plan"> </a>✅ Step 1b. Create a &quot;pay as you go&quot; plan</h3>
<p>Follow this <a href="https://docs.datastax.com/en/astra/docs/creating-your-astra-database.html" target="_blank">guide</a> and use the values provided below, to set up a pay as you go database with a <strong>FREE</strong> $25 monthly credit.</p>
<table>
<thead>
<tr>
<th>Parameter</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td>Database name</td>
<td>sql_to_nosql_db</td>
</tr>
<tr>
<td>Keyspace name</td>
<td>spring_petclinic</td>
</tr>
</tbody>
</table>
<h2><a class="anchor" aria-hidden="true" id="2-create-petclinic-nosql-data-model"> </a>2. Create petclinic NoSQL data model</h2>
<p>Ok, now that you have a database created the next step is to create a tables to work with.</p>
<h3><a class="anchor" aria-hidden="true" id="step-2a-navigate-to-the-cql-console-and-login-to-the-database"> </a>✅ Step 2a. Navigate to the CQL Console and login to the database</h3>
<p>In the Summary screen for your database, select <strong><em>CQL Console</em></strong> from the top menu in the main window. This will take you to the CQL Console and automatically log you in.</p>
<h3><a class="anchor" aria-hidden="true" id="step-2b-describe-keyspaces-and-use-killrvideo"> </a>✅ Step 2b. Describe keyspaces and USE killrvideo</h3>
<p>Ok, now we're ready to rock. Creating tables is quite easy, but before we create one we need to tell the database which keyspace we are working with.</p>
<p>First, let's <strong><em>DESCRIBE</em></strong> all of the keyspaces that are in the database. This will give us a list of the available keyspaces.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre><code>desc KEYSPACES;
</code></pre>
<p><em>&quot;desc&quot; is short for &quot;describe&quot;, either is valid</em></p>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/113758501-f5c3f400-96e1-11eb-8f40-4eb2c9b8c2c4.png" alt="Screen Shot 2021-04-06 at 2 11 09 PM" /></p>
<p>Depending on your setup you might see a different set of keyspaces then in the image. The one we care about for now is <strong><em>spring_petclinic</em></strong>.</p>
<p>From here, execute the <strong><em>USE</em></strong> command with the <strong><em>spring_petclinic</em></strong> keyspace to tell the database our context is within <strong><em>spring_petclinic</em></strong>.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre><code>use spring_petclinic;
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/113758637-2015b180-96e2-11eb-85f0-a53c9a6a604a.png" alt="Screen Shot 2021-04-06 at 2 12 24 PM" /></p>
<p>Notice how the prompt displays <code>token@cqlsh:spring_petclinic&gt;</code> informing us we are <strong>using</strong> the <strong><em>spring_petclinic</em></strong> keyspace. Now we are ready to create our tables.</p>
<h3><a class="anchor" aria-hidden="true" id="2c-create-tables"> </a>✅ 2c. Create tables</h3>
<ul>
<li><em>Execute the following Cassandra Query Language. Copy and paste the following statements into your CQL Console</em></li>
</ul>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="sql"><code>use spring_petclinic;

DROP INDEX IF EXISTS petclinic_idx_vetname;
DROP INDEX IF EXISTS petclinic_idx_ownername;
DROP TABLE IF EXISTS petclinic_vet;
DROP TABLE IF EXISTS petclinic_vet_by_specialty;
DROP TABLE IF EXISTS petclinic_reference_lists;
DROP TABLE IF EXISTS petclinic_owner;
DROP TABLE IF EXISTS petclinic_pet_by_owner;
DROP TABLE IF EXISTS petclinic_visit_by_pet;

/** A vet can have multiple specialties. */
CREATE TABLE IF NOT EXISTS petclinic_vet (
  id          uuid,
  first_name  text,
  last_name   text,
  specialties set&lt;text&gt;,
  PRIMARY KEY ((id))
);


/** We could search veterinarian by their names. */
CREATE INDEX IF NOT EXISTS petclinic_idx_vetname ON petclinic_vet(last_name);

/** We may want to list all radiologists. */
CREATE TABLE IF NOT EXISTS petclinic_vet_by_specialty (
 specialty   text,
 vet_id      uuid,
 first_name  text,
 last_name   text,
 PRIMARY KEY ((specialty), vet_id)
);

/** 
 * Here we want all values on a single node, avoiding full scan. 
 * We pick am unordered set to avoid duplication, list to be sorted at ui side. 
 */
CREATE TABLE IF NOT EXISTS petclinic_reference_lists (
  list_name text,
  values set&lt;text&gt;,
  PRIMARY KEY ((list_name))
);

/** Expecting a combobox list references all specialties. */
INSERT INTO petclinic_reference_lists(list_name, values) 
VALUES ('vet_specialty', {'radiology', 'dentistry', 'surgery'});

CREATE TABLE IF NOT EXISTS petclinic_owner (
  id         uuid,
  first_name text,
  last_name  text,
  address    text,
  city       text,
  telephone  text,
  PRIMARY KEY ((id))
);

/** We could search veterinarians by their names. */
CREATE INDEX IF NOT EXISTS petclinic_idx_ownername ON petclinic_owner(last_name);

CREATE TABLE IF NOT EXISTS petclinic_pet_by_owner (
  owner_id   uuid,
  pet_id     uuid,
  pet_type   text,
  name       text,
  birth_date date,
  PRIMARY KEY ((owner_id), pet_id)
);
CREATE TABLE IF NOT EXISTS petclinic_visit_by_pet (
   pet_id      uuid,
   visit_id    uuid,
   visit_date  date,
   description text,
   PRIMARY KEY ((pet_id), visit_id)
);

INSERT INTO petclinic_reference_lists(list_name, values) 
VALUES ('pet_type ', {'bird', 'cat', 'dog', 'lizard','hamster','snake'});
</code></pre>
<ul>
<li><em>You should now have a set of petclinic tables</em></li>
</ul>
<pre lang="sql"><code>describe tables;
</code></pre>
<p>📗 <strong>Expected output</strong></p>
<p><img src="https://user-images.githubusercontent.com/23346205/113874468-d2ea1c00-9783-11eb-8f7f-e0438682311c.png" alt="Screen Shot 2021-04-07 at 9 29 25 AM" /></p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="3-generate-your-astra-application-token"> </a>3. Generate your Astra application token</h2>
<p>In order for you to securely connect to your Cassandra database on Astra DB you need to generate an application token. The cool thing once you generate this once you can then use it for any of your applications or tools to talk to your database.</p>
<h3><a class="anchor" aria-hidden="true" id="3a-generate-your-application-token"> </a>✅ 3a. Generate your application token</h3>
<p>If you don't already have one follow the instructions <a href="https://docs.datastax.com/en/astra/docs/manage-application-tokens.html#_create_application_token" target="_blank"><strong>HERE</strong></a> to generate your new token. <strong>Don't forget to download it once created because you will not be able to see it again</strong> without generating a new one.</p>
<p>Once you <strong>DOWNLOAD</strong> the token if you view the contents they should look something like this:</p>
<pre lang="shell"><code>&quot;Client Id&quot;,&quot;Client Secret&quot;,&quot;Token&quot;,&quot;Role&quot;
&quot;fdsfdslKFdLFdslDFFDjf&quot;,&quot;aaaaaaadsdadasdasdasdfsadfldsjfldjdsaldjasljdasljdsaljdasljdasljdlasjdal-FLflirFdfl.lfjdfdsljfjdl+fdlffkdsslfd&quot;,&quot;AstraCS:ppppdspfdsdslfjsdlfjdlj:540524888-04384039399999999999999999&quot;,&quot;Admin User&quot;
</code></pre>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token 
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<p>You'll need to use this in a moment to authenticate with DSBulk so <strong>keep it handy</strong>.</p>
<h2><a class="anchor" aria-hidden="true" id="4-transform-and-load-data-with-dsbulk"> </a>4. Transform and load data with DSBulk</h2>
<p>In order to use DSBulk you need to download and install it. While you can do this locally if you would like following the instructions <a href="https://docs.datastax.com/en/astra/docs/loading-and-unloading-data-with-datastax-bulk-loader.html#_prerequisites" target="_blank"><strong>HERE</strong></a> we've already provided it for you using <strong>GitPod</strong>. Click the button below to launch your instance.</p>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-sql-to-nosql-migration" target="_blank"><img src="https://img.shields.io/badge/Gitpod-Open--in--Gitpod-blue?logo=gitpod" alt="Open in Gitpod" /></a></p>
<h3><a class="anchor" aria-hidden="true" id="4a-get-your-secure-connect-bundle"> </a>✅ 4a. Get your secure connect bundle</h3>
<p>We're going to need a secure connect bundle to talk to our Astra DB instance with an external app. The bundle contains all of the information about where our cluster is up on the cloud and how to securly connect. After you launched GitPod you may have noticed a prompt asking you for your <code>Token</code>.</p>
<p><img src="https://user-images.githubusercontent.com/23346205/113955083-12971f00-97e9-11eb-8110-a5a7db1b9c83.png" alt="Screen Shot 2021-04-07 at 9 33 16 PM" /></p>
<p>Now, you will see a prompt asking for your <strong>cluster ID</strong>.</p>
<p><img src="https://user-images.githubusercontent.com/23346205/113955786-67876500-97ea-11eb-8121-6651d44cc4ad.png" alt="Screen Shot 2021-04-07 at 9 43 15 PM" /></p>
<p>Go back to the Astra DB UI dashboard screen and:</p>
<ol>
<li>choose the <code>sql_to_nosql_db</code> database</li>
<li>copy the Cluster ID using the copy widget</li>
</ol>
<p><img src="https://user-images.githubusercontent.com/23346205/113872647-0e83e680-9782-11eb-9dc3-340633466a41.png" alt="Screen Shot 2021-04-07 at 9 15 26 AM" /></p>
<p>Finally, paste the DB ID into prompt in GitPod and hit <strong><code>ENTER</code></strong>. That's it, you should have your bundle.</p>
<p>📗 <strong>Expected output</strong><br />
<img src="https://user-images.githubusercontent.com/23346205/113955908-9d2c4e00-97ea-11eb-8d3c-a9ff44c8c35f.png" alt="Screen Shot 2021-04-07 at 9 43 32 PM" /></p>
<h3><a class="anchor" aria-hidden="true" id="4b-load-code-owner-code-table-sql-export-into-code-petclinic-owner-code-nosql-table"> </a>✅ 4b. Load <code>owner</code> table SQL export into <code>petclinic_owner</code> NoSQL table</h3>
<p>Ok, we're going to use DSBulk in this section to:</p>
<ul>
<li>connect to our Astra DB database using the <strong>CLIENT ID</strong> and <strong>CLIENT SECRET</strong> we created earlier in step 3 and the secure connect bundle <code>astra-creds.zip</code></li>
<li>load data from the owner.csv file (exported from our relational DB <code>owner</code> table)</li>
<li>do this using a regular <strong>INSERT</strong> statement that maps values from our CSV file while <strong>transforming</strong> data with <code>UUID()</code></li>
<li>use CSV file headers to identify what data each delimited column contains</li>
<li>and finally set our delimiter to use &quot;;&quot;</li>
</ul>
<p>Once this command is constructed it should look something like this:<br />
<img width="1184" alt="Screen Shot 2021-04-07 at 8 05 22 AM" src="https://user-images.githubusercontent.com/23346205/113863760-0d4dbc00-9778-11eb-95cb-ffdb9742525d.png"></p>
<p><em>An example of how to construct the above DSBulk command can be found <a href="https://docs.datastax.com/en/dsbulk/doc/dsbulk/reference/dsbulkLoad.html" target="_blank"><strong>HERE</strong></a>.</em></p>
<p>We've made this a little easier by constructing the command for you. Just run the <code>dsbulk.sh</code> script. This will ask for the <strong>CLIENT ID</strong> and <strong>CLIENT SECRET</strong> you created earlier. When it asks, just paste in your value and hit <strong><code>ENTER</code></strong> to go to the next step.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="shell"><code>bash dsbulk.sh
</code></pre>
<p>📗 <strong>Expected output</strong><br />
<img src="https://user-images.githubusercontent.com/23346205/113866689-9c100800-977b-11eb-95dc-b990d268ac9d.png" alt="Screen Shot 2021-04-07 at 8 29 07 AM" /></p>
<p>Now, go back to <code>CQL Console</code> in your Astra DB UI and view the data from the <code>petclinic_owner</code> table.</p>
<p>📘 <strong>Command to execute</strong></p>
<pre lang="SQL"><code>SELECT * FROM petclinic_owner;
</code></pre>
<p>📗 <strong>Expected output</strong><br />
<img src="https://user-images.githubusercontent.com/23346205/113867461-91a23e00-977c-11eb-93b9-0da86fe7e2d7.png" alt="Screen Shot 2021-04-07 at 8 37 54 AM" /></p>
<p>Awesome! You now have data in your new NoSQL table.</p>
<h3><a class="anchor" aria-hidden="true" id="4b-let-s-break-this-down-a-bit"> </a>✅ 4b. Let's break this down a bit</h3>
<p>So great, you just ran the DSBulk command and something happened, but lets explain this a bit more.</p>
<p>First thing, here is the source CSV we are using generated from our SQL relational database for the <code>owner</code> table.<br />
<img width="636" alt="Screen Shot 2021-04-07 at 8 11 49 AM" src="https://user-images.githubusercontent.com/23346205/113864466-eba10480-9778-11eb-9324-1fe57aedbc9d.png"></p>
<p>If you remember from our discussion and the <a href="./slides.pdf" target="_blank"><strong>slide deck</strong></a> when moving into something like Cassandra we don't tend to use INTegers for IDs. We use UUIDs instead. This is to ensure IDs are truly unique when using a distributed system. With that, we need to transform the INT based IDs from the SQL data to UUIDs. We do this by using the <code>**UUID()**</code> function in our <strong>INSERT</strong> statement.</p>
<img width="855" alt="Screen Shot 2021-04-07 at 9 37 31 AM" src="https://user-images.githubusercontent.com/23346205/113875678-02e5ef00-9785-11eb-9a51-8666cb9bb885.png">
<p>This will generate UUIDs for us as data is inserted into our new Cassandra table.</p>
<p>Also, notice the header line in our CSV.</p>
<img width="503" alt="Screen Shot 2021-04-07 at 9 44 17 AM" src="https://user-images.githubusercontent.com/23346205/113876552-d7173900-9785-11eb-8745-dad34f18740c.png">
<p>If you look back to the <strong>INSERT</strong> statement we used you may have noticed something like</p>
<pre lang="sql"><code>VALUES (:first_name,:last_name,:address,:city,:telephone,UUID())
</code></pre>
<p>where you see items <code>:first_name</code> and <code>:last_name</code>. These are bindings. They are binding the values passed into the <strong>INSERT</strong> statement to the each column by the name of the column. You can use this to map values all sorts of ways and this just scratches the surface, but I think you get the idea.</p>
<h2><a class="anchor" aria-hidden="true" id="the-end"> </a>THE END</h2>
<p>Whoohoo! Congrats on making it to the end. While this workshop just touches on this process from a pretty high level hopefully it gives you an idea of the kinds of things you need to do and where to start. To learn more about what you can do with DSBulk take a look at the docs <a href="https://docs.datastax.com/en/dsbulk/doc/dsbulk/reference/dsbulkCmd.html" target="_blank"><strong>HERE</strong></a>. Also, don't forget that you can use Astra DB to experiment and play around with your data model for <strong>FREE</strong> well within the limits of the $25 monthly credit.</p>

<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="workshop-spring-petclinic-reactive"> </a>Workshop 🐈 Spring PetClinic Reactive 🐕</h1>
<img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/badge-petclinic.png?raw=true" width="200" align="right" />
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-spring-reactive" target="_blank"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod" alt="Gitpod ready-to-code" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<blockquote>
<p>⚠️ Difficulty: <strong><code>Intermediate</code>, we expect you to already know Java and Spring.</strong></p>
</blockquote>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/banner.png?raw=true" alt="banner" /></p>
<p>This sample is a fully reactive version of the <a href="https://projects.spring.io/spring-petclinic/" target="_blank">Spring PetClinic</a> application using <a href="https://docs.spring.io/spring-framework/docs/current/reference/html/web-reactive.html">Spring WebFlux</a></p>
<!--- ENDEXCLUDE --->
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>📋 Table of contents</h2>
<img src="https://github.com/datastaxdevs/workshop-spring-reactive/blob/master/doc/img/ui-veterinarians.png?raw=true" align="right" width="400px"/>
<ol>
<li><a href="#1-objectives" target="_blank">Objectives</a></li>
<li><a href="#2-frequently-asked-questions" target="_blank">Frequently asked questions</a></li>
<li><a href="#3-materials-for-the-session" target="_blank">Materials for the Session</a></li>
<li><a href="#4-create-astra-db-instance" target="_blank">Create your Database</a></li>
<li><a href="#5-create-astra-token" target="_blank">Create your Token</a></li>
<li><a href="#6-start-and-setup-gitpod" target="_blank">Start and setup Gitpod</a></li>
<li><a href="#7-create-your-schema-with-cql-console" target="_blank">Create your Schema</a></li>
<li><a href="#8-working-with-cassandra-drivers" target="_blank">Working with Cassandra Drivers</a></li>
<li><a href="#9-working-with-spring-data" target="_blank">Working with Spring Data</a></li>
<li><a href="#10-working-with-spring-webflux" target="_blank">Working with Spring WebFlux</a></li>
<li><a href="#11-angular-user-interface" target="_blank">Working with Angular UI</a></li>
<li><a href="#12-homeworks" target="_blank">Homeworks</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="1-objectives"> </a>1. Objectives</h2>
<p>✅ Learn how Apache Cassandra <strong>data modelling</strong> is different from relational</p>
<p>✅ Understand how <strong>Java Applications</strong> connect to Apache Cassandra™</p>
<p>✅ Learn about <strong>Spring and Spring Boot</strong> Microservices</p>
<p>✅ Understand what are the benefits of <strong>Reactive Programming</strong></p>
<p>✅ <strong>Get a working full stack application Spring Boot-Data-Reactive including a Node.js application for populating data</strong></p>
<h2><a class="anchor" aria-hidden="true" id="2-frequently-asked-questions"> </a>2. Frequently asked questions</h2>
<p/>
<details>
<summary><b> 1️⃣ Can I run this workshop on my computer?</b></summary>
<hr>
<p>There is nothing preventing you from running the workshop on your own machine, If you do so, you will need the following
<ol>
<li><b>git</b> installed on your local system
<li><b>JDK 8+</b> installed on your local system
<li><b>Maven 3.6+</b> installed on your local system
<li><a href="https://www.whitesourcesoftware.com/free-developer-tools/blog/update-node-js/" target="_blank" >Node 15 and npm 7 or later</a>
</ol>
</p>
In this readme, we try to provide instructions for local development as well - but keep in mind that the main focus is development on Gitpod, hence <strong>We can't guarantee live support</strong> about local development in order to keep on track with the schedule. However, we will do our best to give you the info you need to succeed.
</details>
<p/>
<details>
<summary><b> 2️⃣ What other prerequisites are required?</b></summary>
<hr>
<ul>
<li>You will need a GitHub account
<li>You will also need an Astra account: don't worry, we'll work through that in the following
</ul>
</p>
</details>
<p/>
<details>
<summary><b> 3️⃣ Do I need to pay for anything for this workshop?</b></summary>
<hr>
<b>No.</b> All tools and services we provide here are FREE.
</details>
<p/>
<details>
<summary><b> 4️⃣ Will I get a certificate if I attend this workshop?</b></summary>
<hr>
Attending the session is not enough. You need to complete the homeworks detailed below and you will get a nice badge.
</details>
<p/>
<h2><a class="anchor" aria-hidden="true" id="3-materials-for-the-session"> </a>3. Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to work at your own pace,<br />
we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="doc/slides/slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://bit.ly/cassandra-workshop" target="_blank">Datastax Developers Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="4-create-astra-db-instance"> </a>4. Create Astra DB Instance</h2>
<h4><a class="anchor" aria-hidden="true" id="4a-register-or-sign-to-astra"> </a>✅ 4a.Register or Sign to Astra</h4>
<blockquote>
<p>📖 DOCUMENTATION: <a href="https://awesome-astra.github.io/docs/pages/astra/create-account/" target="_blank">How to create an Astra Account</a></p>
</blockquote>
<p><a href="https://astra.dev/4-6" target="_blank"><img src="https://dabuttonfactory.com/button.png?t=+Connect+to+Astra&amp;f=Open+Sans-Bold&amp;ts=12&amp;tc=fff&amp;hp=23&amp;vp=16&amp;c=11&amp;bgt=gradient&amp;bgc=0b5394&amp;ebgc=073763" alt="" /></a></p>
<h4><a class="anchor" aria-hidden="true" id="4c-create-a-database-or-resume-your-database"> </a>✅ 4c.Create a Database (or resume your database)</h4>
<blockquote>
<p>📖 DOCUMENTATION: <a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/" target="_blank">How create a Database</a></p>
</blockquote>
<p>Use the following values:</p>
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
<td><code>workshops</code></td>
</tr>
<tr>
<td>Keyspace name</td>
<td><code>spring_petclinic</code></td>
</tr>
<tr>
<td>Region name</td>
<td>The one you like, no difference</td>
</tr>
</tbody>
</table>
<p><strong>Walkthrough:</strong> <em>The Walkthrough mentions the wrong keyspace, make sure to use <code>spring_petclinic</code></em></p>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/astra-create-db.gif?raw=true" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="5-create-astra-token"> </a>5. Create Astra Token</h2>
<p>To connect to the database from Java code we need some credentials, this is what we are going to do here.</p>
<blockquote>
<p>📖 DOCUMENTATION: <a href="https://awesome-astra.github.io/docs/pages/astra/create-token/#c-procedure" target="_blank">How to create an Astra Token</a></p>
</blockquote>
<table>
<thead>
<tr>
<th>Parameter</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td>Role</td>
<td><code>Database Administrator</code></td>
</tr>
</tbody>
</table>
<p><strong>👁️ Walkthrough</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/astra-create-token.gif?raw=true" alt="image" /></p>
<blockquote>
<p>⚠️ We will use the third argument called <code>TOKEN</code> that looks like <code>AstraCS:...</code> make sure you copy it in the clipboard.</p>
</blockquote>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token 
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="6-start-and-setup-gitpod"> </a>6. Start and Setup Gitpod</h3>
<h4><a class="anchor" aria-hidden="true" id="6a-open-gitpod"> </a>✅ 6a. Open Gitpod</h4>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-spring-reactive" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<p>When you first launch gitpod, it builds the image.<br />
<img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/building-workspace.png?raw=true" alt="image" /></p>
<p>This is the home Screen. It is a VSCode instance in the cloud. As you can see, notice multiple panels are open with 2 terminals, the readme and the explorer.</p>
<h4><a class="anchor" aria-hidden="true" id="6b-setup-cqlsh"> </a>✅ 6b. Setup Cqlsh</h4>
<h4><a class="anchor" aria-hidden="true" id="copy-paste-in-gitpod"> </a>⚠️ COPY-PASTE IN GITPOD</h4>
<blockquote>
<p><em>Some browsers might block the CTRL+C and CRTL+V if that happen you can paste with right-click and paste.</em></p>
</blockquote>
<blockquote>
<p><em>The first time you paste something in Gitpod your might have a pop-up telling you to accept the command</em></p>
</blockquote>
<ul>
<li>There 3 terminal panel on the bottom right hand corner. The last <code>setup-cqlsh:bash</code> got the focus.</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/setup-cqlsh.png?raw=true" alt="cqlsh" /></p>
<ul>
<li>If you look at the terminal windows it is asking for your Astra TOKEN. Please enter the value of your Token it should look like <code>AstraCS....</code> then press enter.</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/gitpod-home.png?raw=true" alt="image" /></p>
<ul>
<li>The initialization will go on for you to get access to <code>CQLSH</code> directly.</li>
</ul>
<pre><code>------------------------------------------------------------
--            Installation of Cqlsh                      ---
------------------------------------------------------------

[OK] - Tools folder has been created
[OK] - Package has been downloaded
[OK] - We will now as you about your ASTRA TOKEN (AstraCS....)
Checking your credentials...

Login to Astra at https://dstx.io/workshops
After login, you can create a database.
Click on your name in the left-hand column
In the dropdown, select &quot;Organization Settings&quot;
    Select &quot;Token Management&quot; from the left-hand column
    Select &quot;Database Administrator&quot; in the Role dropdown
    Click &quot;Generate Token&quot;
    Save to CSV if you want to access it later
✔ Please paste the Database Admin Token here
***********
Credentials set up, checking database
Looking for workshops
     workshops: Current status is ACTIVE
         ... status is ACTIVE
    existing workshops database found.
Looking for spring_petclinic keyspace
    keyspace spring_petclinic already exists
Setting up secure bundle

Deleted file: cqlshrc
[OK] - Database ID is 3ed83de7-d97f-4fb6-bf9f-82e9f7eafa23
[OK] - Database REGION is eu-west-1
[OK] - Database TOKEN is ************
Picked up JAVA_TOOL_OPTIONS:  -Xmx3435m
[OK] - Secure Connect Bundle downloaded
[OK] - Launching CQLSH....
Connected to cndb at 127.0.0.1:9042.
[cqlsh 6.8.0 | Cassandra 4.0.0.6816 | CQL spec 3.4.5 | Native protocol v4]
Use HELP for help.
token@cqlsh&gt;
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="6c-validate-cqlsh"> </a>✅ 6c. Validate CqlSH</h4>
<ul>
<li>You can now list the keyspaces (like oracle schemas) available.</li>
</ul>
<pre lang="sql"><code>describe keyspaces;
</code></pre>
<p>Output:</p>
<pre><code>system_virtual_schema  system_auth   data_endpoint_auth  system_traces
temporal_visibility    system_views  better_reads        ecommerce
netflix                system        spring_petclinic    todos
system_schema          datastax_sla  native_java         feeds_reader
</code></pre>
<ul>
<li>Select the keyspace we will work with today <code>spring_petclinic</code></li>
</ul>
<pre lang="sql"><code>use spring_petclinic;
</code></pre>
<ul>
<li>You can quit wit</li>
</ul>
<pre lang="sql"><code>quit
</code></pre>
<ul>
<li>You can now open the console any time with</li>
</ul>
<pre><code>/workspace/workshop-spring-reactive/cqlsh
</code></pre>
<p>The other Terminal are dedicated for the frontend and the backend.</p>
<h4><a class="anchor" aria-hidden="true" id="6d-know-your-gitpod"> </a>✅ 6d. Know your gitpod</h4>
<ul>
<li><strong>📘 All tools are installed</strong></li>
</ul>
<p>Gitpod provides everything you need to work with JAVA, Node.JS (but also python, docker and many more). Open a new <strong>TERMINAL</strong> and enter the following command.</p>
<ul>
<li>Check Java Version</li>
</ul>
<pre lang="bash"><code>java --version
</code></pre>
<blockquote>
<p>🖥️ Expected output</p>
</blockquote>
<pre><code>Picked up JAVA_TOOL_OPTIONS: -Xmx2576m
openjdk 11.0.11 2021-04-20 LTS
OpenJDK Runtime Environment Zulu11.48+21-CA (build 11.0.11+9-LTS)
OpenJDK 64-Bit Server VM Zulu11.48+21-CA (build 11.0.11+9-LTS, mixed mode)
</code></pre>
<ul>
<li>Check Maven version</li>
</ul>
<pre lang="bash"><code>mvn -v
</code></pre>
<blockquote>
<p>🖥️ Expected output</p>
</blockquote>
<pre><code>Picked up JAVA_TOOL_OPTIONS: -Xmx2576m
Apache Maven 3.8.1 (05c21c65bdfed0f71a2f2ada8b84da59348c4c5d)
Maven home: /home/gitpod/.sdkman/candidates/maven/current
Java version: 11.0.11, vendor: Azul Systems, Inc., runtime: /home/gitpod/.sdkman/candidates/java/11.0.11.fx-zulu
Default locale: en_US, platform encoding: UTF-8
OS name: &quot;linux&quot;, version: &quot;5.4.0-1051-gke&quot;, arch: &quot;amd64&quot;, family: &quot;unix&quot;
</code></pre>
<ul>
<li>Check Node version</li>
</ul>
<pre lang="bash"><code>node -v
</code></pre>
<blockquote>
<p>🖥️ Expected output</p>
</blockquote>
<pre><code>v14.17.0
</code></pre>
<ul>
<li>Check NPM version</li>
</ul>
<pre lang="bash"><code>npm -v
</code></pre>
<blockquote>
<p>🖥️ Expected output</p>
</blockquote>
<pre><code>6.14.13
</code></pre>
<ul>
<li><strong>📘 Remote explorer</strong></li>
</ul>
<p>In the tutorial we will also work with the preview and the remote explorer. To switch from source explorer to remote explorer click on dekstop icon on the menu bar in the left (6th item from top).</p>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/gitpod-remote-explorer.png?raw=true" alt="image" /></p>
<ul>
<li><strong>📘 Simple Browser preview</strong></li>
</ul>
<p>As of now <strong>nothing IS running</strong> but if you want to open a preview or a new browser use the icons as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/gitpod-preview.png?raw=true" alt="image" /></p>
<h4><a class="anchor" aria-hidden="true" id="6e-validate-your-setup"> </a>✅ 6e. Validate your setup</h4>
<ul>
<li>All variables you will need are in file called <code>.env </code>. We will source this file to define the env variables when needed.</li>
</ul>
<pre lang="bash"><code>cat /workspace/workshop-spring-reactive/.env
</code></pre>
<ul>
<li>Take a look at the code of <a href="https://github.com/datastaxdevs/workshop-spring-reactive/blob/master/src/test/java/com/datastax/workshop/petclinic/Test01_Connectivity.java" target="_blank"><code>Test01_Connectivity</code></a> here we use the <code>CqlSession</code> and <code>AstraClient</code> to show some infromation regarding your Astra DB.</li>
</ul>
<pre><code>gp open gp open /workspace/workshop-spring-reactive/src/test/java/com/datastax/workshop/petclinic/Test01_Connectivity.java
</code></pre>
<p>Execute the test with:</p>
<pre lang="bash"><code>cd /workspace/workshop-spring-reactive
set -a
source /workspace/workshop-spring-reactive/.env
set +a
mvn test -Dtest=com.datastax.workshop.petclinic.Test01_Connectivity
</code></pre>
<blockquote>
<p>🖥️ Expected output</p>
</blockquote>
<pre lang="bash"><code>== CQL_SESSION ==
+ Your Keyspace: spring_petclinic
+ Vet Specialty:
[dentistry, radiology, surgery]
== ASTRA ==
+ Your OrganizationID: f9460f14-9879-4ebe-83f2-48d3f3dce13c
+ Your Databases:
workshops : id=3ed83de7-d97f-4fb6-bf9f-82e9f7eafa23, region=eu-west-1
</code></pre>
<p>You are all set.</p>
<h2><a class="anchor" aria-hidden="true" id="7-create-your-schema-with-cql-console"> </a>7. Create your schema with CQL Console</h2>
<h4><a class="anchor" aria-hidden="true" id="7a-open-cqlsh-console"> </a>✅ 7a. Open cqlSH Console</h4>
<pre><code>set -a
source /workspace/workshop-spring-reactive/.env
set +a
/workspace/workshop-spring-reactive/cqlsh
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="7b-use-the-proper-keyspace"> </a>✅ 7b. Use the proper keyspace</h4>
<pre lang="sql"><code>use spring_petclinic;
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="7c-create-your-objects"> </a>✅ 7c. Create your objects</h4>
<pre lang="sql"><code>use spring_petclinic;

DROP INDEX IF EXISTS petclinic_idx_vetname;
DROP INDEX IF EXISTS petclinic_idx_ownername;
DROP TABLE IF EXISTS petclinic_vet;
DROP TABLE IF EXISTS petclinic_vet_by_specialty;
DROP TABLE IF EXISTS petclinic_reference_lists;
DROP TABLE IF EXISTS petclinic_owner;
DROP TABLE IF EXISTS petclinic_pet_by_owner;
DROP TABLE IF EXISTS petclinic_visit_by_pet;

CREATE TABLE IF NOT EXISTS petclinic_vet (
  id          uuid,
  first_name  text,
  last_name   text,
  specialties set&lt;text&gt;,
  PRIMARY KEY ((id))
);


CREATE TABLE IF NOT EXISTS petclinic_vet_by_specialty (
 specialty   text,
 vet_id      uuid,
 first_name  text,
 last_name   text,
 PRIMARY KEY ((specialty), vet_id)
);

CREATE TABLE IF NOT EXISTS petclinic_owner (
  id         uuid,
  first_name text,
  last_name  text,
  address    text,
  city       text,
  telephone  text,
  PRIMARY KEY ((id))
);

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

CREATE TABLE IF NOT EXISTS petclinic_reference_lists (
  list_name text,
  values set&lt;text&gt;,
  PRIMARY KEY ((list_name))
);

/** We could search veterinarians by their names. */
CREATE INDEX IF NOT EXISTS petclinic_idx_ownername ON petclinic_owner(last_name);
/** We could search vet by their names. */
CREATE INDEX IF NOT EXISTS petclinic_idx_vetname ON petclinic_vet(last_name);
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="7d-check-our-6-tables"> </a>✅ 7d. Check our 6 tables</h4>
<pre lang="sql"><code>describe tables;
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="7e-insert-reference-data"> </a>✅ 7e. Insert Reference Data</h4>
<pre lang="sql"><code>INSERT INTO petclinic_reference_lists(list_name, values)
VALUES ('pet_type ', {'bird', 'cat', 'dog', 'lizard','hamster','snake'});

INSERT INTO petclinic_reference_lists(list_name, values)
VALUES ('vet_specialty', {'radiology', 'dentistry', 'surgery'});
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="8-working-with-cassandra-drivers"> </a>8. Working with Cassandra Drivers</h2>
<h4><a class="anchor" aria-hidden="true" id="8a-the-cqlsession"> </a>✅ 8a. The CqlSession</h4>
<ul>
<li>Exist the CqlSH or open a new terminal to take a look on configuration file <code>application.yml</code>.</li>
</ul>
<pre lang="bash"><code>gp open /workspace/workshop-spring-reactive/src/main/resources/application.yml
</code></pre>
<ul>
<li>
<p>The spring Configuration will use load keys coming from <code>astra.*</code> and initialize the object <code>CqlSession</code>. A first way to implement a DAO is to use this object explicitly. Check the code at <a href="https://github.com/datastaxdevs/workshop-spring-reactive/blob/master/src/test/java/com/datastax/workshop/petclinic/Test02_DaoWithCqlSession.java" target="_blank"><code>Test02_DaoWithCqlSession</code></a></p>
</li>
<li>
<p>Take a look at the <code>DAO</code> with <code>CqlSession</code></p>
</li>
</ul>
<pre lang="bash"><code> gp open /workspace/workshop-spring-reactive/src/main/java/com/datastax/workshop/petclinic/reflist/ReferenceListReactiveDao.java
</code></pre>
<ul>
<li>Test source code (invoking the dao)</li>
</ul>
<pre lang="bash"><code>gp open gp open /workspace/workshop-spring-reactive/src/test/java/com/datastax/workshop/petclinic/Test02_DaoWithCqlSession.java
</code></pre>
<ul>
<li>Execute the test with the following:</li>
</ul>
<pre lang="bash"><code>set -a
source /workspace/workshop-spring-reactive/.env
set +a
mvn test -Dtest=com.datastax.workshop.petclinic.Test02_DaoWithCqlSession
</code></pre>
<ol>
<li>Notice how you needed to put a terminal call <code>block()</code> on line 21 or the program is not started.</li>
</ol>
<p>Project <a href="https://projectreactor.io/" target="_blank">Reactor</a> is a fourth-generation reactive library, based on the Reactive Streams specification, for building non-blocking applications on the JVM. We are using the library reactor-test introducing <code>StepVerifier</code> to ease the coding of unit tests:</p>
<pre lang="java"><code>@Test
public void should_list_vet_specialies() {
 System.out.println(referenceListDao
   .findReferenceList(&quot;vet_specialty&quot;).block());

 StepVerifier
  .create(referenceListDao.findReferenceList(&quot;vet_specialty&quot;))
  .expectNext(Set.of(&quot;dentistry&quot;, &quot;radiology&quot;, &quot;surgery&quot;))
  .expectComplete()
  .verify();
}
</code></pre>
<blockquote>
<p>🖥️ Expected output</p>
</blockquote>
<pre><code>15:34:33.926 INFO  com.datastax.workshop.petclinic.Test02_DaoWithCqlSession : Started Test02_DaoWithCqlSession in 14.782 seconds (JVM running for 16.99)
[dentistry, radiology, surgery]
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 16.42 s - in com.datastax.workshop.petclinic.Test02_DaoWithCqlSession
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="8b-the-driver-object-mapping-layer"> </a>✅ 8b. The Driver Object Mapping Layer</h4>
<p>We will illustrate this with the <code>Vet</code> in this <a href="https://github.com/datastaxdevs/workshop-spring-reactive/tree/master/src/main/java/com/datastax/workshop/petclinic/vet/db" target="_blank">package</a></p>
<ol>
<li>
<p>Define an <code>@Entity</code> where object attributes matches the table columns <a href="https://github.com/datastaxdevs/workshop-spring-reactive/blob/master/src/main/java/com/datastax/workshop/petclinic/vet/db/VetEntity.java" target="_blank"><code>VetEntity</code></a></p>
</li>
<li>
<p>Define an <code>@Dao</code> interface with only the method you want to implements <a href="https://github.com/datastaxdevs/workshop-spring-reactive/blob/master/src/main/java/com/datastax/workshop/petclinic/vet/db/VetReactiveDao.java" target="_blank"><code>VetReactiveDao</code></a></p>
</li>
</ol>
<pre lang="java"><code>@Dao
public interface VetReactiveDao {

 @Select
 MappedReactiveResultSet&lt;VetEntity&gt; findById(@NotNull UUID vetId);

 // More methods....
}
</code></pre>
<ol start="3">
<li>Define the <code>@Mapper</code> to explain how to create the <code>Dao</code> from the the Cqlsession. <a href="https://github.com/datastaxdevs/workshop-spring-reactive/blob/master/src/main/java/com/datastax/workshop/petclinic/vet/db/VetReactiveDaoMapper.java" target="_blank"><code>VetReactiveDaoMapper</code></a></li>
</ol>
<pre lang="java"><code>@Mapper
public interface VetReactiveDaoMapper {
  @DaoFactory
  VetReactiveDao vetDao(@DaoKeyspace CqlIdentifier keyspace);
}
</code></pre>
<p>Now execute the test to work with the DAO <code>Test03_DaoWithDriverObjectMapping</code></p>
<pre lang="bash"><code>set -a
source /workspace/workshop-spring-reactive/.env
set +a
mvn test -Dtest=com.datastax.workshop.petclinic.Test03_DaoWithDriverObjectMapping
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="9-working-with-spring-data"> </a>9. Working with Spring Data</h2>
<p><a href="https://spring.io/projects/spring-data" target="_blank">Spring Data</a> provides a common abstraction on top of multiple databases leveraging JPA. The quantity of code is greatly reduced by working with interfaces <code>CrudRepository</code> and entities.</p>
<ul>
<li>
<p>Define an entity <a href=""><code>VetEntitySpring</code></a> where object attributes matches the table columns. You can notice that the set of annotations is not the same as with java driver mapper.</p>
</li>
<li>
<p>Define an interface extending the <code>ReactiveCassandraRepository</code> named <code>VetRepositorySpring</code></p>
</li>
</ul>
<pre lang="java"><code>@Repository
public interface VetRepositorySpring
   extends ReactiveCassandraRepository&lt;VetEntitySpring, UUID&gt; {
}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="9a-execute-the-unit-test"> </a>✅ 9a. Execute the unit test</h4>
<p>Execute the test to work with the DAO <code>Test04_DaoWithSpringData</code></p>
<pre lang="bash"><code>set -a
source /workspace/workshop-spring-reactive/.env
set +a
mvn test -Dtest=com.datastax.workshop.petclinic.Test04_DaoWithSpringData
</code></pre>
<p>Execute the test to work with the DAO <code>Test05_DaoWithSpringDataSimple</code></p>
<pre lang="bash"><code>set -a
source /workspace/workshop-spring-reactive/.env
set +a
mvn test -Dtest=com.datastax.workshop.petclinic.Test05_DaoWithSpringDataSimple
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="10-working-with-spring-webflux"> </a>10. Working with Spring WebFlux</h2>
<blockquote>
<p><a href="https://docs.spring.io/spring-framework/docs/current/reference/html/web-reactive.html" target="_blank">Reference Documentation</a></p>
</blockquote>
<p><em>The original web framework included in the Spring Framework, Spring Web MVC, was purpose-built for the Servlet API and Servlet containers. The reactive-stack web framework, Spring WebFlux, was added later in version 5.0. It is fully non-blocking, supports Reactive Streams back pressure, and runs on such servers as Netty, Undertow, and Servlet 3.1+ containers.</em></p>
<p><em>Both web frameworks mirror the names of their source modules (spring-webmvc and spring-webflux) and co-exist side by side in the Spring Framework. Each module is optional. Applications can use one or the other module or, in some cases, both — for example, Spring MVC controllers with the reactive WebClient.</em></p>
<p>The different DAO we created is injected into a Rest controller. (same as Spring WEB)</p>
<pre lang="java"><code>@RestController
@RequestMapping(&quot;/petclinic/api/specialties&quot;)
public class VetSpecialtyController {

 @Autowired
 ReferenceListReactiveDao dao;

 @GetMapping(produces = APPLICATION_JSON_VALUE)
 public Mono&lt;ResponseEntity&lt;Set&lt;VetSpecialty&gt;&gt;&gt; getAllVetsSpecialties() {
   return refDao.findReferenceList(&quot;vet_specialty&quot;)
    .map(Set::stream)
    .map(s -&gt; s.map(VetSpecialty::new)
    .collect(Collectors.toSet()))
    .map(ResponseEntity::ok);
 }
}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="10a-execute-the-unit-test"> </a>✅ 10a. Execute the unit test</h4>
<pre lang="bash"><code>set -a
source /workspace/workshop-spring-reactive/.env
set +a
mvn test -Dtest=com.datastax.workshop.petclinic.Test06_ApiController
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="10b-start-the-application-with-swagger-ui"> </a>✅ 10b. Start the application with Swagger UI</h4>
<p>We also used SpringDOC to generate a Swagger UI interface. For more information check the class <a href="https://github.com/datastaxdevs/workshop-spring-reactive/blob/master/src/main/java/com/datastax/workshop/petclinic/conf/ApiDocumentationConfig.java" target="_blank"><code>ApiDocumentationConfig</code></a></p>
<pre lang="java"><code>@RestController
@RequestMapping(&quot;/petclinic/api/specialties&quot;)
@Api(value=&quot;/petclinic/api/specialties&quot;, tags = {&quot;Veterinarian Specialties Api&quot;})
public class VetSpecialtyController {
  //...
}
</code></pre>
<p>You can now go ahead and start the application. The application is listening on port <code>9966</code> as defined in <code>application.yaml</code> <em>(Please do not change this, this is what the user interface is looking for)</em></p>
<p>Start the application;</p>
<pre lang="bash"><code>set -a
source /workspace/workshop-spring-reactive/.env
set +a
mvn spring-boot:run
</code></pre>
<p>Open your browser on port <code>9966</code> using the the remote explorer or entering in a new terminal.</p>
<pre lang="bash"><code>gp preview &quot;$(gp url 9966)&quot;
</code></pre>
<p>You should find the Nice user interface:</p>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/swagger.png?raw=true" alt="Pet Clinic Welcome Screen" /></p>
<h4><a class="anchor" aria-hidden="true" id="10c-use-api"> </a>✅ 10c. Use API</h4>
<p>Locate the resource <code>Veterinarian Specialties Api</code> and method the specialities endpoint below to test the service.</p>
<pre lang="bash"><code>GET ​/petclinic​/api​/specialties
</code></pre>
<p>To execute the service expand the method, locate the button <code>[TRY IT OUT]</code></p>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/tryit-1.png?raw=true" alt="Pet Clinic Welcome Screen" /></p>
<p>Click <code>[Execute]</code>, this particular method does not take any argument.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/tryit-2.png?raw=true" alt="Pet Clinic Welcome Screen" /></p>
<p>You should see a response something like below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/tryit-3.png?raw=true" alt="Pet Clinic Welcome Screen" /><br />
<a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="11-angular-user-interface"> </a>11. Angular User Interface</h2>
<blockquote>
<p><a href="https://spring-petclinic.github.io/spring-petclinic-angular/" target="_blank">Reference Documentation</a></p>
</blockquote>
<blockquote>
<p><a href="https://github.com/spring-petclinic/spring-petclinic-angular/tree/4f58177e29476a4866723a7edc6dab614e96eec0" target="_blank">Source Code</a></p>
</blockquote>
<p>Keep the application running on the first terminal. We need our backend. Let'us start the user interface.</p>
<h4><a class="anchor" aria-hidden="true" id="11a-start-the-front-end"> </a>✅ 11a. Start the front end</h4>
<p>On the terminal <code>spring-petclinic-angular:npm</code> navigate to the Angular application.</p>
<pre lang="bash"><code>chunk {main} main.js, main.js.map (main) 331 kB [initial] [rendered]
chunk {polyfills} polyfills.js, polyfills.js.map (polyfills) 293 kB [initial] [rendered]
chunk {polyfills-es5} polyfills-es5.js, polyfills-es5.js.map (polyfills-es5) 463 kB [initial] [rendered]
chunk {runtime} runtime.js, runtime.js.map (runtime) 6.08 kB [entry] [rendered]
chunk {scripts} scripts.js, scripts.js.map (scripts) 411 kB [entry] [rendered]
chunk {styles} styles.js, styles.js.map (styles) 1.16 MB [initial] [rendered]
chunk {vendor} vendor.js, vendor.js.map (vendor) 6.87 MB [initial] [rendered]
** Angular Live Development Server is listening on localhost:4200, open your browser on http://localhost:4200/ **
ℹ ｢wdm｣: Compiled successfully.
</code></pre>
<ul>
<li>Kill the running application (the frontend must start after the backend here)</li>
</ul>
<pre><code>CTRL+C
</code></pre>
<ul>
<li>Start the application again</li>
</ul>
<pre><code> cd /workspace/workshop-spring-reactive/spring-petclinic-angular
 npm run start
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="11b-open-the-user-interface"> </a>✅ 11b. Open the user interface</h4>
<p>Open your browser on port <code>4200</code> using the the remote explorer or entering in a new terminal.</p>
<pre lang="bash"><code>gp preview &quot;$(gp url 4200)&quot;
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/ui-top.png?raw=true" alt="Pet Clinic Welcome Screen" /></p>
<p>This is it for the Hands-on TODAY. The angular project is a separate project on its own and we simply reuse it as a submodule but did not code anything there.</p>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="12-homeworks"> </a>12. Homeworks</h2>
<img src="https://github.com/datastaxdevs/workshop-ai-as-api/raw/master/doc/img/badge-petclinic.png?raw=true" width="200" align="right" />
<p>Don't forget to complete your assignment and get your verified skill badge! Finish and submit your homework!</p>
<ol>
<li>
<p>Complete the practice steps as described below until you have your own app running in Gitpod.</p>
</li>
<li>
<p>Answer the technical questions in the form (We promise, it is NOT difficult if you follow the workshop).</p>
</li>
<li>
<p>Add a funny PET TYPE in the DATABASE and take a SCREENSHOT of the running app with your data.</p>
</li>
<li>
<p>Submit your homework <a href="https://dtsx.io/homework-spring-reactive" target="_blank">here</a></p>
</li>
<li>
<p><em>(totally optional)</em> Challenge for 🌶️🌶️🌶️ EXTRA SPICE 🌶️🌶️🌶️. Fork the project, change the code for more repositories to use Spring Data (replacing the Java drivers) and do a pull request. 👕 If the submission has a good quality we will ship a SWAG BOX for free.</p>
</li>
</ol>
<p>Congratulations you made it to the END !!</p>

<h2><a class="anchor" aria-hidden="true" id="spring-quarkus-and-micronaut-with-apache-cassandra"> </a>🎓 Spring, Quarkus and Micronaut with Apache Cassandra</h2>
<img src="https://github.com/datastaxdevs/workshop-spring-quarkus-micronaut-cassandra/raw/master/img/badge.png?raw=true" width="150" align="right" >
<p><a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p>Welcome to the <em>Explore SpringBoot, Quarkus and Micronaut microservices with NoSQL Apache Cassandra</em>* workshop! In this two-hour workshop, we will show you a sample app architecture with data backed up on Apache Cassandra™ and program logic implemented on each of the three leading implementations of Java platform.</p>
<p>⏲️ <strong>Duration :</strong> 2 hours</p>
<p>🎓 <strong>Level</strong> Beginner to Intermediate</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-quarkus-micronaut-cassandra/raw/master/img/splash.png" alt="" /></p>
<blockquote>
<p><a href="#-start-hands-on" target="_blank">🔖 Accessing HANDS-ON</a></p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>📋 Table of contents</h2>
<ul>
<li><a href="#objectives" target="_blank">Objectives</a></li>
<li><a href="#frequently-asked-questions" target="_blank">Frequently asked questions</a></li>
<li><a href="#materials-for-the-session" target="_blank">Materials for the Session</a></li>
<li><a href="#setup" target="_blank">Setup your environment (DB, IDE)</a></li>
<li><a href="#lab-1---understanding-java-drivers" target="_blank">LAB1 - Understanding java drivers</a></li>
<li><a href="#lab-2---spring-data-cassandra" target="_blank">LAB2 - Spring Boot and Spring Data Cassandra</a></li>
<li><a href="#lab-3---cassandra-quarkus-extension" target="_blank">LAB3 - Quarkus</a></li>
<li><a href="#lab-4---micronaut-cassandra" target="_blank">LAB4 - Micronaut</a></li>
<li><a href="#Homework" target="_blank">Homework</a></li>
</ul>
<p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>
<p>🎯 Creating a ToDo app on multiple Java platforms (Spring Boot, Quarkus, Micronaut)</p>
</li>
<li>
<p>🎯 Data drivers for the app to connect to Astra</p>
</li>
<li>
<p>🎯 Java Native and the respective platforms</p>
</li>
<li>
<p>🎯 [Stretch] Building a native app on each of the platforms</p>
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
<li><b>Astra Cli</b>
<li>Java, Graal VM</b>
</ol>
</p>
In this README, we provide instructions mainly for Gitpod, hence <strong>we can't guarantee live support</strong> about local development in order to keep on track with the schedule. However, we will do our best to give you the info. you need to succeed.
</details>
<p/>
<details>
<summary><b> 2️⃣ What other prerequisites are required?</b></summary>
<hr>
<ul>
<li>You will need enough *real estate* on screen, we will ask you to open a few windows and it would not fit on mobiles (tablets should be OK)
<li>You will need an Astra account: don't worry, we'll work through that in the following
<li>As "Intermediate level" we expect you to know what Java and Spring are. 
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
<li><a href="/slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
<li><a href="https://www.twitch.tv/datastaxdevs" target="_blank">Twitch backup</a></li>
</ul>
<h1><a class="anchor" aria-hidden="true" id="start-hands-on"> </a>🏁 Start Hands-on</h1>
<h2><a class="anchor" aria-hidden="true" id="setup"> </a>Setup</h2>
<h4><a class="anchor" aria-hidden="true" id="code-setup-01-code-create-your-a-href-https-astra-dev-yt-10-5-astra-account-a"> </a><code>✅.setup-01</code>- Create your <a href="https://astra.dev/yt-10-5" target="_blank">Astra Account</a></h4>
<blockquote>
<p><em>ℹ️ Documentation:<a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/#c-procedure" target="_blank">Database creation guide</a></em></p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-setup-02-code-create-code-database-asministrator-code-token"> </a><code>✅.setup-02</code>- Create <code>Database Asministrator</code> Token.</h4>
<blockquote>
<p><em>ℹ️ Documentation: <a href="https://awesome-astra.github.io/docs/pages/astra/create-token/#c-procedure" target="_blank">Token creation guide</a></em>.</p>
</blockquote>
<pre><code>Skip this step is you already have a token. You can reuse the same token in our other workshops, too. Your token should look like: `AstraCS:....`
</code></pre>
<table>
<thead>
<tr>
<th>Field</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Role</strong></td>
<td><code>Database Administrator</code></td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token 
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<p><img src="https://awesome-astra.github.io/docs/img/astra/astra-create-token.gif" alt="token" /></p>
<h4><a class="anchor" aria-hidden="true" id="code-setup-03-code-open-gitpod"> </a><code>✅.setup-03</code>- Open Gitpod</h4>
<p>Gitpod is an IDE based on VSCode deployed in the cloud.</p>
<blockquote>
<p>↗️ <em>Right Click and select open as a new Tab...</em></p>
</blockquote>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-spring-quarkus-micronaut-cassandra" target="_blank"><img src="https://dabuttonfactory.com/button.png?t=Open+Gitpod&f=Open+Sans-Bold&ts=16&tc=fff&hp=20&vp=10&c=11&bgt=unicolored&bgc=0b5394" /></a></p>
<h4><a class="anchor" aria-hidden="true" id="code-setup-04-code-setup-astra-cli"> </a><code>✅.setup-04</code>- Setup Astra CLI</h4>
<p>Go back to your gitpod terminal waiting for your token. Make sure you select the <code>database</code> shell in the bottom-right panel and provide the value where it is asked.</p>
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
<h4><a class="anchor" aria-hidden="true" id="code-setup-05-code-create-database-code-workshops-code-and-keyspace-code-ks-java-code-if-they-do-not-exist"> </a><code>✅.setup-05</code>- Create database <code>workshops</code> and keyspace <code>ks_java</code> if they do not exist:</h4>
<pre lang="bash"><code>astra db create workshops -k ks_java --if-not-exist --wait
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
<td><code>-k ks_java</code></td>
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
<h4><a class="anchor" aria-hidden="true" id="code-setup-06-code-register-token-as-env-variable"> </a><code>✅.setup-06</code>- Register token as env variable</h4>
<pre><code>export ASTRA_DB_APP_TOKEN=`astra config get default --key ASTRA_DB_APPLICATION_TOKEN`
echo ${ASTRA_DB_APP_TOKEN}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-setup-07-code-download-secure-bundle"> </a><code>✅.setup-07</code>- Download Secure bundle</h4>
<ul>
<li>Download credentials in home folder</li>
</ul>
<pre><code>astra db download-scb workshops -f /workspace/workshop-spring-quarkus-micronaut-cassandra/secure-bundle-workshops.zip
</code></pre>
<ul>
<li>Check that the file is about <code>12k</code></li>
</ul>
<pre><code>ls -l /workspace/workshop-spring-quarkus-micronaut-cassandra/
</code></pre>
<p><em>Congratulations your environment is all set, let's start the labs !</em></p>
<h1><a class="anchor" aria-hidden="true" id="lab-1-understanding-java-drivers"> </a>LAB 1 - Understanding Java Drivers</h1>
<h4><a class="anchor" aria-hidden="true" id="code-1-a-code-connectivity"> </a><code>✅.1.a</code>- Connectivity</h4>
<pre><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E00_TestConnectivity.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E00_TestConnectivity
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-b-code-create-schema"> </a><code>✅.1.b</code>- Create Schema</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E01_CreateSchema.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E01_CreateSchema
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-c-code-about-statements"> </a><code>✅.1.c</code>- About Statements</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E02_Statements.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E02_Statements
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-d-code-crud"> </a><code>✅.1.d</code>- CRUD</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E03_OperationsCrudStatements.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E03_OperationsCrud
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-e-code-batches"> </a><code>✅.1.e</code>- Batches</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E04_Batches.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E04_Batches
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-f-code-paging"> </a><code>✅.1.f</code>- Paging</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E05_Paging.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E05_Paging
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-g-code-collections-list-set-map-udt"> </a><code>✅.1.g</code>- Collections: List,Set,Map,Udt</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E06_ListSetMapAndUdt.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E06_ListSetMapAndUdt
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-h-code-working-with-json"> </a><code>✅.1.h</code>- Working with Json</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E07_Json.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E07_Json
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-i-code-asynchronous-programming"> </a><code>✅.1.i</code>- Asynchronous Programming</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E08_Async.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E08_Async
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-j-code-reactive-programming"> </a><code>✅.1.j</code>- Reactive Programming</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E09_Reactive.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E09_Reactive
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-k-code-counters"> </a><code>✅.1.k</code>- Counters</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E10_Counters.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E10_Counters
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-l-code-lightweight-transactions"> </a><code>✅.1.l</code>- LightWeight Transactions</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E11_LightweightTransactions.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E11_LightweightTransactions
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-1-m-code-object-mapping"> </a><code>✅.1.m</code>- Object Mapping</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab1_cassandra_drivers/src/main/java/com/datastax/samples/E12_ObjectMapping.java
mvn clean compile exec:java -Dexec.mainClass=com.datastax.samples.E12_ObjectMapping
</code></pre>
<h1><a class="anchor" aria-hidden="true" id="lab-2-spring-data-cassandra"> </a>LAB 2 - Spring Data Cassandra</h1>
<h2><a class="anchor" aria-hidden="true" id="2-1-configuration"> </a>2.1 - Configuration</h2>
<h4><a class="anchor" aria-hidden="true" id="code-2-1-a-code-create-keyspace-code-ks-spring-code"> </a><code>✅.2.1.a</code>- Create keyspace <code>ks_spring</code></h4>
<pre lang="bash"><code>astra db create-keyspace workshops -k ks_spring
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-2-1-b-code-list-keyspaces"> </a><code>✅.2.1.b</code>- list Keyspaces</h4>
<pre lang="bash"><code>astra db list-keyspaces workshops
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>+---------------------+
| Name                |
+---------------------+
| ks_spring           |
| ks_java (default)   |
+---------------------+
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-2-1-c-code-check-project-configuration"> </a><code>✅.2.1.c</code>- Check Project configuration</h4>
<pre lang="bash"><code>gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab2_spring_data/pom.xml
</code></pre>
<ul>
<li>Spot the following dependency</li>
</ul>
<pre lang="xml"><code>&lt;dependency&gt;
  &lt;groupId&gt;org.springframework.boot&lt;/groupId&gt;
	&lt;artifactId&gt;spring-boot-starter-data-cassandra&lt;/artifactId&gt;
&lt;/dependency&gt;
</code></pre>
<pre lang="bash"><code>gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab2_spring_data/src/main/resources/application.yml
</code></pre>
<ul>
<li>Spot the following configuration</li>
</ul>
<pre lang="yaml"><code>vspring:
  data:
    cassandra:
      keyspace-name: ks_spring
      username: token
      password: ${ASTRA_DB_APP_TOKEN}
datastax:
  astra:
    secure-connect-bundle: /workspace/workshop-spring-quarkus-micronaut-cassandra/secure-bundle-workshops.zip
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-2-1-d-code-test-connectivity"> </a><code>✅.2.1.d</code>- Test connectivity</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab2_spring_data
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab2_spring_data/src/test/java/com/datastax/workshop/E01_SpringDataInit.java
mvn test -Dtest=com.datastax.workshop.E01_SpringDataInit
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="2-2-crud-repositories"> </a>2.2 - Crud Repositories</h2>
<ul>
<li>Given a table</li>
</ul>
<pre lang="sql"><code>CREATE TABLE todos (
    uid uuid PRIMARY KEY,
    completed boolean,
    offset int,
    title text
)
</code></pre>
<ul>
<li>Create an entity and anotate it</li>
</ul>
<blockquote>
<pre lang="java"><code>@Table(value = TodoEntity.TABLENAME)
public class TodoEntity {

 public static final String TABLENAME        = &quot;todos&quot;;
 public static final String COLUMN_UID       = &quot;uid&quot;;
 public static final String COLUMN_TITLE     = &quot;title&quot;;
 public static final String COLUMN_COMPLETED = &quot;completed&quot;;
 public static final String COLUMN_ORDER     = &quot;offset&quot;;

 @PrimaryKey
 @Column(COLUMN_UID)
 @CassandraType(type = Name.UUID)
 private UUID uid;

 @Column(COLUMN_TITLE)
 @CassandraType(type = Name.TEXT)
 private String title;

 @Column(COLUMN_COMPLETED)
 @CassandraType(type = Name.BOOLEAN)
 private boolean completed = false;

 @Column(COLUMN_ORDER)
 @CassandraType(type = Name.INT)
 private int order = 0;

 public TodoEntity(String title, int offset) {
   this(UUID.randomUUID(), title, false, offset);
 }
}
</code></pre>
</blockquote>
<ul>
<li>Create interface extending <code>CassandraRepository</code> providing bean type and primary key class.</li>
</ul>
<pre lang="java"><code>@Repository
public interface TodoRepositoryCassandra extends CassandraRepository&lt;TodoEntity, UUID&gt; {
}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-2-2-a-code-test-repositories"> </a><code>✅.2.2.a</code>- Test Repositories</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab2_spring_data
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab2_spring_data/src/test/java/com/datastax/workshop/E02_SpringDataRepository.java
mvn test -Dtest=com.datastax.workshop.E02_SpringDataRepository
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-2-2-b-code-get-results-from-cqlsh"> </a><code>✅.2.2.b</code>- Get results from cqlsh</h4>
<pre><code>astra db cqlsh workshops -e &quot;SELECT * FROM ks_spring.todos&quot;
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="2-3-cassandraoperations"> </a>2.3 - CassandraOperations</h2>
<ul>
<li><code>SimpleCassandraRepository</code> gives you access to the <code>CqlSession</code>.</li>
</ul>
<pre lang="java"><code>@Repository
public class TodoRepositorySimpleCassandra extends SimpleCassandraRepository&lt;TodoEntity, UUID&gt; {

 protected final CqlSession cqlSession;

 protected final CassandraOperations cassandraTemplate;

 @SuppressWarnings(&quot;unchecked&quot;)
 public TodoRepositorySimpleCassandra(CqlSession cqlSession, CassandraOperations ops) {
   super(new MappingCassandraEntityInformation&lt;TodoEntity, UUID&gt;(
     (CassandraPersistentEntity&lt;TodoEntity&gt;) ops.getConverter().getMappingContext()
     .getRequiredPersistentEntity(TodoEntity.class), ops.getConverter()), ops);
   this.cqlSession = cqlSession;
   this.cassandraTemplate = ops;
 }
}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-2-3-a-code-use-the-simplecassandrarepository"> </a><code>✅.2.3.a</code>- Use the SimpleCassandraRepository</h4>
<pre lang="bash"><code>
cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab2_spring_data
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab2_spring_data/src/test/java/com/datastax/workshop/E03_SpringDataCassandraOperations.java
mvn test -Dtest=com.datastax.workshop.E03_SpringDataCassandraOperations
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="2-4-spring-boot"> </a>2.4 - Spring Boot</h2>
<h4><a class="anchor" aria-hidden="true" id="code-2-4-a-code-start-application"> </a><code>✅.2.4.a</code>- Start application</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab2_spring_data
mvn spring-boot:run
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-2-4-b-code-access-application-apis"> </a><code>✅.2.4.b</code>- Access Application Apis</h4>
<pre><code>gp preview &quot;$(gp url 8080)/api/v1/todos/&quot;
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-2-4-c-code-integration-tests"> </a><code>✅.2.4.c</code>- Integration Tests</h4>
<ul>
<li>
<p>Open a new terminal with the <code>+</code> button on the top right hand corner of terminal panel</p>
</li>
<li>
<p>Set the custom path as environment variable</p>
</li>
</ul>
<pre><code>export SPRING_DATA_URL=`gp url 8080`
cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab2_spring_data
mvn test -Dtest=com.datastax.workshop.E04_SpringControllerTest
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="2-5-spring-native"> </a>2.5 Spring native</h2>
<blockquote>
<p><strong>Documentation:</strong> <a href="https://www.graalvm.org/dev/reference-manual/native-image/guides/build-spring-boot-app-into-native-executable/" target="_blank">Official Documentation</a></p>
</blockquote>
<p/><br/>
<h1><a class="anchor" aria-hidden="true" id="lab-3-cassandra-quarkus-extension"> </a>LAB 3 - Cassandra Quarkus Extension</h1>
<h2><a class="anchor" aria-hidden="true" id="3-1-configuration"> </a>3.1 - Configuration</h2>
<h4><a class="anchor" aria-hidden="true" id="code-3-1-a-code-create-keyspace-code-ks-quarkus-code"> </a><code>✅.3.1.a</code>- Create keyspace <code>ks_quarkus</code></h4>
<pre lang="bash"><code>astra db create-keyspace workshops -k ks_quarkus --if-not-exist
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-3-1-b-code-list-keyspaces"> </a><code>✅.3.1.b</code>- list Keyspaces</h4>
<pre lang="bash"><code>astra db list-keyspaces workshops
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>+---------------------+
| Name                |
+---------------------+
| ks_spring           |
| ks_java (default)   |
| ks_quarkus          |
+---------------------+
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-3-1-c-code-compile-project"> </a><code>✅.3.1.c</code>- Compile project</h4>
<pre lang="bash"><code>gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/pom.xml
</code></pre>
<ul>
<li>Check dependency to use quarkus</li>
</ul>
<pre lang="xml"><code>&lt;dependency&gt;
  &lt;groupId&gt;com.datastax.oss.quarkus&lt;/groupId&gt;
  &lt;artifactId&gt;cassandra-quarkus-client&lt;/artifactId&gt;
  &lt;version&gt;${latest}&lt;/version&gt;
&lt;/dependency&gt;
</code></pre>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/
mvn clean compile
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-3-1-d-code-check-configuration"> </a><code>✅.3.1.d</code>- Check Configuration</h4>
<pre lang="bash"><code>gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/src/main/resources/application.properties
</code></pre>
<ul>
<li>Here how we defined the connectivity</li>
</ul>
<pre lang="ini"><code>quarkus.cassandra.keyspace=ks_quarkus
quarkus.cassandra.cloud.secure-connect-bundle=/workspace/workshop-spring-quarkus-micronaut-cassandra/secure-bundle-workshops.zip
quarkus.cassandra.auth.username=token
quarkus.cassandra.auth.password=${ASTRA_DB_APP_TOKEN}
</code></pre>
<ul>
<li>Make sure this constant <code>ASTRA_DB_APP_TOKEN</code> in our terminal</li>
</ul>
<pre lang="bash"><code>export ASTRA_DB_APP_TOKEN=`astra config get default --key ASTRA_DB_APPLICATION_TOKEN`
echo ${ASTRA_DB_APP_TOKEN}
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="3-2-usage"> </a>3.2 - Usage</h2>
<h4><a class="anchor" aria-hidden="true" id="code-3-2-a-code-validate-configuration"> </a><code>✅.3.2.a</code>- Validate configuration</h4>
<pre><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/
mvn test -Dtest=com.datastax.workshop.E01_QuarkusInit
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-3-2-b-code-use-code-cqlsession-code-with-code-quarkus-code"> </a><code>✅.3.2.b</code>- Use <code>CqlSession</code> with <code>Quarkus</code></h4>
<pre><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/
mvn test -Dtest=com.datastax.workshop.E02_QuarkusCql
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="3-3-object-mapping"> </a>3.3 - Object Mapping</h2>
<h4><a class="anchor" aria-hidden="true" id="code-3-3-a-code-object-mapping-configuration"> </a><code>✅.3.3.a</code>- Object Mapping configuration</h4>
<ul>
<li>Quarkus reuses the Driver Mapper mechanism</li>
</ul>
<pre><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/
gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/src/main/java/com/datastaxdev/todo/cassandra/TodoItem.java
</code></pre>
<ul>
<li>
<p><code>TodoServicesCassandraOM</code> is annotated with <code>@ApplicationScoped</code> to inject the class in the context</p>
</li>
<li>
<p>In constructor we use <code>Mapper</code> to instanciate a <code>DAO</code> created with the driver</p>
</li>
</ul>
<blockquote>
<pre lang="java"><code>todoDao = TodoItemMapper
  .builder(cqlSession)
  .withDefaultKeyspace(cqlSession.getKeyspace().get())
  .build()
  .todoItemDao();
</code></pre>
</blockquote>
<pre><code>gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/src/main/java/com/datastaxdev/todo/cassandra/TodoServicesCassandraOM.java
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-3-3-b-code-object-mapping-test"> </a><code>✅.3.3.b</code>- Object Mapping test</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/
mvn test -Dtest=com.datastax.workshop.E03_QuarkusObjectMapping
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="3-4-rest-api-application"> </a>3.4 - Rest Api Application</h2>
<h4><a class="anchor" aria-hidden="true" id="code-3-4-a-code-start-the-application-with-code-dev-code-plugin"> </a><code>✅.3.4.a</code>- Start the application with <code>dev</code> plugin</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/
mvn quarkus:dev -DskipTests
</code></pre>
<ul>
<li>To access the developer dashboard use on a new tab</li>
</ul>
<pre lang="bash"><code>gp preview &quot;$(gp url 8081)/q/dev&quot;
</code></pre>
<p><em>Dashboard</em><br />
<img src="https://github.com/datastaxdevs/workshop-spring-quarkus-micronaut-cassandra/raw/master/img/quarkus-dashboard.png?raw=true" alt="" /></p>
<h4><a class="anchor" aria-hidden="true" id="code-3-4-b-code-access-swagger-ui"> </a><code>✅.3.4.b</code>- Access Swagger-UI</h4>
<pre lang="bash"><code>gp preview &quot;$(gp url 8081)/q/swagger-ui&quot;
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-spring-quarkus-micronaut-cassandra/raw/master/img/quarkus-swagger.png?raw=true" alt="" /></p>
<h4><a class="anchor" aria-hidden="true" id="code-3-4-c-code-access-apis"> </a><code>✅.3.4.c</code>- Access APIs</h4>
<pre lang="bash"><code>gp preview &quot;$(gp url 8081)/api/v1/clun/todos/&quot;
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-spring-quarkus-micronaut-cassandra/raw/master/img/quarkus-swagger.png?raw=true" alt="" /></p>
<h4><a class="anchor" aria-hidden="true" id="code-3-4-d-code-integration-test"> </a><code>✅.3.4.d</code>- Integration Test</h4>
<p>Stop running application with <code>q</code>.</p>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/
mvn test -Dtest=com.datastax.workshop.E04_QuarkusController
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-3-4-e-code-native-image"> </a><code>✅.3.4.e</code>- Native Image</h4>
<p>You can package the image with the <code>-Pnative</code> option as below.</p>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/
mvn clean package -DskipTests -Pnative
</code></pre>
<blockquote>
<p>🖥️ <code>OUTPUT</code></p>
</blockquote>
<pre><code>INFO] Scanning for projects...
[INFO] 
[INFO] -----------------&lt; com.datastax.samples:lab3-quarkus &gt;------------------
[INFO] Building lab3-quarkus 0.0.1-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ lab3-quarkus ---
[INFO] Deleting /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/target
[INFO] 
[INFO] --- quarkus-maven-plugin:2.3.1.Final:generate-code (default) @ lab3-quarkus ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ lab3-quarkus ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 2 resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.8.1:compile (default-compile) @ lab3-quarkus ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 10 source files to /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/target/classes
[INFO] 
[INFO] --- quarkus-maven-plugin:2.3.1.Final:generate-code-tests (default) @ lab3-quarkus ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ lab3-quarkus ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/src/test/resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.8.1:testCompile (default-testCompile) @ lab3-quarkus ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 4 source files to /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/target/test-classes
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M5:test (default-test) @ lab3-quarkus ---
[INFO] Tests are skipped.
[INFO] 
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ lab3-quarkus ---
[INFO] Building jar: /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/target/lab3-quarkus-0.0.1-SNAPSHOT.jar
[INFO] 
[INFO] --- quarkus-maven-plugin:2.3.1.Final:build (default) @ lab3-quarkus ---
[INFO] [org.jboss.threads] JBoss Threads version 3.4.2.Final
[WARNING] Error reading service account token from: [/var/run/secrets/kubernetes.io/serviceaccount/token]. Ignoring.
[WARNING] Error reading service account token from: [/var/run/secrets/kubernetes.io/serviceaccount/token]. Ignoring.
[WARNING] Error reading service account token from: [/var/run/secrets/kubernetes.io/serviceaccount/token]. Ignoring.
[INFO] [io.quarkus.arc.processor.BeanProcessor] Found unrecommended usage of private members (use package-private instead) in application beans:
        - @Inject field com.datastaxdev.todo.TodoRestController#cqlSession,
        - @Inject field com.datastaxdev.todo.TodoRestController#uriInfo
[WARNING] Micrometer metrics were enabled by configuration, but MicrometerMetricsFactory was not found.
[WARNING] Make sure to include a dependency to the java-driver-metrics-micrometer module.
[INFO] Checking for existing resources in: /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/src/main/kubernetes.
[INFO] [io.quarkus.deployment.pkg.steps.JarResultBuildStep] Building native image source jar: /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/target/lab3-quarkus-0.0.1-SNAPSHOT-native-image-source-jar/lab3-quarkus-0.0.1-SNAPSHOT-runner.jar
[INFO] [io.quarkus.deployment.pkg.steps.NativeImageBuildStep] Building native image from /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/target/lab3-quarkus-0.0.1-SNAPSHOT-native-image-source-jar/lab3-quarkus-0.0.1-SNAPSHOT-runner.jar
[INFO] [io.quarkus.deployment.pkg.steps.NativeImageBuildStep] Running Quarkus native-image plugin on GraalVM 22.1.0 Java 11 CE (Java Version 11.0.15+10-jvmci-22.1-b06)
[INFO] [io.quarkus.deployment.pkg.steps.NativeImageBuildRunner] /home/gitpod/.sdkman/candidates/java/22.1.0.r11-grl/bin/native-image -J-Djava.util.logging.manager=org.jboss.logmanager.LogManager -J-Dsun.nio.ch.maxUpdateArraySize=100 -J-Dvertx.logger-delegate-factory-class-name=io.quarkus.vertx.core.runtime.VertxLogDelegateFactory -J-Dvertx.disableDnsResolver=true -J-Dio.netty.leakDetection.level=DISABLED -J-Dio.netty.allocator.maxOrder=3 -J-Duser.language=en -J-Duser.country=US -J-Dfile.encoding=UTF-8 -H:InitialCollectionPolicy=com.oracle.svm.core.genscavenge.CollectionPolicy\$BySpaceAndTime -H:+JNI -H:+AllowFoldMethods -H:FallbackThreshold=0 -H:+ReportExceptionStackTraces -H:-AddAllCharsets -H:EnableURLProtocols=http,https -H:NativeLinkerOption=-no-pie -H:-UseServiceLoaderFeature -H:+StackTrace -H:-ParseOnce lab3-quarkus-0.0.1-SNAPSHOT-runner -jar lab3-quarkus-0.0.1-SNAPSHOT-runner.jar
======================================================================================================
GraalVM Native Image: Generating 'lab3-quarkus-0.0.1-SNAPSHOT-runner' (executable)...
======================================================================================================
[1/7] Initializing...                                                                  (7.4s @ 0.17GB)
 Version info: 'GraalVM 22.1.0 Java 11 CE'
 C compiler: gcc (linux, x86_64, 9.4.0)
 Garbage collector: Serial GC
 2 user-provided feature(s)
  - io.quarkus.runner.AutoFeature
  - io.quarkus.runtime.graal.ResourcesFeature
[2/7] Performing analysis...  [16:42:29,870 INFO  [com.dat.oss.dri.int.cor.DefaultMavenCoordinates] DataStax Java driver for Apache Cassandra(R) (com.datastax.oss:java-driver-core) version 4.13.0
*16:43:19,387 INFO  [org.jbo.threads] JBoss Threads version 3.4.2.Final
**********]                                           (97.6s @ 2.24GB)
  14,423 (90.29%) of 15,974 classes reachable
  21,418 (64.47%) of 33,223 fields reachable
  72,082 (58.89%) of 122,398 methods reachable
     477 classes,    42 fields, and 1,633 methods registered for reflection
      68 classes,    88 fields, and    54 methods registered for JNI access
[3/7] Building universe...                                                             (6.7s @ 2.88GB)
[4/7] Parsing methods...      [*****]                                                 (26.7s @ 1.92GB)
[5/7] Inlining methods...     [*****]                                                 (17.5s @ 4.86GB)
[6/7] Compiling methods...    [***********]                                          (137.3s @ 4.31GB)
[7/7] Creating image...                                                                (7.2s @ 2.04GB)
  27.50MB (44.39%) for code area:   46,659 compilation units
  27.61MB (44.57%) for image heap:  10,057 classes and 328,598 objects
   6.84MB (11.04%) for other data
  61.95MB in total
------------------------------------------------------------------------------------------------------
Top 10 packages in code area:                      Top 10 object types in image heap:
   1.75MB sun.security.ssl                            6.30MB byte[] for code metadata
   1.11MB com.esri.core.geometry                      3.54MB java.lang.Class
   1.04MB java.util                                   2.95MB java.lang.String
 715.53KB com.sun.crypto.provider                     2.76MB byte[] for general heap data
 484.63KB sun.security.x509                           2.69MB byte[] for java.lang.String
 476.36KB io.quarkus.runtime.generated                1.32MB c.o.svm.core.hub.DynamicHubCompanion
 476.25KB java.util.concurrent                      867.19KB java.util.HashMap$Node
 429.23KB java.lang                                 641.52KB byte[] for reflection metadata
 424.57KB io.netty.buffer                           609.70KB java.lang.String[]
 419.94KB com.typesafe.config.impl                  398.88KB java.util.HashMap$Node[]
      ... 635 additional packages                        ... 3440 additional object types
                                  (use GraalVM Dashboard to see all)
------------------------------------------------------------------------------------------------------
               28.4s (9.1% of total time) in 36 GCs | Peak RSS: 6.95GB | CPU load: 2.00
------------------------------------------------------------------------------------------------------
Produced artifacts:
 /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/target/lab3-quarkus-0.0.1-SNAPSHOT-native-image-source-jar/lab3-quarkus-0.0.1-SNAPSHOT-runner (executable)
 /workspace/workshop-spring-quarkus-micronaut-cassandra/lab3_quarkus/target/lab3-quarkus-0.0.1-SNAPSHOT-native-image-source-jar/lab3-quarkus-0.0.1-SNAPSHOT-runner.build_artifacts.txt
======================================================================================================
Finished generating 'lab3-quarkus-0.0.1-SNAPSHOT-runner' in 5m 10s.
[INFO] [io.quarkus.deployment.pkg.steps.NativeImageBuildRunner] objcopy --strip-debug lab3-quarkus-0.0.1-SNAPSHOT-runner
[INFO] [io.quarkus.deployment.QuarkusAugmentor] Quarkus augmentation completed in 315900ms
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  05:27 min
[INFO] Finished at: 2022-10-04T16:47:29Z
[INFO] ------------------------------------------------------------------------
</code></pre>
<p>and you can run it as below</p>
<pre><code>./target/lab3-quarkus-0.0.1-SNAPSHOT-runner
</code></pre>
<blockquote>
<p>🖥️ <code>OUTPUT</code></p>
</blockquote>
<pre><code>__  ____  __  _____   ___  __ ____  ______ 
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/ 
 -/ /_/ / /_/ / __ |/ , _/ ,&lt; / /_/ /\ \   
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/   
2022-10-04 16:48:45,719 INFO  [com.dat.oss.dri.int.cor.os.Native] (vert.x-eventloop-thread-0) Using Graal-specific native functions
2022-10-04 16:48:45,719 INFO  [com.dat.oss.dri.int.cor.tim.Clock] (vert.x-eventloop-thread-0) Using native clock for microsecond precision
2022-10-04 16:48:47,087 INFO  [com.dat.oss.dri.int.cor.ses.DefaultSession] (vert.x-eventloop-thread-8) [s0] Negotiated protocol version V4 for the initial contact point, but cluster seems to support V5, keeping the negotiated version
2022-10-04 16:48:48,001 INFO  [com.dat.oss.qua.run.int.qua.CassandraClientStarter] (main) Eagerly initializing Quarkus Cassandra client.
2022-10-04 16:48:48,005 INFO  [io.quarkus] (main) lab3-quarkus 0.0.1-SNAPSHOT native (powered by Quarkus 2.3.1.Final) started in 2.610s. Listening on: http://0.0.0.0:8081
2022-10-04 16:48:48,005 INFO  [io.quarkus] (main) Profile prod activated. 
2022-10-04 16:48:48,005 INFO  [io.quarkus] (main) Installed features: [cassandra-client, cdi, kubernetes, micrometer, resteasy-reactive, resteasy-reactive-jackson, smallrye-context-propagation, smallrye-health, smallrye-openapi, vertx]
</code></pre>
<h1><a class="anchor" aria-hidden="true" id="lab-4-micronaut-cassandra"> </a>LAB 4 - Micronaut Cassandra</h1>
<h2><a class="anchor" aria-hidden="true" id="4-1-configuration"> </a>4.1 - Configuration</h2>
<h4><a class="anchor" aria-hidden="true" id="code-4-1-a-code-create-keyspace-code-ks-micronaut-code"> </a><code>✅.4.1.a</code>- Create keyspace <code>ks_micronaut</code></h4>
<pre lang="bash"><code>astra db create-keyspace workshops -k ks_micronaut --if-not-exist
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-4-1-b-code-list-keyspaces"> </a><code>✅.4.1.b</code>- list Keyspaces</h4>
<pre lang="bash"><code>astra db list-keyspaces workshops
</code></pre>
<blockquote>
<p>🖥️ <code>output</code></p>
<pre><code>+---------------------+
| Name                |
+---------------------+
| ks_spring           |
| ks_java (default)   |
| ks_quarkus          |
| ks_micronaut        |
+---------------------+
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-4-1-c-code-compile-project"> </a><code>✅.4.1.c</code>- Compile project</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab4_micronaut/
mvn clean compile
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="code-4-1-d-code-testing-project"> </a><code>✅.4.1.d</code>- Testing project</h4>
<pre><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab4_micronaut/
mvn test -Dtest=com.datastaxdev.E01_MicronautInitTest
</code></pre>
<blockquote>
<p>🖥️ <code>OUTPUT</code></p>
<pre><code>[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.datastaxdev.E01_MicronautInitTest
12:57:12.946 [main] INFO  c.datastaxdev.TodoApplicationStartup - Startup Initialization
12:57:13.067 [main] INFO  c.datastaxdev.TodoApplicationStartup - + Table TodoItems created if needed.
12:57:13.067 [main] INFO  c.datastaxdev.TodoApplicationStartup - [OK]
com.datastax.oss.driver.internal.core.session.DefaultSession@37854b34
12:57:13.108 [main] INFO  c.datastaxdev.E01_MicronautInitTest - Creating your CqlSession to Cassandra...
12:57:13.111 [main] INFO  c.datastaxdev.E01_MicronautInitTest - + [OK] Your are connected to keyspace ks_micronaut
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 7.677 s - in com.datastaxdev.E01_MicronautInitTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  11.262 s
[INFO] Finished at: 2022-10-04T12:57:15Z
[INFO] ------------------------------------------------------------------------
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-4-1-e-code-use-cqlsession"> </a><code>✅.4.1.e</code>- Use CqlSession</h4>
<pre><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab4_micronaut/
mvn test -Dtest=com.datastaxdev.E02_MicronautCqlTest
</code></pre>
<blockquote>
<p>🖥️ <code>OUTPUT</code></p>
<pre><code>[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.datastaxdev.E02_MicronautCqlTest
13:00:21.370 [main] INFO  c.datastaxdev.TodoApplicationStartup - Startup Initialization
13:00:21.482 [main] INFO  c.datastaxdev.TodoApplicationStartup - + Table TodoItems created if needed.
13:00:21.482 [main] INFO  c.datastaxdev.TodoApplicationStartup - [OK]
13:00:22.372 [main] INFO  com.datastaxdev.E02_MicronautCqlTest - Creating the schema...
13:00:22.456 [main] INFO  com.datastaxdev.E02_MicronautCqlTest - + [OK]
13:00:22.457 [main] INFO  com.datastaxdev.E02_MicronautCqlTest - Inserting Data
13:00:22.552 [main] INFO  com.datastaxdev.E02_MicronautCqlTest - + [OK]
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 8.28 s - in com.datastaxdev.E02_MicronautCqlTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  11.441 s
[INFO] Finished at: 2022-10-04T13:00:24Z
[INFO] ------------------------------------------------------------------------
</code></pre>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="4-2-configuration"> </a>4.2 - Configuration</h2>
<h4><a class="anchor" aria-hidden="true" id="code-4-2-a-code-object-mapping"> </a><code>✅.4.2.a</code>- Object Mapping</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab4_micronaut/
mvn test -Dtest=com.datastaxdev.E03_MicronautObjectMappingTest
</code></pre>
<blockquote>
<p>🖥️ <code>OUTPUT</code></p>
<pre><code>[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.datastaxdev.E03_MicronautObjectMappingTest
13:02:03.705 [main] INFO  c.datastaxdev.TodoApplicationStartup - Startup Initialization
13:02:03.810 [main] INFO  c.datastaxdev.TodoApplicationStartup - + Table TodoItems created if needed.
13:02:03.810 [main] INFO  c.datastaxdev.TodoApplicationStartup - [OK]
13:02:04.038 [main] INFO  c.d.E03_MicronautObjectMappingTest - Inserting Data
13:02:04.135 [main] INFO  c.d.E03_MicronautObjectMappingTest - + [OK]
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 7.494 s - in com.datastaxdev.E03_MicronautObjectMappingTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  10.433 s
[INFO] Finished at: 2022-10-04T13:02:06Z
[INFO] ------------------------------------------------------------------------
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-4-2-b-code-integration-tests"> </a><code>✅.4.2.b</code>- Integration Tests</h4>
<ul>
<li>Run integration tests with the following.</li>
</ul>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab4_micronaut/
mvn test -Dtest=com.datastaxdev.E04_MicronautControllerTest
</code></pre>
<blockquote>
<p>🖥️ <code>OUTPUT</code></p>
<pre><code>[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.datastaxdev.E04_MicronautControllerTest
13:10:03.322 [main] INFO  c.datastaxdev.TodoApplicationStartup - Startup Initialization
13:10:03.431 [main] INFO  c.datastaxdev.TodoApplicationStartup - + Table TodoItems created if needed.
13:10:03.431 [main] INFO  c.datastaxdev.TodoApplicationStartup - [OK]
13:10:04.828 [main] INFO  c.d.E04_MicronautControllerTest - 12 task retrieved
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 8.811 s - in com.datastaxdev.E04_MicronautControllerTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  12.778 s
[INFO] Finished at: 2022-10-04T13:10:07Z
[INFO] ------------------------------------------------------------------------
</code></pre>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="4-3-micronaut-application"> </a>4.3 - Micronaut Application</h2>
<h4><a class="anchor" aria-hidden="true" id="code-4-3-a-code-start-the-application"> </a><code>✅.4.3.a</code>- Start the application</h4>
<pre lang="bash"><code>cd /workspace/workshop-spring-quarkus-micronaut-cassandra/lab4_micronaut/
mvn mn:run -DskipTests
</code></pre>
<blockquote>
<p>🖥️ <code>OUTPUT</code></p>
<pre><code> __  __ _                                  _   
|  \/  (_) ___ _ __ ___  _ __   __ _ _   _| |_ 
| |\/| | |/ __| '__/ _ \| '_ \ / _` | | | | __|
| |  | | | (__| | | (_) | | | | (_| | |_| | |_ 
|_|  |_|_|\___|_|  \___/|_| |_|\__,_|\__,_|\__|
  Micronaut (v3.7.1)

13:06:15.990 [main] INFO  c.datastaxdev.TodoApplicationStartup - Startup Initialization
13:06:16.096 [main] INFO  c.datastaxdev.TodoApplicationStartup - + Table TodoItems created if needed.
13:06:16.096 [main] INFO  c.datastaxdev.TodoApplicationStartup - [OK]

</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="code-4-3-b-code-show-the-apis"> </a><code>✅.4.3.b</code>- Show the Apis</h4>
<ul>
<li>Open the application API on port <code>8082</code></li>
</ul>
<pre lang="bash"><code>gp preview &quot;$(gp url 8082)/api/v1/clun/todos/&quot;
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-spring-quarkus-micronaut-cassandra/raw/master/img/micronaut-output.png" alt="out" /></p>
<h2><a class="anchor" aria-hidden="true" id="4-4-native-image"> </a>4.4 - Native Image</h2>
<h4><a class="anchor" aria-hidden="true" id="code-4-4-a-code-build-native-image"> </a><code>✅.4.4.a</code>- Build native image</h4>
<blockquote>
<p><strong><a href="https://docs.micronaut.io/latest/guide/index.html#graal" target="_blank">Documentation</a></strong></p>
</blockquote>
<ul>
<li>Change environment variable</li>
</ul>
<pre><code>gp open /workspace/workshop-spring-quarkus-micronaut-cassandra/lab4_micronaut/src/main/resources/application.yml
</code></pre>
<pre lang="yaml"><code>#password: ${ASTRA_DB_APP_TOKEN}
</code></pre>
<ul>
<li>Compile as native image</li>
</ul>
<pre><code>mvn package -Dpackaging=native-image
</code></pre>
<ul>
<li>Run the Native</li>
</ul>
<pre><code>./target/todo-micronaut
</code></pre>
<ul>
<li>Show the API</li>
</ul>
<pre><code>gp preview &quot;$(gp url 8082)/api/v1/clun/todos/&quot;
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="homeworks"> </a>Homeworks</h2>
<p>To submit the <strong>homework</strong>, please take a screenshot in gitpod with the result of lab <code>4.3</code> where you micronaut application return some TODO, no need to go native.</p>
<p>Don't forget to <a href="https://dtsx.io/homework-spring-quarkus-micronaut" target="_blank">submit your homework</a> and be awarded a nice verified badge!</p>
<h2><a class="anchor" aria-hidden="true" id="what-s-next"> </a>What's NEXT ?</h2>
<p>We've just scratched the surface of what you can do using Astra DB, built on Apache Pulsar and Cassandra.</p>
<p>Go take a look at <a href="https://www.datastax.com/dev" target="_blank">DataStax for Developers</a> to see what else is possible.</p>
<p>There's plenty to dig into!</p>
<p>Congratulations: you made to the end of today's workshop.</p>
<p>Don't forget to <a href="https://dtsx.io/homework-spring-quarkus-micronaut" target="_blank">submit your homework</a> and be awarded a nice verified badge!</p>
<img src="https://github.com/datastaxdevs/workshop-spring-quarkus-micronaut-cassandra/raw/master/img/badge.png?raw=true" width="350" />
<hr />
<p><strong>... and see you at our next workshop!</strong></p>

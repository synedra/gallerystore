<h1><a class="anchor" aria-hidden="true" id="java-driver-code-samples"> </a>Java Driver Code Samples</h1>
<ul>
<li>
<p><em>Latest V3 Driver</em>: <a href="https://maven-badges.herokuapp.com/maven-central/com.datastax.cassandra/cassandra-driver-mapping/" target="_blank"><img src="https://maven-badges.herokuapp.com/maven-central/com.datastax.cassandra/cassandra-driver-mapping/badge.svg" alt="Maven Central" /></a></p>
</li>
<li>
<p><em>Latest V4 Driver</em>: <a href="https://maven-badges.herokuapp.com/maven-central/com.datastax.oss/java-driver-core" target="_blank"><img src="https://maven-badges.herokuapp.com/maven-central/com.datastax.oss/java-driver-core/badge.svg" alt="Maven Central" /></a></p>
</li>
</ul>
<p>This repository contains a list of standalone classes illustrating each a dedicated feature of the <em>DataStax java driver</em>. The purpose is to provide you an extended list of code samples with explicit names to speed up you developments (with copy-paste). We implemented those for both driver 3.x <em>(previous oss)</em> and driver 4.x <em>(latest)</em></p>
<h2><a class="anchor" aria-hidden="true" id="clipboard-table-of-content"> </a>:clipboard: Table of content</h2>
<ol>
<li><a href="#1-prerequisites" target="_blank">Prerequisites</a></li>
<li><a href="#2-start-local-cluster" target="_blank">Start Local Cluster</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="1-prerequisites"> </a>1. Prerequisites</h2>
<h4><a class="anchor" aria-hidden="true" id="java-development-kit-jdk-8"> </a>📦 Java Development Kit (JDK) 8</h4>
<ul>
<li>Use the <a href="https://docs.oracle.com/javase/8/docs/technotes/guides/install/install_overview.html" target="_blank">reference documentation</a> to install a <strong>Java Development Kit</strong></li>
<li>Validate your installation with</li>
</ul>
<pre lang="bash"><code>java --version
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="apache-maven"> </a>📦 Apache Maven</h4>
<ul>
<li>Use the <a href="https://maven.apache.org/install.html" target="_blank">reference documentation</a> to install <strong>Apache Maven</strong></li>
<li>Validate your installation with</li>
</ul>
<pre lang="bash"><code>mvn -version
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="docker-local-installation"> </a>📦 Docker (local Installation)</h4>
<p>Docker is an open-source project that automates the deployment of software applications inside containers by providing an additional layer of abstraction and automation of OS-level virtualization on Linux.</p>
<details>
<summary><b><img src="https://github.com/DataStax-Academy/kubernetes-workshop-online/blob/master/4-materials/images/windows32.png?raw=true" height="24"/> To install on windows</b></summary>
<a href="https://download.docker.com/win/stable/Docker%20Desktop%20Installer.exe" target="_blank">Docker Desktop for Windows Installer</a>
</details>
<details>
<summary><b><img src="https://github.com/DataStax-Academy/kubernetes-workshop-online/blob/master/4-materials/images/mac32.png?raw=true" height="24"/> To install on MAC</b></summary>
<a href="https://download.docker.com/mac/stable/Docker.dmg" target="_blank">Docker Desktop for MAC Installer</a> or <a href="https://download.docker.com/mac/stable/Docker.dmg" target="_blank">Homebrew</a>
<pre>
# Fetch latest version of homebrew and formula.
brew update              
# Tap the Caskroom/Cask repository from Github using HTTPS.
brew tap caskroom/cask                
# Searches all known Casks for a partial or exact match.
brew search docker                    
# Displays information about the given Cask
brew cask info docker
# Install the given cask.
brew cask install docker              
# Remove any older versions from the cellar.
brew cleanup
# Validate installation
docker -v
</pre>
</details>
<details>
<summary><b><img src="https://github.com/DataStax-Academy/kubernetes-workshop-online/blob/master/4-materials/images/linux32.png?raw=true" height="24"/>To install on linux (centOS) you can use the following commands</b></summary>
<pre>
# Remove if already install
sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
# Utils
sudo yum install -y yum-utils
<h1><a class="anchor" aria-hidden="true" id="add-docker-ce-repo"> </a>Add docker-ce repo</h1>
<p>sudo dnf config-manager --add-repo=<a href="https://download.docker.com/linux/centos/docker-ce.repo" target="_blank">https://download.docker.com/linux/centos/docker-ce.repo</a></p>
<h1><a class="anchor" aria-hidden="true" id="install"> </a>Install</h1>
<p>sudo dnf -y  install docker-ce --nobest</p>
<h1><a class="anchor" aria-hidden="true" id="enable-service"> </a>Enable service</h1>
<p>sudo systemctl enable --now docker</p>
<h1><a class="anchor" aria-hidden="true" id="get-status"> </a>Get Status</h1>
<p>systemctl status  docker</p>
<h1><a class="anchor" aria-hidden="true" id="logout-lougin"> </a>Logout....Lougin</h1>
<p>exit</p>
<h1><a class="anchor" aria-hidden="true" id="create-user"> </a>Create user</h1>
<p>sudo usermod -aG docker $USER<br />
newgrp docker</p>
<h1><a class="anchor" aria-hidden="true" id="validation"> </a>Validation</h1>
<p>docker images<br />
docker run hello-world<br />
docker -v<br />
</pre></p>
</details>
<h2><a class="anchor" aria-hidden="true" id="2-start-local-cluster"> </a>2. Start Local Cluster</h2>
<ul>
<li><strong>Start Cassandra</strong></li>
</ul>
<p>After cloning this repository you can start either you local instance of Cassandra with <code>$Cassandra_HOME/bin/cassandra</code> or with docker-compose.</p>
<pre><code>docker-compose up -d
</code></pre>
<ul>
<li><strong>Run Samples</strong></li>
</ul>
<p>You can execute each class with <code>maven</code> and or your favorite IDE. Each class will create everything needed each time <code>keyspace</code> and <code>tables</code>. The working tables will be empty in the beginning for not dropped.</p>
<pre><code>cd example-3x
mvn exec:java -D&quot;exec.mainClass&quot;=&quot;com.datastax.samples.SampleCode3x_CONNECT_ClusterShowMetaData&quot;
</code></pre>
<ul>
<li><strong>Data displayed with CQL Shell</strong></li>
</ul>
<p>If cassandra is running as a docker container and you want to have a cqlsh shell please execute:</p>
<pre><code>docker exec -it `docker ps | grep cassandra:3.11.5 | cut -b 1-12` cqlsh
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="working-with-schema"> </a>Working with Schema</h2>
<table>
<thead>
<tr>
<th align="center">3x</th>
<th align="center">4x</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td align="center"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CONNECT_ClusterShowMetaData.java" target="_blank">ShowMetaData3x</a></td>
<td align="center"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CONNECT_ClusterShowMetaData.java" target="_blank">ShowMetaData4x</a></td>
<td align="left">Connect to cluster then show keyspaces and metadata</td>
</tr>
<tr>
<td align="center"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CONNECT_CreateKeyspace.java" target="_blank">CreateKeyspace3x</a></td>
<td align="center"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CONNECT_CreateKeyspace.java" target="_blank">CreateKeyspace4x</a></td>
<td align="left">Create the <code>killrvideo</code> keyspace using <code>SchemaBuilder</code> if not exist</td>
</tr>
<tr>
<td align="center"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CONNECT_CreateSchema.java" target="_blank">CreateSchema3x</a></td>
<td align="center"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CONNECT_CreateSchema.java" target="_blank">CreateSchema4x</a></td>
<td align="left">Create <code>table</code> and <code>type</code> in <code>killrvideo</code> keyspace if they don't exist</td>
</tr>
<tr>
<td align="center"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CONNECT_DropKeyspace.java" target="_blank">DropKeyspace3x</a></td>
<td align="center"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CONNECT_DropKeyspace.java" target="_blank">DropKeyspace4x</a></td>
<td align="left">Drop the <code>killrvideo</code> keyspace if existis using  <code>SchemaBuilder</code></td>
</tr>
<tr>
<td align="center"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CONNECT_DropSchema.java" target="_blank">DropSchema3x</a></td>
<td align="center"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CONNECT_DropSchema.java" target="_blank">DropSchema4x</a></td>
<td align="left">Drop all  <code>table</code> and <code>type</code> in <code>killrvideo</code> keyspace if they exist</td>
</tr>
<tr>
<td align="center">---</td>
<td align="center"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CONNECT_DriverConfigLoader.java" target="_blank">ConfigurationFile4x</a></td>
<td align="left">Setup the driver using custom conf file and not default <code>application.conf</code></td>
</tr>
<tr>
<td align="center">---</td>
<td align="center"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CONNECT_ProgrammaticConfiguration.java" target="_blank">ProgrammaticConfig4x</a></td>
<td align="left">Setup the driver in a programmatic way</td>
</tr>
</tbody>
</table>
<h2><a class="anchor" aria-hidden="true" id="executing-queries"> </a>Executing Queries</h2>
<table>
<thead>
<tr>
<th align="left">3x</th>
<th align="left">4x</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_00_GettingStarted.java" target="_blank">GettingStarted3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_00_GettingStarted.java" target="_blank">GettingStarted4x</a></td>
<td align="left">First touch with executing queries</td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_01_Simple.java" target="_blank">Simple3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_01_Simple.java" target="_blank">Simple4x</a></td>
<td align="left">Read, update, insert, delete operations using <code>QueryBuilder</code></td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_02_Paging.java" target="_blank">Paging3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_02_Paging.java" target="_blank">Paging4x</a></td>
<td align="left">Illustrating FetchSize and how to retrieve page by page</td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_03_Batches.java" target="_blank">Batches3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_03_Batches.java" target="_blank">Batches4x</a></td>
<td align="left">Group statements within batches</td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_04_ListSetMapAndUdt.java" target="_blank">ListSetMapUdt3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_04_ListSetMapAndUdt.java" target="_blank">ListSetMapUdt4x</a></td>
<td align="left">Advanced types insertions with <code>list</code>, <code>set</code>, <code>map</code> but also <code>User Defined Type</code></td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_05_Json.java" target="_blank">Json3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_05_Json.java" target="_blank">Json4x</a></td>
<td align="left">Work with columns or full record with <code>JSON</code></td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_06_Async.java" target="_blank">Async3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_06_Async.java" target="_blank">Async4x</a></td>
<td align="left">Sample operations as Simple in <code>Asynchronous</code> way</td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_07_ObjectMapping.java" target="_blank">ObjectMapping3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_07_ObjectMapping.java" target="_blank">ObjectMapping4x</a></td>
<td align="left">Map table record to Java POJO at driver level</td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_08_Counters.java" target="_blank">Counter3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_08_Counters.java" target="_blank">Counter4x</a></td>
<td align="left">Working with <code>counters</code> increment/decrement</td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_09_LightweightTransactions.java" target="_blank">Lwt3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_09_LightweightTransactions.java" target="_blank">Lwt4x</a></td>
<td align="left">Working for Lightweight transactions read-before-write</td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CRUD_10_BlobAndCodec.java" target="_blank">BlobAndCodec3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_10_BlobAndCodec.java" target="_blank">BlobAndCodec4x</a></td>
<td align="left">Working with <code>BLOB</code> and binary data but also how to create your own <code>CustomCodec</code></td>
</tr>
<tr>
<td align="left"><a href="./example-3x/src/main/java/com/datastax/samples/SampleCode3x_CONNECT_ServiceCloudAstra.java" target="_blank">CloudAstra3x</a></td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CONNECT_ServiceCloudAstra.java" target="_blank">CloudAstra4x</a></td>
<td align="left">Working with <code>BLOB</code> and binary data but also how to create your own <code>CustomCodec</code></td>
</tr>
<tr>
<td align="left">---</td>
<td align="left"><a href="./example-4x/src/main/java/com/datastax/samples/SampleCode4x_CRUD_11_Reactive.java" target="_blank">Reactive4x</a></td>
<td align="left">Working with the Reactive API introduce in driver 4.x</td>
</tr>
</tbody>
</table>
<p>For reference this is the working schema we used for queries</p>
<pre lang="sql"><code>
// ----------------------------------------
// Sample Keyspace (to be used locally)
// 
// Here a sample if you want to create on multiple node DC
// CREATE KEYSPACE IF NOT EXISTS killrvideo 
// WITH REPLICATION = { 'class' : 'NetworkTopologyStrategy', 'datacenter1' : 3 }
// AND DURABLE_WRITES = true;
// ----------------------------------------

CREATE KEYSPACE IF NOT EXISTS killrvideo 
WITH REPLICATION = { 'class' : 'SimpleStrategy', 'replication_factor' : 1 }
AND DURABLE_WRITES = true;

// ----------------------------------------
// Basic table for basic operations
// ----------------------------------------
// Used by : SampleCodeXx_CRUD_01_Simple
// Used by : SampleCodeXx_CRUD_02_Paging
// Used by : SampleCodeXx_CRUD_06_Async
// Used by : SampleCodeXx_CRUD_09_LightweightTransactions
// ----------------------------------------

CREATE TABLE IF NOT EXISTS users (
 email      text,
 firstname  text,
 lastname   text,
 PRIMARY KEY (email)
);


// ----------------------------------------
// Table to show MAP, LIST, SET, UDT, JSON
// ----------------------------------------
// Used by : SampleCodeXx_CRUD_04_ListSetMapAndUdt
// Used by : SampleCodeXx_CRUD_06_Json
// ----------------------------------------

CREATE TYPE IF NOT EXISTS video_format (
  width   int,
  height  int
);

CREATE TABLE IF NOT EXISTS videos (
  videoid    uuid,
  title      text,
  upload     timestamp,
  email      text,
  url        text,
  tags       set &lt;text&gt;,
  frames     list&lt;int&gt;,
  formats    map &lt;text,frozen&lt;video_format&gt;&gt;,
  PRIMARY KEY (videoid)
);


// ----------------------------------------
// Table to show Batches, ObjectMapping
// ----------------------------------------
// Used by : SampleCodeXx_CRUD_03_Bacthes
// Used by : SampleCodeXx_CRUD_07_ObjectMapping
// ----------------------------------------

CREATE TABLE IF NOT EXISTS comments_by_video (
    videoid uuid,
    commentid timeuuid,
    userid uuid,
    comment text,
    PRIMARY KEY (videoid, commentid)
) WITH CLUSTERING ORDER BY (commentid DESC);

CREATE TABLE IF NOT EXISTS comments_by_user (
    userid uuid,
    commentid timeuuid,
    videoid uuid,
    comment text,
    PRIMARY KEY (userid, commentid)
) WITH CLUSTERING ORDER BY (commentid DESC);


// ----------------------------------------
// Table to show Counters
// ----------------------------------------
// Used by : SampleCodeXx_CRUD_08_Counters
// ----------------------------------------

CREATE TABLE IF NOT EXISTS videos_views (
    videoid     uuid,
    views       counter,
    PRIMARY KEY (videoid)
);


// ----------------------------------------
// Table to show Binary DATA
// ----------------------------------------
// Used by : SampleCodeXx_CRUD_10_Blob
// ----------------------------------------

CREATE TABLE IF NOT EXISTS files (
   filename  text,
   upload    timestamp,
   extension text static,
   binary    blob,
   PRIMARY KEY((filename), upload)
) WITH CLUSTERING ORDER BY (upload DESC);


</code></pre>

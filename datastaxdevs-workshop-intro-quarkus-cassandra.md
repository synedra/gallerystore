<h1><a class="anchor" aria-hidden="true" id="intro-to-quarkus-and-cassandra-with-kubernetes"> </a>Intro to Quarkus and Cassandra with Kubernetes</h1>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/quarkus-astra-intro-demo" target="_blank"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod" alt="Gitpod ready-to-code" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p>Today we showcase an application using <strong>Apache Cassandra™</strong> as a backend implemented with <strong>Quarkus</strong>, and experience some developer joy with features that often have been an envy for Java programmers - hot reloading, debugging, containerizing and finally generating native code.</p>
<p>There are many other features of the Quarkus platform that we will not be looking into that are widely considered as unique strengths of the platform including testing.</p>
<p>We will deploy the app on containers in Kubernetes using Lens.</p>
<p>The application we will be using is based on <a href="https://github.com/tjake/todo-astra-react-serverless/" target="_blank">Jake's port</a> of the <a href="https://github.com/tastejs/todomvc/tree/master/examples/react">TodoMVC code</a> originally written by <a href="https://github.com/petehunt">Pete Hunt</a>. The example is modified from <a href="https://github.com/huksley/todo-react-ssr-serverless">https://github.com/huksley/todo-react-ssr-serverless</a>.</p>
<p>A screenshot of this simple app is below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/AstraTodos.png?raw=true" alt="AstraTodo" /></p>
<p>ℹ️ <strong>Objective(s) of workshop</strong></p>
<p>Whether you're a seasoned developer or relatively new to programming, you will be spending a lot of time in an Integrated Development Environment and the &quot;inner loop&quot; of development with a lightweight CI/CD cycle.</p>
<p>Once you have a stable environment after repeated iterations in the editor, testing environments, profiler, debugger, etc. you push it to the outer loop which has a more robust CI/CD cycle usually backed by gitops, Jenkins and other CI/CD tools.</p>
<p>The objective of today's workshop is to understand how the Quarkus platform simplifies the &quot;inner loop&quot; of development which results in huge developer productivity gains. You will see in today's workshop you can go from plain old Java to containers with relative ease and yet not make a significant change in devlopment.</p>
<p>Although, the Quarkus platform leverages a reactive architecture, the developer tools are drawn from a list that they are familar with and complements them while making those same tools leaner and more performant. This means that Quarkus does not force developers to use reactive programming styles. Additionally, it helps to build better and more performant applications (which is always necessary) and also enhances the day-to-day life of a developer having to bridge the gap between their existing platforms and taking a plunge into microservices, service mesh and so on. Developers can use their current tools and methodologies and let Quarkus take care of being &quot;reactive&quot;, or build new fully-reactive applications that take advantage of Quarkus' reactive core.</p>
<p>ℹ️ <strong>Frequently asked questions</strong></p>
<ul>
<li><em>Can I run the workshop on my computer?</em>
<blockquote>
<p>There is nothing preventing you from running the workshop on your own machine. If you do so, you will need <em>java jdk11+</em>, <em>Graal VM</em>, <em>Maven</em>, an IDE like <em>VSCode, IntelliJ, Eclipse, Spring STS</em>. You will have to adapt commands and paths based on your environment and install the dependencies by yourself. <strong>We won't provide support</strong> to keep on track with schedule.</p>
</blockquote>
</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="prerequisites"> </a>Prerequisites</h2>
<p>We strive to make our hands-on workshops prerequisites free -- who has the time to install prerequistes? :-)</p>
<p>However, docker login credentials, some familiarity with an IDE like <a href="https://code.visualstudio.com" target="_blank">Visual Studio Code</a> or <a href="https://gitpod.io">Gitpod</a> (although not strictly necessary) might help.</p>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="./slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://bit.ly/cassandra-workshop" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
<li><a href="https://github.com/datastaxdevs/quarkus-astra-intro-demo" target="_blank">Workshop code</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="alternate-learning-path-s-in-this-workshop"> </a>Alternate Learning Path(s) in this workshop</h2>
<p>If you're primarily interested in containerization (as in <strong>Slay the complexity of Kubernetes Inner Loop Development</strong>), you can skip most of the early steps and jump straight to <a href="#10-containerizing" target="_blank">Containerizing</a>. Summarizing</p>
<table>
<thead>
<tr>
<th>Focus</th>
<th>Step(s)</th>
<th>Verify connection</th>
<th>Step(s) skipped</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Containers/Inner loop</strong></td>
<td>Do steps 1-6 and 10 onwards</td>
<td><a href="#6-run-some-unit-tests" target="_blank">After steps 1-6, verify connection</a></td>
<td>Skip steps 7,8,9</td>
</tr>
</tbody>
</table>
<h2><a class="anchor" aria-hidden="true" id="0-table-of-contents"> </a>0. Table of contents</h2>
<ol>
<li><a href="#1-create-astra-db-instance" target="_blank">Database Initialization</a></li>
<li><a href="#3-launch-gitpod" target="_blank">Launch Gitpod</a></li>
<li><a href="#4-know-your-gitpod" target="_blank">Know your Gitpod</a></li>
<li><a href="#5-setup-your-application" target="_blank">Setup your Application</a></li>
<li><a href="#6-run-some-unit-tests" target="_blank">Run Unit test(s)</a></li>
<li><a href="#7-quarkus-dev-mode" target="_blank">Quarkus Dev Mode</a></li>
<li><a href="#8-debugging" target="_blank">Debugging</a></li>
<li><a href="#9-packaging" target="_blank">Packaging</a></li>
<li><a href="#10-containerizing" target="_blank">Containerizing</a></li>
<li><a href="#11-native-image" target="_blank">Native Image</a></li>
<li><a href="#12-homework" target="_blank">Homework</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="1-database-initialization"> </a>1. Database Initialization</h2>
<h3><a class="anchor" aria-hidden="true" id="1-1-create-an-astra-account"> </a>1.1 - Create an Astra Account</h3>
<blockquote>
<p><strong>Note</strong>: <strong>Datastax Astra</strong> is a cloud-native, fully managed database-as-a-service (DBaaS) based on Apache Cassandra. It provides a scalable, performant and highly available database solution without the operational overhead of managing Cassandra clusters. Astra supports both SQL and NoSQL APIs, and includes features like backup and restore, monitoring and alerting, and access control. It enables developers to focus on application development while the database infrastructure is managed by Datastax.</p>
</blockquote>
<ul>
<li><code>✅ 1.1.a</code> - Access <a href="https://astra.datastax.com" target="_blank">https://astra.datastax.com</a> and register with <code>Google</code> or <code>Github</code> account</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/astra-login.png?raw=true%22" alt="" /></p>
<h3><a class="anchor" aria-hidden="true" id="1-2-create-an-astra-db"> </a>1.2 - Create an Astra DB</h3>
<blockquote>
<p><strong>Info</strong> <a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/" target="_blank">Reference Documentation</a></p>
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
<td>Database name</td>
<td><code>workshops</code></td>
</tr>
<tr>
<td>Keyspace name</td>
<td><code>todolist</code></td>
</tr>
<tr>
<td>Cloud</td>
<td><code>GCP</code></td>
</tr>
<tr>
<td>Region</td>
<td><code>us-east1</code></td>
</tr>
</tbody>
</table>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/astra-create-db.png?raw=true%22" alt="" /></p>
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h3><a class="anchor" aria-hidden="true" id="1-3-create-an-astra-token"> </a>1.3 - Create an Astra Token</h3>
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
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="2-gitpod"> </a>2. Gitpod</h2>
<p><a href="https://www.gitpod.io/" target="_blank">Gitpod</a> is an IDE 100% online based on <a href="https://github.com/gitpod-io/vscode/blob/gp-code/LICENSE.txt?lang=en-US">VS Code</a>. To initialize your environment simply click on the button below<br />
<em>(CTRL + Click to open in new tab)</em> You will be asked for you github account, as needed.</p>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/quarkus-astra-intro-demo" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<p><strong>👁️ Expected output</strong></p>
<p><em>The screenshot may be slightly different based on your default skin and a few edits in the read me.</em></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/gitpod-01-home-plain.png?raw=true" alt="gitpod" /></p>
<p><strong>That's it.</strong> Gitpod provides all tools we will need today including <code>maven</code> and exposing port <code>8080</code>, ports <code>5005</code> which is used for debugging, etc.</p>
<p><strong>You may safely ignore the error output at the end of the terminal window.</strong></p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/gitpod-quarkus-1.jpg?raw=true" alt="image" /></p>
<p>Although GitPod terminal might seem to be available, the setup might still be ongoing. Wait for a few minutes before entering commands in the GitPod terminal window.</p>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="4-know-your-gitpod"> </a>4. Know your gitpod</h2>
<p>Take a moment to read this entire section since it'll help you with the rest of the workshop as you'll be spending most of your time in Gitpod. If you're familiar with Gitpod, you can easily skip this entire section.</p>
<p>The extreme left side has the explorer view(1). The top left, middle to right is where you'll be editing files(2), etc. and the bottom left, middle to right is what we will refer to as the Gitpod terminal window(3) as shown below.</p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/gitpod-01-home-annotated.png?raw=true" alt="gitpod" /></p>
<p>You can always get back to the file explorer view whenever by clicking on the hamburger menu on the top left followed by <code>View</code> and <code>Explorer</code> as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/Filexplorer0.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 4a: Know your public URL</strong></p>
<p>The workshop application has opened with an ephemeral URL. To know the URL where your application endpoint will be exposed you can run the following command in the terminal after the build has completed. <strong>Please note this URL and open this up in a new browser window as shown below</strong>.</p>
<pre lang="bash"><code>gp url 8080
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/gitpod-02-url.png?raw=true" alt="gitpod" /></p>
<p>Although the application is not running yet,<br />
launch a new browser window (<strong>don't close it for the rest of the workshop since you'll continually keep using this</strong>. If you accidentally close it, just come back to this step. The browser will generate an error (due to application not running yet) which is fine for now as shown below.</p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/newbrowser1.png?raw=true" alt="gitpod" /></p>
<p>You may encounter the following at different steps and although this may not be applicable right away, the steps are included <strong>in advance</strong> and summarized here so that you can keep an eye out for it. Different paths and different environments might be slightly different although Gipod levels the playing field a bit.</p>
<p>You can allow cutting and pasting into the window by clicking on <code>Allow</code> as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/allow.png?raw=true" alt="gitpod" /></p>
<p>Or allow ports to be opened by just exiting windows that are informational messages about ports like below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/OpenPorts.png?raw=true" alt="gitpod" /></p>
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="5-setup-your-application"> </a>5. Setup your application</h2>
<p>To run the application you need to provide the credentials and identifier to the application.</p>
<p>Issue the following command from the Gitpod terminal window.</p>
<pre><code>gp open src/main/resources/application.properties
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/editapplicationproperties1.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 5a: Enter 2 values from the token</strong></p>
<p>Enter the values of <code>Client Id</code> and <code>Client Secret</code> from values noted earlier for <code>astra-username</code> and <code>astra-password</code> respectively. The two lines with a TBD in comments is shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/editapplicationproperties2.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 5b: Download the secure connect bundle</strong></p>
<pre><code>curl -Ls &quot;https://dtsx.io/get-astra-cli&quot; | bash
source /home/gitpod/.astra/cli/astra-init.sh
astra
astra setup --token &lt;&gt;
astra db download-scb workshops -f /workspace/quarkus-astra-intro-demo/secure-connect-workshops.zip 
ls -l secure-connect-workshops.zip
</code></pre>
<p>The file size should be roughly 12K otherwise something may have gone wrong in the process.</p>
<p><strong>👁️ Expected output</strong></p>
<pre><code>-rw-r--r-- 1 gitpod gitpod 12231 Oct 26 00:15 secure-connect-workshops.zip
</code></pre>
<p>TADA your application is now configured we can finally play with some code.</p>
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="6-run-some-unit-test-s"> </a>6. Run some unit test(s)</h2>
<p>The application is now set and you should be able to interact with your DB, although connecting to a &quot;real&quot; DB is not necessary in order to execute tests. The application's tests use the <a href="https://github.com/datastax/cassandra-quarkus/tree/main/test-framework" target="_blank">Quarkus Cassandra Test Framework</a>. Quarkus will automatically bootstrap a Cassandra Docker container and connect it to the application when the tests execute.</p>
<p>Under the covers, all interaction with Cassandra is implemented in Java through the <code>com.datastax.oss.driver.api.core.CqlSession</code>, part of the <a href="https://docs.datastax.com/en/developer/java-driver/latest" target="_blank">DataStax Java Driver</a>. Higher level frameworks like Quarkus, Spring, Spring Data, rely on this object. The <a href="https://github.com/datastax/cassandra-quarkus/tree/main/test-framework">Quarkus Cassandra Test Framework</a> makes sure its available to the tests.</p>
<p>Let's run this unit test in the Gitpod terminal window.</p>
<pre lang="bash"><code>./mvnw test -Dtest=com.datastaxdev.todo.rest.TodoResourceTests
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre><code>Picked up JAVA_TOOL_OPTIONS:  -Xmx3435m
[INFO] Scanning for projects...
[INFO] 
[INFO] ---------&lt; quarkus-astra-intro-demo:quarkus-astra-intro-demo &gt;----------
[INFO] Building quarkus-astra-intro-demo 0.01
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ quarkus-astra-intro-demo ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 24 resources
[INFO] 
[INFO] --- quarkus-maven-plugin:2.9.1.Final:generate-code (default) @ quarkus-astra-intro-demo ---
[INFO] 
[INFO] --- maven-compiler-plugin:3.8.1:compile (default-compile) @ quarkus-astra-intro-demo ---
[INFO] Nothing to compile - all classes are up to date
[INFO] 
[INFO] --- quarkus-maven-plugin:2.9.1.Final:generate-code-tests (default) @ quarkus-astra-intro-demo ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ quarkus-astra-intro-demo ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 1 resource
[INFO] 
[INFO] --- maven-compiler-plugin:3.8.1:testCompile (default-testCompile) @ quarkus-astra-intro-demo ---
[INFO] Nothing to compile - all classes are up to date
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M5:test (default-test) @ quarkus-astra-intro-demo ---
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[ERROR] Picked up JAVA_TOOL_OPTIONS:  -Xmx3435m
[INFO] Running com.datastaxdev.todo.rest.TodoResourceTests
INFO  [org.jbo.threads] (main) JBoss Threads version 3.4.2.Final
INFO  [org.tes.uti.ImageNameSubstitutor] (main) Image name substitution will be performed by: DefaultImageNameSubstitutor (composite of 'ConfigurationFileImageNameSubstitutor' and 'PrefixingImageNameSubstitutor')
INFO  [org.tes.doc.DockerClientProviderStrategy] (pool-4-thread-1) Loaded org.testcontainers.dockerclient.UnixSocketClientProviderStrategy from ~/.testcontainers.properties, will try it first
INFO  [org.tes.doc.DockerClientProviderStrategy] (pool-4-thread-1) Found Docker environment with local Unix socket (unix:///var/run/docker.sock)
INFO  [org.tes.DockerClientFactory] (pool-4-thread-1) Docker host IP address is localhost
INFO  [org.tes.DockerClientFactory] (pool-4-thread-1) Connected to docker: 
  Server Version: 20.10.14
  API Version: 1.41
  Operating System: Ubuntu 20.04.4 LTS
  Total Memory: 64312 MB
INFO  [org.tes.uti.RegistryAuthLocator] (pool-4-thread-1) Failure when attempting to lookup auth config. Please ignore if you don't have images in an authenticated registry. Details: (dockerImageName: testcontainers/ryuk:0.3.3, configFile: /home/gitpod/.docker/config.json. Falling back to docker-java default behaviour. Exception message: /home/gitpod/.docker/config.json (No such file or directory)
INFO  [org.tes.uti.RyukResourceReaper] (pool-4-thread-1) Ryuk started - will monitor and terminate Testcontainers containers on JVM exit
INFO  [org.tes.DockerClientFactory] (pool-4-thread-1) Checking the system...
INFO  [org.tes.DockerClientFactory] (pool-4-thread-1) ✔︎ Docker server version should be at least 1.6.0
INFO  [org.tes.DockerClientFactory] (pool-4-thread-1) ✔︎ Docker environment should have more than 2GB free disk space
INFO  [com.dat.oss.qua.tes.CassandraTestResource] (pool-4-thread-1) Container cassandra:latest starting...
INFO  [🐳 [cassandra:latest]] (pool-4-thread-1) Creating container for image: cassandra:latest
INFO  [🐳 [cassandra:latest]] (pool-4-thread-1) Container cassandra:latest is starting: 001d53b387a0a5861466621f6828e753036bec4d9958562ba24a934442c430e5
INFO  [com.dat.dri.core] (ducttape-0) DataStax Java driver 3.7.1 for Apache Cassandra
INFO  [com.dat.dri.cor.GuavaCompatibility] (ducttape-0) Detected Guava &gt;= 19 in the classpath, using modern compatibility layer
INFO  [com.dat.dri.cor.ClockFactory] (ducttape-0) Using native clock to generate timestamps.
INFO  [com.dat.dri.cor.NettyUtil] (ducttape-0) Did not find Netty's native epoll transport in the classpath, defaulting to NIO.
INFO  [com.dat.dri.cor.ClockFactory] (ducttape-0) Using native clock to generate timestamps.
INFO  [com.dat.dri.cor.ClockFactory] (ducttape-0) Using native clock to generate timestamps.
WARN  [com.dat.dri.cor.Cluster] (ducttape-0) You listed localhost/127.0.0.1:49156 in your contact points, but it wasn't found in the control host's system.peers at startup
INFO  [com.dat.dri.cor.pol.DCAwareRoundRobinPolicy] (ducttape-0) Using data-center name 'datacenter1' for DCAwareRoundRobinPolicy (if this is incorrect, please provide the correct datacenter name with DCAwareRoundRobinPolicy constructor)
INFO  [com.dat.dri.cor.Cluster] (ducttape-0) New Cassandra host localhost/0:0:0:0:0:0:0:1:49156 added
INFO  [🐳 [cassandra:latest]] (pool-4-thread-1) Container cassandra:latest started in PT9.049449S
INFO  [org.tes.ext.ScriptUtils] (pool-4-thread-1) Executing database script from init_script.cql
INFO  [com.dat.dri.cor.ClockFactory] (pool-4-thread-1) Using native clock to generate timestamps.
WARN  [com.dat.dri.cor.Cluster] (pool-4-thread-1) You listed localhost/127.0.0.1:49156 in your contact points, but it wasn't found in the control host's system.peers at startup
INFO  [com.dat.dri.cor.pol.DCAwareRoundRobinPolicy] (pool-4-thread-1) Using data-center name 'datacenter1' for DCAwareRoundRobinPolicy (if this is incorrect, please provide the correct datacenter name with DCAwareRoundRobinPolicy constructor)
INFO  [com.dat.dri.cor.Cluster] (pool-4-thread-1) New Cassandra host localhost/0:0:0:0:0:0:0:1:49156 added
INFO  [org.tes.ext.ScriptUtils] (pool-4-thread-1) Executed database script from init_script.cql in 2132 ms.
INFO  [com.dat.dri.cor.ClockFactory] (pool-4-thread-1) Using native clock to generate timestamps.
WARN  [com.dat.dri.cor.Cluster] (pool-4-thread-1) You listed localhost/0:0:0:0:0:0:0:1:49156 in your contact points, but it wasn't found in the control host's system.peers at startup
INFO  [com.dat.dri.cor.pol.DCAwareRoundRobinPolicy] (pool-4-thread-1) Using data-center name 'datacenter1' for DCAwareRoundRobinPolicy (if this is incorrect, please provide the correct datacenter name with DCAwareRoundRobinPolicy constructor)
INFO  [com.dat.dri.cor.Cluster] (pool-4-thread-1) New Cassandra host localhost/127.0.0.1:49156 added
INFO  [com.dat.oss.qua.tes.CassandraTestResource] (pool-4-thread-1) Container cassandra:latest listening on 127.0.0.1:49156 (inferred local DC: datacenter1)
WARN  [io.qua.config] (main) Unrecognized configuration key &quot;quarkus.kubernetes.service-type&quot; was provided; it will be ignored; verify that the dependency extension for this configuration is set or that you did not make a typo
WARN  [io.qua.config] (main) Unrecognized configuration key &quot;quarkus.kubernetes.env.secrets&quot; was provided; it will be ignored; verify that the dependency extension for this configuration is set or that you did not make a typo
INFO  [com.dat.oss.qua.run.int.qua.CassandraClientRecorder] (main) Enabling Cassandra metrics using Micrometer.
INFO  [com.dat.oss.qua.run.int.qua.CassandraClientStarter] (main) Eagerly initializing Quarkus Cassandra client.
INFO  [com.dat.oss.dri.int.cor.DefaultMavenCoordinates] (main) DataStax Java driver for Apache Cassandra(R) (com.datastax.oss:java-driver-core) version 4.14.0
INFO  [com.dat.oss.dri.int.cor.tim.Clock] (vert.x-eventloop-thread-0) Using native clock for microsecond precision
INFO  [com.dat.tod.res.TodoResource] (main) **** Table created true****
INFO  [io.quarkus] (main) quarkus-astra-intro-demo 0.01 on JVM (powered by Quarkus 2.9.1.Final) started in 16.146s. Listening on: http://localhost:41159
INFO  [io.quarkus] (main) Profile test activated. 
INFO  [io.quarkus] (main) Installed features: [cassandra-client, cdi, micrometer, resteasy-reactive, resteasy-reactive-jackson, smallrye-context-propagation, smallrye-health, smallrye-openapi, swagger-ui, vertx]
[INFO] Tests run: 8, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 19.304 s - in com.datastaxdev.todo.rest.TodoResourceTests
INFO  [com.dat.oss.qua.run.int.qua.CassandraClientRecorder] (main) Closing Quarkus Cassandra session.
INFO  [io.quarkus] (main) quarkus-astra-intro-demo stopped in 0.039s
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 8, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  25.096 s
[INFO] Finished at: 2022-05-16T18:22:07Z
[INFO] ------------------------------------------------------------------------
</code></pre>
<p>You can see from the output that the <code>cassandra:latest</code> Docker container was started before the tests were executed.</p>
<p>Verfiy that the table got created with the following command</p>
<pre lang="bash"><code>./mvnw test -Dcom.datastaxdev.todo.rest.TodoResourceTests | grep -i table
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre><code>INFO  [com.dat.tod.res.TodoResource] (main) **** Table created true****
</code></pre>
<blockquote>
<p>You will likely see that output repeated more than once.</p>
</blockquote>
<p>Although a significant strength of the Quarkus platform is it's <a href="https://quarkus.io/guides/continuous-testing" target="_blank">continuous testing</a> capabilities, we will skip tests going foraward and focus on the other capabilities of the platform (perhaps, another workshop sometime focussed mainly on testing capabilities, assuming there is enough demand).</p>
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="7-quarkus-dev-mode"> </a>7. Quarkus Dev Mode</h2>
<p>Before we get started let's check that the Graal VM is available.</p>
<pre><code>echo $GRAALVM_HOME
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre><code>/home/gitpod/.sdkman/candidates/java/current
</code></pre>
<p>✅ <strong>Step 7a: Begin dev</strong></p>
<p>In the Gitpod terminal window, We will begin the inner loop journey in dev mode using the following command.</p>
<pre lang="bash"><code>./mvnw quarkus:dev -DskipTests
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre><code>__  ____  __  _____   ___  __ ____  ______ 
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/ 
 -/ /_/ / /_/ / __ |/ , _/ ,&lt; / /_/ /\ \   
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/   
WARN  [io.qua.config] (Quarkus Main Thread) Unrecognized configuration key &quot;quarkus.kubernetes.service-type&quot; was provided; it will be ignored; verify that the dependency extension for this configuration is set or that you did not make a typo

WARN  [io.qua.config] (Quarkus Main Thread) Unrecognized configuration key &quot;quarkus.kubernetes.env.secrets&quot; was provided; it will be ignored; verify that the dependency extension for this configuration is set or that you did not make a typo
INFO  [com.dat.oss.qua.run.int.qua.CassandraClientRecorder] (Quarkus Main Thread) Enabling Cassandra metrics using Micrometer.
INFO  [com.dat.oss.qua.run.int.qua.CassandraClientStarter] (Quarkus Main Thread) Eagerly initializing Quarkus Cassandra client.
INFO  [com.dat.oss.dri.int.cor.DefaultMavenCoordinates] (Quarkus Main Thread) DataStax Java driver for Apache Cassandra(R) (com.datastax.oss:java-driver-core) version 4.14.0
INFO  [com.dat.oss.dri.int.cor.tim.Clock] (vert.x-eventloop-thread-0) Using native clock for microsecond precision
INFO  [com.dat.oss.dri.int.cor.ses.DefaultSession] (vert.x-eventloop-thread-9) [s0] Negotiated protocol version V4 for the initial contact point, but cluster seems to support V5, keeping the negotiated version
INFO  [com.dat.tod.res.TodoResource] (Quarkus Main Thread) **** Table created true****
INFO  [io.quarkus] (Quarkus Main Thread) quarkus-astra-intro-demo 0.01 on JVM (powered by Quarkus 2.9.1.Final) started in 7.383s. Listening on: http://localhost:8080
INFO  [io.quarkus] (Quarkus Main Thread) Profile dev activated. Live Coding activated.
INFO  [io.quarkus] (Quarkus Main Thread) Installed features: [cassandra-client, cdi, micrometer, resteasy-reactive, resteasy-reactive-jackson, smallrye-context-propagation, smallrye-health, smallrye-openapi, swagger-ui, vertx]

--
Tests paused
Press [r] to resume testing, [o] Toggle test output, [:] for the terminal, [h] for more options&gt;
</code></pre>
<p>✅ <strong>Step 7b: Explore Quarkus dev mode</strong></p>
<p>Typing <code>h</code> in the terminal window should bring up the following</p>
<p><strong>👁️ Expected output</strong></p>
<pre><code>The following commands are currently available:

== Continuous Testing

[r] - Resume testing
[o] - Toggle test output (disabled)

== Exceptions

[x] - Opens last exception in IDE (None)

== HTTP

[w] - Open the application in a browser
[d] - Open the Dev UI in a browser

== System

[s] - Force restart
[i] - Toggle instrumentation based reload (disabled)
[l] - Toggle live reload (enabled)
[j] - Toggle log levels (INFO)
[h] - Shows this help
[:] - Enters terminal mode
[q] - Quits the application

--
Tests paused
Press [r] to resume testing, [o] Toggle test output, [:] for the terminal, [h] for more options&gt;
</code></pre>
<p>You can try the different options available.</p>
<p>Note that you may have to allow popups from <code>gitpod.io</code> as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/quarkus-dev-0.png?raw=true" alt="gitpod" /></p>
<p>Try connecting to the application in a browser by pressing the <code>w</code> key as indicated above. This should bring up the application as below.</p>
<blockquote>
<p><strong>NOTE:</strong> This may not actually work in Gitpod because of the way Gitpod handles links. If the page doesn't open for you simply go to the browser tab you opened back in step 4a.</p>
</blockquote>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/quarkus-dev-1.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 7c: Hot reload</strong><br />
Now, let's go ahead and make an illustrative change.</p>
<p>Navigate to the file <code>src/main/java/resources/META-INF/resources/index.html</code> and change the <code>data-ribbon</code> entry from &quot;Fork me on Github&quot; to &quot;Fork me today on Github.&quot;</p>
<p>Next, refresh the browser page. You should immediately see the update. This hot reloading feature of Quarkus works for more than just static content too!</p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/quarkus-dev-2.png?raw=true" alt="gitpod" /></p>
<p>You could add a few entries to the &quot;todo list&quot; as shown below.</p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/quarkus-dev-3.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 7d: Quarkus dev metrics</strong></p>
<p>You can get Quarkus development metrics and so on hitting the <code>d</code> key as indicated in the help and this should bring up a window that looks like below.</p>
<blockquote>
<p><strong>NOTE:</strong> Again, because of the way Gitpod works, this may not bring up the window. If it doesn't, go back to the browser window containing the running application and append <code>/q/dev</code> to the URL.</p>
</blockquote>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/quarkus-dev-4.png?raw=true" alt="gitpod" /></p>
<blockquote>
<p>The <code>/q/dev</code> end point can be accessed using the URL below when the application is running in <code>dev</code> mode. You can use another <code>bash</code> tab in the gitpod terminal window to enter the commands while the application is running and switch between tabs as required.</p>
</blockquote>
<pre><code>echo $(gp url 8080)/q/dev
</code></pre>
<p>and the <code>openapi</code> spec is at</p>
<pre><code>echo $(gp url 8080)/q/openapi
</code></pre>
<p>as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/quarkus-dev-5.png?raw=true" alt="gitpod" /></p>
<p>You could continue developing your entire application without ever leaving dev mode! It will even handle refactorings and project dependency changes!</p>
<p>Let's out of development mode by hitting <code>q</code> or hitting <code>&lt;Ctrl&gt;+C</code>.</p>
<p>✅ <strong>Step 7e: Quarkus smart dispatch</strong></p>
<p>Let's quickly examine the <a href="https://quarkus.io/blog/resteasy-reactive-smart-dispatch" target="_blank">Quarkus smart dispatching mechanism</a>. Let's open the <code>com.datastaxdev.todo.rest.TodoResource.java</code> class by executing the following in a terminal:</p>
<pre><code>gp open src/main/java/com/datastaxdev/todo/rest/TodoResource.java
</code></pre>
<p>Notice some methods return <a href="https://quarkus.io/guides/mutiny-primer" target="_blank">Mutiny reactive types</a> (i.e. <code>Uni</code> and <code>Multi</code>) while others return non-reactive types (i.e. <code>String</code>, <code>Response</code>, and <code>void</code>). Quarkus doesn't care whether you write reactive or blocking code. Quarkus will make sure reactive code runs on the I/O thread while blocking code will be moved off onto worker thread(s). As you can see, you can even mix and match within the same class!</p>
<p>This application was designed to illustrate both approaches. Which methods are implemented in which manner were randomly chosen.</p>
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="8-debugging"> </a>8. Debugging</h2>
<p>You can always get back to the file explorer view whenever by clicking on the hamburger menu on the top left followed by <code>View</code> and <code>Explorer</code> as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/Filexplorer0.png?raw=true" alt="gitpod" /></p>
<p>Let's go ahead and hit <code>q</code> or <code>Ctrl+C</code> to exit out of the running application if you have not already.</p>
<p>Before we set a breakpoint and start debugging, let's explain the application's structure a bit. The <code>TodoResource</code> class (which you saw in the previous section) calls a <code>com.datastaxdev.todo.service.AstraService</code>. <code>AstraService</code> is an interface with 2 implementations:</p>
<ol>
<li><code>com.datastaxdev.todo.service.CqlSessionAstraService.java</code>
<ul>
<li>Uses the <code>com.datastax.oss.quarkus.runtime.api.session.QuarkusCqlSession</code> directly using CQL queries to implement the operations.</li>
</ul>
</li>
<li><code>com.datastaxdev.todo.service.MapperAstraService.java</code>
<ul>
<li>Uses the <a href="https://docs.datastax.com/en/developer/java-driver/latest/manual/mapper" target="_blank">DataStax Object Mapper</a> and <a href="https://quarkus.io/guides/cassandra#creating-the-data-model-and-data-access-objects">Cassandra Entity Modeling</a> to model entities as Java objects, greatly simplifying the application's data access layer by sparing you the hassle of writing CQL queries by hand. This is conceptually similar to how <a href="https://hibernate.org">Hibernate</a> works in the <a href="https://docs.oracle.com/javaee/6/tutorial/doc/bnbpz.html">JPA</a> world.</li>
<li>Uses <a href="https://mapstruct.org" target="_blank">Mapstruct</a> to easily convert between the <code>com.datastaxdev.todo.dao.TodoItem</code> dao entities and the <code>com.datastaxdev.todo.api.Todo</code> POJO used at the REST layer. See the <code>com.datastaxdev.todo.mapping.TodoMapper</code> class for details.</li>
</ul>
</li>
</ol>
<p>The application has a <a href="https://quarkus.io/guides/cdi-reference#enable_build_properties" target="_blank">build-time property</a> (not overridable at runtime) called <code>astra-service.type</code>. Resolving dependency injection at build time is one of the key benefits of Quarkus, allowing Quarkus applications to be super small and memory-performant.</p>
<p>By default, if this property is undefined <em>OR</em> has the value <code>cql-session</code>, <code>com.datastaxdev.todo.service.CqlSessionAstraService</code> will be injected as the implementation for <code>com.datastaxdev.todo.service.AstraService</code>.</p>
<p>If, at build time, <code>astra-service.type=dao</code>, then <code>com.datastaxdev.todo.service.MapperAstraService</code> will be used instead.</p>
<p>The <code>com.datastaxdev.todo.config.AstraConfig</code> class contains everything needed for reading the <code>astra-service.type</code> flag at build time and injecting the appropriate <code>com.datastaxdev.todo.service.AstraService</code> implementation.</p>
<p>There is a full suite of unit tests that cover both implementations! See <code>src/test/java/com/datastaxdev/todo/service/CqlSessionAstraServiceTests.java</code> and  <code>src/test/java/com/datastaxdev/todo/service/MapperAstraServiceTests.java</code> for details.</p>
<blockquote>
<p>If you'd like to play around with the mapper implementation, open <code>src/main/resources/application.properties</code> and un-comment the line <code>#astra-service.type=dao</code>.</p>
</blockquote>
<p>Since the application, by default, uses the <code>com.datastaxdev.todo.service.CqlSessionAstraService</code> implementation, we'll use that implementation for setting the breakpoint.</p>
<p>✅ <strong>Step 8a: Set breakpoint</strong></p>
<p>Now issue the following command to open up the file where we will subsequently set a breakpoint to be hit whenever we create a new todo item.</p>
<pre><code>gp open src/main/java/com/datastaxdev/todo/service/CqlSessionAstraService.java
</code></pre>
<p>Now navigate to line 52 and set a breakpoint by clicking to the left of the line number 52 and you'll see a stop sign as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/debug1.png?raw=true" alt="gitpod" /></p>
<p>Re-run the application with the following command and we will debug it live.</p>
<pre lang="bash"><code>./mvnw quarkus:dev
</code></pre>
<p>✅ <strong>Step 8b: Start debugging</strong></p>
<p>First, click on the debug button on the left towards top.</p>
<p>Then, click on the arrow on the top left to start debugging as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/debug2.png?raw=true" alt="gitpod" /></p>
<p>Notice debug related information populate in the left side of the window as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/debug3.png?raw=true" alt="gitpod" /></p>
<blockquote>
<p>If for some reason the debugger doesn't attach, there may be some weirdness going on with the Gitpod IDE. Refreshing the browser tab containing the workspace or restarting the workspace will usually fix it.</p>
</blockquote>
<p>We will demonstrate debugging by fixing a todo item that was entered although there are more powerful features that you can try.</p>
<p>Go to the new browser window you created and the application should be up and running. Hit enter after filling up a todo item as shown below. The application freezes and you see a red square that signals the breakpoint has been hit.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/debug4.png?raw=true" alt="gitpod" /></p>
<p>Now that you hit the breakpoint, Cool! Let's go back to the Gitpod window and verify if the breakpoint was really hit. You should see something like below.</p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/debug5.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 8c: Use debugger features</strong></p>
<p>Now, fix the entry spelling in debug mode by clicking on the left(&gt;) arrow of <code>todo</code>, double clicking on the <code>title</code> entry and entering <code>debugging</code>. Finally, hit arrow button in the top small middle pane in the center which will allow the application to continue as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/debug6.png?raw=true" alt="gitpod" /></p>
<p>Go back to your browser and check the todo item that was added to the list. You should see that the updated entry that you fixed with a debug session is what's persisted.</p>
<p>Hit <code>q</code> or <code>Ctrl+C</code> in the GitPod terminal window to exit the application.</p>
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="9-packaging"> </a>9. Packaging</h2>
<p>✅ <strong>Step 9a: Package</strong><br />
You can package up the application with the command below.</p>
<pre lang="bash"><code>./mvnw clean package -DskipTests
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre><code>Picked up JAVA_TOOL_OPTIONS:  -Xmx3435m
[INFO] Scanning for projects...
[INFO] 
[INFO] ---------&lt; quarkus-astra-intro-demo:quarkus-astra-intro-demo &gt;----------
[INFO] Building quarkus-astra-intro-demo 0.01
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ quarkus-astra-intro-demo ---
[INFO] Deleting /workspace/quarkus-astra-intro-demo/target
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ quarkus-astra-intro-demo ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 24 resources
[INFO] 
[INFO] --- quarkus-maven-plugin:2.9.1.Final:generate-code (default) @ quarkus-astra-intro-demo ---
[INFO] 
[INFO] --- maven-compiler-plugin:3.8.1:compile (default-compile) @ quarkus-astra-intro-demo ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 10 source files to /workspace/quarkus-astra-intro-demo/target/classes
[INFO] 
[INFO] --- quarkus-maven-plugin:2.9.1.Final:generate-code-tests (default) @ quarkus-astra-intro-demo ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ quarkus-astra-intro-demo ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 1 resource
[INFO] 
[INFO] --- maven-compiler-plugin:3.8.1:testCompile (default-testCompile) @ quarkus-astra-intro-demo ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 6 source files to /workspace/quarkus-astra-intro-demo/target/test-classes
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M5:test (default-test) @ quarkus-astra-intro-demo ---
[INFO] Tests are skipped.
[INFO] 
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ quarkus-astra-intro-demo ---
[INFO] Building jar: /workspace/quarkus-astra-intro-demo/target/quarkus-astra-intro-demo-0.01.jar
[INFO] 
[INFO] --- quarkus-maven-plugin:2.9.1.Final:build (default) @ quarkus-astra-intro-demo ---
[WARNING] [io.quarkus.config] Unrecognized configuration key &quot;quarkus.kubernetes.env.secrets&quot; was provided; it will be ignored; verify that the dependency extension for this configuration is set or that you did not make a typo
[WARNING] [io.quarkus.config] Unrecognized configuration key &quot;quarkus.kubernetes.service-type&quot; was provided; it will be ignored; verify that the dependency extension for this configuration is set or that you did not make a typo
[INFO] [io.quarkus.deployment.QuarkusAugmentor] Quarkus augmentation completed in 2076ms
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  9.681 s
[INFO] Finished at: 2022-05-16T20:21:41Z
[INFO] ------------------------------------------------------------------------
</code></pre>
<p>✅ <strong>Step 9b: Run</strong></p>
<p>You can run the recently packaged application as below.</p>
<pre lang="bash"><code>java -jar ./target/quarkus-app/quarkus-run.jar
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre><code>Picked up JAVA_TOOL_OPTIONS:  -Xmx3435m
__  ____  __  _____   ___  __ ____  ______ 
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/ 
 -/ /_/ / /_/ / __ |/ , _/ ,&lt; / /_/ /\ \   
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/   
WARN  [io.qua.config] (main) Unrecognized configuration key &quot;quarkus.kubernetes.service-type&quot; was provided; it will be ignored; verify that the dependency extension for this configuration is set or that you did not make a typo
WARN  [io.qua.config] (main) Unrecognized configuration key &quot;quarkus.kubernetes.env.secrets&quot; was provided; it will be ignored; verify that the dependency extension for this configuration is set or that you did not make a typo
INFO  [com.dat.oss.qua.run.int.qua.CassandraClientRecorder] (main) Enabling Cassandra metrics using Micrometer.
INFO  [io.qua.sma.ope.run.OpenApiRecorder] (main) Default CORS properties will be used, please use 'quarkus.http.cors' properties instead
INFO  [com.dat.oss.qua.run.int.qua.CassandraClientStarter] (main) Eagerly initializing Quarkus Cassandra client.
INFO  [com.dat.oss.dri.int.cor.DefaultMavenCoordinates] (main) DataStax Java driver for Apache Cassandra(R) (com.datastax.oss:java-driver-core) version 4.14.0
INFO  [com.dat.oss.dri.int.cor.tim.Clock] (vert.x-eventloop-thread-0) Using native clock for microsecond precision
INFO  [com.dat.oss.dri.int.cor.ses.DefaultSession] (vert.x-eventloop-thread-9) [s0] Negotiated protocol version V4 for the initial contact point, but cluster seems to support V5, keeping the negotiated version
INFO  [com.dat.tod.res.TodoResource] (main) **** Table created true****
INFO  [io.quarkus] (main) quarkus-astra-intro-demo 0.01 on JVM (powered by Quarkus 2.9.1.Final) started in 3.882s. Listening on: http://0.0.0.0:8080
INFO  [io.quarkus] (main) Profile prod activated. 
INFO  [io.quarkus] (main) Installed features: [cassandra-client, cdi, micrometer, resteasy-reactive, resteasy-reactive-jackson, smallrye-context-propagation, smallrye-health, smallrye-openapi, swagger-ui, vertx]
</code></pre>
<p>You can play with the application from the new browser window you created in step 4.</p>
<p>Hit <code>Ctrl+C</code> in the GitPod terminal window to exit the application.</p>
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="10-containerizing"> </a>10. Containerizing</h2>
<p>✅ <strong>Step 10a: Adjust for containerization</strong></p>
<p>We are using the <a href="https://quarkus.io/guides/container-image#jib" target="_blank">Quarkus Jib container extension</a> for easy containerization. Copy the secure connect bundle to the directory that Jib will create on the container as below. We take advantage of the property of Jib plugin which automaticaly includes the relevant artifacts from the <code>src/main/jib</code> sub-directory as part of the process -- we include the secure connect bundle to be able to connect to the Astra database.</p>
<pre lang="bash"><code>mkdir -p src/main/jib/workspace/quarkus-astra-intro-demo/
cp secure-connect-workshops.zip src/main/jib/workspace/quarkus-astra-intro-demo/
</code></pre>
<p>✅ <strong>Step 10b: Containerize</strong></p>
<p>Let's containerize the application with the following command.</p>
<pre lang="bash"><code>./mvnw clean package -Dquarkus.container-image.build=true -DskipTests
</code></pre>
<p>Once complete, check that the image exists on your local repository with the following command:</p>
<pre lang="bash"><code>docker images
</code></pre>
<p><strong>Expected Output</strong></p>
<pre><code>REPOSITORY                 TAG       IMAGE ID       CREATED          SIZE
gitpod/quarkus-cassandra   0.01      77431983359a   26 seconds ago   216MB
</code></pre>
<p>✅ <strong>Step 10c: Run the containerized image</strong></p>
<p>You can execute the recently generated containerized image with the following command.</p>
<pre lang="bash"><code>docker run -i --rm -p 8080:8080 gitpod/quarkus-cassandra:0.01
</code></pre>
<p>Hit &lt;Ctrl+C&gt; in the GitPod terminal window to exit the application.</p>
<p>✅ <strong>Step 10d: docker login</strong></p>
<p>Login to Dockerhub to be able to push containerized images and to be able for you and the rest of the world to pull them.</p>
<p>If you do not have a docker login credential you can skip this step and go right to <a href="#11-native-image" target="_blank">Native Image</a></p>
<pre lang="bash"><code>docker login
</code></pre>
<p><strong>Expected Output</strong></p>
<pre><code>Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.
Username: ragsns
Password: 
WARNING! Your password will be stored unencrypted in /home/gitpod/.docker/config.json.
Configure a credential helper to remove this warning. See
https://docs.docker.com/engine/reference/commandline/login/#credentials-store

Login Succeeded
</code></pre>
<p>Get the Docker ID as below.</p>
<pre lang="bash"><code>docker system info | grep -E 'Username' || echo &quot;you have not done a docker login(yet)&quot;
DOCKER_LOGINID=$(docker system info | grep -E 'Username' | awk '{print $2}')
echo &quot;Docker login ID that will be used: &quot; &quot;$DOCKER_LOGINID&quot;
</code></pre>
<p>You should see an output of your Docker Login ID. If you do not see this repeat this step from the beginning.</p>
<pre><code>Docker login ID that will be used:  ragsns
</code></pre>
<p>✅ <strong>Step 10e: Push to Dockerhub</strong></p>
<p>Let's not only build the containerized image but also push it to DockerHub (<strong>be sure to substitute the group with docker ID</strong>) with the following command.</p>
<pre lang="bash"><code>./mvnw clean package -Dquarkus.container-image.build=true -Dquarkus.container-image.push=true -Dquarkus.container-image.group=$DOCKER_LOGINID -DskipTests
</code></pre>
<p><strong>NOTE:</strong> If the repo in your Docker Hub account didn't previously exist it will be created for you as a <em>private</em> repo. You will need to go into your Docker Hub account and make the repo public.</p>
<p>In today's world of microservices and service meshes, it's all about deploying to Kubernetes. Quarkus gives us an easy way to do that!</p>
<p><strong>Step A</strong>: Quarkus includes the <a href="https://quarkus.io/guides/deploying-to-kubernetes" target="_blank">Kubernetes extension</a>, allowing developers to deploy directly to Kubernetes and use Kubernetes <code>ConfigMap</code>s and <code>Secret</code>s as configuration sources. To use this update <code>pom.xml</code> with the following command in the Gitpod ternimal window as below.</p>
<pre lang="bash"><code>./mvnw quarkus:add-extension -Dextensions=&quot;kubernetes&quot;
</code></pre>
<p>and verify with the following command</p>
<pre lang="bash"><code>git diff pom.xml
</code></pre>
<p>which should that the <code>io.quarkus:quarkus-kubernetes</code> dependency has been added.</p>
<pre lang="bash"><code>diff --git a/pom.xml b/pom.xml
index 371e35e..4b842d8 100644
--- a/pom.xml
+++ b/pom.xml
+    &lt;dependency&gt;
+      &lt;groupId&gt;io.quarkus&lt;/groupId&gt;
+      &lt;artifactId&gt;quarkus-kubernetes&lt;/artifactId&gt;
+    &lt;/dependency&gt;
</code></pre>
<p><strong>Step B</strong>:<br />
Ensure that <code>DOCKER_LOGINID</code> was set in the earlier step as below and the command should output the Docker login ID.</p>
<pre><code>echo $DOCKER_LOGINID
</code></pre>
<p>Next, let's generate the containerized image with the secrets as below.</p>
<pre><code>./mvnw clean package -Dquarkus.container-image.build=true -Dquarkus.container-image.push=false -Dquarkus.container-image.group=$DOCKER_LOGINID -DskipTests
</code></pre>
<p>Next, let's generate and push the containerized image with the secrets removed as below.</p>
<pre><code>sed -i '/# TBD Below/,+4 d' ./target/classes/application.properties
./mvnw package -Dquarkus.container-image.build=true -Dquarkus.container-image.push=true -Dquarkus.container-image.group=$DOCKER_LOGINID -DskipTests
</code></pre>
<p>✅ <strong>Step 10f: Stand up application in Kubernetes</strong></p>
<p>Hereafter, there are two paths -- steps prefixed with <code>Lens</code> OR steps prefixed with <code>Okteto</code> as summarized below.</p>
<table>
<thead>
<tr>
<th>Steps prefixed with</th>
<th>Details</th>
<th>First step</th>
</tr>
</thead>
<tbody>
<tr>
<td>Lens</td>
<td>Install on Lens IDE</td>
<td>Lens.A</td>
</tr>
<tr>
<td>Okteto</td>
<td>Sample Kubernetes provider</td>
<td>Okteto.A</td>
</tr>
</tbody>
</table>
<p>If you're familiar with using <code>kubectl</code> command you can pick either. If you're not you're recommended to use Steps prefixed with <code>Lens</code>.</p>
<p><strong>Step Lens.A</strong>: Download Lens</p>
<p><a href="https://k8slens.dev/" target="_blank">Lens</a> is a popular Integrated Development Environment (IDE) for Kubernetes and enables developers and engineers to develop and deploy apps on multiple clusters and adminster them easier than using command line tools like <code>kubectl</code>.</p>
<p><a href="https://docs.k8slens.dev/main/#downloading-lens" target="_blank">Download</a> Lens on your local system.</p>
<p><strong>Step Lens.B</strong>: Download, install and run Lens Desktop</p>
<p>Sign up for a free trial and download Lens desktop and install it as shown below. Make sure you select the tiny icon on the bottom left and click on the free trial as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/LensDownload1.png?raw=true" alt="lens" /></p>
<p>If needed, launch the desktop manually as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/LensLaunchManual1.png?raw=true" alt="lens" /></p>
<p>After the launch the Lens Desktop might be in a stopped state as shown in the bottom left below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/LensStop1.png?raw=true" alt="lens" /></p>
<p>Click on the <code>Lens Desktop Kube: Stopped</code> and pick appropriate values as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/Lensvalues1.png?raw=true" alt="lens" /></p>
<p>Note that the current state is shown as stopped as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/LensStopped1.png?raw=true" alt="lens" /></p>
<p>Toggle the button as shown below to move it from stopped to running.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/LensRunning1.png?raw=true" alt="lens" /></p>
<p>Make sure that Lens is running as shown below. <strong>It might take well over five minutes for the state to move to running.</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/LensRunning2.png?raw=true" alt="lens" /></p>
<p>You should have Lens desktop in your clusters list as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/LensLDK1.png?raw=true" alt="lens" /></p>
<p>Now that Lens Desktop is installed, up and running we're ready to deploy the ToDo app.</p>
<p><strong>Step Lens.C</strong>: Set up secrets</p>
<p>Start by clicking on <code>Config</code>, <code>Secrets</code> and <code>+</code> as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/Lenssecret01.png?raw=true" alt="lens" /></p>
<p>Now add the secret <code>astra</code> and the secrets <code>astra-username</code> and <code>astra-password</code>  as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/Lenssecret02.png?raw=true" alt="lens" /></p>
<p>You can verify you entered the values correctly by hitting the button as shown below which will show the values in clear.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/Lenssecret03.png?raw=true" alt="lens" /></p>
<p><strong>Step Lens.D</strong>: Start the workload</p>
<p>We use the generated <code>kubernetes.yml</code> file to install the workload in Lens.</p>
<p>Click on <code>+</code> and <code>Create resource</code> as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/Lensresource01.png?raw=true" alt="lens" /></p>
<p>We are going to cut-n-paste the contents from the Gitpod window into Lens.</p>
<p>Issue the following command in the Gitpod terminal window to look at the Kubernetes manifests that were automatically generated and applied to the cluster.</p>
<pre><code>gp open target/kubernetes/kubernetes.yml
</code></pre>
<p>and cut-n-paste the contents into Lens as shown below and hit <code>Create</code> as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/Lensresource02.png?raw=true" alt="lens" /></p>
<p>If you dig into <code>Pods</code> you should be see it running as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/Lensresource03.png?raw=true" alt="lens" /></p>
<p>You can look through other Kubernetes artifacts which you can easily navigate via Lens.</p>
<p><strong>Step Lens.F</strong>: Setup port forwarding</p>
<p>Click on Network, Services and Forward... as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/LensPortForward1.png?raw=true" alt="lens" /></p>
<p>Next forward to <code>8080</code> as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/LensPortForward2.png?raw=true" alt="lens" /></p>
<p>This will setup the port forwarding to the appropriate pod. Ignore errors if any. You can now access the app via <code>8080</code> on <code>localhost</code>.</p>
<p><strong>Step Lens.G</strong>: Cleanup</p>
<p>You can delete the service, deployment and secret using Lens.</p>
<p>You're now done with Lens deployment and can skip other deployment(s).</p>
<p><strong>OR</strong></p>
<p><strong>Step Okteto.A</strong>: Create a cluster</p>
<p>We've included some steps here using <a href="https://www.okteto.com" target="_blank">okteto</a> (you can modify the steps below depending on your choice of provider).</p>
<p>Create a Kubernetes cluster. You can get one for free at <a href="https://okteto.com" target="_blank">https://okteto.com</a> with your Github credentials.</p>
<p><strong>Step Okteto.B</strong>: Download config file</p>
<p>Download the <code>config</code> file from <a href="https://cloud.okteto.com/#/settings/setup" target="_blank">https://cloud.okteto.com/#/settings/setup</a> locally as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/oktetoconfig1.png?raw=true" alt="okteto" /></p>
<p><strong>Step Okteto.C</strong>: Drag and drop config into Gitpod</p>
<p>Now &quot;drag and drop&quot; it over to the gitpod window (similar to how we transferred the secure connect bundle) as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/oktetoconfig2.png?raw=true" alt="okteto" /></p>
<p><strong>Step Okteto.D</strong>: Setup config in Gitpod window</p>
<p>Use the transferred okteto config file with the following command in the Gitpod terminal window and verify</p>
<pre lang="bash"><code>export KUBECONFIG=okteto-kube.config
kubectl config get-contexts
kubectl get all
</code></pre>
<p>If you get a message like <code>error: You must be logged in to the server (Unauthorized)</code> reauthorize and download the <code>okteto-kube.config</code> file again.</p>
<p>Since okteto only provides access to your namespace, you should see something like below and you won't be able to run other commands like you would normally with a cluster that you created.</p>
<pre><code>No resources found in ragsns namespace.
</code></pre>
<p><strong>Step Okteto.E</strong>: Setup secrets</p>
<p>The <code>application.properties</code> file is setup to use the Kubernetes secrets already (<code>quarkus.kubernetes.env.secrets=astra</code>). Setup the Kubernetes secrets as below from the<code>Client Id</code> and <code>Client Secret</code> respectively as we did earlier.</p>
<pre><code>kubectl create secret generic astra --from-literal=astra-username=&lt;Client Id&gt; --from-literal=astra-password=&lt;Client Secret&gt;
</code></pre>
<p>Verify the screts are setup properly with the following commands.</p>
<pre lang="bash"><code>kubectl get secret astra -o jsonpath=&quot;{.data.astra-username}&quot; | base64 --decode
kubectl get secret astra -o jsonpath=&quot;{.data.astra-password}&quot; | base64 --decode
</code></pre>
<p>The <code>kubernetes.yml</code> deployment file that will be generated in the next step will be setup to use the secrets.</p>
<p><strong>Step Okteto.F</strong>: Push image</p>
<p>You may want to remove the actual values of <code>astra-username</code> and <code>astra-password</code> from the<code>application.properties</code> file as below before pushing the container image to a public registry.</p>
<pre><code>sed -i '/# TBD Below/,+4 d' ./target/classes/application.properties
./mvnw package -Dquarkus.container-image.build=true -Dquarkus.container-image.push=true -Dquarkus.container-image.group=$DOCKER_LOGINID -Dquarkus.kubernetes.deploy=true -DskipTests
</code></pre>
<p>The result of this command will be that your application's container image is built, pushed to the registry, and then deployed on Kubernetes. The Quarkus Kubernetes extension generates all the necessary Kubernetes desriptors for you.</p>
<p>Issue the following command in the Gitpod terminal window to look at the Kubernetes manifests that were automatically generated and applied to the cluster.</p>
<pre><code>gp open target/kubernetes/kubernetes.yml
</code></pre>
<p>You should see the following output which indicates the deployment and the service have been created. <strong>You can ignore errors related to webhook.</strong></p>
<pre><code>[INFO] [io.quarkus.container.image.jib.deployment.JibProcessor] Pushed container image xxx/quarkus-cassandra:0.01 (sha256:xxxxxx)

[INFO] [io.quarkus.kubernetes.deployment.KubernetesDeployer] Deploying to kubernetes server: https://a.b.c.d:443/ in namespace: xxxx.
[INFO] [io.quarkus.kubernetes.deployment.KubernetesDeployer] Applied: Service quarkus-cassandra.
[INFO] [io.quarkus.kubernetes.deployment.KubernetesDeployer] Applied: Deployment quarkus-cassandra.
[INFO] [io.quarkus.deployment.QuarkusAugmentor] Quarkus augmentation completed in 12904ms
</code></pre>
<p>Running the command</p>
<pre lang="bash"><code>kubectl get all
</code></pre>
<p>should yield a different output as below.</p>
<pre><code>NAME                                    READY   STATUS    RESTARTS   AGE
pod/quarkus-cassandra-5f4d69b8d-lx46l   1/1     Running   0          95s

NAME                        TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)   AGE
service/quarkus-cassandra   ClusterIP   10.154.219.218   &lt;none&gt;        80/TCP    96s

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/quarkus-cassandra   1/1     1            1           96s

NAME                                          DESIRED   CURRENT   READY   AGE
replicaset.apps/quarkus-cassandra-5f4d69b8d   1         1         1       96s
</code></pre>
<p>You should be able to access the application from the endpoint provided by the <a href="https://cloud.okteto.com/#/spaces" target="_blank">okteto console</a> and also be able to access the application logs as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/oktetorunning1.png?raw=true" alt="okteto" /></p>
<p>Alternately, you can access the application provided by the gitpod URL like we have always been doing throughout the workshop by issuing the following command.</p>
<pre><code>kubectl port-forward svc/quarkus-cassandra 8080:80 &amp;
</code></pre>
<p><strong>Step Okteto.G</strong>: Cleanup</p>
<p>You can stop the port forwarding by deleting the background job as below.</p>
<pre><code>kill -9 %1
</code></pre>
<p>You can go ahead and get rid of the application as well with the following command from the Gitpod terminal window.</p>
<pre><code>kubectl delete all --all
</code></pre>
<p>and you should see the following output.</p>
<pre><code>pod &quot;quarkus-cassandra-886d9f8b9-h7tw5&quot; deleted
service &quot;quarkus-cassandra&quot; deleted
deployment.apps &quot;quarkus-cassandra&quot; deleted
</code></pre>
<p>Additionally, you should delete the <code>Secret</code> you created.</p>
<pre><code>kubectl delete secret astra
</code></pre>
<p>If the public docker image contains the credentials to be able to access the database, it's a good idea to delete the docker image <a href="http://hub.docker.com" target="_blank">from docker hub</a> right away, anyway.</p>
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="11-native-image"> </a>11. Native Image</h2>
<p>Finally, Quarkus can build a native executable image with the help of the GraalVM that was pre-installed with a simple command as below. <strong>Get yourself some coffee</strong> or water as this will take almost 10 minutes but exceuting this image will be super fast with minimal startup time since it does not depend on the JVM.</p>
<p>✅ <strong>Step 11a: Generating Native Image</strong></p>
<pre lang="bash"><code>./mvnw clean package -Pnative -DskipTests
</code></pre>
<p><strong>Expected output:</strong></p>
<pre><code>Picked up JAVA_TOOL_OPTIONS:  -Xmx3435m
[INFO] Scanning for projects...
[INFO] 
[INFO] ---------&lt; quarkus-astra-intro-demo:quarkus-astra-intro-demo &gt;----------
[INFO] Building quarkus-astra-intro-demo 0.01
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ quarkus-astra-intro-demo ---
[INFO] Deleting /workspace/quarkus-astra-intro-demo/target
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ quarkus-astra-intro-demo ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 24 resources
[INFO] 
[INFO] --- quarkus-maven-plugin:2.9.1.Final:generate-code (default) @ quarkus-astra-intro-demo ---
[INFO] 
[INFO] --- maven-compiler-plugin:3.8.1:compile (default-compile) @ quarkus-astra-intro-demo ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 10 source files to /workspace/quarkus-astra-intro-demo/target/classes
[INFO] 
[INFO] --- quarkus-maven-plugin:2.9.1.Final:generate-code-tests (default) @ quarkus-astra-intro-demo ---
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ quarkus-astra-intro-demo ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 1 resource
[INFO] 
[INFO] --- maven-compiler-plugin:3.8.1:testCompile (default-testCompile) @ quarkus-astra-intro-demo ---
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 6 source files to /workspace/quarkus-astra-intro-demo/target/test-classes
[INFO] 
[INFO] --- maven-surefire-plugin:3.0.0-M5:test (default-test) @ quarkus-astra-intro-demo ---
[INFO] Tests are skipped.
[INFO] 
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ quarkus-astra-intro-demo ---
[INFO] Building jar: /workspace/quarkus-astra-intro-demo/target/quarkus-astra-intro-demo-0.01.jar
[INFO] 
[INFO] --- quarkus-maven-plugin:2.9.1.Final:build (default) @ quarkus-astra-intro-demo ---
[INFO] [io.quarkus.deployment.pkg.steps.JarResultBuildStep] Building native image source jar: /workspace/quarkus-astra-intro-demo/target/quarkus-astra-intro-demo-0.01-native-image-source-jar/quarkus-astra-intro-demo-0.01-runner.jar
[INFO] Checking for existing resources in: /workspace/quarkus-astra-intro-demo/src/main/kubernetes.
[INFO] [io.quarkus.deployment.pkg.steps.NativeImageBuildStep] Building native image from /workspace/quarkus-astra-intro-demo/target/quarkus-astra-intro-demo-0.01-native-image-source-jar/quarkus-astra-intro-demo-0.01-runner.jar
[INFO] [io.quarkus.deployment.pkg.steps.NativeImageBuildStep] Running Quarkus native-image plugin on GraalVM 22.0.0.2 Java 11 CE (Java Version 11.0.14+9-jvmci-22.0-b05)
[INFO] [io.quarkus.deployment.pkg.steps.NativeImageBuildRunner] /home/gitpod/.sdkman/candidates/java/current/bin/native-image -J-Dsun.nio.ch.maxUpdateArraySize=100 -J-Djava.util.logging.manager=org.jboss.logmanager.LogManager -J-Dvertx.logger-delegate-factory-class-name=io.quarkus.vertx.core.runtime.VertxLogDelegateFactory -J-Dvertx.disableDnsResolver=true -J-Dio.netty.leakDetection.level=DISABLED -J-Dio.netty.allocator.maxOrder=3 -J-Duser.language=en -J-Duser.country=US -J-Dfile.encoding=UTF-8 -H:-ParseOnce -J--add-exports=java.security.jgss/sun.security.krb5=ALL-UNNAMED -J--add-opens=java.base/java.text=ALL-UNNAMED -H:InitialCollectionPolicy=com.oracle.svm.core.genscavenge.CollectionPolicy\$BySpaceAndTime -H:+JNI -H:+AllowFoldMethods -J-Djava.awt.headless=true -H:FallbackThreshold=0 -H:+ReportExceptionStackTraces -H:-AddAllCharsets -H:EnableURLProtocols=http,https -H:NativeLinkerOption=-no-pie -H:-UseServiceLoaderFeature -H:+StackTrace quarkus-astra-intro-demo-0.01-runner -jar quarkus-astra-intro-demo-0.01-runner.jar
Picked up JAVA_TOOL_OPTIONS:  -Xmx3435m
========================================================================================================================
GraalVM Native Image: Generating 'quarkus-astra-intro-demo-0.01-runner'...
========================================================================================================================
[1/7] Initializing...                                                                                    (4.9s @ 0.42GB)
 Version info: 'GraalVM 22.0.0.2 Java 11 CE'
 3 user-provided feature(s)
  - io.quarkus.runner.AutoFeature
  - io.quarkus.runtime.graal.DisableLoggingAutoFeature
  - io.quarkus.runtime.graal.ResourcesFeature
[2/7] Performing analysis...  [20:33:32,360 INFO  [com.dat.oss.qua.run.int.qua.CassandraClientRecorder] Enabling Cassandra metrics using Micrometer.
20:33:36,471 INFO  [com.dat.oss.dri.int.cor.DefaultMavenCoordinates] DataStax Java driver for Apache Cassandra(R) (com.datastax.oss:java-driver-core) version 4.14.0
**********]                                                              (31.7s @ 2.17GB)
  14,155 (95.32%) of 14,850 classes reachable
  20,586 (66.60%) of 30,912 fields reachable
  69,696 (82.00%) of 84,993 methods reachable
     482 classes,    39 fields, and   850 methods registered for reflection
      68 classes,    88 fields, and    54 methods registered for JNI access
[3/7] Building universe...                                                                               (2.0s @ 2.69GB)
[4/7] Parsing methods...      [***]                                                                      (5.3s @ 1.81GB)
[5/7] Inlining methods...     [*****]                                                                    (4.7s @ 3.18GB)
[6/7] Compiling methods...    [*****]                                                                   (22.6s @ 3.42GB)
[7/7] Creating image...                                                                                  (4.3s @ 2.54GB)
  25.64MB (36.89%) for code area:   46,599 compilation units
  37.07MB (53.33%) for image heap:   9,899 classes and 350,222 objects
   6.80MB ( 9.78%) for other data
  69.50MB in total
------------------------------------------------------------------------------------------------------------------------
Top 10 packages in code area:                               Top 10 object types in image heap:
   1.67MB sun.security.ssl                                    19.83MB byte[] for general heap data
   1.03MB java.util                                            3.40MB java.lang.Class
 686.94KB com.sun.crypto.provider                              2.65MB java.lang.String
 531.52KB io.quarkus.runtime.generated                         2.21MB byte[] for java.lang.String
 490.01KB sun.security.x509                                  627.75KB java.util.HashMap$Node
 458.87KB java.util.concurrent                               581.63KB java.util.LinkedHashMap
 446.33KB io.netty.buffer                                    534.65KB com.oracle.svm.core.util.LazyFinalReference
 426.93KB com.oracle.svm.core.reflect                        526.91KB java.lang.String[]
 425.74KB com.typesafe.config.impl                           439.28KB byte[] for method metadata
 379.99KB java.lang                                          427.69KB c.o.s.c.h.DynamicHub$$Lambda$~31d9af6a7fe68cfc2a1f
      ... 661 additional packages                                 ... 3407 additional object types
                                           (use GraalVM Dashboard to see all)
------------------------------------------------------------------------------------------------------------------------
                        6.2s (7.7% of total time) in 40 GCs | Peak RSS: 5.21GB | CPU load: 4.98
------------------------------------------------------------------------------------------------------------------------
Produced artifacts:
 /workspace/quarkus-astra-intro-demo/target/quarkus-astra-intro-demo-0.01-native-image-source-jar/quarkus-astra-intro-demo-0.01-runner (executable)
 /workspace/quarkus-astra-intro-demo/target/quarkus-astra-intro-demo-0.01-native-image-source-jar/quarkus-astra-intro-demo-0.01-runner.build_artifacts.txt
========================================================================================================================
Finished generating 'quarkus-astra-intro-demo-0.01-runner' in 1m 20s.
[INFO] [io.quarkus.deployment.pkg.steps.NativeImageBuildRunner] objcopy --strip-debug quarkus-astra-intro-demo-0.01-runner
[INFO] [io.quarkus.deployment.QuarkusAugmentor] Quarkus augmentation completed in 83782ms
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  01:29 min
[INFO] Finished at: 2022-05-16T20:34:47Z
[INFO] ------------------------------------------------------------------------
</code></pre>
<p>✅ <strong>Step 11b: Running Native Image</strong></p>
<p>Run the native image with the following command:</p>
<pre lang="bash"><code>./target/quarkus-astra-intro-demo-0.01-runner
</code></pre>
<pre><code>__  ____  __  _____   ___  __ ____  ______ 
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/ 
 -/ /_/ / /_/ / __ |/ , _/ ,&lt; / /_/ /\ \   
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/   
INFO  [io.qua.sma.ope.run.OpenApiRecorder] (main) Default CORS properties will be used, please use 'quarkus.http.cors' properties instead
INFO  [com.dat.oss.qua.run.int.qua.CassandraClientStarter] (main) Eagerly initializing Quarkus Cassandra client.
INFO  [com.dat.oss.dri.int.cor.os.Native] (vert.x-eventloop-thread-0) Using Graal-specific native functions
INFO  [com.dat.oss.dri.int.cor.tim.Clock] (vert.x-eventloop-thread-0) Using native clock for microsecond precision
INFO  [com.dat.oss.dri.int.cor.ses.DefaultSession] (vert.x-eventloop-thread-9) [s0] Negotiated protocol version V4 for the initial contact point, but cluster seems to support V5, keeping the negotiated version
INFO  [com.dat.tod.res.TodoResource] (main) **** Table created true****
INFO  [io.quarkus] (main) quarkus-astra-intro-demo 0.01 native (powered by Quarkus 2.9.1.Final) started in 2.273s. Listening on: http://0.0.0.0:8080
INFO  [io.quarkus] (main) Profile prod activated. 
INFO  [io.quarkus] (main) Installed features: [cassandra-client, cdi, kubernetes, micrometer, resteasy-reactive, resteasy-reactive-jackson, smallrye-context-propagation, smallrye-health, smallrye-openapi, swagger-ui, vertx]
</code></pre>
<p>Notice the fast startup time since the image is running as a native image.</p>
<p>Hit <code>Ctrl+C</code> in the GitPod terminal window to exit the application.</p>
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="12-homework"> </a>12. Homework</h2>
<img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/badge.png?raw=true" width="200" align="right" />
<p>Don't forget to complete your upgrade and get your verified skill badge! Finish and submit your homework! You have 2 options (option A or Option B). Pick whichever works for you.</p>
<p>Option A. Complete the practice steps from this repository as described above (including optional steps 10d and 10e) and deploy to a Kubernetes cluster.  Make screenshots of the deployment to a Kubernetes cluster.</p>
<p>Option B: Learn more about Quarkus and do some development with <a href="https://github.com/datastax/cassandra-quarkus" target="_blank">https://github.com/datastax/cassandra-quarkus</a>. Send a screenshot of the working &quot;Fruits application&quot; with the following entry &quot;Jackfruit&quot; and the correpsonding description as &quot;King/Queen of fruits&quot;.</p>
<p>Submit your homework <a href="https://docs.google.com/forms/d/e/1FAIpQLSd3hMHgHURsNGq2-jDAIr-XPLJGHqaRAm9CAMkYveybuYfBRw/viewform" target="_blank">here</a></p>
<p>That's it, you are done! Expect an email next week!</p>
<p><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="13-the-end"> </a>13. The END</h2>
<p>Congratulations, your made it to the END of the show.</p>
<p><strong>🧑🏻‍🤝‍🧑🏽 Let's get in touch</strong></p>
<table>
<thead>
<tr>
<th><img src="https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/rags.png" alt="B" /></th>
</tr>
</thead>
<tbody>
<tr>
<td>Rags Srinivas <br><a href="https://github.com/ragsns" target="_blank">@ragsns</a></td>
</tr>
</tbody>
</table>
<h2><a class="anchor" aria-hidden="true" id="a-href-0-table-of-contents-back-to-table-of-contents-a"> </a><a href="#0-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></h2>
<p><a href=""><img src=" target="_blank"https://github.com/datastaxdevs/workshop-intro-quarkus-cassandra/raw/master/images/tutorials/thankyou.gif" alt="thankyou" /></a></p>

<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="getting-started-with-apache-cassandratm-and-java-using-datastax-astra-db"> </a>Getting Started with Apache Cassandra™ and Java using DataStax Astra DB</h1>
<p><em>50 minutes, Intermediate, <a href="https://github.com/DataStax-Examples/getting-started-with-astra-java#prerequisites" target="_blank">Start Building</a></em></p>
<p>This provides an example REST backend built in Java using <code>Spring Boot</code> for use with the <a href="https://github.com/DataStax-Examples/getting-started-with-astra-ui" target="_blank">Getting Started with Astra UI</a>.</p>
<!--- ENDEXCLUDE --->
<p><img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-sample-app-default.png" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>How to connect to Astra DB via the Secure Connect Bundle</li>
<li>How to manage a Cassandra Session within a JAVA web application</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="how-this-works"> </a>How this Works</h2>
<p>This is an example of a Spring Boot Microservice for use with the Astra Getting Started UI which is found <a href="https://github.com/DataStax-Examples/getting-started-with-astra-ui" target="_blank">here</a>.</p>
<h2><a class="anchor" aria-hidden="true" id="get-started"> </a>Get Started</h2>
<p>To build and play with this app, follow the build instructions that are located here: <a href="https://github.com/DataStax-Examples/getting-started-with-astra-java#prerequisites" target="_blank">https://github.com/DataStax-Examples/getting-started-with-astra-java</a></p>
<!--- STARTEXCLUDE --->
<h2><a class="anchor" aria-hidden="true" id="prerequisites"> </a>Prerequisites</h2>
<p>Let's do some initial setup by creating a serverless(!) database.</p>
<h3><a class="anchor" aria-hidden="true" id="datastax-astra"> </a>DataStax Astra</h3>
<ol>
<li>
<p>Create a <a href="https://dtsx.io/3zBltF7" target="_blank">DataStax Astra account</a> if you don't already have one:<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-register-basic-auth.png" alt="image" /></p>
</li>
<li>
<p>On the home page. Locate the button <strong><code>Create Database</code></strong><br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-dashboard.png" alt="image" /></p>
</li>
<li>
<p>Locate the <strong><code>Get Started</code></strong> button to continue<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-select-plan.png" alt="image" /></p>
</li>
<li>
<p>Define a <strong>database name</strong>, <strong>keyspace name</strong> and select a database <strong>region</strong>, then click <strong>create database</strong>.<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-create-db.png" alt="image" /></p>
</li>
<li>
<p>Your Astra DB will be ready when the status will change from <em><code>Pending</code></em> to <strong><code>Active</code></strong> 💥💥💥<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-active.png" alt="image" /></p>
</li>
<li>
<p>After your database is provisioned, we need to generate an Application Token for our App. Go to the <code>Settings</code> tab in the database home screen.<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-settings.png" alt="image" /></p>
</li>
<li>
<p>Select <code>Admin User</code> for the role for this Sample App and then generate the token. Download the CSV so that we can use the credentials we need later.<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-settings-token.png" alt="image" /></p>
</li>
<li>
<p>After you have your Application Token, head to the database connect screen and select the driver connection that we need. Go ahead and download the <code>Secure Bundle</code> for the driver.<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-connect-bundle.png" alt="image" /></p>
</li>
<li>
<p>Make note of where to use the <code>Client Id</code> and <code>Client Secret</code> that is part of the Application Token that we generated earlier.<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-connect-bundle-driver.png" alt="image" /></p>
</li>
</ol>
<h3><a class="anchor" aria-hidden="true" id="github"> </a>Github</h3>
<ol>
<li>
<p>Click <code>Use this template</code> at the top of the <a href="https://github.com/DataStax-Examples/getting-started-with-astra-java" target="_blank">GitHub Repository</a>:<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-use-template.png" alt="image" /></p>
</li>
<li>
<p>Enter a repository name and click 'Create repository from template':<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-create-repository.png" alt="image" /></p>
</li>
<li>
<p>Clone the repository:<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-clone.png" alt="image" /></p>
</li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="getting-started-paths"> </a>🚀 Getting Started Paths:</h2>
<p><em>Make sure you've completed the <a href="#prerequisites" target="_blank">prerequisites</a> before starting this step</em></p>
<ul>
<li><a href="#running-on-your-local-machine" target="_blank">Running on your local machine</a></li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="running-on-your-local-machine"> </a>Running on your local machine</h3>
<p>Make sure that you have:</p>
<ul>
<li>Java 11</li>
<li>An Astra DB compatible Java driver, instructions may be found <a href="https://docs.datastax.com/en/astra/docs/connect/drivers/connect-java.html" target="_blank">here</a> to install this locally.</li>
<li>An Astra database with the CQL schema located in <a href="https://raw.githubusercontent.com/DataStax-Examples/getting-started-with-astra-java/master/src/main/resources/schema.cql" target="_blank">schema.cql</a> already added.</li>
<li>The username, password, keyspace name, and secure connect bundle downloaded from your Astra DB.  For information on how to obtain these credentials please read the documentation found <a href="https://docs.datastax.com/en/astra/docs/connect/secure-connect-bundle.html" target="_blank">here</a></li>
</ul>
<p>This application is a Spring Boot web application. This sample can be run from the root directory using:</p>
<pre lang="sh"><code>cd getting-started-with-astra-java

mvn spring-boot:run
</code></pre>
<p>This will startup the application running on <code>http://localhost:8080</code></p>
<p>You will know that you are up and working when you get the following in your terminal window:</p>
<pre lang="sh"><code>16:23:01.569 INFO  com.datastax.astra.GettingStartedWithAstra  : Started GettingStartedWithAstra in 1.851 seconds (JVM running for 2.39)
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="access-the-api-documentation-from-a-browser"> </a>Access the API documentation from a browser</h4>
<p><a href="http://localhost:8080" target="_blank">http://localhost:8080</a></p>
<p><em>Note: If you want to change the listening port of the application, locate the file <code>src/main/resources/application.yml</code> and change key <code>server.port</code></em></p>
<h4><a class="anchor" aria-hidden="true" id="setup-the-user-interface-to-use-this-backend"> </a>Setup the user interface to use this backend</h4>
<p>To setup the UI to connect to Java backend define a <code>.env</code> file in the <code>getting-started-with-astra-ui</code> project main directory. Inside the file it should have one entry pointing to this project's API endpoint:</p>
<pre lang="sh"><code>BASE_ADDRESS=http://localhost:8080/api
</code></pre>
<p>Once you start that project with a <code>npm run build</code> it will point the UI to the backend API which will then be using Astra DB as a database. When you first connect to the UI, a dialog box will open asking for Astra DB connection information.</p>
<!--- ENDEXCLUDE --->

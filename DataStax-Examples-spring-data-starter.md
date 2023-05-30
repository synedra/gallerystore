<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="spring-data-cassandra-rest-api"> </a>Spring Data Cassandra REST API</h1>
<p><em>10 minutes, Beginner, <a href="https://github.com/DataStax-Examples/spring-data-starter#prerequisites" target="_blank">Start Building</a></em></p>
<p>This application uses Spring Data Cassandra and DataStax Astra DB to build a REST API for a backend service that interacts with products and orders.</p>
<!--- ENDEXCLUDE --->
<p><img src="https://user-images.githubusercontent.com/3254549/90944387-439a1f00-e3d3-11ea-9df4-e8a5580c62cd.png" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>Run a REST API that connects to DataStax Astra DB</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="how-this-works"> </a>How this works</h2>
<p>We're using Spring Data Cassandra and Datastax Astra DB to build a REST API that stores Products and Orders.</p>
<h2><a class="anchor" aria-hidden="true" id="get-started"> </a>Get Started</h2>
<p>To build and play with this app, follow the build instructions that are located here: <a href="https://github.com/DataStax-Examples/spring-data-starter#prerequisites" target="_blank">https://github.com/DataStax-Examples/spring-data-starter</a></p>
<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="running-spring-data-cassandra-rest-api"> </a>Running Spring Data Cassandra REST API</h1>
<p>Follow the instructions below to get started.</p>
<h2><a class="anchor" aria-hidden="true" id="prerequisites"> </a>Prerequisites</h2>
<p>Let's do some initial setup by creating a serverless(!) database.</p>
<h3><a class="anchor" aria-hidden="true" id="datastax-astra"> </a>DataStax Astra</h3>
<ol>
<li>
<p>Create a <a href="https://dtsx.io/38HWu73" target="_blank">DataStax Astra account</a> if you don't already have one:<br />
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
<p>Click <code>Use this template</code> at the top of the <a href="https://github.com/DataStax-Examples/spring-data-starter" target="_blank">GitHub Repository</a>:<br />
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
<li><a href="#running-on-gitpod" target="_blank">Running on Gitpod</a></li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="running-on-gitpod"> </a>Running on Gitpod</h3>
<ol>
<li>
<p>Click the 'Open in Gitpod' link:<br />
<a href="https://dtsx.io/2QjoULs" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in IDE" /></a></p>
</li>
<li>
<p>Once your Gitpod workspace has loaded, you'll be asked to paste your service account credentials in the Gitpod terminal at the bottom of the screen:<br />
<img src="https://user-images.githubusercontent.com/3254549/90944321-e900c300-e3d2-11ea-9624-dae5f81b6a0a.png" alt="image" /></p>
</li>
<li>
<p>When the app is finished building, click the 'Open Browser' button on the bottom right of the screen:<br />
<img src="https://user-images.githubusercontent.com/3254549/90944371-249b8d00-e3d3-11ea-8305-b7d4fad9742c.png" alt="image" /></p>
</li>
<li>
<p>You've successfully build a Spring Data Cassandra application!<br />
<img src="https://user-images.githubusercontent.com/3254549/90944387-439a1f00-e3d3-11ea-9df4-e8a5580c62cd.png" alt="image" /></p>
</li>
</ol>
<!--- ENDEXCLUDE --->

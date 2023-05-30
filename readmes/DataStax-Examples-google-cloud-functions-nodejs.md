<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="astra-db-rest-api-with-google-cloud-functions-in-node-js"> </a>Astra DB REST API with Google Cloud Functions in Node.js</h1>
<p><em>30 minutes, Intermediate, <a href="https://github.com/DataStax-Examples/google-cloud-functions-nodejs#prerequisites" target="_blank">Start Building</a></em></p>
<p>This example shows how to use <a href="https://cloud.google.com/functions/" target="_blank">Google Cloud Functions</a> with the <a href="https://docs.datastax.com/en/developer/nodejs-driver/latest">Node.js DataStax Cassandra Driver</a> to set up a basic REST API for a Cassandra database via HTTP Endpoints. The <a href="https://serverless.com/">Serverless Framework</a> is used to facilitate the setup and deployment of the functions.</p>
<!--- ENDEXCLUDE --->
<p><img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-sample-app-default.png" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>How to use the DataStax Cassandra Driver with Google Cloud Functions</li>
<li>How to use the Serverless Framework to set up Google Cloud Functions HTTP Endpoints</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="how-it-works"> </a>How it works</h2>
<p>The Serverless Framework handles the packaging and deployment of the functions to the Google Cloud resources. Once the functions are deployed, the DataStax Cassandra Driver establishes the connection to the database and returns the results via the Google Cloud HTTP Endpoints which can be accessed to interact with the database.</p>
<h2><a class="anchor" aria-hidden="true" id="get-started"> </a>Get Started</h2>
<p>To build and play with this app, follow the build instructions that are located here: <a href="https://github.com/DataStax-Examples/google-cloud-functions-nodejs#prerequisites" target="_blank">https://github.com/DataStax-Examples/google-cloud-functions-nodejs</a></p>
<!--- STARTEXCLUDE --->
<h2><a class="anchor" aria-hidden="true" id="prerequisites"> </a>Prerequisites</h2>
<p>Let's do some initial setup by creating a serverless(!) database.</p>
<h3><a class="anchor" aria-hidden="true" id="datastax-astra"> </a>DataStax Astra</h3>
<!--- enter a unique UTM_CODE for your sample app below --->
<ol>
<li>
<p>Create a <a href="https://dtsx.io/3jENJkP" target="_blank">DataStax Astra account</a> if you don't already have one:<br />
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
<p>Click <code>Use this template</code> at the top of the <a href="https://github.com/DataStax-Examples/google-cloud-functions-nodejs" target="_blank">GitHub Repository</a>:<br />
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
<p>Before running with this example, head over to the <a href="https://raw.githubusercontent.com/DataStax-Examples/google-cloud-functions-nodejs/master/SETUP-README.md" target="_blank">SETUP-README</a> for instructions on how to</p>
<ol>
<li>launch an instance in Google Cloud</li>
<li>install and start a Cassandra database</li>
<li>setup your local development environment for Node.js and <a href="https://serverless.com" target="_blank">serverless</a></li>
</ol>
<p>Once the above is completed, you will have all of the needed pieces in place to run this example.</p>
<ol>
<li>Install the DataStax Cassandra Driver</li>
</ol>
<pre lang="sh"><code>npm install cassandra-driver
</code></pre>
<ol start="4">
<li>Install serverless-google-cloudfunctions plugin</li>
</ol>
<pre lang="sh"><code>npm install serverless-google-cloudfunctions
</code></pre>
<ol start="5">
<li>Configure <code>serverless.yml</code> with your project-id, credentials file, Contact Points ( public IP of GCP instance ), and Local Data Center ( likely <code>datacenter1</code> )</li>
</ol>
<p>From the project directory, deploy your function. This should output the endpoints that you can use to access the database.</p>
<pre lang="sh"><code>sls deploy
</code></pre>
<ul>
<li>When you are done, don't forget to clean things up with</li>
</ul>
<pre><code>sls remove
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="createcatalog"> </a>createCatalog</h4>
<pre lang="sh"><code>curl -X POST https://us-central1-&lt;project-id&gt;.cloudfunctions.net/createCatalog
</code></pre>
<p>expected output:</p>
<pre lang="sh"><code>&quot;Successfully created shopping.catalog schema&quot;
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="additem"> </a>addItem</h4>
<p>Note the <code>-H &quot;Content-Type:application/json&quot;</code> is required here.</p>
<pre lang="sh"><code>curl -X POST -H &quot;Content-Type:application/json&quot; -d '{&quot;item_id&quot;: 0, &quot;name&quot;: &quot;name_0&quot;, &quot;description&quot;: &quot;desc_0&quot;, &quot;price&quot;: 10.1}' https://us-central1-&lt;project-id&gt;.cloudfunctions.net/addItem
</code></pre>
<p>expected output:</p>
<pre lang="sh"><code>{&quot;query&quot;:&quot;INSERT INTO shopping.catalog (item_id, name, description, price) VALUES (?, ?, ?, ?)&quot;,&quot;item_id&quot;:0,&quot;name&quot;:&quot;name_0&quot;,&quot;description&quot;:&quot;desc_0&quot;,&quot;price&quot;:10.1}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="getitem"> </a>getItem</h4>
<pre lang="sh"><code>curl -X GET https://us-central1-&lt;project-id&gt;.cloudfunctions.net/getItem/0
</code></pre>
<p>expected output:</p>
<pre lang="sh"><code>{&quot;query&quot;:&quot;SELECT name, description, price FROM shopping.catalog WHERE item_id = ?&quot;,&quot;item_id&quot;:[&quot;0&quot;],&quot;name&quot;:&quot;name_0&quot;,&quot;description&quot;:&quot;desc_0&quot;,&quot;price&quot;:&quot;10.1&quot;}
</code></pre>
<!--- ENDEXCLUDE --->

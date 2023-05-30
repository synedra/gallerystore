<h1><a class="anchor" aria-hidden="true" id="apache-cassandra-rest-api-with-azure-functions-in-node-js"> </a>Apache Cassandra REST API with Azure Functions in Node.js</h1>
<p>This example shows how to use <a href="https://azure.microsoft.com/en-us/services/functions/" target="_blank">Azure Functions</a> with the <a href="https://docs.datastax.com/en/developer/nodejs-driver/latest">Node.js DataStax Cassandra Driver</a> to set up a basic REST API for a Cassandra database via HTTP Endpoints. The <a href="https://serverless.com/">Serverless Framework</a> is used to facilitate the setup and deployment of the functions.</p>
<p>Contributor(s): <a href="https://github.com/csplinter" target="_blank">Chris Splinter</a></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>How to use the DataStax Cassandra Driver with Azure Functions</li>
<li>How to use the Serverless Framework to set up Azure Functions HTTP Endpoints</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="project-layout"> </a>Project Layout</h2>
<ul>
<li><a href="index.js" target="_blank">index.js</a>: Contains the DataStax Cassandra Driver connection and queries as well as the Azure Functions entry points.</li>
<li><a href="serverless.yml" target="_blank">serverless.yml</a>: Used by serverless to deploy and configure the Azure artifacts needed to run the function.</li>
<li><a href="package.json" target="_blank">package.json</a>: Defines the dependencies and descriptive example metadata.</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="how-it-works"> </a>How it works</h2>
<p>The Serverless Framework handles the packaging and deployment of the functions to the Azure resources. Once the functions are deployed, the DataStax Cassandra Driver establishes the connection to the database and returns the results to the Azure HTTP Endpoints which can be accessed to interact with the database.</p>
<h2><a class="anchor" aria-hidden="true" id="setup-running"> </a>Setup &amp; Running</h2>
<h3><a class="anchor" aria-hidden="true" id="setup"> </a>Setup</h3>
<p>Before running with this example, head over to the <a href="SETUP-README.md" target="_blank">SETUP-README</a> for instructions on how to</p>
<ol>
<li>launch an instance in Azure</li>
<li>install and start an Apache Cassandra database</li>
<li>setup your local development environment for Node.js and <a href="https://serverless.com" target="_blank">serverless</a></li>
</ol>
<p>Once the above is completed, you will have all of the needed pieces in place to run this example.</p>
<ol>
<li>Clone this repository</li>
</ol>
<pre><code>git clone https://github.com/DataStax-Examples/azure-functions-nodejs.git
</code></pre>
<ol start="2">
<li>Go to the directory</li>
</ol>
<pre><code>cd azure-functions-nodejs
</code></pre>
<ol start="3">
<li>Install the DataStax Cassandra Driver</li>
</ol>
<pre><code>npm install cassandra-driver
</code></pre>
<ol start="4">
<li>Install serverless-azure-functions plugin</li>
</ol>
<pre><code>npm install serverless-azure-functions
</code></pre>
<ol start="5">
<li>Configure <code>serverless.yml</code> with your Contact Points ( public IP of Azure instance ), and Local Data Center ( likely <code>datacenter1</code> )</li>
</ol>
<h3><a class="anchor" aria-hidden="true" id="running"> </a>Running</h3>
<p>From the project directory, deploy your function. This should output the endpoints that you can use to access the database.</p>
<pre><code>sls deploy
</code></pre>
<ul>
<li>When you are done, don't forget to clean things up with</li>
</ul>
<pre><code>sls remove
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="using-the-http-endpoints"> </a>Using the HTTP Endpoints</h3>
<h4><a class="anchor" aria-hidden="true" id="createcatalog"> </a>createCatalog</h4>
<p>Note the <code>-d '{}'</code> is required here</p>
<pre><code>curl -X POST -d '{}' &lt;function-app-name&gt;.azurewebsites.net/api/catalog/create
</code></pre>
<p>expected output:</p>
<pre><code>Successfully created shopping.catalog schema
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="additem"> </a>addItem</h4>
<pre><code>curl -X POST -d '{&quot;item_id&quot;: 0, &quot;name&quot;: &quot;name_0&quot;, &quot;description&quot;: &quot;desc_0&quot;, &quot;price&quot;: 10.1}' &lt;function-app-name&gt;.azurewebsites.net/api/catalog/add
</code></pre>
<p>expected output:</p>
<pre><code>{&quot;query&quot;:&quot;INSERT INTO shopping.catalog (item_id, name, description, price) VALUES (?, ?, ?, ?)&quot;,&quot;item_id&quot;:0,&quot;name&quot;:&quot;name_0&quot;,&quot;description&quot;:&quot;desc_0&quot;,&quot;price&quot;:10.1}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="getitem"> </a>getItem</h4>
<pre><code>curl -X GET &lt;function-app-name&gt;.azurewebsites.net/api/catalog/get/0
</code></pre>
<p>expected output:</p>
<pre><code>{&quot;query&quot;:&quot;SELECT name, description, price FROM shopping.catalog WHERE item_id = ?&quot;,&quot;item_id&quot;:&quot;0&quot;,&quot;name&quot;:&quot;name_0&quot;,&quot;description&quot;:&quot;desc_0&quot;,&quot;price&quot;:&quot;10.1&quot;}
</code></pre>

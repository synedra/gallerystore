<h1><a class="anchor" aria-hidden="true" id="apache-cassandra-rest-api-with-aws-lambda-in-node-js"> </a>Apache Cassandra REST API with AWS Lambda in Node.js</h1>
<p>This example shows how to use <a href="https://aws.amazon.com/lambda/" target="_blank">AWS Lambda</a> with the <a href="https://docs.datastax.com/en/developer/nodejs-driver/latest">Node.js DataStax Cassandra Driver</a> to set up a basic REST API for a Cassandra database via HTTP Endpoints. The <a href="https://serverless.com/">Serverless Framework</a> is used to facilitate the setup and deployment of the functions.</p>
<p>Contributor(s): <a href="https://github.com/csplinter" target="_blank">Chris Splinter</a></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>How to use the DataStax Cassandra Driver with AWS Lambda functions</li>
<li>How to use the Serverless Framework to set up AWS LAmbda functions HTTP Endpoints</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="project-layout"> </a>Project Layout</h2>
<ul>
<li><a href="handler.js" target="_blank">handler.js</a>: Contains the DataStax Cassandra Driver connection and queries as well as the AWS Lambda function entry points.</li>
<li><a href="serverless.yml" target="_blank">serverless.yml</a>: Used by serverless to deploy and configure the AWS Lambda artifacts needed to run the function.</li>
<li><a href="package.json" target="_blank">package.json</a>: Defines the dependencies and descriptive example metadata.</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="how-it-works"> </a>How it works</h2>
<p>The Serverless Framework handles the packaging and deployment of the functions to the AWS resources. Once the functions are deployed, the DataStax Cassandra Driver establishes the connection to the database and returns the results via the AWS Lambda HTTP Endpoints which can be accessed to interact with the database.</p>
<h2><a class="anchor" aria-hidden="true" id="setup-running"> </a>Setup &amp; Running</h2>
<h3><a class="anchor" aria-hidden="true" id="setup"> </a>Setup</h3>
<p>Before running with this example, head over to the <a href="SETUP-README.md" target="_blank">SETUP-README</a> for instructions on how to</p>
<ol>
<li>launch an instance in AWS EC2</li>
<li>install and start a Cassandra database</li>
<li>setup your local development environment for Node.js and <a href="https://serverless.com" target="_blank">serverless</a></li>
</ol>
<p>Once the above is completed, you will have all of the needed pieces in place to run this example.</p>
<ol>
<li>Clone this repository</li>
</ol>
<pre><code>git clone https://github.com/DataStax-Examples/aws-lambda-nodejs.git
</code></pre>
<ol start="2">
<li>Go to the <code>aws-lambda-nodejs</code> directory</li>
</ol>
<pre><code>cd aws-lambda-nodejs
</code></pre>
<ol start="3">
<li>Install the DataStax Cassandra Driver</li>
</ol>
<pre><code>npm install cassandra-driver
</code></pre>
<ol start="4">
<li>Configure <code>serverless.yml</code> with your S3 bucket, Contact Points ( public IP of AWS EC2 instance ), and Local Data Center ( likely <code>datacenter1</code> )</li>
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
<pre><code>curl -X POST https://&lt;function-id&gt;.execute-api.us-east-2.amazonaws.com/dev/catalog/create
</code></pre>
<p>expected output:</p>
<pre><code>Successfully created shopping.catalog schema
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="additem"> </a>addItem</h4>
<pre><code>curl -X POST -d '{&quot;item_id&quot;: 0, &quot;name&quot;: &quot;name_0&quot;, &quot;description&quot;: &quot;desc_0&quot;, &quot;price&quot;: 10.1}' https://&lt;function-id&gt;.execute-api.us-east-2.amazonaws.com/dev/catalog/add
</code></pre>
<p>expected output:</p>
<pre><code>{&quot;query&quot;:&quot;INSERT INTO shopping.catalog (item_id, name, description, price) VALUES (?, ?, ?, ?)&quot;,&quot;item_id&quot;:0,&quot;name&quot;:&quot;name_0&quot;,&quot;description&quot;:&quot;desc_0&quot;,&quot;price&quot;:10.1}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="getitem"> </a>getItem</h4>
<pre><code>curl -X GET https://&lt;function-id&gt;.execute-api.us-east-2.amazonaws.com/dev/catalog/get/0
</code></pre>
<p>expected output:</p>
<pre><code>{&quot;query&quot;:&quot;SELECT name, description, price FROM shopping.catalog WHERE item_id = ?&quot;,&quot;item_id&quot;:&quot;0&quot;,&quot;name&quot;:&quot;name_0&quot;,&quot;description&quot;:&quot;desc_0&quot;,&quot;price&quot;:&quot;10.1&quot;}
</code></pre>

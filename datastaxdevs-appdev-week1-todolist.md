<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="todo-astra-cassandra"> </a>TODO + Astra + Cassandra 📒</h1>
<p><em>10 minutes, Beginner, <a href="https://github.com/DataStax-Examples/todo-astra-jamstack-netlify#prerequisites" target="_blank">Start Building</a></em></p>
<p>This is an example React To-Do application using a <a href="https://astra.dev/9-9" target="_blank">DataStax Astra</a> free tier database.</p>
<!--- ENDEXCLUDE --->
<p><img src="https://monosnap.com/image/Fv0yPAznbeNJD3vYlQfztME6yogzFT" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>🎯 Objectives</h2>
<ul>
<li>Create a &quot;from scratch&quot; <strong>React</strong> app using NPX</li>
<li>Learn about <strong>React</strong> components and how they are used to dynamically update the DOM with new information</li>
<li>Learn how <strong>state</strong> and <strong>props</strong> changes are used</li>
<li>Learn how to use Swagger to interact with the database using a <strong>REST</strong> API</li>
<li>Leverage Netlify and DataStax Astra DB</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="frequently-asked-questions"> </a>ℹ️ Frequently asked questions ℹ️</h2>
<ul>
<li><em>Can I run the workshop on my computer?</em></li>
</ul>
<blockquote>
<p>There is nothing preventing you from running the workshop on your own machine.<br />
If you do so, you will need</p>
<ul>
<li>git installed on your local system</li>
<li><a href="https://www.whitesourcesoftware.com/free-developer-tools/blog/update-node-js/" target="_blank">node 15 and npm 7 or later</a></li>
</ul>
<p>You will have to adapt commands and paths based on your environment and install the dependencies by yourself. <strong>We won't provide support</strong> to keep on track with schedule. However, we will do our best to give you the info you need to be successful.</p>
</blockquote>
<ul>
<li><em>What other prerequisites are there?</em></li>
</ul>
<blockquote>
<ul>
<li>You will need a github account</li>
<li>You will also need an Astra DB account, but we'll work through that in the exercises</li>
<li>Use <strong>Chrome</strong> or <strong>Firefox</strong> for the best experience. Other browsers are great, but don't work well with the GitPod integration we use a bit later.</li>
</ul>
</blockquote>
<ul>
<li><em>Do I need to pay for anything for this workshop?</em></li>
</ul>
<blockquote>
<ul>
<li><strong>No.</strong> All tools and services we provide here are FREE.</li>
</ul>
</blockquote>
<ul>
<li><em>Will I get a certificate if I attend this workshop?</em></li>
</ul>
<blockquote>
<p>Attending the session is not enough. You need to complete the homework detailed below and you will get a nice badge.</p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="./slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://bit.ly/cassandra-workshop" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h2>
<img src="https://user-images.githubusercontent.com/23346205/124651231-a7e99400-de68-11eb-9f3f-ab6b88da0cdf.png?raw=true" width="200" align="right" />
<p>Don't forget to complete your upgrade and get your verified skill badge! Finish and submit your homework!</p>
<ol>
<li>Complete the practice steps from this repository as described below.</li>
<li>Create a <strong>React</strong> app from scratch using NPX. Follow <a href="https://github.com/datastaxdevs/react-basics" target="_blank">these</a> instructions. <strong>Take a screenshot of your final working app</strong>.</li>
<li>Launch the TODO starter app, connect it to the database, and display your changes from the database. <strong>Take a screenshot of your TODO app with your unique entries</strong>.</li>
<li>Submit your homework <a href="https://github.com/datastaxdevs/appdev-week1-todolist/issues/new?assignees=HadesArchitect%2C+SonicDMG%2C+RyanWelford&amp;labels=homework%2C+wait+for+review&amp;template=homework-assignment.md&amp;title=%5BHW%5D+%3CNAME%3E" target="_blank">here</a>. Note:<br />
<em>never share your Astra DB tokens!</em></li>
</ol>
<p>That's it, you are done! Expect an email next week!</p>
<h1><a class="anchor" aria-hidden="true" id="let-s-start"> </a>Let's start</h1>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>Table of contents</h2>
<ol>
<li><a href="#1-login-or-register-to-astradb-and-create-database" target="_blank">Login or Register to AstraDB and create database</a></li>
<li><a href="#2-create-a-security-token" target="_blank">Create a security token</a></li>
<li><a href="#3-create-a-table-with-rest-api-using-swagger" target="_blank">Create a table with REST API using Swagger</a></li>
<li><a href="#4-insert-data-in-the-table-with-the-rest-api-using-swagger" target="_blank">Insert data in the Table with the REST API using Swagger</a></li>
<li><a href="#5-retrieving-values" target="_blank">Retrieving values</a></li>
<li><a href="#6-launch-gitpod-ide" target="_blank">Launch GitPod IDE</a></li>
<li><a href="#7-launch-the-todo-app" target="_blank">Launch the TODO app</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="an-introduction-to-web-development"> </a>An introduction to web development</h2>
<h3><a class="anchor" aria-hidden="true" id="codepen-starter-examples"> </a>CodePen starter examples</h3>
<ul>
<li><a href="https://codepen.io/DatastaxDevs/pen/WNjrXXp" target="_blank">HTML</a></li>
<li><a href="https://codepen.io/DatastaxDevs/pen/QWvyOOv" target="_blank">CSS</a></li>
<li><a href="https://codepen.io/DatastaxDevs/pen/mdmVRwy" target="_blank">Javascript</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="1-login-or-register-to-astradb-and-create-database"> </a>1. Login or Register to AstraDB and create database</h2>
<p><strong><code>ASTRADB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, $25.00 USD credit every month, roughly 5M writes, 30M reads, 40GB storage monthly - sufficient to run small production workloads.</p>
<h3><a class="anchor" aria-hidden="true" id="step-1a-click-the-button-to-login-or-register-with-datastax-you-can-use-your-code-github-code-code-google-code-accounts-or-register-with-an-code-email-code"> </a>✅ Step 1a: Click the button to login or register with Datastax. You can use your <code>Github</code>, <code>Google</code> accounts or register with an <code>email</code>.</h3>
<p><em>Make sure to chose a password with minimum 8 characters, containing upper and lowercase letters, at least one number and special character</em></p>
<p><a href="https://astra.dev/9-9" target="_blank"><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/blob/main/img/create_astra_db.png?raw=true" /></a></p>
<ul>
<li>
<details><summary>Show me!</summary>
  <img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/main/images/tutorials/astra-create-db.gif?raw=true" />
</li>
</ul>
</details>
<p><strong>Use the following values when creating the database</strong></p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>database name</strong></td>
<td><code>todos_workshop_db</code></td>
</tr>
<tr>
<td><strong>keypace</strong></td>
<td><code>todos</code></td>
</tr>
<tr>
<td><strong>Cloud Provider</strong></td>
<td><em>Use the one you like, click a cloud provider logo,  pick an Area in the list and finally pick a region.</em></td>
</tr>
</tbody>
</table>
<p><em>You can technically use whatever you want and update the code to reflect the keyspace. This is really to get you on a happy path for the first run.</em></p>
<p>You will see your new database <code>pending</code> in the Dashboard.</p>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/blob/main/tutorial/images/db-pending.png?raw=true" alt="image" /></p>
<p>The status will change to <code>Active</code> when the database is ready, this will only take 2-3 minutes. You will also receive an email when it is ready.</p>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="2-create-a-security-token"> </a>2. Create a security token</h2>
<p>✅  <strong>Step 2a:</strong>  <a href="https://docs.datastax.com/en/astra/docs/manage-application-tokens.html" target="_blank">Create a token for your app</a> to use in the settings screen. Use &quot;Database Administrator&quot; permission.</p>
<p>✅  <strong>Step 2b:</strong>  Copy the token value (eg <code>AstraCS:KDfdKeNREyWQvDpDrBqwBsUB:ec80667c....</code>) in your clipboard and save the CSV, this value would not be provided afterward.</p>
<p><strong>👁️ Expected output</strong></p>
<ul>
<li>
<details><summary>Show me!</summary>
  <img src="https://github.com/datastaxdevs/workshop-graphql-netflix/blob/main/tutorial/images/astra-create-token.gif?raw=true" />
</li>
</ul>
</details>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="3-create-a-table-with-rest-api-using-swagger"> </a>3. Create a table with REST API using Swagger</h2>
<p>✅  <strong>Step 3a:</strong> Open <strong>Swagger</strong> by</p>
<ol>
<li>Click on your active database</li>
<li>Click <code>Connect</code> TAB</li>
<li>Click <code>REST API</code></li>
<li>Clik link to your swagger endpoint.</li>
</ol>
<p><em>As shown on the picture below.</em><br />
<img src="https://user-images.githubusercontent.com/23346205/124656913-d28b1b00-de6f-11eb-9712-e7629f5b8867.png?raw=true" alt="image" /></p>
<p>✅  <strong>Step 3b:</strong> Navigate to <strong>create a table</strong> section</p>
<ol>
<li>Once <strong>Swagger</strong> is launched, scroll down and navigate to the <strong>schemas</strong> section</li>
</ol>
<p><img src="https://user-images.githubusercontent.com/23346205/124658644-ffd8c880-de71-11eb-8064-c26a2979b66f.png?raw=true" alt="image" /></p>
<ol start="2">
<li>Then, within the <strong>schemas</strong> section navigate to <strong>Create a table</strong> and click on it to open the section.</li>
</ol>
<ul>
<li>Take particular note of the REST URI <strong>/api/rest/v2/schemas/keyspaces/{keyspaceName}/tables</strong>.</li>
<li>Also take note this is using a <strong>POST</strong> command.</li>
</ul>
<p><img src="https://user-images.githubusercontent.com/23346205/124658990-71187b80-de72-11eb-8d25-01e6c6216aa5.png?raw=true" alt="image" /></p>
<ol start="3">
<li>Click the &quot;Try it out&quot; button</li>
</ol>
<p><img src="https://user-images.githubusercontent.com/23346205/124659185-ae7d0900-de72-11eb-9108-1595c3306bb3.png?raw=true" alt="image" /></p>
<p>✅  <strong>Step 3c:</strong> Create table <strong>restfromreadme_by_id</strong></p>
<ol>
<li>Enter your <strong>Astra token <em>(X-Cassandra-Token)</em></strong></li>
<li>Enter the <strong>keyspaceName</strong> <code>todos</code></li>
</ol>
<p><img src="https://github.com/datastaxdevs/appdev-week1-todolist/blob/main/images/3c2_create-table.png?raw=true" alt="image" /></p>
<ol start="3">
<li>Finally, copy the create table statement using the code below into the <strong>body</strong> field</li>
</ol>
<pre lang="json"><code>{
  &quot;name&quot;: &quot;restfromreadme_by_id&quot;,
  &quot;ifNotExists&quot;: true,
  &quot;columnDefinitions&quot;: [
    {
      &quot;name&quot;: &quot;id&quot;,
      &quot;typeDefinition&quot;: &quot;uuid&quot;,
      &quot;static&quot;: false
    },
    {
      &quot;name&quot;: &quot;text&quot;,
      &quot;typeDefinition&quot;: &quot;text&quot;,
      &quot;static&quot;: false
    },
    {
      &quot;name&quot;: &quot;key&quot;,
      &quot;typeDefinition&quot;: &quot;text&quot;,
      &quot;static&quot;: false
    },
        {
          &quot;name&quot;: &quot;completed&quot;,
          &quot;typeDefinition&quot;: &quot;boolean&quot;
        }
  ],
  &quot;primaryKey&quot;: {
    &quot;partitionKey&quot;: [
      &quot;id&quot;
    ]
  }
}
</code></pre>
<ol start="4">
<li>And click <strong>execute</strong> to apply the command and create the table</li>
</ol>
<p><img src="https://user-images.githubusercontent.com/23346205/124660673-84c4e180-de74-11eb-89a9-55dfb017bb8f.png?raw=true" alt="image" /></p>
<p>You should see a <strong>201</strong> response telling you it correctly created the &quot;restfromreadme_by_id&quot; table.</p>
<p>Again, take a note of the Request URL that was used to create the table. This comes into play later when we take a look at the code in <code>astraRestClient.js</code> used to create our TODO application table.</p>
<p><img src="https://user-images.githubusercontent.com/23346205/124663337-f05c7e00-de77-11eb-8daa-856d15f0d223.png?raw=true" alt="image" /></p>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="4-insert-data-in-the-table-with-the-rest-api-using-swagger"> </a>4. Insert data in the Table with the REST API using Swagger</h2>
<p>Now that we have a table to use, let's insert a row of data into the table, again using REST to do so.</p>
<p>✅  <strong>Step 4a:</strong> Navigate to <strong>Add row</strong> section</p>
<ol>
<li>Scroll down and navigate to the <strong>data</strong> section</li>
<li>Then find <strong>Add row</strong> and click it to open the section</li>
</ol>
<ul>
<li>Also take note this is using a <strong>POST</strong> command.</li>
</ul>
<ol start="3">
<li>Click <strong>Try it out</strong> just like we did previously</li>
</ol>
<p><img src="https://user-images.githubusercontent.com/23346205/124664268-2fd79a00-de79-11eb-8902-1d6636e986fb.png?raw=true" alt="image" /></p>
<p>✅  <strong>Step 4b:</strong> FIll in values and add a row</p>
<ol>
<li>Add your Astra token</li>
<li>Add the keyspaceName <code>todos</code></li>
<li>Add the tableName <code>restfromreadme_by_id</code>. Note, this is the table we created in the earlier step</li>
</ol>
<p><img src="https://github.com/datastaxdevs/appdev-week1-todolist/blob/main/images/4b3_insert-row.png?raw=true" alt="image" /></p>
<ol start="4">
<li>Copy the following JSON into the <strong>body</strong></li>
</ol>
<pre lang="json"><code>{&quot;id&quot;:&quot;57dbd260-d905-11eb-b985-c522859819b9&quot;,&quot;completed&quot;:false,&quot;text&quot;:&quot;TODO FROM README&quot;,&quot;key&quot;:&quot;none&quot;}
</code></pre>
<ol start="5">
<li>Click <strong>Execute</strong>. You should see code <strong>201</strong> in the response telling you it was a success and displaying the id of the row you just created.</li>
</ol>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="5-retrieving-values"> </a>5. Retrieving values</h2>
<p>Finally, now that we created a table and inserted a row of data let's <strong>GET</strong> the data back out.</p>
<p>✅  <strong>Step 5a:</strong> Navigate to <strong>Retrieve all rows</strong> section</p>
<ol>
<li>Scroll up within the <strong>data</strong> section</li>
<li>Then find <strong>Retrieve all rows</strong> and click it to open the section</li>
</ol>
<ul>
<li>Take note this is using a <strong>GET</strong> command.</li>
</ul>
<ol start="3">
<li>Click <strong>Try it out</strong> just like we did previously</li>
</ol>
<p><img src="https://user-images.githubusercontent.com/23346205/124666300-d6bd3580-de7b-11eb-8bf6-aeeb0487962b.png?raw=true" alt="image" /></p>
<p>✅  <strong>Step 5b:</strong> Execute the command to display the data</p>
<ol>
<li>Enter your <strong>Astra token <em>(X-Cassandra-Token)</em></strong></li>
<li>Enter the <strong>keyspaceName</strong> <code>todos</code></li>
<li>Enter the <strong>tableName</strong> <code>restfromreadme_by_id</code></li>
</ol>
<p><img src="https://github.com/datastaxdevs/appdev-week1-todolist/blob/main/images/5b3_retrieve-rows.png?raw=true" alt="image" /></p>
<ol start="4">
<li>Click <strong>Execute</strong></li>
<li>View the end result data that should be exactly what we created in the previous step</li>
</ol>
<p><img src="https://user-images.githubusercontent.com/23346205/124666847-9d38fa00-de7c-11eb-8673-84f421ff9282.png?raw=true" alt="image" /></p>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="6-launch-gitpod-ide"> </a>6. Launch GitPod IDE</h2>
<ul>
<li>Click the button to launch the GitPod IDE.</li>
</ul>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/appdev-week1-todolist/" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<h1><a class="anchor" aria-hidden="true" id="need-a-refresher-on-react-basics"> </a>Need a refresher on React Basics?</h1>
<details><summary>Take me to the React stuff</summary>
  We've created a separate repo going over the Basics of React. To get there, click the link below.
<p><a href="https://github.com/datastaxdevs/react-basics" target="_blank">GOTO React-Basics</a></p>
<p>When you're done, just click on the &quot;Back to Main&quot; breadcrumb to come back here.</p>
</details>
<h2><a class="anchor" aria-hidden="true" id="7-launch-the-todo-app"> </a>7. Launch the TODO app</h2>
<p>✅  <strong>Step 7a:</strong> Retrieve application token to securely connect to the database</p>
<p>Use the token you previously generated. If you no longer have the token and did not download a .csv, you can generate a new token using <a href="#2-create-a-security-token" target="_blank">the instructions above</a></p>
<p>✅  <strong>Step 7b:</strong> Configure Environment Variables and Install Dependencies</p>
<ol>
<li>Create <code>.env</code> file</li>
</ol>
<p>In the repository directory run the following command  to set up your Astra environment.  Note that this does require Node 15 and NPM 7 to work.  You can install a node version manager like <code>nvm</code> or <code>n</code> to use multiple versions on your system.</p>
<pre lang="bash"><code>npm exec astra-setup todos_workshop_db todos
</code></pre>
<ol start="2">
<li>👩‍💻  Install all the packages</li>
</ol>
<pre lang="bash"><code>npm install -g netlify-cli
</code></pre>
<p>✅  <strong>Step 7c:</strong> Launch your app</p>
<ul>
<li>Run the application</li>
</ul>
<pre><code>netlify dev
</code></pre>
<ul>
<li>The application should automatically launch in the GitPod preview pane</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="things-to-note"> </a>Things to Note:</h3>
<ul>
<li>The contents of this repo are based on <a href="https://github.com/tjake/todo-astra-react-serverless/" target="_blank">Jake's port</a> of the <a href="https://github.com/tastejs/todomvc/tree/master/examples/react">TodoMVC code</a> originally written by <a href="https://github.com/petehunt">Pete Hunt</a>.</li>
<li>The example is modified from <a href="https://github.com/huksley/todo-react-ssr-serverless" target="_blank">https://github.com/huksley/todo-react-ssr-serverless</a>.</li>
</ul>
<!--- ENDEXCLUDE --->

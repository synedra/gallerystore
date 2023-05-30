<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="jamstack-netlify-astra-db-cassandra"> </a>JAMStack + Netlify + Astra DB + Cassandra</h1>
<p><em>10 minutes, Beginner, <a href="https://github.com/DataStax-Examples/todo-astra-jamstack-netlify#quick-start" target="_blank">Start Building</a></em></p>
<p>This is an example React To-Do application using a <a href="https://dtsx.io/2Yhvqtv" target="_blank">DataStax Astra</a> free tier database.</p>
<!--- ENDEXCLUDE --->
<p><img src="https://raw.githubusercontent.com/DataStax-Examples/todo-astra-jamstack-netlify/master/hero.png" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="quick-start"> </a>Quick Start</h2>
<!--- STARTEXCLUDE --->
<ol start="0">
<li><a href="https://dtsx.io/2Yhvqtv" target="_blank">Signup for DataStax Astra</a>, or login to your already existing account.</li>
</ol>
<!--- ENDEXCLUDE --->
<ol>
<li><a href="https://github.com/DataStax-Examples/sample-app-template/blob/master/GETTING_STARTED.md#create-an-astra-db" target="_blank">Create an Astra DB Database</a> or use an existing one.</li>
<li><a href="https://github.com/DataStax-Examples/sample-app-template/blob/master/GETTING_STARTED.md#create-an-astra-db-keyspace" target="_blank">Create an Astra DB Keyspace</a> called <code>sag_todo_jamstack</code> in your database.</li>
<li><a href="https://github.com/DataStax-Examples/sample-app-template/blob/master/GETTING_STARTED.md#create-an-application-token" target="_blank">Generate an Application Token</a> with the role of <code>Database Administrator</code> for the Organization that your Astra DB is in.</li>
<li>Click the 'Open in Gitpod' link: <a href="https://gitpod.io/#https://github.com/DataStax-Examples/todo-astra-jamstack-netlify" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in IDE" /></a></li>
<li>Once the app is finished launching in the Gitpod IDE, copy the <code>.env.example</code> file to a file named <code>.env</code> and fill the required values in from your Application Token and <a href="https://github.com/DataStax-Examples/sample-app-template/blob/master/GETTING_STARTED.md#get-your-astra-db-connection-settings" target="_blank">Astra DB connection settings</a>.</li>
<li>Start the example by running <code>npm run dev</code> in the Gitpod console.</li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>Provide a fullstack development example using Astra DB as the storage backend</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="how-this-works"> </a>How this works</h2>
<p>Once the Astra DB credentials are provided, the necessary tables are created in the database. The webservice will be available on port 8888 once the application has been deployed (<em>Note</em>: ignore the message about a service being available on port 3000, what you are looking for is at an URL starting with <code>https://8888-...</code>).</p>
<p><a href="https://jamstack.org/" target="_blank">JAMstack</a> is a big leap forward in how we can write web applications that are easy to write, deploy, scale, and also maintain. Using this approach means that newly created content is rendered from a content API, while a static render of it is being built into the site for future.</p>

<h1><a class="anchor" aria-hidden="true" id="introduction-to-graphql-react-java-astra-db"> </a>🎓 Introduction to GraphQL + React + Java + Astra DB</h1>
<p><a href="https://gitpod.io/from-referrer/" target="_blank"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod" alt="Gitpod ready-to-code" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p><em>50 minutes, Beginner/Intermediate, <a href="#1-login-or-register-to-astradb-and-create-database" target="_blank">Start Building</a></em></p>
<p>Both a simple <strong>graphQL</strong> enabled <strong>ReactJS</strong> app built using <a href="https://create-react-app.dev/" target="_blank"><strong>create-react-app</strong></a> AND a simple <strong>Java</strong> backend <strong>graphQL</strong> service built with <a href="https://start.spring.io/"><strong>Spring Initializr</strong></a> and using <a href="https://netflix.github.io/dgs/getting-started/"><strong>The Netflix DGS framework</strong></a> PLUS <strong>Astra DB</strong> hooked up and ready to rock! :heart_eyes_cat:</p>
<p>This is a companion to our <a href="https://github.com/datastaxdevs/appdev-week3-graphql" target="_blank">Netflix Clone using Astra DB and GraphQL</a> workshop and is essentially a &quot;prologue&quot; to that content. Once complete, feel free to to go deploy a Netflix clone using what you learned here.</p>
<p>Finally, this content uses <strong>React/JS</strong> concepts. If you are not familiar with those or need a refresher, <a href="https://github.com/datastaxdevs/react-basics" target="_blank">take a look HERE</a> to get up to date.</p>
<p>The materials have been built by the DataStax developer advocates team.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/./tutorial/images/graphQL_logo.png" alt="GraphQL Logo" /></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>🎯 Objectives</h2>
<ul>
<li>An overview of what GraphQL is and what makes it cool</li>
<li>What differs between GraphQL and other APIs (such as REST), including their pros/cons</li>
<li>Hands-on examples of GraphQL queries and mutations</li>
<li>How to build GraphQL APIs for mobile and web applications</li>
<li>Setting up your Astra DB to store application data via GraphQL</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="frequently-asked-questions"> </a>ℹ️ Frequently asked questions ℹ️</h2>
<p/>
<details>
<summary><b> 1️⃣ Can I run the code for this workshop on my local computer instead of using Gitpod?</b></summary>
<hr>
<p>There is nothing preventing you from running the workshop on your own machine. If you do so, you will need the following:
<ol>
  <li><a href="https://www.whitesourcesoftware.com/free-developer-tools/blog/update-node-js/" target="_blank">node 15 or 16 and npm 7 or later</a></li>
  <li>netlify-cli (use "npm install -g netlify-cli")</li>
</ol>
</p>
You will have to adapt commands and paths based on your environment (including digging into file ".gitpod.yml") and install the dependencies by yourself. <strong>We won't provide support</strong> to keep on track with schedule. However, we will do our best to give you the info you need to be successful. <strong>This is considered a more advanced path to take.</strong>
</details>
<p/>
<details>
<summary><b> 2️⃣ What other prerequisites are there?</b></summary>
<hr>
<ul>
<li>You will need a github account</li>
<li>You should use Chrome or Firefox (other browsers might have trouble displaying Gitpod correctly)</li>
<li>You will need an Astra DB account, but we'll cover that in the exercises</li>
</ul>
</p>
</details>
<p/>
<details>
<summary><b> 3️⃣ Do I need to pay for anything for this workshop?</b></summary>
<hr>
<b>No.</b> All tools and services we provide here are FREE. FREE not only during the session but also afterwards.
</details>
<p/>
<details>
<summary><b> 4️⃣ Will I get a certificate if I attend this workshop?</b></summary>
<hr>
Attending the session is not enough. You need to complete the homework detailed below and you will get a nice badge that you can share on linkedin or anywhere else <strong>(open badge specification)</strong>.
</details>
<p/>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="./slides/slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://bit.ly/cassandra-workshop" target="_blank">Discord chat</a></li>
<li><a href="https://stackoverflow.com/questions/tagged/cassandra" target="_blank">&quot;cassandra&quot; on StackOverflow</a></li>
<li><a href="https://dba.stackexchange.com/questions/tagged/cassandra" target="_blank">&quot;cassandra&quot; on DBA StackExchange</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h2>
<img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-badge.png?raw=true" width="200" align="right" />
<p>Don't forget to complete your upgrade and get your verified skill badge! Finish and submit your homework!</p>
<ol>
<li>Complete the practice steps from this repository, as described below, to the end;</li>
<li>Insert (mutate) a <strong>new show</strong> or a <strong>new genre</strong> of your choice in the database;</li>
<li>Take a single <strong>screenshot</strong> of the React app with all of the working Astra DB sections and showing the entry you just added;</li>
<li>Submit your homework <a href="https://dtsx.io/homework-intro-graphql" target="_blank">here</a>.</li>
</ol>
<p>That's it, done.<br />
We will then grade the submissions: expect an email in a few days!</p>
<h1><a class="anchor" aria-hidden="true" id="let-s-start"> </a>Let's start</h1>
<h3><a class="anchor" aria-hidden="true" id="extra-resources"> </a>Extra resources</h3>
<p><a href="https://graphql.org/" target="_blank">graphql.org</a> - The first place to learn about GraphQL</p>
<p><a href="https://netflix.github.io/dgs/getting-started/" target="_blank">The Netflix DGS framework Tutorial</a> - Java/Spring GraphQL backend (used to generate this code)</p>
<p><a href="https://start.spring.io/" target="_blank">Spring Initializr</a> - Used in the ^above tutorial to generate the Java/Spring backend starter</p>
<p><a href="https://www.gatsbyjs.com/docs/how-to/querying-data/running-queries-with-graphiql/" target="_blank">GraphiQL</a> - GraphQL IDE included with The Netflix DGS Framework</p>
<p><a href="https://www.apollographql.com/docs/react/" target="_blank">Apollo client</a> - Awesome GraphQL client for React/JS (not used here, but really solid, Netflix uses this)</p>
<p><a href="https://hasura.io/blog/top-7-graphql-ides-you-should-know-about-in-2021/" target="_blank">Top 7 GraphQL IDEs</a> - A nice collection of cool GraphQL IDEs to use</p>
<p><a href="https://create-react-app.dev/" target="_blank">create-react-app tutorial</a> - Create a React app from scratch (used to generate this code)</p>
<p><a href="https://www.youtube.com/watch?v=c2fJ7T0N1Sk" target="_blank">A Beginner's Guide to GraphQL</a> - Ali Spittel's really awesome GraphQL starter video</p>
<h2><a class="anchor" aria-hidden="true" id="1-login-or-register-to-astra-db-and-create-database"> </a>1. Login or Register to Astra DB and create database</h2>
<p><em><strong><code>ASTRA DB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, 40M read/write operations and about 80GB storage monthly for free - sufficient to run small production workloads. If you use up your credits the databases will pause, no charge, and you will be given the option to upgrade to a higher tier.</em></p>
<p>Leveraging <a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/#c-procedure" target="_blank">Database creation guide</a> create a database. <em>Right-Click the following button</em> with <em>Open in a new TAB.</em></p>
<p><a href="https://astra.dev/yt-11-23" target="_blank"><img src="tutorial/images/create_astra_db.png?raw=true" /></a></p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Database Name</strong></td>
<td><code>workshops</code></td>
</tr>
<tr>
<td><strong>Keyspace Name</strong></td>
<td><code>intrographql</code></td>
</tr>
<tr>
<td><strong>Regions</strong></td>
<td>Select <code>GOOGLE CLOUD</code>, then an Area close to you, then a region with no LOCK 🔒 icons: the LOCKed regions are the region not accessible to the Free Tier.</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>ℹ️ Note:</strong> If you already have a database <code>workshops</code>, simply add a keyspace <code>intrographql</code> using the <code>Add Keyspace</code> button on the bottom right hand corner of the DB Dashboard page. You may have to &quot;Resume&quot; the database first in case it is in &quot;hibernated&quot; state.</p>
</blockquote>
<p>While the database is being created, you will also get a <strong>Security token</strong> (needed to authenticate with your database and start using it):<br />
<strong>please IGNORE THIS ONE, as we will be soon creating a new, more powerful token for today</strong>.</p>
<p>The status will change from <code>Pending</code> to <code>Active</code> when the database is ready, this usually only takes 2-3 minutes.</p>
<h2><a class="anchor" aria-hidden="true" id="2-create-a-security-token"> </a>2. Create a security token</h2>
<blockquote>
<p>Note: this step is very important, as the token generated automatically for you with<br />
the database lacks some permissions we'll use in the workshop.</p>
</blockquote>
<p><a href="https://awesome-astra.github.io/docs/pages/astra/create-token/#c-procedure" target="_blank">Create a token for your app</a>, <em>using the <strong>&quot;Database Administrator&quot;</strong> role</em>.<br />
Keep it handy for later use (best to download it in CSV format, as the values<br />
will not be visible afterward).<br />
This will provide authentication later when interacting with the database.<br />
Today, in particular, we will need the string labeled &quot;token&quot; (the one starting with <code>AstraCS:...</code>).</p>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show the token creation on screen,
but will then destroy it immediately for security reasons.
</code></pre>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="3-launch-gitpod"> </a>3. Launch Gitpod</h2>
<p><a href="https://www.gitpod.io/" target="_blank">Gitpod</a> is an 100% online IDE based on <a href="https://github.com/gitpod-io/vscode/blob/gp-code/LICENSE.txt?lang=en-US">Visual Studio Code</a>. To initialize your environment simply click on the button below <em>(CTRL + Click to open in new tab)</em> You will be asked for you github account, as needed.</p>
<p><strong>Warning</strong>: for best results, open the link with Chrome or Firefox!</p>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-intro-to-graphql" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<p>This will bootstrap your demo environment. Be patient, it will take a few minutes as everything loads up.</p>
<blockquote>
<p><strong>Note</strong>: during loading of the Gitpod environment, a new tab will be tentatively opened<br />
with an URL such as <code>https://8080-datastaxdev-[...].gitpod.io/graphiql</code>.<br />
Please <strong>CHECK YOUR POPUP BLOCKER</strong> and allow it before continuing: this will be your GraphiQL interface!</p>
</blockquote>
<details>
<summary><strong>Show me how Gitpod looks like for this workshop</strong></summary>
<p>Gitpod starts with a file explorer on the left (1), an editor panel on the top (2),<br />
and - in the case of this specific environment - two consoles side by side,<br />
one to launch commands and later start the Node app (3) and one busy with<br />
running the Java backend (4). On the right you will find a console switcher to<br />
easily locate any console and make it active (but even just clicking<br />
on the desired console would do the trick).</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/gitpod-shape.png" alt="The shape of Gitpod" /></p>
</details>
<h2><a class="anchor" aria-hidden="true" id="4-experiment-with-graphiql"> </a>4. Experiment with GraphiQL</h2>
<p>It just so happens that <a href="https://netflix.github.io/dgs/getting-started/" target="_blank">The Netflix DGS framework</a> comes with GraphiQL already integrated and ready for use. This is a wonderful tool you can use to explore graphQL queries and mutations. Let's experiment with this now!</p>
<blockquote>
<p><em>Note:</em> the GraphiQL should be open already in a new tab for you; in case it isn't for some reason,<br />
run this command in a Gitpod console and manually point a new tab to the URL it prints:<code>echo `gp url 8080`/graphiql</code>.</p>
</blockquote>
<p>Something to point out here is there is no database just yet. We are powering the graphQL schema via the back-end Java application and the graphQL data is completely hardcoded.<br />
Take a look at both <strong><code>ShowsDatafetcher.java</code></strong> and <strong><code>GenresDatafetcher.java</code></strong> located in <strong><code>graphql-backend-examples/src/main/java/com/example/demo</code></strong><br />
to find the simple implementations using DGS annotations <code>@DgsComponent</code> and <code>@DgsQuery</code>.</p>
<details>
<summary><strong>Show me how to open these files in Gitpod</strong></summary>
<p>In the left toolbar, choose the first tool (&quot;Explorer&quot;) and navigate the directory to the desired directory; then, clicking on the files will open them in the editor (topmost panel on the right).</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/open-java-DGS-files-in-gitpod.png" alt="Open files in Gitpod" /></p>
</details>
<h4><a class="anchor" aria-hidden="true" id="now-let-s-try-out-some-graphql-queries"> </a>Now, let's try out some graphQL queries</h4>
<p>Plug these into the GraphiQL IDE that launched into a new tab from GitPod.</p>
<pre lang="GraphQL"><code>query justTitle {
  shows {
    title
  }
}
</code></pre>
<pre lang="GraphQL"><code>query withReleaseYear {
  shows {
    title
    releaseYear
  }
}
</code></pre>
<pre lang="GraphQL"><code>query getOneShow {
  shows (titleFilter: &quot;Ozark&quot;) {
      title
      releaseYear
  }
}
</code></pre>
<pre lang="GraphQL"><code>query ShowsAndGenres {
  shows {
    title
    releaseYear
  }
  genres {
    value
  }
}
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphiql-queries.png" alt="GraphiQL queries" /></p>
<h4><a class="anchor" aria-hidden="true" id="compare-the-graphql-schema"> </a>Compare the GraphQL schema</h4>
<p>The objects known to a GraphQL API are defined starting from its &quot;Schema&quot;.<br />
In the case of our DGS Java application, the schema is found in<br />
<code>graphql-backend-examples/src/main/resources/schema/schema.graphqls</code>.<br />
Take a look at its contents: notice the special <code>Query</code> item that defines<br />
the possible queries and, after that, the user-defined types available to<br />
the API:</p>
<pre lang="GraphQL"><code>type Query {
    shows(titleFilter: String): [Show]
    genres(labelFilter: String): [Genre]
}

type Show {
    title: String
    releaseYear: Int
}

type Genre {
    value: String!
}
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="5-experiment-with-astra-db-s-graphql-playground"> </a>5. Experiment with Astra DB's GraphQL Playground</h2>
<p>Ok, let's take this a step further and prepare the data layer for our app.<br />
At this point you should have already <a href="#1-login-or-register-to-astradb-and-create-database" target="_blank">created your Astra DB database</a>.<br />
Follow the instructions below to launch the <strong>GraphQL Playground</strong> provided in <strong>Astra DB</strong>:</p>
<h4><a class="anchor" aria-hidden="true" id="step-5a-open-graphql-playground"> </a>✅  Step 5a: Open GraphQL Playground:</h4>
<ol start="0">
<li>Ensure you are logged on to your <a href="https://astra.datastax.com" target="_blank">Astra</a> account</li>
<li>Click on the &quot;workshops&quot; database on the left (expanding the list if needed)</li>
<li>Click <code>Connect</code> TAB</li>
<li>Click the <code>APIs</code>  connection method</li>
<li>Make sure <code>GraphQL API</code> is selected</li>
<li>Locate the link to your GraphQL Playground in the text</li>
</ol>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/open-playground-2.png" alt="Open Astra DB GraphQL Playground image" /></p>
<details>
<summary><strong>Click here if you are using the "New Astra Experience" UI</strong></summary>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/open-playground-2-wh.png" alt="Open Astra DB GraphQL Playground image, new Astra UI" /></p>
</details>
<p><strong>Note</strong>: in the following, we will refer to &quot;playground tabs&quot;. These are <em>not</em> the tabs<br />
in your browser, rather they are tabs <em>within</em> the Playground application,<br />
to switch between the (logically distinct) realms of &quot;managing schema&quot; and &quot;managing data in the tables&quot;<br />
(more on that later).</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/tabs-vs-playgroundtabs-labeled.png" alt="Playground tabs VS Browser tabs" /></p>
<h4><a class="anchor" aria-hidden="true" id="step-5b-insert-the-astra-db-token-to-run-schema-queries"> </a>✅  Step 5b: Insert the Astra DB Token to run schema queries</h4>
<p>In the GraphQL Playground, <strong>Populate HTTP HEADER</strong> variable <code>x-cassandra-token</code> on the bottom of the page with your token (including the <code>AstraCS:</code> part).<br />
<em>This is the &quot;Database Administrator&quot; token you created earlier on the Astra DB dashboard (Step 2 above).</em></p>
<p><strong>Note</strong>: make sure you are on the <strong><code>graphql-schema</code></strong> playground tab in this step, as this image illustrates:</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-playground.png" alt="GraphQL Playground and token header, Schema playground tab" /></p>
<blockquote>
<p>Note: the GraphQL Playground starts with a ready-to-use <em>temporary token</em> as the <code>x-cassandra-token</code> header. But we want the queries run in the Playground<br />
to be identical to those that the Netlify functions will run from code, so <strong>please replace the token with your DB token as instructed</strong>.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="step-5c-create-a-table-in-the-graphql-playground"> </a>✅  Step 5c: Create a table in the GraphQL Playground</h4>
<p>Run the following mutation in the <code>graphql-schema</code> playground tab, making sure to replace <code>intrographql</code> in the URL if you used a different keyspace name:</p>
<ul>
<li>Copy the following mutation on the left panel</li>
</ul>
<pre lang="GraphQL"><code>mutation {
  reference_list: createTable(
    keyspaceName:&quot;intrographql&quot;,
    tableName:&quot;reference_list&quot;,
    ifNotExists:true
    partitionKeys: [ 
      { name: &quot;label&quot;, type: {basic: TEXT} }
    ]
    clusteringKeys: [
      { name: &quot;value&quot;, type: {basic: TEXT}, order: &quot;ASC&quot; }
    ]
  )
}
</code></pre>
<p>Click on the arrow in the middle of the screen to execute the query.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/playground-1.png" alt="Execute a query in GraphQL Playground" /></p>
<h2><a class="anchor" aria-hidden="true" id="6-insert-data-to-db-using-the-graphql-playground"> </a>6. Insert data to DB using the GraphQL Playground</h2>
<h4><a class="anchor" aria-hidden="true" id="step-6a-adjust-the-second-playground-tab-to-your-keyspace"> </a>✅  Step 6a: Adjust the second playground tab to your keyspace</h4>
<p>In the GraphQL playground, switch to the second Playground tab (<code>graphql</code>). Edit the ending of the URL <em>shown within the Playground page</em> from <code>system</code> to the keyspace name <code>intrographql</code>:</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-url-ending.png" alt="GraphQL URL ending" /></p>
<h4><a class="anchor" aria-hidden="true" id="step-6b-set-the-token-to-run-data-queries"> </a>✅  Step 6b: Set the token to run data queries</h4>
<p>Populate the <strong>HTTP HEADER</strong> variable <code>x-cassandra-token</code> on the bottom of the page with your DB token as shown below <em>(Note: you did this for the <code>graphql-schema</code> playground tab, now repeat for the <code>graphql</code> playground tab!)</em></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-playground-2b.png" alt="GraphQL Playground and token header, GraphQL playground tab" /></p>
<h4><a class="anchor" aria-hidden="true" id="step-6c-insert-genre-names-with-the-playground"> </a>✅  Step 6c: Insert genre names with the Playground</h4>
<p>In the GraphQL Playground, populate the <code>reference_list</code> table with all values:<br />
copy the following mutation on the left panel</p>
<pre lang="GraphQL"><code>mutation insertGenres {
  action: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Action&quot;}) {
    value{value}
  }
  anime: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Anime&quot;}) {
     value{value}
  }
  award: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Award-Winning&quot;}) {
     value{value}
  }
  children: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Children &amp; Family&quot;}) {
     value{value}
  }
  comedies: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Comedies&quot;}) {
     value{value}
  }
  documentaries: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Documentaries&quot;}) {
     value{value}
  }
  drama: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Dramas&quot;}) {
     value{value}
  }
  fantasy: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Fantasy&quot;}) {
     value{value}
  }
  french: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;French&quot;}) {
     value{value}
  }
  horror: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Horror&quot;}) {
     value{value}
  }
  independent: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Independent&quot;}) {
     value{value}
  }
  music: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Music &amp; Musicals&quot;}) {
     value{value}
  }
  romance: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Romance&quot;}) {
     value{value}
  }
  scifi: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Sci-Fi&quot;}) {
     value{value}
  }
  thriller: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Thriller&quot;}) {
     value{value}
  }  
}
</code></pre>
<p>Click on the arrow in the middle of the screen to execute the query.</p>
<h2><a class="anchor" aria-hidden="true" id="7-retrieve-values-from-db-using-the-graphql-playground"> </a>7. Retrieve values from DB using the GraphQL Playground</h2>
<h4><a class="anchor" aria-hidden="true" id="step-7a-read-genres-with-a-query-in-the-playground"> </a>✅  Step 7a: Read genres with a query in the Playground</h4>
<p>In the GraphQL Playground (staying on the <code>graphql</code> playground tab), list values from the table with the following query:</p>
<pre lang="yaml"><code>query getAllGenre {
    reference_list (value: {label:&quot;genre&quot;}) {
      values {
      	value
      }
    }
}
</code></pre>
<p><em>👁️ Expected output</em><br />
<img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-playground-3.png" alt="Playground getAllGenre query result" /></p>
<h2><a class="anchor" aria-hidden="true" id="8-start-up-react"> </a>8. Start up React</h2>
<p>So far we have executed GraphQL queries and mutations by hand from specific UIs.<br />
Now it's time to start the React client app and query the GraphQL endpoints from it!</p>
<blockquote>
<p>&quot;Endpoints&quot;, two of them. Each GraphQL server exposes a single endpoint for everything,<br />
but remember this app will query both the local DGS app and the Astra DB server!</p>
</blockquote>
<p>First you need to run a couple commands to get things set up:<br />
in your <strong><code>GitPod</code></strong> IDE navigate to the &quot;Client&quot; terminal<br />
<em>(it should already be open for you on the bottom left)</em><br />
and make sure you are in the <strong><code>workshop-intro-to-graphql/graphql-client-examples</code></strong> directory.<br />
<strong>This is where you'll be running the nodejs/React app.</strong></p>
<details>
<summary><strong>Remind me what is this "client terminal" ...</strong></summary>
<p>It is the block labeled as &quot;3&quot;. Click on it, or use the switcher (5):</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/gitpod-shape.png" alt="The shape of Gitpod" /></p>
</details>
<h4><a class="anchor" aria-hidden="true" id="step-8a-execute-the-following-command"> </a>✅ Step 8a: Execute the following command</h4>
<pre lang="shell"><code>npm install -g netlify-cli
</code></pre>
<p>This will install the <strong>Netlify CLI</strong> (command line interface) which our <strong>React/JS</strong> app uses in conjunction with the serverless functions we've setup to talk to our <strong>graphQL</strong> endpoints.</p>
<h4><a class="anchor" aria-hidden="true" id="step-8b-then-execute"> </a>✅  Step 8b: Then, execute</h4>
<pre lang="shell"><code>netlify dev
</code></pre>
<p>This will start the <strong>React/JS</strong> application and display results from both the <strong><code>Shows</code></strong> and <strong><code>Genres</code></strong> <strong>graphQL</strong> queries and endpoints we were just experimenting with.</p>
<p>You should see Gitpod's mini-browser opening up by itself and showing the client application wihtin Gitpod.</p>
<blockquote>
<p><em>Note:</em> the client, at this point, should be opened in the mini-browser within Gitpod; to open it manually,<br />
run this command in a Gitpod console and point a new tab to the URL it prints:<code>echo `gp url 8888` </code>.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="compare-javascript-code-to-our-graphql-queries-from-above"> </a>Compare javascript code to our graphQL queries from above</h4>
<p>If you take a look at both <strong><code>getShowsBackend.js</code></strong> and <strong><code>getGenresBackend.js</code></strong> located in <strong><code>graphql-client-examples/functions</code></strong> you should notice that both use the <strong>same exact</strong> <strong>graphQL</strong> queries that we used above.</p>
<pre lang="javascript"><code>const query = `
    query getAllShows {
      shows {
        title
        releaseYear
      }
    }
  `
</code></pre>
<pre lang="javascript"><code>  const query = `
    query getAllGenres {
      genres {
        value
      }
    }
  `
</code></pre>
<p>All of the javascript wrapped around these is simply there to call the <strong>graphQL</strong> endpoint with the given query and pass the responseBody back to the calling function.</p>
<h4><a class="anchor" aria-hidden="true" id="now-for-the-cool-part"> </a>Now for the cool part</h4>
<p>Take a look at <strong><code>Shows.js</code></strong> and <strong><code>Genres.js</code></strong> located in <strong><code>graphql-client-examples/src/components/</code></strong>. In both cases they use <strong>React</strong> state, <code>gqlResult</code></p>
<pre lang="javascript"><code>  const [gqlResult, setGqlResult] = useState(null)
</code></pre>
<p>to receive the responseBody from from our <strong>graphQL</strong> queries, set the <strong>React</strong> state, and inject the values dynamically into the DOM. Check out the following javascript snippet from <strong><code>Shows.js</code></strong>.</p>
<pre lang="javascript"><code>// Asynchronously fetch any &quot;shows&quot; graphQL data from the Java backend
// using the getShowsBackend serverless function to call out to the
// Netflix DGS Java graphQL endpoint
const response = await fetch(&quot;/.netlify/functions/getShowsBackend&quot;, {
    method: &quot;POST&quot;,
})
const responseBody = await response.json()
setGqlResult(responseBody) // on response set our graphQL result state
</code></pre>
<p>Notice how the fields (title, releaseYear) match our <strong>graphQL</strong> <code>Shows</code> schema exactly.</p>
<pre lang="javascript"><code>// Finally, if all other checks pass get the data
// from the payload via gqlResult state and inject it into the DOM
// Notice how the payload example below and the fields &quot;title&quot; and &quot;releaseYear&quot; match exactly
// {&quot;data&quot;:{&quot;shows&quot;:[{&quot;title&quot;:&quot;Stranger Things&quot;,&quot;releaseYear&quot;:2016},{&quot;title&quot;:&quot;Ozark&quot;,&quot;releaseYear&quot;:2017}...
return gqlResult.data.shows.map(({ title, releaseYear }) =&gt; (
    &lt;div key={title}&gt;
        &lt;p&gt;
        {title}: {releaseYear}
        &lt;/p&gt;
    &lt;/div&gt;
  ));
</code></pre>
<p>Notice how the field (value) matches our <strong>graphQL</strong> <code>Genres</code> schema exactly.</p>
<pre lang="javascript"><code>// Finally, if all other checks pass get the data
// from the payload via gqlResult state and inject it into the DOM
// Notice how the payload example below and the field &quot;value&quot; match exactly
// {&quot;data&quot;:{&quot;genres&quot;:[{&quot;value&quot;:&quot;Action&quot;},{&quot;value&quot;:&quot;Anime&quot;}...
return gqlResult.data.genres.map(({ value }) =&gt; (
    &lt;div key={value}&gt;
        &lt;p&gt;
        {value}
        &lt;/p&gt;
    &lt;/div&gt;
  ));
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="9-hook-the-database-up-to-the-react-client-app"> </a>9. Hook the database up to the React client app</h2>
<p>The next step is to make the client able to retrieve the genres and the shows<br />
from the database, by querying Astra DB's GraphQL API. To achieve this,<br />
it's time to provide connection details (addresses, secrets) to the<br />
serverless Netlify functions which will back the React client.</p>
<h4><a class="anchor" aria-hidden="true" id="step-9a-initialize-astra-cli"> </a>✅ Step 9a: Initialize Astra CLI</h4>
<p>In the <strong><code>GitPod</code></strong> IDE, click on the &quot;Client&quot; terminal to make it active, hit <code>Ctrl-C</code> to stop the running client, if any, and make sure you are in the <strong><code>workshop-intro-to-graphql/graphql-client-examples</code></strong> directory.</p>
<p>Now you will create a <code>.env</code> file with connection info (addresses and secrets) for the Netlify function to be able to reach both the local backend and your Astra DB's GraphQL endpoint.<br />
You will use the Astra command-line interface to prepare a dot-env file for you; then you will complete it by adding a line defining the address of the local backend (i.e. the DGS locally-running GraphQL API).</p>
<p>Run the following command and provide your <strong>DB Administrator</strong> token string (starting with <code>AstraCS:...</code>) when prompted:</p>
<pre><code>astra setup
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="step-9b-configure-database-credentials"> </a>✅ Step 9b: Configure database credentials</h4>
<p>Once you get a &quot;Configuration has been saved&quot; confirmation, proceed with:</p>
<pre><code>astra db create-dotenv workshops -k intrographql
cat .local-backend.env &gt;&gt; .env
gp open .env
</code></pre>
<p>The credentials are now all set up: your dot-env file should be now shown in the editor for you to check its contents.<br />
You will see several lines pertaining to Astra DB (not all of which will be used by today's client)<br />
and, at the end, a single setting about the Java GraphQL API you tested earlier.</p>
<p>Here is how the <code>.env</code> might look like (as a reference, check out the provided <code>.env.sample</code>):</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/dot-env-2.png" alt="Sample dot-env file" /></p>
<blockquote>
<p>If you are preparing the file manually (i.e. as opposed to using the <code>astra-cli</code> tool), be aware that the only<br />
variables needed by the React client are: <code>ASTRA_DB_APPLICATION_TOKEN</code>, <code>ASTRA_DB_GRAPHQL_URL</code><br />
and <code>JAVA_GRAPHQL_ENDPOINT</code>.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="step-9c-start-your-react-app-again"> </a>✅ Step 9c: Start your React app again</h4>
<p>Launch the following command once more:</p>
<pre lang="shell"><code>netlify dev
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="step-9d-verify-data-load"> </a>✅ Step 9d: Verify data load</h4>
<p>At this point your app should be running with a bunch of data displayed in the <strong><code>Shows</code></strong>, <strong><code>Genres,</code></strong> and <strong><code>ReferenceList</code></strong> sections, but notice the <strong><code>ShowsByName</code></strong> section displays <strong>&quot;Error :(&quot;</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/error_shows_by_name.png" alt="Error in Shows by name" /></p>
<h4><a class="anchor" aria-hidden="true" id="can-you-figure-out-what-s-going-on-here"> </a>Can you figure out what's going on here?</h4>
<p>Let's break this down.</p>
<ul>
<li>
<p>We just added the database configuration and the <strong><code>ReferenceList</code></strong> section is populated which tells us our DB config and graphQL endpoints are configured properly</p>
</li>
<li>
<p>In the GraphQL Playground we added a schema for the <strong><code>reference_list</code></strong> table and added some data to the table, but we never created a schema for the <strong><code>ShowsByName</code></strong> section</p>
</li>
<li>
<p>If you take a look at the <strong><code>getShowsAstra.js</code></strong> script in <strong><code>graphql-client-examples/functions</code></strong> you can see the graphQL being used to query for data</p>
</li>
</ul>
<pre lang="javascript"><code>exports.handler = async function (event) {
  const query = `
    query getAllShows {
      show_by_name {
        values {
          title
          releaseYear
        }
      }
    }
  `
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="step-9e-test-this-query"> </a>✅ Step 9e: Test this query</h4>
<p>Go back to the GraphQL <strong><code>graphQL</code></strong> playground tab.</p>
<p>Copy this into the playground and press the <em>&quot;play&quot;</em> button to execute the query. <strong>NOTE, you can simply append the query to the end of the list and then choose the query you wish to execute when you hit the &quot;play&quot; button.</strong></p>
<pre lang="GraphQL"><code>query getAllShows {
      show_by_name {
        values {
          title
          releaseYear
        }
      }
    }
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-getallshows.png" alt="GraphQL getAllShows execution" /></p>
<h4><a class="anchor" aria-hidden="true" id="view-results"> </a>View Results</h4>
<p>Notice what happened here. We have a validation error because there is no schema associated with the query we just executed. GraphQL uses a typed validation system so this is something to expect if a query is malformed, missing a schema, or something along those lines. You will want to control for this in your code.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-field-undefined-error.png" alt="GraphQL &quot;Field undefined&quot; error" /></p>
<h4><a class="anchor" aria-hidden="true" id="step-9f-create-the-missing-table"> </a>✅ Step 9f: Create the missing table</h4>
<p>To fix up the schema issue, and resolve the error,<br />
create the <strong><code>ShowsByName</code></strong> table with a graphQL mutation to fix the app.<br />
Execute the following mutation in the <strong><code>graph-schema</code></strong> Playground tab</p>
<pre lang="GraphQL"><code>mutation CreateShowsTable {
  createTable(
    keyspaceName: &quot;intrographql&quot;
    tableName: &quot;show_by_name&quot;
    partitionKeys: [{
      name: &quot;title&quot;, type: {basic:TEXT}
    }]
    values:[{
      name: &quot;releaseYear&quot;, type: {basic:INT}
    }]
  )
}
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-CreateShowsTable.png" alt="GraphQL CreateShowsTable query" /></p>
<h4><a class="anchor" aria-hidden="true" id="verify-result"> </a>✅ Verify result</h4>
<p>Once executed you should see a result like this</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-CreateShowsTable_result.png" alt="GrahQL CreateShowsTable result" /></p>
<h4><a class="anchor" aria-hidden="true" id="step-9g-add-some-data"> </a>✅ Step 9g: Add some data</h4>
<p>Now, go back to the <strong><code>graphql</code></strong> playground tab and add the following mutation</p>
<pre lang="GraphQL"><code>mutation insertShows {
  stranger: insertshow_by_name (
    value: {
      title: &quot;Stranger Things&quot;,
      releaseYear: 2016}) {
  	value{title}
  }
  ozark: insertshow_by_name (
    value: {
      title: &quot;Ozark&quot;,
      releaseYear: 2017}) {
  	value{title}
  }
}
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-insertShows.png" alt="GraphQL &quot;insertShows&quot;" /></p>
<h4><a class="anchor" aria-hidden="true" id="check-the-result"> </a>✅ Check the result</h4>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-insertShows_result.png" alt="GraphQL insertShows, result" /></p>
<h4><a class="anchor" aria-hidden="true" id="step-9h-check-the-client-again"> </a>✅ Step 9h: Check the client again</h4>
<p>Finally, refresh your React app.</p>
<p>Notice this no longer displays an error. Now it correctly displays the data you just inserted (mutated). It might be fun to add some of your own data to this schema and refresh your page.</p>
<p><img src="https://github.com/datastaxdevs/workshop-intro-to-graphql/raw/master/tutorial/images/graphql-client-showing-shows.png" alt="GraphQL, client showing shows from DB" /></p>
<h4><a class="anchor" aria-hidden="true" id="play-a-bit-more"> </a>Play a bit more!</h4>
<p>Feel free to experiment with a couple more graphQL queries now that you have some data in the table</p>
<p>Queries usually offer some way to restrict the results returned,<br />
in the form of parameters passed to queries. Recall the original <code>getAllShows</code>, repeated here for convenience:</p>
<pre lang="GraphQL"><code>query getAllShows {
  show_by_name {
    values {
      title
      releaseYear
    }
  }
}
</code></pre>
<p>Now let's see a way to pass a <code>title</code> parameter to the query and just get<br />
matching values (a single entry, in this case):</p>
<pre lang="GraphQL"><code>query getOneShow {
  show_by_name (value: {title: &quot;Ozark&quot;}) {
    values {
      title
      releaseYear
    }
  }
}
</code></pre>
<p>The following query, which uses the <a href="https://docs.datastax.com/en/astra/docs/develop/dev-with-graphql-cql-first.html#_retrieve_data" target="_blank">more general <code>filter</code> syntax</a>,<br />
is completely equivalent to the previous one:</p>
<pre lang="GraphQL"><code>query getOneShowF {
  show_by_name(filter: {title: {eq: &quot;Ozark&quot;}}){
    values {
      title
      releaseYear
    }
  }
}
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="that-s-it-you-did-it-nice-job"> </a>That's it, you did it! Nice job!</h3>
<p>We hope this workshop gave you enough information on GraphQL to be dangerous and start you on a journey to using GraphQL in your own apps.<br />
Also, don't forget your <a href="#homework" target="_blank">HOMEWORK</a>.</p>

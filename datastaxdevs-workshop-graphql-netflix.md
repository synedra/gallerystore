<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="netflix-clone-using-astra-db-and-graphql"> </a>🎓 Netflix Clone using Astra DB and GraphQL</h1>
<p><a href="https://gitpod.io/from-referrer/" target="_blank"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod" alt="Gitpod ready-to-code" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p><em>50 minutes, Intermediate, <a href="#1-login-or-register-to-astradb-and-create-database" target="_blank">Start Building</a></em></p>
<p>A simple <strong>ReactJS</strong> Netflix homepage clone running on <em>Astra DB</em> that leverages the GraphQL API with <em>paging</em> and <em>infinite scrolling.</em><br />
This application is the result of the collaboration between <a href="https://www.youtube.com/channel/UC5DNytAJ6_FISueUfzZCVsw" target="_blank">Ania Kubow</a> and the Datastax Developer Advocate team.</p>
<!--- ENDEXCLUDE --->
<p>See the <a href="https://imgur.com/3ns3UJB" target="_blank">Video Demo</a> of what you will build!</p>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/ui.png" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>🎯 Objectives</h2>
<ul>
<li>Build and run a Netflix clone.</li>
<li>Learn <strong>GraphQL API</strong> and how to use it with a database to create the tables and navigate the data.</li>
<li>Learn about <strong>pagination</strong> and <strong>infinite scrolling</strong> in a Web UI.</li>
<li>Leverage Netlify and DataStax Astra DB.</li>
<li>Deploy the Netflix clone to production with Netlify.</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="frequently-asked-questions"> </a>ℹ️ Frequently asked questions ℹ️</h2>
<details>
<summary><strong>Can I run the workshop on my computer?</strong></summary>
<p>There is nothing preventing you from running the workshop on your own machine.<br />
If you do so, you will need</p>
<ul>
<li>git installed on your local system</li>
<li><a href="https://www.whitesourcesoftware.com/free-developer-tools/blog/update-node-js/" target="_blank">node 15 and npm 7 or later</a></li>
</ul>
<p>You will have to adapt commands and paths based on your environment and install the dependencies by yourself. <strong>We won't provide support</strong> to keep on track with schedule. However, we will do our best to give you the info you need to be successful.</p>
</details>
<details>
<summary><strong>What other prerequisites are there?</strong></summary>
<ul>
<li>You will need a github account</li>
<li>You will also need Netlify and Astra DB accounts, but we'll work through that in the exercises</li>
<li>Use <strong>Chrome</strong> or <strong>Firefox</strong> for the best experience. Other browsers are great, but don't work well with the GitPod integration we use a bit later.</li>
</ul>
</details>
<details>
<summary><strong>Do I need to pay for anything for this workshop?</strong></summary>
<p><strong>No.</strong> All tools and services we provide here are FREE.</p>
</details>
<details>
<summary><strong>Will I get a certificate if I attend this workshop?</strong></summary>
<p>Yes, but attending the session is not enough. You need to complete the homeworks detailed below and you will get a participation badge.</p>
</details>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="slides/slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">Discord chat</a></li>
<li><a href="https://stackoverflow.com/questions/tagged/cassandra" target="_blank">&quot;cassandra&quot; on StackOverflow</a></li>
<li><a href="https://dba.stackexchange.com/questions/tagged/cassandra" target="_blank">&quot;cassandra&quot; on DBA StackExchange</a></li>
</ul>
<h1><a class="anchor" aria-hidden="true" id="let-s-start"> </a>Let's start</h1>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>Table of contents</h2>
<h3><a class="anchor" aria-hidden="true" id="part-i-db-setup-data-ingest"> </a>Part I - DB Setup &amp; Data Ingest</h3>
<ol>
<li><a href="#1-login-or-register-to-astradb-and-create-database" target="_blank">Create Astra DB Instance</a></li>
<li><a href="#2-create-a-security-token" target="_blank">Create a security token</a></li>
<li><a href="#3-create-table-for-genres-with-graphql" target="_blank">Create table for genres with GraphQL</a></li>
<li><a href="#4-insert-genre-data-with-graphql" target="_blank">Insert genre data with GraphQL</a></li>
<li><a href="#5-retrieve-genres-with-graphql" target="_blank">Retrieve genres with GraphQL</a></li>
<li><a href="#6-create-a-table-for-movies" target="_blank">Create a table for movies</a></li>
<li><a href="#7-insert-a-few-movies" target="_blank">Insert a few movies</a></li>
<li><a href="#8-retrieve-movies-pagination" target="_blank">Retrieve movies: Pagination</a></li>
</ol>
<h3><a class="anchor" aria-hidden="true" id="part-ii-build-and-deploy-front-end"> </a>Part II - Build and Deploy Front-End</h3>
<ol>
<li><a href="#1-deploy-skeletal-gui-to-netlify" target="_blank">Deploy skeletal GUI to Netlify</a></li>
<li><a href="#2-launch-gitpod-from-your-github-repo" target="_blank">Launch Gitpod from YOUR Github repo</a></li>
<li><a href="#3-set-up-and-use-astra-cli" target="_blank">Set up and use <code>astra-cli</code></a></li>
<li><a href="#4-serverless-functions" target="_blank">Serverless Functions</a></li>
<li><a href="#5-fetching-from-the-front-end" target="_blank">Fetching from the Front-End</a></li>
<li><a href="#6-install-the-netlify-cli" target="_blank">Install the Netlify CLI</a></li>
<li><a href="#7-provide-db-connection-parameters" target="_blank">Provide DB connection parameters</a></li>
<li><a href="#8-run-the-app-in-dev-mode" target="_blank">Run the app in dev mode</a></li>
<li><a href="#9-connect-to-your-netlify-site" target="_blank">Connect to your Netlify site</a></li>
<li><a href="#10-deploy-in-production" target="_blank">Deploy in production!</a></li>
</ol>
<p><a href="#homework" target="_blank"><strong>🎓 Complete the assignment, receive your Badge!</strong></a></p>
<h3><a class="anchor" aria-hidden="true" id="extra-resources"> </a>Extra resources</h3>
<ul>
<li><a href="https://github.com/datastaxdevs/workshop-intro-to-graphql" target="_blank">Intro to GraphQL Workshop</a></li>
<li><a href="https://github.com/datastaxdevs/react-basics" target="_blank">React starter using NPX</a></li>
<li><a href="https://github.com/datastaxdevs/appdev-week1-todolist" target="_blank">React ToDo app</a></li>
<li><a href="https://github.com/datastaxdevs/workshop-battlestax/blob/master/README_JAM.md" target="_blank">What is JamStack?</a></li>
<li><a href="#video-tutorial-with-ania-kubow" target="_blank">Video tutorial with Ania Kubow</a></li>
</ul>
<h1><a class="anchor" aria-hidden="true" id="part-1-db-setup-data-ingest"> </a>Part 1 - DB Setup &amp; Data Ingest</h1>
<h2><a class="anchor" aria-hidden="true" id="1-login-or-register-to-astradb-and-create-database"> </a>1. Login or Register to AstraDB and create database</h2>
<blockquote>
<p>🎁 <em>When creating your instance, use the promotion code <strong>ANIA200</strong> to get 200$ of additional free credit!</em></p>
</blockquote>
<p><em><strong><code>ASTRA DB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, 40M read/write operations and about 80GB storage monthly for free - sufficient to run small production workloads. If you use up your credits the databases will pause, no charge, and you will be given the option to upgrade to a higher tier.</em></p>
<p>Leveraging <a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/#c-procedure" target="_blank">Database creation guide</a> create a database. <strong>Right-Click</strong> the following button and <em>Open in a new TAB.</em></p>
<p><a href="https://astra.dev/yt-01-04" target="_blank" target="blank"><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/create_astra_db.png?raw=true" /></a></p>
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
<td><code>netflix</code></td>
</tr>
<tr>
<td><strong>Regions</strong></td>
<td>Select <code>GOOGLE CLOUD</code>, then an Area close to you, then a region with no LOCK 🔒 icons: the LOCKed regions are the region not accessible to the Free Tier.</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>ℹ️ Note:</strong> If you already have a database <code>workshops</code>, simply add a keyspace <code>netflix</code> using the <code>Add Keyspace</code> button on the bottom right hand corner of the DB Dashboard page. You may have to &quot;Resume&quot; the database first in case it is in &quot;hibernated&quot; state.</p>
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
Today, in particular, you'll need the string labeled &quot;token&quot; (the one starting with <code>AstraCS:...</code>).</p>
<blockquote>
<p><strong>⚠️ Important</strong><br />
The instructor will show the token creation on screen,<br />
but will then destroy it immediately for security reasons.</p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="3-create-table-for-genres-with-graphql"> </a>3. Create table for genres with GraphQL</h2>
<p>✅  <strong>Step 3a:</strong> Open <strong>GraphQL Playground</strong>:</p>
<ol start="0">
<li>Ensure you are logged on to your <a href="https://astra.datastax.com" target="_blank">Astra</a> account</li>
<li>Click on the &quot;workshops&quot; database on the left (expanding the list if needed)</li>
<li>Click <code>Connect</code> TAB</li>
<li>Click the <code>APIs</code>  connection method</li>
<li>Make sure <code>GraphQL API</code> is selected</li>
<li>Locate the link to your GraphQL Playground in the text</li>
</ol>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/open-playground-2-wh.png" alt="Open Astra DB GraphQL Playground image" /></p>
<details>
<summary><strong>Click here if you are not using the "New Astra Experience" UI (yet)</strong></summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/open-playground-2.png" alt="Open Astra DB GraphQL Playground image, old Astra UI" /></p>
</details>
<p><strong>Note</strong>: in the following, we will refer to &quot;playground tabs&quot;. These are <em>not</em> the tabs<br />
in your browser, rather they are tabs <em>within</em> the Playground application,<br />
to switch between the (logically distinct) realms of &quot;managing schema&quot; and &quot;managing data in the tables&quot;<br />
(more on that later).</p>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/tabs-vs-playgroundtabs-labeled-2.png" alt="Playground tabs VS Browser tabs" /></p>
<p>✅  <strong>Step 3b:</strong> Provide the database token as header</p>
<p>In the GraphQL Playground, <strong>Populate HTTP HEADER</strong> variable <code>x-cassandra-token</code> on the bottom of the page with your token (including the <code>AstraCS:</code> part).<br />
<em>This is the &quot;Database Administrator&quot; token you created earlier on the Astra DB dashboard (Step 2 above).</em></p>
<details>
<summary>
<strong>Note</strong>: make sure you are on the <strong>graphql-schema</strong> playground tab in this step. Click here to show image.
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/graphql-playground.png" alt="GraphQL Playground and token header, Schema playground tab" /></p>
</details>
<blockquote>
<p>Note: the GraphQL Playground starts with a ready-to-use <em>temporary token</em> as the <code>x-cassandra-token</code> header. But you want the queries run in the Playground<br />
to be identical to those that the Netlify functions will run from code, so <strong>please replace the token with your DB token as instructed</strong>.</p>
</blockquote>
<p>✅  <strong>Step 3c:</strong> In GraphQL Playground, create the <code>reference_list</code> table:</p>
<p>Copy the following <strong>mutation</strong> to the left panel</p>
<pre lang="yaml"><code>mutation createReferenceList {
  reference_list: createTable(
    keyspaceName:&quot;netflix&quot;,
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
<details>
<summary>and then use the big "play button" arrow in the center to execute it. Click for screenshot.</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/playground-1.png" alt="image" /></p>
</details>
<p><strong>GraphQL Playground troubleshooting</strong> (covers this whole section)</p>
<table>
<thead>
<tr>
<th>Trouble</th>
<th>Shooting</th>
</tr>
</thead>
<tbody>
<tr>
<td>Server cannot be reached</td>
<td>Add Astra token to headers (including <code>AstraCS:...</code>; check quotes)</td>
</tr>
<tr>
<td>Server cannot be reached (second playground tab)</td>
<td>Check playground target URL ends with <code>netflix</code></td>
</tr>
<tr>
<td>Response not successful: Received status code 401</td>
<td>Same as &quot;server cannot be reached&quot;</td>
</tr>
<tr>
<td>Response not successful: Received status code 404</td>
<td>Check spelling of keyspace in target URL</td>
</tr>
<tr>
<td>&quot;Play&quot; button does nothing</td>
<td>Ensure query is syntactically correct</td>
</tr>
<tr>
<td>&quot;Validation error of type FieldUndefined&quot;</td>
<td>Most likely query in the wrong playground tab, or writing to table not created yet</td>
</tr>
</tbody>
</table>
<h2><a class="anchor" aria-hidden="true" id="4-insert-genre-data-with-graphql"> </a>4. Insert genre data with GraphQL</h2>
<p>✅  <strong>Step 4a:</strong> Get to the API URL for your keyspace</p>
<p>In graphQL playground, <strong>change playground tab</strong> to now use <code>graphql</code>. The Playground has its own address bar<br />
(<strong>note</strong>: it's <em>not</em> the address bar of your browser). Edit the ending of the URL shown there, from <code>system</code> to the<br />
name of the keyspace: <code>netflix</code></p>
<p>✅  <strong>Step 4b:</strong> Repeat the insertion of the <code>x-cassandra-token</code> header for this playground tab (as you did for the first one):</p>
<details>
<summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/graphql-playground-2.png" alt="image" /></p>
</details>
<p>✅  <strong>Step 4c:</strong> In the GraphQL Playground, run the mutation that writes genre data:</p>
<p>Copy the following mutation on the left panel:</p>
<pre lang="yaml"><code>mutation insertGenres {
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
  classic: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Classic&quot;}) {
     value{value}
  } 
  comedies: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Comedies&quot;}) {
     value{value}
  }
  crime: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Crime&quot;}) {
     value{value}
  } 
  cult: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Cult&quot;}) {
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
  international: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;International&quot;}) {
     value{value}
  } 
  italian: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Italian&quot;}) {
     value{value}
  } 
  musicmusicals: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Music &amp; Musicals&quot;}) {
     value{value}
  } 
  realitytv: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;Reality TV&quot;}) {
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
  tvshow: insertreference_list(value: {label:&quot;genre&quot;, value:&quot;TV Show&quot;}) {
     value{value}
  } 
}
</code></pre>
<p>then click on the big &quot;play button&quot; arrow in the center to execute the mutation</p>
<h2><a class="anchor" aria-hidden="true" id="5-retrieve-genres-with-graphql"> </a>5. Retrieve genres with GraphQL</h2>
<p>✅  <strong>Step 5a:</strong> In GraphQL Playground, not changing playground tab (stay on the second: &quot;graphql&quot;, yeah) run the following query to read the <code>value</code> column of all table rows:</p>
<pre lang="yaml"><code>query getAllGenres {
    reference_list (value: {label:&quot;genre&quot;}) {
      values {
      	value
      }
    }
}
</code></pre>
<details>
<summary>
Show me!
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/graphql-playground-3.png" alt="image" /></p>
</details>
<h2><a class="anchor" aria-hidden="true" id="6-create-a-table-for-movies"> </a>6. Create a table for movies</h2>
<p>✅  <strong>Step 6a:</strong> Switch back to first playground tab (&quot;graphql-schema&quot;; the token header will be already set).</p>
<details>
<summary>
Click for screenshot
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/graphql-back.png" alt="image" /></p>
</details>
<p>Use the following mutation to create a new table:</p>
<pre lang="yaml"><code>mutation createMoviesTable {
  movies_by_genre: createTable(
    keyspaceName:&quot;netflix&quot;,
    tableName:&quot;movies_by_genre&quot;,
    ifNotExists: true,
    partitionKeys: [
      { name: &quot;genre&quot;, type: {basic: TEXT} }
    ]
    clusteringKeys: [ 
      { name: &quot;year&quot;, type: {basic: INT}, order: &quot;DESC&quot; },
      { name: &quot;title&quot;, type: {basic: TEXT}, order: &quot;ASC&quot; }
    ]
    values: [
      { name: &quot;synopsis&quot;, type: {basic: TEXT} },
      { name: &quot;duration&quot;, type: {basic: INT} },
      { name: &quot;thumbnail&quot;, type: {basic: TEXT} }
    ]
  )
}
</code></pre>
<details>
<summary>
Show me!
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/graphql-playground-4.png" alt="image" /></p>
</details>
<h2><a class="anchor" aria-hidden="true" id="7-insert-a-few-movies"> </a>7. Insert a few movies</h2>
<p>✅  <strong>Step 7a:</strong> Go to playground tab &quot;graphql&quot; again.</p>
<details>
<summary>
Click for screenshot
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/graphql-playground-2.png" alt="image" /></p>
</details>
<p>Use the following mutation to populate the <code>movies_by_genre</code> table with four movies:</p>
<pre lang="yaml"><code>mutation insertMovies {
  inception: insertmovies_by_genre(
    value: { 
      genre:&quot;Sci-Fi&quot;, 
      year:2010,
      title:&quot;Inception&quot;,
      synopsis:&quot;Cobb steals information from his targets by entering their dreams.&quot;,
      duration:121,
      thumbnail:&quot;https://i.imgur.com/RPa4UdO.mp4&quot;}) {
        value{title}
    }
  
  prometheus: insertmovies_by_genre(value: { 
      genre:&quot;Sci-Fi&quot;, 
      year:2012,
      title:&quot;Prometheus&quot;,
      synopsis:&quot;After a clue to mankind's origins is discovered, explorers are sent to the darkest corner of the universe.&quot;,
      duration:134,
      thumbnail:&quot;https://i.imgur.com/L8k6Bau.mp4&quot;}) {
        value{title}
    }
  
  	aliens: insertmovies_by_genre(value: { 
      genre:&quot;Sci-Fi&quot;, 
      year:1986,
      title:&quot;Aliens&quot;,
      synopsis:&quot;Ellen Ripley is sent back to the planet LV-426 to establish contact with a terraforming colony.&quot;,
      duration:134,
      thumbnail:&quot;https://i.imgur.com/QvkrnyZ.mp4&quot;}) {
        value{title}
    }
  
    bladeRunner: insertmovies_by_genre(value: { 
      genre:&quot;Sci-Fi&quot;, 
      year:1982,
      title:&quot;Blade Runner&quot;,
      synopsis:&quot;Young Blade Runner K's discovery of a long-buried secret leads him to track down former Blade Runner Rick Deckard.&quot;,
      duration:145,
      thumbnail:&quot;https://i.imgur.com/xhhvmj1.mp4&quot;}) {
        value{title}
    }
  }
</code></pre>
<details>
<summary>
Show me!
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/graphql-playground-5.png" alt="image" /></p>
</details>
<h2><a class="anchor" aria-hidden="true" id="8-retrieve-movies-pagination"> </a>8. Retrieve movies: Pagination</h2>
<p>✅  <strong>Step 8a:</strong> In GraphQL Playground, not changing playground tab (stay on the second tab, &quot;graphql&quot;, yeah) list values from the table with the following command:</p>
<pre lang="yaml"><code>query getMovieAction {
  movies_by_genre (
      value: {genre:&quot;Sci-Fi&quot;},
      orderBy: [year_DESC]
  ) {
    values {
      year,
      title,
      duration,
      synopsis,
      thumbnail
    }
  }
}
</code></pre>
<details>
<summary>
Show me!
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/graphql-playground-6.png" alt="image" /></p>
</details>
<p>✅ <strong>Step 8b: Enable pagination:</strong> On a small dataset, you can retrieve all values in the table at once; but in general, for performance or network reasons, you'll need pagination. Run a similar query as before, but this time asking for a <em>page size of 2</em>:</p>
<pre lang="yaml"><code>query getMovieActionPag1 {
    movies_by_genre (
        value: {genre:&quot;Sci-Fi&quot;},
        options: {pageSize: 2},
        orderBy: [year_DESC]
    ) {
      values {
        year,
        title,
        duration,
        synopsis,
        thumbnail
      }
    pageState
    }
}
</code></pre>
<details>
<summary>
Show me!
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/playground-2.png" alt="image" /></p>
</details>
<p>✅ <strong>Step 8c: Fetch the next page:</strong></p>
<p>Notice that <code>pageState</code> now is also returned. Use it to fetch the next 2 items (next page):<br />
edit the next query to replace <code>YOUR_PAGE_STATE</code> with your own string value:</p>
<pre lang="yaml"><code>query getMovieActionNextPage {
    movies_by_genre (
        value: {genre:&quot;Sci-Fi&quot;},
        options: {pageSize: 2, pageState: &quot;YOUR_PAGE_STATE&quot;},
        orderBy: [year_DESC]
    ) {
      values {
        year,
        title,
        duration,
        synopsis,
        thumbnail
      }
    pageState
    }
}
</code></pre>
<details>
<summary>
Show me!
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/playground-3.png" alt="image" /></p>
</details>
<p>If you try to paste the <em>newly-obtained</em> value for <code>pageState</code> and re-run the query, you get an empty list and a null <code>pageState</code> in return. D'oh! You had scrolled through all rows already:<br />
<em>this is how pagination signals the end of the full results list.</em></p>
<h1><a class="anchor" aria-hidden="true" id="part-2-build-and-deploy-front-end"> </a>Part 2 - Build and Deploy Front-End</h1>
<h2><a class="anchor" aria-hidden="true" id="1-deploy-skeletal-gui-to-netlify"> </a>1. Deploy skeletal GUI to Netlify</h2>
<p>✅ <strong>Step 1a: Netlify Button:</strong> Click the following button to deploy the skeletal GUI to Netlify. There is no data since there is no database connected to the app (yet); we will connect the database to the app shortly.</p>
<p><strong>Note</strong>: preferrably Ctrl-click for a new tab.</p>
<details>
<summary>
What does the Netlify deploy button do?
</summary>
<p>The Netlify deploy button will:</p>
<ul>
<li>Create a new repository for you on Github (Note: it's an unrelated <em>copy</em>, not a fork)</li>
<li>Create a site on Netlify (and deploy a nonworking build of the app, which lacks the DB connection parameters still)</li>
<li>Link the two together.</li>
</ul>
</details>
<p><a href="https://app.netlify.com/start/deploy?repository=https://github.com/datastaxdevs/workshop-graphql-netflix" target="_blank"><img src="https://www.netlify.com/img/deploy/button.svg" alt="Deploy to Netlify" /></a></p>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/deploy-to-netlify.gif" alt="Netlify button in action" /></p>
</details>
<p>This will take a few minutes:</p>
<ul>
<li>you may have to authenticate through Github in the process;</li>
<li>confirm the repo name and &quot;Save &amp; Deploy&quot; when asked.</li>
</ul>
<p><em>Note: if there is an existing account in Netlify, check the settings to make sure the Netlify account is connected to your Github account.</em></p>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/netlify-connect-01.png" alt="Deploy to Netlify, &quot;connected accounts&quot;" /></p>
</details>
<p>✅ <strong>Step 1b: Check the deploy logs:</strong> Click on <code>Site deploy in progress</code> within the Netlify UI.</p>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/deploy-1.png" alt="Deploy to Netlify, &quot;site deploy in progress&quot;" /></p>
</details>
<p>Then click the top deploy link to see the build process.</p>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/deploy-2.png" alt="Deploy to Netlify, &quot;Production/Building&quot;" /></p>
</details>
<p>✅ <strong>Step 1c: Complete the build:</strong> Wait until the build shows <code>Netlify Build Complete</code>,  <strong>When you see &quot;<em>Pushing to repository...</em>&quot;</strong> you're ready to move on.</p>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/deploy-3b.png" alt="Deploy to Netlify, logs showing build finishing" /></p>
</details>
<p>✅ <strong>Step 1d: Get back to your new site:</strong> Scroll up to the top and click on the site name (it'll be after &quot;<em>[your login]</em>'s Team&quot; next to the Netlify button). Then locate your app's full URL and click to open it.</p>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/deploy-4.png" alt="Deploy to Netlify, site name next to your team's name" /></p>
<p>Clicking on the full URL (something like <code>https://YOUR-SITE-NAME.netlify.app</code>) you will see the skeletal GUI (without the data from the database) in a new tab. Here is where to click:</p>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/deploy-4sitename.png" alt="Deploy to Netlify, access the skeletal GUI" /></p>
<p>and here, finally, your skeletal GUI in its full splendour:</p>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/deploy-4skeletal.png" alt="Netlify site, no data yet (skeletal GUI)" /></p>
</details>
<h2><a class="anchor" aria-hidden="true" id="2-launch-gitpod-from-your-github-repo"> </a>2. Launch Gitpod from YOUR Github repo</h2>
<p>✅ <strong>Step 2a: Jump to YOUR repo:</strong> Click on the <code>GitHub</code> in <code>Deploys from GitHub</code> to get to your new repository on Github.<br />
Scroll to where you were in the README.</p>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/deploy-5.png" alt="Deploy to Netlify, " /></p>
</details>
<blockquote>
<p><strong>Note</strong> At this point, you MUST be reading this README from <strong>YOUR</strong> Github repository.<br />
That is, if the address bar still says <code>https://github.com/datastaxdevs/...</code> please<br />
head over to YOUR copy of the repo before going the Gitpod route!</p>
</blockquote>
<p>✅ <strong>Step 2b: Launch Gitpod:</strong></p>
<p>Use this link to open Gitpod from <strong>YOUR</strong> repository! (<em>Tip: Ctrl-click on the button to open in new tab.</em>)</p>
<p><a href="https://gitpod.io/from-referrer/" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<p><em>Note: the button works on <img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/chrome-logo.svg" height="20"/> Chrome and <img src="images/firefox-logo.svg" height="20"/> Firefox.</em></p>
<details>
<summary>Click to troubleshoot if you have another browser</summary>
<img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/gitpod_trick.png" />
</details>
<p>ℹ️ <em>It may take a few minutes (approx. 3-5) for GitPod to fully initialize.<br />
Please wait until the console in the lower half of Gitpod is responsive.</em></p>
<blockquote>
<p>You may see a dialog about &quot;opening this workspace in VS Code Desktop&quot;: you can safely dismiss it.</p>
</blockquote>
<p>Gitpod will be your IDE from now on. If you are familiar with VSCode, you can probably<br />
just use it. Otherwise, take a moment to review a separate page<br />
<a href="know_your_gitpod.md" target="_blank">&quot;Know your Gitpod&quot;</a><br />
and then come back here.</p>
<h2><a class="anchor" aria-hidden="true" id="3-set-up-and-use-code-astra-cli-code"> </a>3. Set up and use <code>astra-cli</code></h2>
<p>You are going to use a CLI tool to simplify operations with Astra DB. The tool<br />
is <a href="https://docs.datastax.com/en/astra-classic/docs/astra-cli/installation.html" target="_blank">preinstalled</a><br />
on your Gitpod.</p>
<p>✅ <strong>Step 3a: Set up the CLI:</strong></p>
<p>Run the following in the Gitpod terminal and,<br />
when prompted, enter the <code>AstraCS:...</code> you obtained at the beginning.</p>
<pre lang="bash"><code>astra setup
</code></pre>
<details>
<summary>
Show me!
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/astra-cli-setup-2.png" alt="astra-cli" /></p>
</details>
<p>✅ <strong>Step 3b: Bulk data load:</strong> Load a large movie dataset in the database.<br />
This command installs and properly launches the <code>DSBulk</code> tool (<a href="https://docs.datastax.com/en/dsbulk/docs/dsbulkAbout.html" target="_blank">docs</a>):</p>
<pre lang="bash"><code>astra db load workshops \
  -url data/movies_by_genre.csv \
  -k netflix \
  -t movies_by_genre
</code></pre>
<details>
<summary>
Show me!
</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/astra-cli-dsbulk-2.png" alt="astra-cli" /></p>
</details>
<details><summary>Show the syntax for old versions of astra-cli (click here)</summary>
<p>Note: you should not need this.</p>
<pre lang="bash"><code>astra db dsbulk workshops load \
  -url data/movies_by_genre.csv \
  -k netflix \
  -t movies_by_genre
</code></pre>
</details>
<blockquote>
<p><em>Note</em>: we mock the trailers for these thousands of movies by using a handful<br />
of them over and over. Don't be surprised if you'll see the wrong trailers<br />
for your favorite movie!</p>
</blockquote>
<p>That's it! All 6000+ movies are now loaded and ready to go!</p>
<h2><a class="anchor" aria-hidden="true" id="4-serverless-functions"> </a>4. Serverless Functions</h2>
<blockquote>
<p><em>Note</em>: this section and the next one (&quot;Fetching from the Front-End&quot;)<br />
are not steps to &quot;perform&quot;, rather suggestions to dive in the app<br />
code and figure out how the various parts (React components, Netlify<br />
functions and finally the GraphQL server in Astra DB) fit together.<br />
<strong>You can skip these and jump to the <a href="#6-install-the-netlify-cli" target="_blank">next practical step</a></strong><br />
if you are in a hurry, but please come back to these<br />
for reference if you want to dissect the code!</p>
</blockquote>
<details><summary>Show me this section</summary>
<p>Take a look at <code>functions/getGenres.js</code></p>
<pre lang="javascript"><code>const fetch = require('node-fetch')

exports.handler = async function (event) {

  const body = JSON.parse(event.body)
  const url = process.env.ASTRA_DB_GRAPHQL_URL
  const query = `
    query getAllGenres {
      reference_list (
        value: { label: &quot;genre&quot;},
        options: {
          pageSize: ${JSON.stringify(body.pageSize)},
          pageState: ${JSON.stringify(body.pageState)}
        }
      ) {
        values {
          value
        }
        pageState
      }
    }
  `

  const response = await fetch(url, {
    method: 'POST',
    headers: {
      &quot;Content-Type&quot;: &quot;application/json&quot;,
      &quot;x-cassandra-token&quot;: process.env.ASTRA_DB_APPLICATION_TOKEN
    },
    body: JSON.stringify({ query })
  })

  try {
    const responseBody = await response.json()
    return {
      statusCode: 200,
      body: JSON.stringify(responseBody)
    }
  } catch (e) {
    console.log(e)
    return {
      statusCode: 500,
      body: JSON.stringify(e)
    }
  }
}
</code></pre>
<p>You'll notice the familiar GraphQL query &quot;getAllGenres&quot; you used previously in the playground.<br />
It's been modified a bit to utilize pagination.<br />
When building the GraphQL query, you pass the desired page size and state to the GraphQL API:</p>
<pre lang="javascript"><code>options: {
  pageSize: ${JSON.stringify(body.pageSize)},
  pageState: ${JSON.stringify(body.pageState)}
}
</code></pre>
<p>You ask the API server to give us back the table column &quot;value&quot; (containing the genre name), but also the page state<br />
for when you'll need the next page:</p>
<pre lang="javascript"><code>{
  values {
    value
  }
  pageState
}
</code></pre>
<p>The serverless function <code>functions/getMovies.js</code> works in much the same way, but you provide the specific genre you want and the page size is hardcoded:</p>
<pre lang="javascript"><code>query {
  movies_by_genre (
    value: { genre: ${JSON.stringify(genre)}},
    orderBy: [year_DESC],
    options: { pageSize: 6, pageState: ${JSON.stringify(pageState)} }
  ) {
    values {
      year,
      title,
      duration,
      synopsis,
      thumbnail
    }
    pageState
  }
}
</code></pre>
</details>
<h2><a class="anchor" aria-hidden="true" id="5-fetching-from-the-front-end"> </a>5. Fetching from the Front-End</h2>
<details><summary>Show me this section</summary>
<p>Take a look at how you fetch from these serverless functions from the front-end. Start in <code>src/App.js</code></p>
<p>There is a fetch method defined, that will retrieve a page of genres by calling the <code>getGenres</code> serverless function.</p>
<pre lang="javascript"><code>const fetchData = async () =&gt; {
  if (! isFetching)  {
    setIsFetching(true)
    const response = await fetch(&quot;/.netlify/functions/getGenres&quot;, {
      method: &quot;POST&quot;,
      body: JSON.stringify({pageState, pageSize}),
    })
    const responseBody = await response.json()
    setPageState(responseBody.data.reference_list.pageState)
    setGenres(gs =&gt; (gs || []).concat(responseBody.data.reference_list.values))
    setIsFetching(false)
  }
}
</code></pre>
<p>You pass in the current <code>pageState</code> and <code>pageSize</code> state variables and receive a response from the serverless function. You then set the <code>pageState</code> var to the new pagestate, and set the <code>genres</code> state variable to the received data. (Note that you are concatenating the new data to the var, since you want to keep all previously fetched data, not replace).</p>
<p>When rendering the page, you generate a <code>&lt;Section&gt;</code> component for each genre, plus a <code>&lt;div&gt;</code> at the bottom, which will detect a <code>mouseEnter</code> event and trigger the loading of a new pageful of genres:</p>
<pre lang="javascript"><code>&lt;&gt;
  &lt;NavBar /&gt;
  &lt;HeroSection /&gt;
  {genres &amp;&amp; (
    &lt;div className=&quot;container&quot;&gt;
      {Object.values(genres).map((genre) =&gt; (
        &lt;Section key={genre.value} genre={genre.value} /&gt;
      ))}
    &lt;/div&gt;
  )}
  &lt;div
    className=&quot;page-end&quot;
    onMouseEnter={() =&gt; {
      setRequestedPage( np =&gt; np + 1 )
    }}
  /&gt;
&lt;/&gt;
</code></pre>
<p>The <code>&lt;Section&gt;</code> component works in the same way, but you will fully replace the data in the <code>movies</code> variable this time.</p>
<pre lang="javascript"><code>const fetchData = async () =&gt; {
  const response = await fetch(&quot;/.netlify/functions/getMovies&quot;, {
    method: &quot;POST&quot;,
    body: JSON.stringify({ genre: genre, pageState: pageState }),
  })
  const responseBody = await response.json()
  setMovies(responseBody.data.movies_by_genre.values)
  setPageState(responseBody.data.movies_by_genre.pageState)
}
</code></pre>
<p>Now that you know how the front-end works, launch the app!</p>
</details>
<h2><a class="anchor" aria-hidden="true" id="6-install-the-netlify-cli"> </a>6. Install the Netlify CLI</h2>
<p>In the <code>workshop-graphql-netflix</code> directory, run the following:</p>
<pre><code>npm install -g netlify-cli
</code></pre>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/netlify-install-cli.png" alt="Install Netlify CLI" /></p>
</details>
<p>With the Netlify command-line interface you will build and deploy<br />
the application directly from the Gitpod terminal.</p>
<h2><a class="anchor" aria-hidden="true" id="7-provide-db-connection-parameters"> </a>7. Provide DB connection parameters</h2>
<p>The &quot;serverless functions&quot; part of your app, in order to speak to<br />
your DB through GraphQL, needs two important pieces of information:<br />
the API endpoint and the token. You will now create a <code>.env</code> file which<br />
defines them as environment variables.</p>
<p>The quickest way is to have <code>astra-cli</code> generate one for you:</p>
<pre><code>astra db create-dotenv -k netflix workshops
</code></pre>
<details><summary>I want to do it manually</summary>
<p>If for some reason you don't use <code>astra-cli</code>, follow these steps:</p>
<ul>
<li>copy <code>cp .env.sample .env</code> and open it: <code>gp open .env</code>;</li>
<li><code>.env</code> is now open in the IDE editor and has two placeholders to replace:</li>
<li>insert the <code>AstraCS:...</code> database token (keep the quotes);</li>
<li>insert the GraphQL API address (it will look something like <code>https://b2f[...]/graphql/netflix</code>).</li>
</ul>
<p>You can generate a new database token if you want. The GraphQL address<br />
can be found in the playground: it is the URL you have edited to end in <code>netflix</code><br />
in the second playground tab (<a href="#4-insert-genre-data-with-graphql" target="_blank">Part 1, step 4a</a>).</p>
</details>
<h2><a class="anchor" aria-hidden="true" id="8-run-the-app-in-dev-mode"> </a>8. Run the app in dev mode</h2>
<p>✅ <strong>Step 8a: Install dependencies:</strong></p>
<pre lang="bash"><code>npm install
</code></pre>
<p>✅ <strong>Step 8b: Start the app:</strong> With the command</p>
<pre><code>netlify dev
</code></pre>
<p>the application should automatically be displayed in GitPod's &quot;simple browser&quot;.<br />
Note that in this <strong>dev-mode run</strong> everything is local to your Gitpod instance:<br />
<em>the &quot;serverless functions&quot;, in particular, are actually running there,<br />
alongside the rest of the application!</em></p>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/preview.png" alt="run-in-preview-pane" /></p>
</details>
<p>You can copy the URL found in Gitpod's simple browser and open in a new tab<br />
(of your real browser, that is) for a<br />
better experience. But now it's time to move to the actual deploy phase.</p>
<h2><a class="anchor" aria-hidden="true" id="9-connect-to-your-netlify-site"> </a>9. Connect to your Netlify site</h2>
<p>✅ <strong>Step 9a:</strong> Stop the dev run with <code>Ctrl-C</code>.</p>
<p>✅ <strong>Step 9b:</strong> Authenticate with Netlify: run</p>
<pre><code>netlify login
</code></pre>
<p>then grab the URL printed on the console<br />
(something like <code>https://app.netlify.com/authorize?response[...]</code>)<br />
and manually <strong>open it in a new tab</strong> (Gitpod blocks it for security).<br />
You will be asked to authorize &quot;netlify-cli&quot; to access your Netlify account<br />
in the process.</p>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/waiting_for_authorization-2.png" alt="Netlify login" /></p>
</details>
<p>Once you complete the login, you will see a console output like this:</p>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/netlify-login-2.png" alt="Netlify login" /></p>
<p>✅ <strong>Step 9c:</strong> Associate to your Netlify site: run</p>
<pre><code>netlify link
</code></pre>
<p>and make sure you confirm the choice of associating to<br />
&quot;current git remote origin&quot;.</p>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/netlify-link-2.png" alt="Netlify link" /></p>
</details>
<h2><a class="anchor" aria-hidden="true" id="10-deploy-in-production"> </a>10. Deploy in production!</h2>
<p>✅ <strong>Step 10a:</strong> Inject secrets to the Netlify site</p>
<pre><code>netlify env:import .env
</code></pre>
<p>Now the (actually) serverless functions in Netlify have the connection<br />
parameters they need.</p>
<details><summary>Show me!</summary>
<p><em>Note: If you generated the <code>.env</code> with<br />
<code>astra-cli</code>, the actual output is much more verbose.</em></p>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/netlify_env_import.png" alt="image" /></p>
</details>
<p>✅ <strong>Step 10b:</strong> Build the app</p>
<p>Run</p>
<pre><code>netlify build
</code></pre>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/netlify-build.png" alt="Netlify build" /></p>
</details>
<p>✅ <strong>Step 10c:</strong> Deploy!</p>
<pre><code>netlify deploy --prod
</code></pre>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/netlify-deploy-prod-2.png" alt="Netlify deploy in prod" /></p>
</details>
<p>✅ <strong>Step 10d:</strong> Visit your site.</p>
<pre><code>netlify open:site
</code></pre>
<details><summary>Show me!</summary>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/netlify-open-site-2.png" alt="Netlify Open site" /></p>
</details>
<p>If needed, manually copy-paste your site URL in a new browser tab... and enjoy<br />
your work!</p>
<p><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/deployed_netflix_clone.png" alt="Netlify Setup Example" /></p>
<h2><a class="anchor" aria-hidden="true" id="the-end"> </a>The END</h2>
<p>Congratulations, you made it!</p>
<p>Now don't forget to complete your assignment and <a href="#homework" target="_blank">submit it</a><br />
to get your badge of completion!</p>
<pre><code>       ██╗    ██╗███████╗██╗     ██╗          
       ██║    ██║██╔════╝██║     ██║          
       ██║ █╗ ██║█████╗  ██║     ██║          
       ██║███╗██║██╔══╝  ██║     ██║          
       ╚███╔███╔╝███████╗███████╗███████╗     
        ╚══╝╚══╝ ╚══════╝╚══════╝╚══════╝     
                                              
       ██████╗  ██████╗ ███╗   ██╗███████╗██╗ 
       ██╔══██╗██╔═══██╗████╗  ██║██╔════╝██║ 
       ██║  ██║██║   ██║██╔██╗ ██║█████╗  ██║ 
       ██║  ██║██║   ██║██║╚██╗██║██╔══╝  ╚═╝ 
       ██████╔╝╚██████╔╝██║ ╚████║███████╗██╗ 
       ╚═════╝  ╚═════╝ ╚═╝  ╚═══╝╚══════╝╚═╝ 
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h2>
<img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/images/netflix-badge.png?raw=true" width="200" align="right" />
<p>🎓 Complete your upgrade and get your verified skill badge! Do the assignment and submit your homework!</p>
<ol>
<li>Complete the practice steps from this repository as described below.</li>
<li>Insert a movie OR genre of your choice in the database (It's OK to re-use the trailer file URL from another movie! Just make the title recognizable as yours).</li>
<li>Take a screenshot of your Netflix clone running either from your Gitpod or (better) deployed to production in Netlify (in this case, you could also give us the Netlify URL).</li>
<li>The screenshot should clearly show the movie/genre you added (make sure you tell us its name when submitting).</li>
<li>(Optional for extra wisdom) Watch the 2-hour video by Ania <a href="#video-tutorial-with-ania-kubow" target="_blank">HERE</a>, build the app yourself, and show us the running final result.</li>
<li>Submit your homework <a href="https://dtsx.io/homework-graphql-netflix" target="_blank">here</a>.</li>
</ol>
<p>That's it, you are done: expect an email in the next days!</p>
<h1><a class="anchor" aria-hidden="true" id="extra-resources"> </a>Extra resources</h1>
<h2><a class="anchor" aria-hidden="true" id="video-tutorial-with-ania-kubow"> </a>Video tutorial with Ania Kubow</h2>
<p>Thank you to our wonderful friend Ania Kubow for producing the Netflix clone. If you are not aware of Ania and love learning about coding you should absolutely check out her YouTube channel listed below.</p>
<p>While we focused on getting you up and running to production with Astra DB and Netlify, Ania's video will dig into more details on the app itself. Check it out to dig in more.</p>
<p><a href="https://www.youtube.com/watch?v=g8COh40v2jU" target="_blank">Ania's Netflix Video</a></p>

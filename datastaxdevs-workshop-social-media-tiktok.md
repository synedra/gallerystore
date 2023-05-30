<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="astra-db-tiktok-clone-workshop"> </a>Astra DB TikTok Clone Workshop</h1>
<p><a href="https://gitpod.io/#https://github.com/DataStax-Academy/workshop-spring-data-cassandra" target="_blank"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod" alt="Gitpod ready-to-code" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p><em>50 minutes, Intermediate, <a href="#running-astra-tik-tok" target="_blank">Start Building</a></em></p>
<p>A simple Tik-Tok clone running on Astra DB that leverages the Document API.</p>
<!--- ENDEXCLUDE --->
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./screenshot.jpg" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>Deploy a TikTok clone &quot;locally&quot; and to production</li>
<li>Learn how to use the @astrajs document API to quickly and easily interact with JSON documents</li>
<li>Leverage Netlify and DataStax AstraDB</li>
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
<li>You will also need Netlify and Astra DB accounts, but we'll work through that in the exercises</li>
<li>Use <strong>Chrome</strong> or <strong>Firefox</strong> for the best experience. Other browsers are great, but don't work well with the GitPod integration we use a bit later.</li>
</ul>
</blockquote>
<ul>
<li><em>Do I need to pay for anything for this workshop?</em></li>
</ul>
<blockquote>
<ul>
<li>No. All tools and services we provide here are FREE.</li>
</ul>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="./slides/slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://bit.ly/cassandra-workshop" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h2>
<img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/tiktok-badge.png?raw=true" width="200" align="right" />
<p>Don't forget to complete your upgrade and get your verified skill badge! Finish and submit your homework!</p>
<ol>
<li>Complete the practice steps from this repository as described below. Take a screenshot and show us your deployed production TikTok clone up in Netlify.</li>
<li>(Optional extra credit) Watch the 2 hour Ania video <a href="#video-tutorial-with-ania-kubow" target="_blank">HERE</a>, build the app yourself, and show us the completed app.</li>
<li>Submit your homework <a href="https://docs.google.com/forms/d/1BV5qJstc2Z8CV4XamolOLe5UjuDFoIunbMgpi4_iiys" target="_blank">here</a></li>
</ol>
<p>That's it, you are done! Expect an email next week!</p>
<h1><a class="anchor" aria-hidden="true" id="let-s-start"> </a>Let's start</h1>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>Table of contents</h2>
<h3><a class="anchor" aria-hidden="true" id="part-i-run-and-deploy"> </a>Part I - Run and Deploy</h3>
<ol>
<li><a href="#1-login-or-register-to-astra-db-and-create-database" target="_blank">Create Astra DB Instance</a></li>
<li><a href="#2-deploy-to-netlify" target="_blank">Deploy to Netlify</a></li>
<li><a href="#3-access-your-github-repository" target="_blank">Access YOUR GitHub repository</a></li>
<li><a href="#4-launch-gitpod-ide" target="_blank">Launch GitPod</a></li>
<li><a href="#5-install-the-netlify-cli-command-line-interface" target="_blank">Install the Netlify CLI</a></li>
<li><a href="#6-generate-application-token-to-securely-connect-to-the-database" target="_blank">Generate application token to securely connect to the database</a></li>
<li><a href="#7-configure-and-connect-database" target="_blank">Configure and connect database</a></li>
<li><a href="#8-launch-your-app" target="_blank">Launch your app</a></li>
<li><a href="#9-connect-netlify-to-your-site" target="_blank">Connect Netlify to your site</a></li>
<li><a href="#10-deploy-to-production" target="_blank">Deploy to production</a></li>
</ol>
<h3><a class="anchor" aria-hidden="true" id="part-2-working-with-astra-db-and-the-document-api"> </a>Part 2 - Working with Astra DB and the document API</h3>
<ol start="11">
<li><a href="#11-connecting-the-database" target="_blank">Connecting the Database</a></li>
</ol>
<h3><a class="anchor" aria-hidden="true" id="part-3-serverless-functions-how-they-work"> </a>Part 3 - Serverless Functions, how they work</h3>
<ol start="12">
<li><a href="#12-create" target="_blank">Create</a></li>
<li><a href="#13-update" target="_blank">Update</a></li>
<li><a href="#14-find" target="_blank">Find</a></li>
<li><a href="#15-serverless-configuration" target="_blank">Serverless configuration</a></li>
</ol>
<h3><a class="anchor" aria-hidden="true" id="extra-resources"> </a>Extra resources</h3>
<p><a href="jamstack.md" target="_blank">What is JamStack?</a></p>
<p><a href="#video-tutorial-with-ania-kubow" target="_blank">Video tutorial with Ania Kubow</a></p>
<h1><a class="anchor" aria-hidden="true" id="part-1-run-and-deploy"> </a>Part 1 - Run and Deploy</h1>
<h3><a class="anchor" aria-hidden="true" id="1-login-or-register-to-astra-db-and-create-database"> </a>1. Login or Register to Astra DB and create database</h3>
<p>Click the button to login or register with Datastax</p>
<p><a href="https://astra.dev/11-10" target="_blank"><img src="tutorial/images/create_astra_db.png?raw=true" /></a></p>
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
<td><code>workshops</code></td>
</tr>
<tr>
<td><strong>keyspace</strong></td>
<td><code>tiktok_keyspace</code></td>
</tr>
<tr>
<td><strong>Cloud Provider</strong></td>
<td><em>Use the one you like, click a cloud provider logo,  pick an Area in the list and finally pick a region.</em></td>
</tr>
</tbody>
</table>
<h3><a class="anchor" aria-hidden="true" id="2-deploy-to-netlify"> </a>2. Deploy to Netlify</h3>
<ul>
<li>
<details><summary> What does the netlify deploy button do?</summary>The Netlify deploy button will:<ul>
  <li>Create a new repository for you on Github</li>
  <li>Create a site on Netlify</li>
  <li>Link the two together.</li></ul>
</li>
</ul>
</details>
<ul>
<li>
<p>Click the button to deploy</p>
<p><a href="https://app.netlify.com/start/deploy?repository=https://github.com/datastaxdevs/workshop-astra-tik-tok" target="_blank"><img src="https://www.netlify.com/img/deploy/button.svg" alt="Deploy to Netlify" /></a></p>
</li>
</ul>
<ul>
<li>
<details><summary>Show me!</summary>
 <img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/deploy-to-netlify.gif?raw=true" />
 </details>
</li>
</ul>
<p>This will take a few minutes.</p>
<ul>
<li>
<p>Click on <code>Site deploy in progress</code> within the Netlify UI,</p>
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/deploy-1.png" />
</details>
</li>
<li>
<p>Click the top deploy link to see the build process.</p>
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/deploy-2.png" />
</details>
</li>
<li>
<p>Wait until the build complete <code>Netlify Build Complete</code>,  <strong>When you see Pushing to repository</strong> you're ready to move on.</p>
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/deploy-3.png" />
</details>
</li>
<li>
<p>Scroll up to the top and click on the site name (it'll be after {yourlogin}'s Team next to the Netlify button).</p>
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/deploy-4.png" />
</details>
</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="3-access-your-github-repository"> </a>3. Access YOUR GitHub repository</h3>
<ul>
<li>Click on the <code>GitHub</code> in <code>Deploys from GitHub</code> to get back to your new repository.  Scroll to where you were in the README.
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/deploy-5.png" />
</details>
</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="4-launch-gitpod-ide"> </a>4. Launch GitPod IDE</h3>
<ul>
<li>Click the button to launch the GitPod IDE from <strong>YOUR</strong> repository.</li>
</ul>
<ul>
<li><em>Supported by <img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/chrome-logo.svg" height="20"/> Chrome and <img src="tutorial/images/firefox-logo.svg" height="20"/> Firefox</em></li>
</ul>
<h4><a class="anchor" aria-hidden="true" id="wait-before-moving-on-ensure-you-are-working-out-of-your-repository-not-the-datastaxdevs-repository"> </a>WAIT! Before moving on ensure you are working out of YOUR repository, not the datastaxdevs repository.</h4>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/correct-not-correct.png?raw=true" alt="correct notcorrect" /></p>
<p>If you are still using the <code>datastaxdevs</code> repo please ensure to follow the previous step, <a href="#3-clone-your-github-repository" target="_blank">step3</a> to get to your repo.</p>
<ul>
<li>
<p>Ok, I've got it, just give me the button already</p>
</li>
<li>
<details>
  <summary>CLICK HERE to launch GitPod</summary>
<p><a href="https://gitpod.io/from-referrer/" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
</details>
</li>
</ul>
<h4><a class="anchor" aria-hidden="true" id="wait-before-moving-on-ensure-you-are-working-out-of-your-repository-not-the-datastaxdevs-repository"> </a>WAIT! Before moving on ensure you are working out of YOUR repository, not the datastaxdevs repository.</h4>
<ul>
<li>From your GitPod terminal execute the following command</li>
</ul>
<pre><code>git remote -v
</code></pre>
<p>If the result returned from the command displays <strong><code>datastaxdevs</code></strong> then you are not in the correct repository. If this is the case please <a href="#3-access-your-github-repository" target="_blank">repeat step 3 above</a>, otherwise just move on to the next step.</p>
<h3><a class="anchor" aria-hidden="true" id="5-install-the-netlify-cli-command-line-interface"> </a>5. Install the Netlify CLI (Command Line Interface)</h3>
<ul>
<li>In the <code>workshop-astra-tik-tok</code> directory run the following command to install the netlify-cli</li>
</ul>
<pre><code>npm install -g netlify-cli
</code></pre>
<ul>
<li>
<details><summary>Show me!</summary>
 <img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/netlify-install-cli.png?raw=true" />
 </details>
</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="6-generate-application-token-to-securely-connect-to-the-database"> </a>6. Generate application token to securely connect to the database</h3>
<p>Following the <a href="https://docs.datastax.com/en/astra/docs/manage-application-tokens.html" target="_blank">Documentation</a> create a token with <code>Database Admnistrator</code> roles.</p>
<ul>
<li>
<p>Go the <code>Organization Settings</code></p>
</li>
<li>
<p>Go to <code>Token Management</code></p>
</li>
<li>
<p>Pick the role <code>Database Admnistrator</code> on the select box</p>
</li>
<li>
<p>Click Generate token</p>
</li>
</ul>
<ul>
<li>
<details><summary>Show me!</summary>
 <img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/astra-create-token.gif?raw=true" />
 </details>
</li>
</ul>
<p>This is what the token page looks like.</p>
<ul>
<li>Click the <strong><code>Download CSV</code></strong> button. You are going to need these values here in a moment.</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/tutorial/images/astra-token.png?raw=true" alt="image" /></p>
<p>Notice the clipboard icon at the end of each value.</p>
<ul>
<li>
<p><code>Client ID:</code> We will <em>not</em> use this during this workshop</p>
</li>
<li>
<p><code>Client Secret:</code> We will <em>not</em> use this during this workshop</p>
</li>
<li>
<p><code>Token:</code> <em>This is your token!</em> We will use it as a api Key to interact with APIS</p>
</li>
</ul>
<p><a href="https://www.youtube.com/watch?v=TUTCLsBuUd4" target="_blank">This video</a> describes the procedure to generate a token in Astra DB.</p>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token 
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="7-configure-and-connect-database"> </a>7. Configure and connect database</h3>
<ul>
<li>In the repository directory run the following command to set up your Astra DB environment. This will verify the database you created earlier or create a new one for you if it can't find your database.</li>
</ul>
<pre><code>npm exec astra-setup workshops tiktok_keyspace
</code></pre>
<details>
<summary>What does astra-setup do?</summary>
    To setup your ASTRA instance, you want to run `npm exec astra-setup`
<pre><code>This will do the following:
* Have you go to your [Astra DB instance](https://datastx.io/workshops) to register or login. There is no credit card required to sign up. The 'Pay as you go' option gives you a huge amount of transactions for free:
    * 30 million reads
    * 5 million writes
    * 40 gigabytes of storage
* Give steps to grab a Database Administrator Token and paste it into the input field
* Ask you what database you want to use (default, existing, create)
* Create or access the database
* Create/update an .env file in the project root
* Create/update an .astrarc file in your home directory
    * This can be used by httpie-astra `pip3 install httpie-astra`
    * It can also be used by the @astra/collections and @astra/rest node modules

## Specify the database and keyspace
You can run the script and tell it which database/keyspace to use by using:
`npm exec astra-setup databasename keyspacename`
</code></pre>
</details>
<h3><a class="anchor" aria-hidden="true" id="8-launch-your-app"> </a>8. Launch your app</h3>
<ul>
<li>Run the application</li>
</ul>
<pre><code>netlify dev
</code></pre>
<ul>
<li>The application should automatically launch in the GitPod preview pane</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="9-connect-netlify-to-your-site"> </a>9. Connect Netlify to your site</h3>
<p>Execute each of the commands below to link your code to your Netlify deployment.</p>
<ul>
<li>First thing, we'll need to <strong>STOP</strong> the <code>netlify dev</code> command we issued a moment ago. In the terminal where you executed the netlify command issue a <code>CTRL-C</code> (control key + the C key) in order to stop the process.</li>
<li>Then continue with the following commands</li>
<li>This will pop up a browser to authenticate with netlify</li>
</ul>
<pre><code>netlify login
</code></pre>
<p><em>Note, when using GitPod the preview pane will not display this properly. You must click the &quot;open in a new window&quot; button in the very top right of the preview pane.</em></p>
<ul>
<li>This will link your workspace to the associated site</li>
</ul>
<pre><code>netlify link
</code></pre>
<ul>
<li>This will take the .env file created by astra-setup and upload it to netlify</li>
</ul>
<pre><code>netlify env:import .env
</code></pre>
<!--
  * Will be used to allow you to execute `netlify open`
  ```
  netlify sites:list
  ```
-->
<h3><a class="anchor" aria-hidden="true" id="10-deploy-to-production"> </a>10. Deploy to production</h3>
<p>Now that you've hooked everything up, time to deploy to production.</p>
<ul>
<li>Run</li>
</ul>
<pre><code>netlify build
</code></pre>
<ul>
<li>Then run</li>
</ul>
<pre><code>netlify deploy --prod
</code></pre>
<ul>
<li>Then finally run</li>
</ul>
<pre><code>netlify open:site
</code></pre>
<p>You've deployed your app to Netlify!<br />
<img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/netlify-livesite.png?raw=true" alt="Netlify Setup Example" /></p>
<h1><a class="anchor" aria-hidden="true" id="part-2-working-with-astradb-and-the-document-api"> </a>Part 2 - Working with AstraDB and the document API</h1>
<h3><a class="anchor" aria-hidden="true" id="11-connecting-the-database"> </a>11. Connecting the Database</h3>
<p>Let's briefly dive into the connection between our serverless functions and our Astra DB.<br />
We are using the <code>@astrajs/collections</code> library to make the connection using the Document API provided by Stargate. To do so, we start by creating a 'client'.</p>
<p>(See: <code>functions/utils/astraClient.js</code>)</p>
<pre lang="javascript"><code>const { createClient } = require(&quot;@astrajs/collections&quot;);

let astraClient = null;

const getAstraClient = async () =&gt; {
  if (astraClient === null) {
    astraClient = await createClient(
      {
        astraDatabaseId: process.env.ASTRA_DB_ID,
        astraDatabaseRegion: process.env.ASTRA_DB_REGION,
        applicationToken: process.env.ASTRA_DB_APPLICATION_TOKEN,
      },
      30000
    );
  }
  return astraClient;
};
</code></pre>
<p>Here we are defining a new method called <code>getAstraClient</code> that uses the <code>createClient</code> method from our <code>astrajs</code> library to create a connection to our database. We then provide it the needed database credentials we added to our environment varaiables earlier;</p>
<ul>
<li><code>ASTRA_DB_ID</code></li>
<li><code>ASTRA_DB_REGION</code></li>
<li><code>ASTRA_DB_APPLICATION_TOKEN</code></li>
</ul>
<p>Then we return the <code>astraClient</code> we can then use in our API calls.</p>
<p>We also need to create a document collection to store our data.</p>
<pre lang="javascript"><code>const getCollection = async () =&gt; {
  const documentClient = await getAstraClient();
  return documentClient
    .namespace(process.env.ASTRA_DB_KEYSPACE)
    .collection(&quot;tktkposts&quot;);
};
</code></pre>
<p>In this method, we are using our previously created <code>getAstraClient</code> method to initialize the database connection, and then create a collection in the keyspace we defined in our environment variables;</p>
<ul>
<li><code>ASTRA_DB_KEYSPACE</code></li>
</ul>
<p>We will call the collection &quot;<strong>tktkposts</strong>&quot;.</p>
<p>So now, any time we want to perform operations on our data, we will reference this method <code>getCollection</code>, and use the Document API from Stargate to do so.</p>
<p>✅ Now that we have locally deployed our TikTok app, let's take a look at this in our database. Head to your <a href="astra.datastax.com" target="_blank">Astra DB dashboard</a> and click the <code>Connect</code> button next to your database ('workshops').</p>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/db_connect.png?raw=true" alt="db_connect" /></p>
<p>✅ Then scroll down to the section called 'Launching SwaggerUI' and click the link. We'll be using SwaggerUI to make api calls to our database and see the results.</p>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/swaggerui_link.png?raw=true" alt="swaggerui_link" /></p>
<p>✅ Open up the first section labelled &quot;List collections in namespace&quot; and click the button &quot;Try it out&quot;.</p>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/swaggerui_listcollections_02.png?raw=true" alt="swaggerui_link" /></p>
<p>✅ We need to provide our Application Token, and our keyspace name. Fortunately we have these already saved in our environment variables in the <code>.env</code> file. Go ahead and copy those over, then click 'Execute'.</p>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/swaggerui_listcollections_03.png?raw=true" alt="swaggerui_link" /></p>
<p>And there we go, we see that a collection has been made in our database called &quot;<strong>tktkposts</strong>&quot;</p>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/swaggerui_listcollections_04.png?raw=true" alt="swaggerui_link" /></p>
<br/>
<h2><a class="anchor" aria-hidden="true" id="document-api"> </a>Document API</h2>
<p>For our TikTok app, we will not be dealing with the Document API directly. Instead <code>@astrajs/collections</code> does that for us, and provides us with easy to use methods.</p>
<p>If you want a comprehensive list of the capabilities of <code>@astrajs/collections</code>, check out this documentation: <a href="https://docs.datastax.com/en/astra/docs/astra-collection-client.html" target="_blank">AstraJS Collections</a></p>
<p>For now, let's go over the 3 methods we'll be using in this app:</p>
<ul>
<li><code>create</code></li>
<li><code>update</code></li>
<li><code>find</code></li>
</ul>
<br/>
<h3><a class="anchor" aria-hidden="true" id="12-create"> </a>12. Create</h3>
<p>The <code>create</code> method is used when we want to add documents to our collection. For example, in <strong><code>functions/add.js</code></strong> we get our collection from the database using our <code>getCollection</code> method.</p>
<pre lang="javascript"><code>const users = await getCollection();
</code></pre>
<p>Then we use the <code>create</code> method to create a document, providing the <em>id</em> and <em>body</em> of the document.</p>
<pre lang="javascript"><code>try {
    const user = await users.create(id, event.body);
    return {
      statusCode: 200,
      body: JSON.stringify(user),
    };
}
</code></pre>
<br/>
<h3><a class="anchor" aria-hidden="true" id="13-update"> </a>13. Update</h3>
<p>The <code>update</code> method is used to update portions of existing documents. Take a look at <strong><code>functions/edit.js</code></strong>. Again we use <code>getCollection()</code> to get our collection from the database, then we use the <code>update</code> method, provide it with an id for the document we want to edit, and the data that needs updating.</p>
<pre lang="javascript"><code>try {
    users.update(body.userId, body.data);
    return {
      statusCode: 200,
    };
  }
</code></pre>
<br/>
<h3><a class="anchor" aria-hidden="true" id="14-find"> </a>14. Find</h3>
<p>And finally the <code>find</code> method is used to retrieve documents. In <strong><code>functions/posts.js</code></strong> we are again using <code>getCollections()</code> and using the <code>find</code> method on the result.</p>
<pre lang="javascript"><code>try {
    const res = await users.find({});
    return {
      statusCode: 200,
      body: JSON.stringify(Object.keys(res).map((i) =&gt; res[i])),
    };
  }
</code></pre>
<p>In this case, we are passing an empty object to retrieve all documents. In a real-world scenario, we would pass a qualifier to get only the documents relevant to a specific user.</p>
<p>Let's go back to SwaggerUI and give this a test.</p>
<p>✅ Back in SwaggerUI, open up the section labelled &quot;Search documents in a collection&quot;.</p>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/swaggerui_searchdocuments_02.png?raw=true" alt="swaggerui_link" /></p>
<p>✅ Again, we have to provide the Application Token, keyspace name, and this time we will also include the collection id: <strong><code>tktkposts</code></strong>. We should also increase the page size as the tool defaults to only returning 1 document, and we will be retrieving many. Go ahead and fill those fields and click 'Execute'.</p>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/swaggerui_searchdocuments_03.png?raw=true" alt="swaggerui_link" /></p>
<p>And we see all of the documents stored in our database.</p>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/swaggerui_searchdocuments_04.png?raw=true" alt="swaggerui_link" /></p>
<h1><a class="anchor" aria-hidden="true" id="part-3-serverless-functions-how-they-work"> </a>Part 3 - Serverless Functions, how they work</h1>
<p>So how do these functions work with no back-end server?</p>
<p>The short answer is that Netlify is providing the back-end environment for us. All we have to do is tell Netlify where to find the functions. Netlify will do the rest.</p>
<h3><a class="anchor" aria-hidden="true" id="15-serverless-configuration"> </a>15. Serverless configuration</h3>
<p>Take a look at <code>netlify.toml</code>.</p>
<pre><code>[build]
command = &quot;npm run build&quot;
functions = &quot;functions&quot;
publish = &quot;build&quot;
</code></pre>
<p>This is the configuration file we include in our codebase that tells Netlify how to build our app. In our case it's really simple. First we give the <code>build</code> command to build our app: <code>npm run build</code>. Then we tell Netlify where to find our serverless functions, and finally where to find the resulting app after build.</p>
<p>So Netlify will create endpoints for our serverless functions based on the files it finds in our functions folder.</p>
<p>For example, we have a function called <code>posts.js</code>. As we saw before, this function returns all of the current posts in our database. Netlify will see that file in our <code>functions</code> directory and dynamically create an endpoint at <code>/.netlify/functions/posts</code>.</p>
<p>✅ We can see these functions in our Netlify account.</p>
<ul>
<li>Go to netlify.com and sign in.</li>
<li>Select your site from the list.</li>
<li>Select the &quot;Functions&quot; tab at the top.</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/netlify_functions_tab.gif" alt="netlify_functions" /></p>
<p>From here we can see all our functions and get direct links as well as watch real time logs.</p>
<p>We can also see this in action by manually going to the endpoint on our Netlify site: <code>[your-site-url]/.netlify/functions/posts</code>.</p>
<p><img src="https://github.com/datastaxdevs/workshop-social-media-tiktok/raw/master/./tutorial/images/netlify_endpoint_nav.gif" alt="netlify_endpoint" /></p>
<h1><a class="anchor" aria-hidden="true" id="extra-resources"> </a>Extra resources</h1>
<h2><a class="anchor" aria-hidden="true" id="video-tutorial-with-ania-kubow"> </a>Video tutorial with Ania Kubow</h2>
<p>Thank you to our wonderful friend Ania Kubow for producing the TikTok clone. If you are not aware of Ania and love learning about coding you should absolutely check out her YouTube channel listed below.</p>
<p>While we focused on getting you up and running to production with Astra DB and Netlify, Ania's video will dig into more details on the app itself. Check it out to dig in more.</p>
<!--- STARTEXCLUDE --->
<h2><a class="anchor" aria-hidden="true" id="running-astra-db-tik-tok"> </a>Running Astra DB Tik-Tok</h2>
<p>We're using Create-React-App and the Astra DB Document API to create a simple Tik-Tok clone.  Follow along in this video tutorial: <a href="https://youtu.be/IATOicvih5A" target="_blank">https://youtu.be/IATOicvih5A</a>.</p>
<p>Follow the instructions below to get started.</p>
<h3><a class="anchor" aria-hidden="true" id="video-content"> </a>Video Content:</h3>
<ul>
<li><a href="https://youtu.be/IATOicvih5A" target="_blank">https://youtu.be/IATOicvih5A</a></li>
<li>(00:00) Introduction</li>
<li>(03:05) Creating our Database on DataStax</li>
<li>(06:52) Setting up our App</li>
<li>(12:37) Routing Pages</li>
<li>(18:02) Creating Components</li>
<li>(28:32) Introduction to Data with Netlify and Stargate</li>
<li>(30:10) Introduction to using the astrajs/collections</li>
<li>(34:01) Posting data to our Database (creating dummy Tik Tok posts)</li>
<li>(34:01) Adding authorization to access our Database</li>
<li>(43:10) Getting data from our Database (getting all our Tik Tok posts)</li>
<li>(50: 32) Viewing all our Data</li>
<li>(51:56) Rendering components based on our Data</li>
<li>(01:17:01) Editing our Data (following/unfollowing a user)</li>
<li>(01:32:57) Adding new Data to our Database (creating a Tik Tok post)</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="if-you-did-like-this-video-please-hit-the-like-and-subscribe-button-so-i-know-to-make-more"> </a>If you did like this video, please hit the Like and Subscribe button so I know to make more!</h3>
<ul>
<li>Twitter: <a href="https://twitter.com/ania_kubow" target="_blank">https://twitter.com/ania_kubow</a></li>
<li>YouTube: <a href="https://youtube.com/aniakubow" target="_blank">https://youtube.com/aniakubow</a></li>
<li>Instagram: <a href="https://instagram.com/aniakubow" target="_blank">https://instagram.com/aniakubow</a></li>
</ul>
<!--- ENDEXCLUDE --->

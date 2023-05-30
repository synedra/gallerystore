<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="jamstack-netlify-astra-cassandra"> </a>JAMStack + Netlify + Astra + Cassandra 📒</h1>
<p><em>10 minutes, Beginner, <a href="https://github.com/DataStax-Examples/todo-astra-jamstack-netlify#prerequisites" target="_blank">Start Building</a></em></p>
<p>This is an example React To-Do application using a <a href="https://astra.datastax.com/register?utm_source=devplay&amp;utm_medium=github&amp;utm_campaign=todo-astra-jamstack-netlify" target="_blank">DataStax Astra</a> free tier database.</p>
<!--- ENDEXCLUDE --->
<p><img src="https://monosnap.com/image/Fv0yPAznbeNJD3vYlQfztME6yogzFT" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>Provide a fullstack development example using Astra as the storage backend</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="how-this-works"> </a>How this works</h2>
<p>Once the Astra credentials are provided, the necessary tables are created in the database. The webservice will be available on port 8080 once the application has been deployed.</p>
<p><a href="https://jamstack.org/" target="_blank">JAMstack</a> is a big leap forward in how we can write web applications that are easy to write, deploy, scale, and also maintain. Using this approach means that newly created content is rendered from a content API, while a static render of it is being built into the site for future.</p>
<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="running-jamstack-netlify-astra-cassandra"> </a>Running JAMStack + Netlify + Astra + Cassandra</h1>
<p>Follow the instructions below to get started.</p>
<h2><a class="anchor" aria-hidden="true" id="prerequisites"> </a>Prerequisites</h2>
<ul>
<li>git installed on your local system</li>
<li>github account</li>
<li><a href="https://www.whitesourcesoftware.com/free-developer-tools/blog/update-node-js/" target="_blank">node 15 and npm 7 or later</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="getting-started"> </a>Getting Started</h2>
<p>Let's do some initial setup by creating a serverless(!) database.</p>
<ol>
<li><strong>Login/Register</strong><br />
Click the button to login or register with Datastax.</li>
</ol>
<ul>
<li><a href="https://astra.datastax.com/register?utm_source=github&utm_medium=referral&utm_campaign=todo-astra-jamstack-netlify" target="_blank"><img src="https://dabuttonfactory.com/button.png?t=Create+Astra+Database&f=Calibri-bold&ts=20&tc=fff&hp=40&vp=10&c=8&bgt=unicolored&bgc=6fa8dc" /></a></li>
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
<td><code>netlify</code></td>
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
<ol start="2">
<li><strong>Deploy to Netlify</strong></li>
</ol>
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
<li>Click the button to deploy:<br />
<a href="https://app.netlify.com/start/deploy?repository=https://github.com/datastaxdevs/netlify-astra-example" target="_blank"><img src="https://www.netlify.com/img/deploy/button.svg" alt="Deploy to Netlify" /></a></li>
</ul>
<ul>
<li>
<details><summary>Show me!</summary>
 <img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/main/images/tutorials/astra-create-token.gif?raw=true" />
 </details>
</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="3-access-your-github-repository"> </a>3. Access YOUR GitHub repository</h3>
<ul>
<li>Click on the <code>GitHub</code> in <code>Deploys from GitHub</code> to get back to your new repository.  Scroll to where you were in the README.
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/netlify-astra-example/raw/master/tutorial/images/deploy-5.png" />
</details>
</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="4-launch-gitpod-ide"> </a>4. Launch GitPod IDE</h3>
<ul>
<li>Click the button to launch the GitPod IDE from <strong>YOUR</strong> repository.</li>
</ul>
<ul>
<li><em>Supported by <img src="https://github.com/datastaxdevs/netlify-astra-example/raw/master/tutorial/images/chrome-logo.svg" height="20"/> Chrome and <img src="tutorial/images/firefox-logo.svg" height="20"/> Firefox</em></li>
</ul>
<h4><a class="anchor" aria-hidden="true" id="wait-before-moving-on-ensure-you-are-working-out-of-your-repository-not-the-datastaxdevs-repository"> </a>WAIT! Before moving on ensure you are working out of YOUR repository, not the datastaxdevs repository.</h4>
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
 <img src="https://github.com/datastaxdevs/netlify-astra-example/raw/master/tutorial/images/netlify-install-cli.png?raw=true" />
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
 <img src="https://github.com/datastaxdevs/netlify-astra-example/raw/master/tutorial/images/astra-create-token.gif?raw=true" />
 </details>
</li>
</ul>
<p>This is what the token page looks like.</p>
<ul>
<li>Click the <strong><code>Download CSV</code></strong> button. You are going to need these values here in a moment.</li>
</ul>
<p><img src="https://github.com/datastaxdevs/netlify-astra-example/raw/master/tutorial/images/astra-token.png?raw=true" alt="image" /></p>
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
<h3><a class="anchor" aria-hidden="true" id="7-configure-and-connect-database"> </a>7. Configure and connect database</h3>
<ul>
<li>In the repository directory run the following command to set up your Astra DB environment. This will verify the database you created earlier or create a new one for you if it can't find your database.</li>
</ul>
<pre><code>npm exec astra-setup tiktok_workshop_db tiktok_keyspace
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
<img src="https://github.com/datastaxdevs/netlify-astra-example/raw/master/./tutorial/images/netlify-livesite.png?raw=true" alt="Netlify Setup Example" /></p>

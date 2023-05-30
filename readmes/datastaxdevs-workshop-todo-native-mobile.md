<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="react-native-todo-list-astra-db-netlify"> </a>React Native Todo List + Astra DB + Netlify 📒</h1>
<p><em>40 minutes, Beginner/Intermediate</em></p>
<p>In this workshop, you will learn how to convert the Todo web application from a previous <a href="https://github.com/datastaxdevs/appdev-week1-todolist" target="_blank">DataStaxDevs workshop</a> into a React Native mobile and web application. We will actually be using the same database setup as before, so if you've already created it during the prior workshop, you can skip the Database setup section of this workshop.</p>
<p>Before going all React Native, if you would like to learn more about React and create your first React app take a look at our previous Todo app workshop. <a href="https://github.com/datastaxdevs/appdev-week1-todolist" target="_blank">HERE</a>.</p>
<p>This is an example React Native Todo application using a <a href="https://dtsx.io/appdev-7-7" target="_blank">DataStax AstraDB</a> free tier database.</p>
<!--- ENDEXCLUDE --->
<p><strong>Mobile App on Android:</strong></p>
<img width="45%" alt="AndroidTodoApp" src="https://user-images.githubusercontent.com/82838476/130680926-3cb3732a-e3ef-4167-8f09-0a25bf8732e5.png">
<p><strong>Mobile App on iOS:</strong></p>
<img width="45%" alt="iPhoneTodoApp" src="https://user-images.githubusercontent.com/82838476/130680807-a7108e00-55a2-42c5-a5f0-3f258b6d9d39.png">
<p><strong>Web Application in Chrome:</strong></p>
<img width="1680" alt="WebBrowserToDoApp" src="https://user-images.githubusercontent.com/82838476/129105493-4668143d-a923-437c-b19d-809fa7c55066.png">
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>🎯 Objectives</h2>
<ul>
<li>Implement a <strong>React Native</strong> Todo app using Expo</li>
<li>Learn about <strong>React Native</strong> components and how they are used to dynamically update the DOM with new information</li>
<li>Learn how to convert a React web app to a <strong>React Native</strong> mobile and web app</li>
<li>Learn how <strong>state</strong> and <strong>props</strong> changes are used</li>
<li>Leverage Netlify and DataStax AstraDB</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="frequently-asked-questions"> </a>ℹ️ Frequently asked questions ℹ️</h2>
<ul>
<li><em>Are there any prerequites?</em></li>
</ul>
<blockquote>
<ul>
<li>You will need a <a href="https://github.com/" target="_blank">GitHub account</a></li>
<li>You will need to <a href="https://expo.dev/client" target="_blank">download Expo Go</a> on your mobile phone (if you wish to do that part)</li>
</ul>
</blockquote>
<ul>
<li><em>What other prerequisites are there?</em></li>
</ul>
<blockquote>
<ul>
<li>You will also need an Astra DB account, but we'll work through that in the exercises</li>
<li>Use <strong>Chrome</strong> or <strong>Firefox</strong> for the best experience. Other browsers are great, but don't work well with the GitPod integration we use a bit later.</li>
</ul>
</blockquote>
<ul>
<li><em>Can I run the workshop on my computer?</em></li>
</ul>
<blockquote>
<p>There is nothing preventing you from running the workshop on your own machine.<br />
If you do so, you will need</p>
<ul>
<li>git installed on your local system</li>
<li><a href="https://www.whitesourcesoftware.com/free-developer-tools/blog/update-node-js/" target="_blank">node 15 and npm 7 or later</a></li>
<li><a href="https://docs.expo.dev/get-started/installation/" target="_blank">Expo CLI, Watchman, Xcode, Android Studio, and an iPhone or Android</a></li>
</ul>
<p>You will have to adapt commands and paths based on your environment and install the dependencies by yourself. <strong>We won't provide support</strong> to keep on track with schedule. However, we will do our best to give you the info you need to be successful.</p>
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
<img src="https://github.com/datastaxdevs/workshop-todo-native-mobile/raw/master/tutorial/images/react-badge.png?raw=true" width="200" align="right" />
<p>Don't forget to complete your upgrade and get your verified skill badge! Finish and submit your homework!</p>
<ol>
<li>Complete your mobile app deployment by completing the practice steps below <strong>THROUGH STEP 9</strong> by launching the app in GitPod and viewing it in Expo Go</li>
<li>A single image of the working mobile app with some fun todo items deployed on your phone is fine (if you cannot do this on your phone a screen of the web app is just fine)</li>
<li>Extra credit to fully deploy this up on Netlify and access from your mobile device using steps 10 and 11</li>
<li>Submit your homework <a href="https://github.com/datastaxdevs/workshop-todo-native-mobile/issues/new?assignees=HadesArchitect%2C+SonicDMG%2C+RyanWelford&amp;labels=homework%2C+wait+for+review&amp;template=homework-assignment.md&amp;title=%5BHW%5D+%3CNAME%3E" target="_blank">here</a></li>
</ol>
<p>That's it, you are done! Expect an email next week!</p>
<h1><a class="anchor" aria-hidden="true" id="let-s-start"> </a>Let's start</h1>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>Table of contents</h2>
<ol>
<li><a href="#1-login-or-register-to-astradb-and-create-database" target="_blank">Login or Register to AstraDB and Create Database</a></li>
<li><a href="#2-create-a-security-token" target="_blank">Create a Security Token</a></li>
<li><a href="#3-deploy-to-netlify" target="_blank">Deploy to Netlify</a></li>
<li><a href="#4-access-your-github-repository-and-launch-gitpod-ide" target="_blank">Access your GitHub repository and Launch GitPod IDE</a></li>
<li><a href="#5-check-node-and-npm-versions-in-gitpod" target="_blank">Check Node and NPM versions in GitPod</a></li>
<li><a href="#6-register-for-an-expo-account-in-gitpod" target="_blank">Register for an Expo Account in GitPod</a></li>
<li><a href="#7-install-expo-mobile-application-on-your-phone" target="_blank">Install Expo Mobile Application on Your Phone</a></li>
<li><a href="#8-launch-the-todo-app" target="_blank">Launch the Todo app</a></li>
<li><a href="#9-view-mobile-app" target="_blank">View Mobile App</a></li>
<li><a href="#10-link-to-and-configure-netlify" target="_blank">Link to and Configure Netlify</a></li>
<li><a href="#11-deploy-to-production" target="_blank">Deploy to Production</a></li>
</ol>
<p><strong>Part 1: Create the Database</strong></p>
<h2><a class="anchor" aria-hidden="true" id="1-login-or-register-to-astradb-and-create-database"> </a>1. Login or Register to AstraDB and create database</h2>
<p><strong><code>ASTRADB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, $25.00 USD credit every month, roughly 5M writes, 30M reads, 40GB storage monthly - sufficient to run small production workloads.</p>
<h3><a class="anchor" aria-hidden="true" id="step-1a-click-the-button-to-login-or-register-with-datastax-you-can-use-your-code-github-code-code-google-code-accounts-or-register-with-an-code-email-code"> </a>✅ Step 1a: Click the button to login or register with Datastax. You can use your <code>Github</code>, <code>Google</code> accounts or register with an <code>email</code>.</h3>
<p><em>Make sure to chose a password with minimum 8 characters, containing upper and lowercase letters, at least one number and special character</em></p>
<p><a href="https://astra.dev/8-26" target="_blank"><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/blob/main/img/create_astra_db.png?raw=true" /></a></p>
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
<td><code>todos_native_workshop_db</code></td>
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
<h2><a class="anchor" aria-hidden="true" id="2-create-a-security-token"> </a>2. Create a Security Token</h2>
<p>✅  <strong>Step 2a:</strong>  <a href="https://docs.datastax.com/en/astra/docs/manage-application-tokens.html" target="_blank">Create a token for your app</a> to use in the settings screen. Use &quot;Database Administrator&quot; permission.</p>
<p>✅  <strong>Step 2b:</strong>  Copy the token value (eg <code>AstraCS:KDfdKeNREyWQvDpDrBqwBsUB:ec80667c...</code>) in your clipboard and save the CSV, this value would not be provided afterward.</p>
<p><strong>👁️ Expected output</strong></p>
<ul>
<li>
<details><summary>Show me!</summary>
  <img src="https://github.com/datastaxdevs/workshop-graphql-netflix/blob/main/tutorial/images/astra-create-token.gif?raw=true" />
</li>
</ul>
</details>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token 
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="3-deploy-to-netlify"> </a>3. Deploy to Netlify</h2>
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
<p><a href="https://app.netlify.com/start/deploy?repository=https://github.com/datastaxdevs/workshop-todo-native-mobile" target="_blank"><img src="https://www.netlify.com/img/deploy/button.svg" alt="Deploy to Netlify" /></a></p>
</li>
</ul>
<ul>
<li>
<details><summary>Show me!</summary>
 <img src="https://github.com/datastaxdevs/appdev-week2-tiktok/blob/master/tutorial/images/deploy-to-netlify.gif?raw=true" />
 </details>
</li>
</ul>
<p>This will take a few minutes.</p>
<ul>
<li>
<p>If there is a pre-existing account in Netlify, make sure the Netlify account settings show that it's connected to the appropriate git repository (and you can ignore the error),</p>
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/workshop-todo-native-mobile/raw/master/tutorial/images/netlify-connect-01.png" />
</details>
</li>
<li>
<p>Click on <code>Site deploy in progress</code> within the Netlify UI,</p>
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/appdev-week2-tiktok/blob/master/tutorial/images/deploy-1.png" />
</details>
</li>
<li>
<p>Click the top deploy link to see the build process.</p>
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/appdev-week2-tiktok/blob/master/tutorial/images/deploy-2.png" />
</details>
</li>
<li>
<p>Wait until the build complete <code>Netlify Build Complete</code>,  <strong>When you see Pushing to repository</strong> you're ready to move on.</p>
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/appdev-week2-tiktok/blob/master/tutorial/images/deploy-3.png" />
</details>
</li>
<li>
<p>Scroll up to the top and click on the site name (it'll be after {yourlogin}'s Team next to the Netlify button).</p>
<details>
<summary>Show me! </summary>
<img src="https://github.com/datastaxdevs/appdev-week2-tiktok/blob/master/tutorial/images/deploy-4.png" />
</details>
</li>
</ul>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<p><strong>Part 2: Launch the Native Application</strong></p>
<h2><a class="anchor" aria-hidden="true" id="4-access-your-github-repository-and-launch-gitpod-ide"> </a>4. Access your GitHub repository and Launch GitPod IDE</h2>
<p>✅  <strong>Step 4a:</strong></p>
<ul>
<li>Click on the <code>GitHub</code> in <code>Deploys from GitHub</code> to get back to your new repository.  Scroll to where you were in the README.<br />
<img src="https://github.com/datastaxdevs/appdev-week3-graphql/blob/main/tutorial/images/deploy-5.png?raw=true" /></li>
</ul>
<p>✅  <strong>Step 4b:</strong></p>
<ul>
<li>Click the button to launch the GitPod IDE from <strong>YOUR</strong> repository.</li>
</ul>
<p><a href="https://gitpod.io/from-referrer/" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<h4><a class="anchor" aria-hidden="true" id="wait-before-moving-on-ensure-you-are-working-out-of-your-repository-not-the-datastaxdevs-repository"> </a>WAIT! Before moving on ensure you are working out of YOUR repository, not the datastaxdevs repository.</h4>
<ul>
<li>From your GitPod terminal execute the following command</li>
</ul>
<pre><code>git remote -v
</code></pre>
<p>If you are still using the <code>datastaxdevs</code> repo please ensure to follow the previous step, <a href="#3-deploy-to-netlify" target="_blank">step3</a> to get to your repo.</p>
<p>ℹ️ <em>It may take 3-5 minutes for GitPod to fully initialize.</em></p>
<blockquote>
<p>(<em>Note</em>: if the Gitpod button does not work, for example you are using Safari, don't despair!<br />
You can manually build the URL you need and open it in a new tab like this: <code>https://gitpod.io/#&lt;YOUR REPO FULL URL&gt;</code>,<br />
pasting in it the full address of <strong>your</strong> GitHub repository. For example,<br />
<code>https://gitpod.io/#https://github.com/JohnSmith/workshop-todo-native-mobile</code>, assuming you are &quot;JohnSmith&quot;<br />
on Github and your repo is &quot;workshop-todo-native-mobile&quot;).</p>
</blockquote>
<ul>
<li>Check out the <strong>.gitpod.yml</strong> file to see the environment setup. We've installed the Expo CLI, the Netlify CLI, and updated Node and NPM for you already.</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="5-check-node-and-npm-versions-in-gitpod"> </a>5. Check Node and NPM versions in GitPod</h2>
<p>✅  <strong>Step 5a:</strong></p>
<ul>
<li>Create split terminals</li>
</ul>
<p><strong>Click on the double-panel icon:</strong></p>
<img width="567" alt="Screen Shot 2021-08-17 at 2 06 26 PM" src="https://user-images.githubusercontent.com/82838476/130680540-601d7a0c-b30f-4d4a-8ec7-32d930157cec.png">
<p><strong>End Result:</strong></p>
 <img width="1223" alt="Screen Shot 2021-08-24 at 2 39 22 PM" src="https://user-images.githubusercontent.com/82838476/130693619-655e8e6f-9e10-4a6e-969d-b0461a5d77c7.png">
<p>✅  <strong>Step 5b:</strong><br />
You will need node 15 and npm 7 or later in both terminals.</p>
<pre lang="bash"><code>npm -v
</code></pre>
<pre lang="bash"><code>node -v
</code></pre>
<p>If either are not updated, run the following commands respectively.</p>
<pre lang="bash"><code>nvm install node
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="6-register-for-an-expo-account-in-gitpod"> </a>6. Register for an Expo Account in GitPod</h2>
<p>If you don't have an account:</p>
<pre lang="bash"><code>expo register
</code></pre>
<p>Open <a href="https://expo.dev/signup" target="_blank">https://expo.dev/signup</a> <strong>in a new tab</strong>.</p>
<p><em>Note, when using GitPod the preview pane will not display this properly. You must click the &quot;open in a new window&quot; button in the very top right of the preview pane.</em></p>
<p>Login to your account in the terminal:</p>
<pre lang="bash"><code>expo login
</code></pre>
<p>Double check that you are logged in.</p>
<pre lang="bash"><code>expo whoami 
</code></pre>
<p>You should see:</p>
<img width="427" alt="Screen Shot 2021-08-24 at 12 41 00 PM" src="https://user-images.githubusercontent.com/82838476/130679435-ea46b61a-b7b1-48da-a578-ab84f0a665fe.png">
<h2><a class="anchor" aria-hidden="true" id="7-install-expo-mobile-application-on-your-phone"> </a>7. Install Expo Mobile Application on Your Phone</h2>
<p>Download the Expo App from the Android Play Store or iOS App Store.</p>
<p><strong>Android:</strong></p>
<img width="45%" alt="PlayStore" src="https://user-images.githubusercontent.com/82838476/130651174-ed432081-811f-48f9-a161-1175c64a8680.jpg">
<p><strong>iOS:</strong></p>
<img width="45%" alt="AppStore" src="https://user-images.githubusercontent.com/82838476/130651399-649bdc12-5fd4-4760-81a7-5871846091e4.png">
<h2><a class="anchor" aria-hidden="true" id="8-launch-the-todo-app"> </a>8. Launch the Todo app</h2>
<p>✅  <strong>Step 8a:</strong> Retrieve application token to securely connect to the database</p>
<p>Use the token you previously generated. If you no longer have the token and did not download a .csv, you can generate a new token using <a href="#2-create-a-security-token" target="_blank">the instructions above</a></p>
<p>✅  <strong>Step 8b:</strong> Configure Environment Variables and Install Dependencies</p>
<ol>
<li>Set up your Astra Environment</li>
</ol>
<p>In the repository directory run the following command  to set up your Astra environment.  Note that this does require Node 15 and NPM 7 to work.  You can install a node version manager like <code>nvm</code> or <code>n</code> to use multiple versions on your system.</p>
<pre lang="bash"><code>npm exec astra-setup todos_native_workshop_db todos
</code></pre>
<ul>
<li>You will be asked to: <strong>Please paste the Database Admin Token here</strong> so copy over the Token you saved earlier, and hit enter. It will start with AstraCSAstraCS:cvdPRONUrUUT:...</li>
</ul>
<img width="738" alt="Screen Shot 2021-08-24 at 12 17 57" src="https://user-images.githubusercontent.com/82838476/130652258-5a8a5da0-b2a4-4acf-9d1c-3b3a98a97d6a.png">
<p>✅  <strong>Step 8c:</strong> Add Host URL to .env</p>
<p>Get workspace URL:</p>
<pre lang="bash"><code>bash hostURL.sh
</code></pre>
<p>Final output should look like the below:</p>
<img width="452" alt="Screen Shot 2021-08-17 at 9 13 21 PM" src="https://user-images.githubusercontent.com/82838476/129835879-135a30f4-b3bc-4ca5-889b-4483176d77f3.png">
<p>You can see the output of the .env file by running <code>cat .env</code>.</p>
<p>✅  <strong>Step 8d:</strong> Start Netlify and Expo</p>
<ul>
<li>Run the application (Ignore the QR code generated here)</li>
</ul>
<pre><code>netlify dev ; gp preview $(gp url 8888)
</code></pre>
<p>If this doesn't open in the right port (for example, 19003) - swap the port number to 8888. You will get the right url by running:</p>
<pre><code>gp preview $(gp url 8888)
</code></pre>
<p>In a new terminal window: (or have a split terminal)</p>
<pre><code>expo start --tunnel
</code></pre>
<p>Enter 'y' for yes when asked to use another port. Port 19000 is being used for the web app launched with netlify dev, that starts the web app with expo start --web (This opens when you run netlify dev.)</p>
  <img width="45%" alt="Screen Shot 2021-08-08 at 11 44 25 PM" src="https://user-images.githubusercontent.com/82838476/128941524-db4b7c9a-d21f-41e8-bc6d-729b189d6325.png">
<p>✅  <strong>Step 8e:</strong> Launch your app in the web browser</p>
<p>Open your web application at the URL specified in the HOST line of your .env file in a new tab in your browser.</p>
<p><strong>Web Application in Chrome:</strong></p>
<img width="1680" alt="WebBrowserToDoApp" src="https://user-images.githubusercontent.com/82838476/129105493-4668143d-a923-437c-b19d-809fa7c55066.png">
<p>✅  <strong>Step 8f:</strong> Launch your app on your mobile device</p>
<p><strong>Scan the QR code</strong> with your phone camera to open your application in the Expo App! You may need to resize the terminal to make the QR code render properly. You can also scan the QR code from within the Expo Go app. Once the QR code is scanned, it may take a few minutes for the app to be loaded and run on your phone.</p>
<p>Scanning in the Expo Go App:</p>
<img width="45%" alt="WebBrowserTodoApp" src="https://user-images.githubusercontent.com/82838476/130652900-fbdf3874-b014-445d-ba9b-c3a2996defef.jpg">
<h2><a class="anchor" aria-hidden="true" id="9-view-mobile-app"> </a>9. View Mobile App</h2>
<p>✅  <strong>Step 9a:</strong> Launch your app on your mobile device</p>
<p>You may see this screen for a while -- Expo Go is loading the application.</p>
<img width="45%" alt="WebBrowserTodoApp" src="https://user-images.githubusercontent.com/82838476/130679108-b6e0ef6f-e9b2-4571-a89b-35f5b98162d4.jpg">
<p>Add some items to your Todo list (type in the 'What needs to be done?' input and hit enter)! These get stored in Astra DB.</p>
<p>See examples of what your finished product should look like:</p>
<p><strong>Mobile App on Android:</strong></p>
<img width="45%" alt="AndroidTodoApp" src="https://user-images.githubusercontent.com/82838476/130680926-3cb3732a-e3ef-4167-8f09-0a25bf8732e5.png">
<p><strong>Mobile App on iOS:</strong></p>
<img width="45%" alt="iPhoneTodoApp" src="https://user-images.githubusercontent.com/82838476/130680807-a7108e00-55a2-42c5-a5f0-3f258b6d9d39.png">
<p>✅  <strong>Step 9b:</strong> See your Todos in Astra DB.</p>
<ul>
<li>Navigate to the Dashboard in Astra DB and click on the todos_native_workshop_db.</li>
</ul>
<img width="45%" alt="Screen Shot 2021-08-24 at 9 49 13 AM" src="https://user-images.githubusercontent.com/82838476/130657937-b25aed15-c14a-4e88-b065-b930c475c998.png">
<ul>
<li>Then click on the CQL tab.</li>
</ul>
<img width="45%" alt="Screen Shot 2021-08-24 at 9 49 28 AM" src="https://user-images.githubusercontent.com/82838476/130657954-32d9840b-2fff-4783-b171-7ca013cd8062.png">
<p>Finally, run the following commands:</p>
<pre><code>use todos;
</code></pre>
<pre><code>describe tables;
</code></pre>
<pre><code>select * from rest;
</code></pre>
<p>The output should look like the following:</p>
<img width="45%" alt="Screen Shot 2021-08-24 at 12 33 32" src="https://user-images.githubusercontent.com/82838476/130656955-253b9857-7200-4414-a309-b6acff53cbc8.png">
<h2><a class="anchor" aria-hidden="true" id="10-link-to-and-configure-netlify"> </a>10. Link to and Configure Netlify</h2>
<p>Execute each of the commands below to link your code to your Netlify deployment.</p>
<ul>
<li>First thing, we'll need to <strong>STOP</strong> both programs running: the <code>netlify dev</code> command we issued a moment ago, as well as the expo start --tunnel command. In the terminal where you executed the netlify command issue a <code>CTRL-C</code> (control key + the C key) in order to stop the process. From here on, you will only need one console.</li>
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
<li>Update the environment variables in your .env file - (See generateEndpoint function in api.js to see why we do this).</li>
</ul>
<p>Before:</p>
<pre><code>IS_PROD=&quot;false&quot;
GITPOD=&quot;true&quot;
</code></pre>
<p>After:</p>
<pre><code>IS_PROD=&quot;true&quot;
GITPOD=&quot;false&quot;
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
<h2><a class="anchor" aria-hidden="true" id="11-deploy-to-production"> </a>11. Deploy to Production</h2>
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
<p>You've deployed your app to Netlify!</p>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h1><a class="anchor" aria-hidden="true" id="need-a-refresher-on-react-basics"> </a>Need a refresher on React Basics?</h1>
<details><summary>Take me to the React stuff</summary>
  We've created a separate repo going over the Basics of React. To get there, click the link below.
<p><a href="https://github.com/datastaxdevs/react-basics" target="_blank">GOTO React-Basics</a></p>
<p>When you're done, just click on the &quot;Back to Main&quot; breadcrumb to come back here.</p>
</details>
<h3><a class="anchor" aria-hidden="true" id="things-to-note"> </a>Things to Note:</h3>
<ul>
<li>The contents of this repo are based on <a href="https://github.com/tjake/todo-astra-react-serverless/" target="_blank">Jake's port</a> of the <a href="https://github.com/tastejs/todomvc/tree/master/examples/react">TodoMVC code</a> originally written by <a href="https://github.com/petehunt">Pete Hunt</a>.</li>
<li>The example is modified from <a href="https://github.com/huksley/todo-react-ssr-serverless" target="_blank">https://github.com/huksley/todo-react-ssr-serverless</a>.</li>
</ul>
<!--- ENDEXCLUDE --->

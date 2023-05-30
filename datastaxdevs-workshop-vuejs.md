<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="build-an-app-with-vuejs-and-typescript"> </a>Build an App with VueJS and Typescript 📒</h1>
<p><em>15 minutes, Beginner</em></p>
<p>This is an example VueJS application using a <a href="https://astra.dev/10-20" target="_blank">DataStax Astra</a> free tier database.</p>
<!--- ENDEXCLUDE --->
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>🎯 Objectives</h2>
<ul>
<li>Learn the basics of building Vue Components and composing a <strong>VueJS</strong> app</li>
<li>Learn how to implement <strong>serverless functions</strong> and connect the front-end to the back-end</li>
<li>Learn how to connect a live <strong>NoSQL</strong> database using a <strong>Document API</strong></li>
<li>Leverage <strong>Netlify</strong> and <strong>DataStax Astra DB</strong></li>
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
<li><a href="https://dtsx.io/workshop" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h2>
<img src="https://github.com/datastaxdevs/workshop-vuejs/blob/main/tutorial/imgs/VueJS_Badge_transparent.png" width="200" align="right" />
<p>Don't forget to complete your upgrade and get your verified skill badge! Finish and submit your homework!</p>
<ol>
<li>Complete the practice steps from this repository as described below.</li>
<li>Launch the <strong>Vue</strong> app and connect it to the database. <strong>Take a screenshot of your HOOT app with your unique URL</strong>.</li>
<li>[OPTIONAL] Edit the size of the pack to open more cards each time!</li>
<li>Submit your homework <a href="https://github.com/datastaxdevs/workshop-vuejs/issues/new?assignees=SonicDMG%2C+RyanWelford&amp;labels=homework&amp;template=homework-assignment.md&amp;title=%5BHW%5D+%3CNAME%3E" target="_blank">here</a>. Note:<br />
<em>never share your Astra DB tokens!</em></li>
</ol>
<p>That's it, you are done! Expect an email next week!</p>
<h1><a class="anchor" aria-hidden="true" id="let-s-start"> </a>Let's start</h1>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>Table of contents</h2>
<ol>
<li><a href="#1-login-or-register-to-astradb-and-create-database" target="_blank">Login or Register to AstraDB and create database</a></li>
<li><a href="#2-create-a-security-token" target="_blank">Create a security token</a></li>
<li><a href="#3-launch-gitpod-ide" target="_blank">Launch GitPod IDE</a></li>
<li><a href="#4-project-overview" target="_blank">Project Overview</a></li>
<li><a href="#5-create-a-vue-component" target="_blank">Create a Vue Component</a></li>
<li><a href="#6-database-connection-setup" target="_blank">Database Connection Setup</a></li>
<li><a href="#7-create-a-serverless-function" target="_blank">Create a Serverless Function</a></li>
<li><a href="#8-calling-serverless-functions-from-the-front-end" target="_blank">Calling Serverless Functions from the Front-End</a></li>
<li><a href="#9-launching-the-app" target="_blank">Launching the App</a></li>
</ol>
<h3><a class="anchor" aria-hidden="true" id="demo"> </a>Demo</h3>
<ul>
<li><a href="http://www.hootcards.io" target="_blank">App Demo</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="1-login-or-register-to-astradb-and-create-database"> </a>1. Login or Register to AstraDB and create database</h2>
<p><strong><code>ASTRADB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, $25.00 USD credit every month, roughly 5M writes, 30M reads, 40GB storage monthly - sufficient to run small production workloads.</p>
<h3><a class="anchor" aria-hidden="true" id="step-1a-click-the-button-to-login-or-register-with-datastax-you-can-use-your-code-github-code-code-google-code-accounts-or-register-with-an-code-email-code"> </a>✅ Step 1a: Click the button to login or register with Datastax. You can use your <code>Github</code>, <code>Google</code> accounts or register with an <code>email</code>.</h3>
<p><em>Make sure to chose a password with minimum 8 characters, containing upper and lowercase letters, at least one number and special character</em></p>
<p><a href="https://astra.dev/10-20" target="_blank"><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/blob/main/img/create_astra_db.png?raw=true" /></a></p>
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
<td><code>vue_workshop_db</code></td>
</tr>
<tr>
<td><strong>keypace</strong></td>
<td><code>vue_keyspace</code></td>
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
<h2><a class="anchor" aria-hidden="true" id="3-launch-gitpod-ide"> </a>3. Launch GitPod IDE</h2>
<ul>
<li>Click the button to launch the GitPod IDE.</li>
</ul>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-vuejs/" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<p><a href="#table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="4-project-overview"> </a>4. Project Overview</h2>
<p>Let's start by taking a look at the current structure of our app.</p>
<h3><a class="anchor" aria-hidden="true" id="strong-nuxt-strong"> </a><strong>Nuxt</strong></h3>
<p>This app was built using <a href="https://nuxtjs.org/" target="_blank">Nuxt</a>, a framework for Vue that helps get a new app up and running quickly. We won't get into too much detail of what Nuxt does, just know that it does a lot of things under the hood so we don't have to worry about them. We can just focus on designing our app experience.</p>
<h3><a class="anchor" aria-hidden="true" id="strong-pages-strong"> </a><strong>Pages</strong></h3>
<p>Take a look at <code>pages/index.vue</code>. This is the primary page served by our app. You'll notice it's broken up into 3 main sections. <code>&lt;template&gt;...&lt;/template&gt;</code>, <code>&lt;script&gt;...&lt;/script&gt;</code>, and <code>&lt;style&gt;...&lt;/style&gt;</code>. This is the standard structure of a VueJS 3 component.</p>
<ul>
<li>The <code>&lt;template&gt;</code> section contains our <code>HTML</code> layout</li>
<li>The <code>&lt;script&gt;</code> section contains the <code>Javascript</code> for logic and data management</li>
<li>The <code>&lt;style&gt;</code> section contains our <code>CSS</code> styles which can be scoped to the current component only if desired.</li>
</ul>
<blockquote>
<p><em>Note that the <code>lang=&quot;ts&quot;</code></em> flag in the <code>&lt;script&gt;</code> section signifies that we are using Typescript. VueJS 3 has built in Typescript support and this flag also enables type-checking.</p>
</blockquote>
<p>You'll notice also, in the <code>&lt;script&gt;</code> section we have some hardcoded data:</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-pages-index-vue-code-em"> </a><em><code>pages/index.vue</code></em></h5>
<pre lang="javascript"><code>data() {
    return {
      cards: [
        {
          &quot;rarityOrder&quot;: 0,
          &quot;rarity&quot;: &quot;common&quot;,
          &quot;imgURL&quot;: &quot;https://i.imgur.com/Ppl525s.png&quot;
        },
        {
          &quot;rarityOrder&quot;: 0,
          &quot;rarity&quot;: &quot;common&quot;,
          &quot;imgURL&quot;: &quot;https://i.imgur.com/lFmgnFj.png&quot;
        },
        {
          &quot;rarityOrder&quot;: 1,
          &quot;rarity&quot;: &quot;uncommon&quot;,
          &quot;imgURL&quot;: &quot;https://i.imgur.com/Xl5borx.png&quot;
        },
        {
          &quot;rarityOrder&quot;: 2,
          &quot;rarity&quot;: &quot;rare&quot;,
          &quot;imgURL&quot;: &quot;https://i.imgur.com/nfXbo4I.png&quot;
        },
        {
          &quot;rarityOrder&quot;: 3,
          &quot;rarity&quot;: &quot;ultra-rare&quot;,
          &quot;imgURL&quot;: &quot;https://i.imgur.com/CIV2Yhq.png&quot;
        }
      ],
    }
  }
</code></pre>
<p>Right now, this is our array of card objects. It's currently hardcoded for development purposes, but we will be retrieving this data from the database in the end.</p>
<p>You also might notice some interesting tags in the <code>&lt;template&gt;</code> section. <code>&lt;van-row&gt;</code> is an element from the ui library that we selected while setting up the Nuxt project, called Vant. A UI library provides some out-of-the-box elements we can use to help us with layout and look/feel. Nuxt provides many other selections as well.</p>
<p><code>&lt;CardFlip :card=&quot;card&quot; /&gt;</code> references another component that is being used on this page. Let's go take a look at that component.</p>
<p>You'll see the familiar 3-section layout but now the <code>&lt;style&gt;</code> section is <code>scoped</code> to keep any specific styles to this component. There's also a new structure in our <code>&lt;script&gt;</code> section.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-components-cardflip-vue-code-em"> </a><em><code>components/CardFlip.vue</code></em></h5>
<pre lang="javascript"><code>props: {
    card: {
        type: Object,
        default () {
            return {
                rarity: 'none',
                igmURL: ''
            }
        }
    }
}
</code></pre>
<p>This section defines the <code>props</code> or properties that can be passed into this component. In this case, we are defining a <code>prop</code> called <code>card</code> that expects an <code>Object</code>. If you remember, our reference to this component looked like this: <code>&lt;CardFlip :card=&quot;card&quot; /&gt;</code>. Here, we are passing in an object (also called <code>card</code>) into that <code>prop</code>.</p>
<p>If we take a look at the template section, we see a placeholder for another component. The front side of the card.</p>
<p>Let's make that component.</p>
<h2><a class="anchor" aria-hidden="true" id="5-create-a-vue-component"> </a>5. Create a Vue Component</h2>
<h3><a class="anchor" aria-hidden="true" id="strong-step-5a-strong"> </a>✅  <strong>Step 5a:</strong></h3>
<p>First, let's start by creating a new file in the components folder called <code>HootCard.vue</code>. Then fill in the standard sections; <code>&lt;template&gt;</code>, <code>&lt;script&gt;</code>, and <code>&lt;style&gt;</code>.</p>
<p>The <code>&lt;template&gt;</code> is going to be very simple. All we want is to display an image, similar to the back side of the card that we saw in the <code>CardFlip.vue</code> component.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-components-hootcard-vue-template-code-em"> </a><em><code>components/HootCard.vue - &lt;template&gt;</code></em></h5>
<pre lang="html"><code>&lt;template&gt;
    &lt;div class=&quot;card&quot; :class=&quot;rarity&quot;&gt;
        &lt;img class=&quot;owl&quot; :src=&quot;imgURL&quot; /&gt;
    &lt;/div&gt;
&lt;/template&gt;
</code></pre>
<p>Notice that we are utilizing a few custom css classes. We'll define those in the <code>&lt;style&gt;</code> section. We also have some data references: <code>:class=&quot;rarity&quot;</code> and <code>:src=&quot;imgURL&quot;</code>. This is so that we can dynamically change the elements based on the type of card.</p>
<p>Let's get some of that data set up.<br />
In the <code>&lt;script&gt;</code> section:</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-components-hootcard-vue-script-code-em"> </a><em><code>components/HootCard.vue - &lt;script&gt;</code></em></h5>
<pre lang="html"><code>&lt;script lang=&quot;ts&quot;&gt;
import Vue from 'vue';

export default Vue.extend({

})
&lt;/script&gt;
</code></pre>
<p>We know that we are going to pass in a prop for the card data, so let's set that up. We know what the data structure for the pack is, based on our hard-coded example.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-array-of-5-cards-reference-code-em"> </a><em><code>Array of 5 Cards - Reference</code></em></h5>
<p><img src="https://github.com/datastaxdevs/workshop-vuejs/raw/master//tutorial/imgs/card_array.png" alt="image" /></p>
<p>We are dealing primarily with the <code>rarity</code> and <code>imgURL</code> properties. So, in our <code>props</code> we need to specify an object with those two properties.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-components-hootcard-vue-script-code-em"> </a><em><code>components/HootCard.vue - &lt;script&gt;</code></em></h5>
<pre lang="html"><code>&lt;script lang=&quot;ts&quot;&gt;
import Vue from 'vue';

export default Vue.extend({
    props: {
        card: {
            type: Object,
            default () {
                return {
                    rarity: 'none',
                    imgURL: ''
                }
            }
        }
    }
})
&lt;/script&gt;
</code></pre>
<p>Now we need to return those <code>props</code> as <code>data</code> values so our template can use them.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-components-hootcard-vue-script-code-em"> </a><em><code>components/HootCard.vue - &lt;script&gt;</code></em></h5>
<pre lang="html"><code>&lt;script lang=&quot;ts&quot;&gt;
import Vue from 'vue';

export default Vue.extend({
    props: {
        card: {
            type: Object,
            default () {
                return {
                    rarity: 'none',
                    imgURL: ''
                }
            }
        }
    },
    data() {
        return {
            rarity: this.card.rarity,
            imgURL: this.card.imgURL
        }
    }
})
&lt;/script&gt;
</code></pre>
<p>And that's it for our logic! Now, the card image will be dynamic based on the card that's passed in, as well as the style. Speaking of which let's get that custom css in here.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-components-hootcard-vue-style-code-em"> </a><em><code>components/HootCard.vue - &lt;style&gt;</code></em></h5>
<pre lang="html"><code>&lt;style scoped&gt;
.card {
    width: 100%;
    border-radius: 12px;
    position: relative;
    padding-top: 140%
}

.card.ultra-rare {
    background: #f1ba24;
    box-shadow: 0px 0px 20px #f1ba24;
}
.card.rare {
    background: #72286d;
    box-shadow: 0px 0px 20px #72286d;
}
.card.uncommon {
    background: #b12659;
}
.card.common {
    background: #7f949b; /*84d4d4*/
}

.owl {
    width: 50%;
    left: 50%;
    top: 50%;
    position: absolute;
    transform: translate(-50%, -50%);
}
&lt;/style&gt;
</code></pre>
<p>And that's it! We've just created a custom Vue component to dynamically display our cards! Let's test it out!</p>
<p>First we need to add the component to <code>CardFlip.vue</code>. Replace the <code>&lt;!-- CARD COMPONENT HERE --&gt;</code> line with this:</p>
<pre lang="javascript"><code>&lt;HootCard :card=&quot;card&quot; /&gt;   
</code></pre>
<p>In the terminal, run:</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-terminal-run-code-em"> </a><em><code>Terminal - Run</code></em></h5>
<pre lang="bash"><code>npm run dev
</code></pre>
<p>A browser window should open automatically.</p>
<p><img src="https://github.com/datastaxdevs/workshop-vuejs/raw/master//tutorial/imgs/firstRun.png" alt="image" /></p>
<p>Now we have an interactive experience opening a pack of cards. The cards are always the same though, we'll need to connect our app to our database and get serverless functions up and running to make it more dynamic.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-terminal-code-em"> </a><em><code>Terminal</code></em></h5>
<p><code>CTRL-C</code> to kill the running service</p>
<h2><a class="anchor" aria-hidden="true" id="6-database-connection-setup"> </a>6. Database Connection Setup</h2>
<p>Ok, we have a few things to set up before we can implement our serverless functions.</p>
<ul>
<li>Run <code>astra-setup</code></li>
<li>Install <code>@astrajs/collections</code></li>
<li>Create <code>astraClient.js</code></li>
<li>Install <code>netlify-cli</code></li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="strong-step-6a-strong"> </a>✅  <strong>Step 6a:</strong></h3>
<p>First lets run a tool called <code>astra-setup</code>. You will need the authentication token you generated in <a href="#2-create-a-security-token" target="_blank">step 2</a>.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-terminal-run-code-em"> </a><em><code>Terminal - Run</code></em></h5>
<pre lang="bash"><code>npm exec astra-setup vue_workshop_db vue_keyspace
</code></pre>
<p>This tool will create <em><strong>environment variables</strong></em> for you in a new file: <code>.env</code>. These variables are used for authenticating and connecting to your Astra DB. This includes your authentication token, so these variables are only stored locally and should never be stored in a public facing repository.</p>
<p>It should look something like this. You can run <code>cat /workspace/workshop-vuejs/.env</code> to take a look at yours.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-env-code-em"> </a><em><code>.env</code></em></h5>
<pre><code>ASTRA_DB_ADMIN_TOKEN=&quot;&lt;TOKEN&gt;&quot;
ASTRA_DB_APPLICATION_TOKEN=&quot;&lt;TOKEN&gt;&quot;
ASTRA_DB_ID=&quot;&lt;ID&gt;&quot;
ASTRA_DB_REGION=&quot;&lt;REGION&gt;&quot;
ASTRA_DB_KEYSPACE=&quot;vue_keyspace&quot;
ASTRA_GRAPHQL_ENDPOINT=&quot;&lt;URL&gt;&quot;
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="strong-step-6b-strong"> </a>✅  <strong>Step 6b:</strong></h3>
<p>Now let's install the library for connecting to our Astra DB.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-terminal-run-code-em"> </a><em><code>Terminal - Run</code></em></h5>
<pre lang="bash"><code>npm install @astrajs/collections
</code></pre>
<p>We will be using the <em><strong>Document API</strong></em> to store and retrieve <code>JSON</code> Documents to the database. First though, we need to create a utility to create the client that our serverless functions will use.</p>
<h3><a class="anchor" aria-hidden="true" id="strong-step-6c-strong"> </a>✅  <strong>Step 6c:</strong></h3>
<p>Create a new file in <code>functions/utils/</code> called <code>astraClient.js</code>.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-functions-utils-astraclient-js-code-em"> </a><em><code>functions/utils/astraClient.js</code></em></h5>
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

const getCollection = async () =&gt; {
    const documentClient = await getAstraClient();
    return documentClient
        .namespace(process.env.ASTRA_DB_KEYSPACE)
        .collection(&quot;cards&quot;);
};

module.exports = { getAstraClient, getCollection };
</code></pre>
<p>Okay, this is simpler than it looks. There are two functions here to talk about. The first is <code>getAstraClient</code>. This function initializes the connection to the database using the evironment variables we imported previously (<code>process.env.ASTRA_...</code>).</p>
<p>The second function get the reference to the document collection we want. It first intitializes the client using the previous function:</p>
<pre lang="javascript"><code>const documentClient = await getAstraClient();
</code></pre>
<p>Then returns the specified collection <code>&quot;cards&quot;</code>, from the given keyspace:</p>
<pre lang="javascript"><code>return documentClient.namespace(process.env.ASTRA_DB_KEYSPACE).collection(&quot;cards&quot;);
</code></pre>
<p>This function can now be used anywhere to get a reference to this collection.</p>
<blockquote>
<p>*If you want to have a more flexible function, you can replace the <code>&quot;cards&quot;</code> name with a parameter that gets passed in, allowing this one function to reference any specified collection.</p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="strong-step-6d-strong"> </a>✅  <strong>Step 6d:</strong></h3>
<p>Alright, one last thing before we can get to our serverless functions is to install <code>netlify-cli</code>. Netlify is a Global CDN that provides hosting solutions to web-apps and also provides a back-end infrastructure to serve up our serverless functions. Our function implementation is not restricted to Netlify, but we have found it to be a very robust and easy-to-use solution. The CLI tool we are installing here will allow us to run a local evironment that emulates the production environment and give us access to the serverless functions.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-terminal-run-code-em"> </a><em><code>Terminal - Run</code></em></h5>
<pre lang="bash"><code>npm install -g netlify-cli
</code></pre>
<p>And that's it! On to our first serverless function!</p>
<h2><a class="anchor" aria-hidden="true" id="7-create-a-serverless-function"> </a>7. Create a Serverless Function</h2>
<p>The serverless functions are pretty easy to implement, but there's a few things to note. First is that you want to separate each function into a separate file. This is because Netlify will generate endpoints to your functions based on the files in the <code>functions</code> folder. So, one function, one file, one endpoint.</p>
<p>Example: we already have a serverless function ready in the functions folder called <code>uploadCards.js</code>. This is for writing all of our cards to the database to make life easier, it isn't needed for the main app. Netlify will generate an endpoint for this function at <code>/.netlify/functions/uploadCards</code>. This will be the pattern for any function we make. <em>(We'll use this path later in the front-end)</em>.</p>
<p>Let's start our new serverless function. Create a new file in the <code>functions</code> directory called <code>getCards.js</code>.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-functions-getcards-js-code-em"> </a><em><code>functions/getCards.js</code></em></h5>
<pre lang="javascript"><code>exports.handler = async function () {
    return {
        statusCode: 200,
        body: '',
        headers: {
            'Content-type': 'application/json',
        },
    };
};
</code></pre>
<p>This is our simple boiler-plate serverless function. The bare-bones needed for everything to work. Currently though, we are just returning a status 200 (success) and and empty body, so not very helpful.</p>
<p>Here's what we want to do in our serverless function.</p>
<ul>
<li>Retrieve all the cards from the database.</li>
<li>Randomly select 5 cards</li>
<li>Send the newly created &quot;pack&quot; back to the front end for display</li>
</ul>
<p>Luckily for us, (and for time), we have some pre-made functions for randomly selecting the 5 cards in <code>functions/utils/packBuilder.js</code>. Let's import that into our serverless function so we can use it. We also are going to need our <code>getCollection</code> function from <code>astraClient.js</code> so we can retrieve our cards, so we'll import that as well.</p>
<pre lang="javascript"><code>const { getCollection } = require(&quot;./utils/astraClient&quot;);
const { packBuilder } = require(&quot;./utils/packBuilder&quot;);
</code></pre>
<details>
<summary>Show me in context</summary>
<h5><a class="anchor" aria-hidden="true" id="em-code-functions-getcards-js-code-em"> </a><em><code>functions/getCards.js</code></em></h5>
<pre lang="javascript"><code>const { getCollection } = require(&quot;./utils/astraClient&quot;);
const { packBuilder } = require(&quot;./utils/packBuilder&quot;);

exports.handler = async function () {
    return {
        statusCode: 200,
        body: '',
        headers: {
            'Content-type': 'application/json',
        },
    };
};
</code></pre>
</details>
<br>
<p>So in the function itself, let's start by creating a reference to our collection:</p>
<pre lang="javascript"><code>const collection = await getCollection();
</code></pre>
<details>
<summary>Show me in context</summary>
<h5><a class="anchor" aria-hidden="true" id="em-code-functions-getcards-js-code-em"> </a><em><code>functions/getCards.js</code></em></h5>
<pre lang="javascript"><code>const { getCollection } = require(&quot;./utils/astraClient&quot;);
const { packBuilder } = require(&quot;./utils/packBuilder&quot;);

exports.handler = async function () {
    const collection = await getCollection();

    return {
        statusCode: 200,
        body: '',
        headers: {
            'Content-type': 'application/json',
        },
    };
};
</code></pre>
</details>
<br>
<p>Now we can use <code>collection</code> as our reference and use the <em><strong>Document API</strong></em> to retrieve data. First though, we need to implement a <code>try</code> block to catch any errors that might occur. Here's what it should look like so far.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-functions-getcards-js-code-em"> </a><em><code>functions/getCards.js</code></em></h5>
<pre lang="javascript"><code>const { getCollection } = require(&quot;./utils/astraClient&quot;);
const { packBuilder } = require(&quot;./utils/packBuilder&quot;);

exports.handler = async function () {
    const collection = await getCollection();

    try {
        return {
            statusCode: 200,
            body: '',
            headers: {
                'Content-type': 'application/json',
            },
        };
    } catch (e) {
        console.error(e);
        return {
            statusCode: 500,
            body: JSON.stringify(e),
        };
    }
};
</code></pre>
<p>So now, within the <code>try</code> block we can retrieve our data, create the pack, and send the response. Any error will be caught and logged.</p>
<h3><a class="anchor" aria-hidden="true" id="document-api"> </a>Document API</h3>
<p>There are several methods built into the <em><strong>Document API</strong></em> and are included in the <code>@astrajs/collections</code> library.</p>
<ul>
<li><code>create</code> - For inserting documents into the collection</li>
<li><code>update</code> - For updating/editing a document in the collection</li>
<li><code>find</code> - For retrieving documents from the collection</li>
</ul>
<p>In this serverless function, we just want to retrieve all the cards we have available, so we'll use <code>find</code>.</p>
<pre lang="javascript"><code>const res = await collection.find({});
</code></pre>
<blockquote>
<p>*Note that the empty braces - <code>{}</code> - signify that we want <strong>all</strong> the documents from the collection.</p>
</blockquote>
<p>Then we can use our <code>packBuilder</code> function to randomly select 5 cards, and create a pack - an array of 5 cards.</p>
<pre lang="javascript"><code>let pack = packBuilder(Object.keys(res.data).map((key) =&gt; res.data[key]));
</code></pre>
<p>Whoa. Stop. What is <code>Object.keys(res).map((key) =&gt; res[key])</code>??</p>
<p>Ok. So when we retrieve the documents using <code>collection.find({})</code>, it will return each document with it's auto-generated 'document id'. This is useful if we were looking for a specific document, but we don't care about it in this case. What we need is all the cards in an array. So this crazy line uses the built in methods for Arrays (<code>.map</code>) and Objects (<code>.keys</code>) and creates an array of the documents, while throwing out the document ids that we don't need.</p>
<p>Now we need to return the resulting <code>pack</code> to the front-end. Let's change our successful return to this:</p>
<pre lang="javascript"><code>return {
    statusCode: 200,
    body: JSON.stringify(pack),
    headers: {
        'Content-type': 'application/json',
    },
};
</code></pre>
<p>And that's it! This serverless function is done! Here's what it should look like in the end.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-functions-getcards-js-code-em"> </a><em><code>functions/getCards.js</code></em></h5>
<pre lang="javascript"><code>const { getCollection } = require(&quot;./utils/astraClient&quot;);
const { packBuilder } = require(&quot;./utils/packBuilder&quot;);

exports.handler = async function () {
    const collection = await getCollection();

    try {
        const res = await collection.find({});
        let pack = packBuilder(Object.keys(res.data).map((key) =&gt; res.data[key]));
        
        return {
            statusCode: 200,
            body: JSON.stringify(pack),
            headers: {
                'Content-type': 'application/json',
            },
        };
    } catch (e) {
        console.error(e);
        return {
            statusCode: 500,
            body: JSON.stringify(e),
        };
    }
};
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="8-calling-serverless-functions-from-the-front-end"> </a>8. Calling Serverless Functions from the Front-End</h2>
<p>Alright! Let's use our new serverless function by calling it from the front-end!</p>
<p>We'll need to make some changes to <code>index.vue</code>. Namely, getting rid of the hardcoded card array and adding a new fetch method to retrieve our server-generated pack.</p>
<p>First let's get rid of the hard-coded card array, and replace it with an empty array. This will simply initialize our <code>cards</code> variable.</p>
<p>Next, let's import a library called <code>axios</code> that will help us with our fetch method.</p>
<blockquote>
<p><em>Note: Javascript does have built in fetch capabilities, so this library is technically optional. Axios is a good library though, and provides many other tools as well</em></p>
</blockquote>
<pre lang="javascript"><code>import axios from 'axios';
</code></pre>
<p>Now we'll implement a fetch method in our component.</p>
<pre lang="javascript"><code>async fetch() {
    this.cards = await axios.get('/.netlify/functions/getCards').then(res =&gt; res.data);
},
</code></pre>
<p>Notice the path to the endpoint - <code>'/.netlify/functions/getCards'</code>. Same as mentioned before, this is the standard path that Netlify will generate for each of our serverless functions.</p>
<p>So here's what <code>index.vue</code> should look like now. (<code>&lt;script&gt;</code> section)</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-pages-index-vue-code-em"> </a><em><code>pages/index.vue</code></em></h5>
<pre lang="html"><code>&lt;script lang=&quot;ts&quot;&gt;
import Vue from 'vue';
import axios from 'axios';


export default Vue.extend({
  data() {
    return {
      cards: [],
    }
  },
  async fetch() {
    this.cards = await axios.get('/.netlify/functions/getCards').then(res =&gt; res.data);
  },
  methods: {
    reloadPage() {
      window.location.reload();
    }
  }
})
&lt;/script&gt;
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="9-launching-the-app"> </a>9. Launching the App</h2>
<p>Let's launch our site now, using the Netlify CLI to provide our new serverless functions.</p>
<h5><a class="anchor" aria-hidden="true" id="em-code-terminal-run-code-em"> </a><em><code>Terminal - Run</code></em></h5>
<pre lang="bash"><code>netlify dev
</code></pre>
<p>You may not be getting any cards yet. That's because we haven't uploaded any to the database! Remember the other function though? We can manually run that function by running <code>curl $(gp url 8888)/.netlify/functions/uploadCards</code> in a new terminal, then refresh the app!</p>

<h1><a class="anchor" aria-hidden="true" id="sample-swift-ios-app-using-datastax-astra-s-document-api"> </a>Sample Swift IOS app using Datastax Astra's Document API</h1>
<h3><a class="anchor" aria-hidden="true" id="contributor"> </a>Contributor:</h3>
<p><a href="https://github.com/vmic2002" target="_blank">Victor Micha</a>, Datastax Polaris Intern</p>
<h3><a class="anchor" aria-hidden="true" id="objective"> </a>Objective:</h3>
<p>Build an app in Swift that connects to the Datastax Astra Database. By replicating this project, you will have an IOS app with fully functional backend and frontend.</p>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to work at your own pace,<br />
we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="https://www.youtube.com/watch?v=U2R-6gKeXXk" target="_blank">Workshop Video/Youtube Link</a></li>
<li><a href="Slides/workshop-Swift-IOS-Astra.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
<li><a href="https://gist.github.com/vmic2002/68bdfb71a55a1410ba0e708a81b24af1" target="_blank">Code for the workshop</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="about"> </a>About:</h2>
<p>This sample app is coded in Swift and was developed on the Xcode IDE. It connects to the Astra DB using the Document API. It handles user accounts (signing up, signing in, changing password and deleting accounts) as well as manually entering an order, taking a picture of the receipt to post an order, and seeing all past orders.</p>
<p>GroceryHandler is an application for facilitating the accounting of splitting expenses with others. For example, if roommates buy groceries together in one order, this app would be able to indicate how much each person owes the buyer.</p>
<h2><a class="anchor" aria-hidden="true" id="for-beginners"> </a>For beginners:</h2>
<p>If you are new to databases, <a href="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra#for-beginners-to-databases" target="_blank">click here</a>.<br />
If you are new to the Document API, <a href="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra#intro-to-document-api" target="_blank">click here</a>.</p>
<h2><a class="anchor" aria-hidden="true" id="prerequisites"> </a>Prerequisites:</h2>
<ol>
<li><a href="https://developer.apple.com/xcode/" target="_blank">Download Xcode</a>.<br />
The Xcode version for this application is version 13.4.1.<br />
It will take a while to download. While this is happening, move on to the next step.</li>
<li><a href="https://auth.cloud.datastax.com/auth/realms/CloudUsers/login-actions/registration?client_id=auth-proxy&amp;tab_id=sbXNIWyPYDw&amp;redirect_uri=https://astra.datastax.com/welcome" target="_blank">Create an Astra database account:</a><br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%2011.08.20%20AM.png" alt="" /></li>
<li>After verifying the account, click on <em>Create Database</em>:<br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%2010.52.43%20AM.png" alt="" /></li>
<li>Enter a database name, keyspace name, and region. Name them whatever you like. For the sample app, the keyspace is named <em>gh_orders_userinfo</em>. Then click on <em>Create Database</em><br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%2010.57.15%20AM.png" alt="" /></li>
<li>Click on <em>Go To Database</em><br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%2011.01.41%20AM.png" alt="" /></li>
<li>In the dashboard, click on the <em>Connect</em> tab:<br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%2011.04.35%20AM.png" alt="" /></li>
<li>Create an application token:<br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%2011.09.38%20AM.png" alt="" /></li>
<li>Select the role <em>Administrator User</em> then click on <em>Generate Token</em><br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%2011.20.17%20AM.png" alt="" /></li>
<li>Make sure to copy the <em>Token</em> somewhere for later<br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%2011.23.58%20AM.png" alt="" /></li>
</ol>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token 
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="how-to-replicate-the-project"> </a>How to replicate the project:</h2>
<p>See -&gt; <a href="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra#prerequisites" target="_blank">Prerequisites first</a></p>
<p>Go to the directory where you would like your project to reside. If you are not sure what this means, open your Terminal app:</p>
<p><img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-18%20at%203.18.37%20PM.png" alt="" /></p>
<p>If you want your project to reside in your <code>Desktop</code> sub-directory for example, run (run means type this command in your terminal window):</p>
<pre lang="bash"><code>cd Desktop
</code></pre>
<p>Clone the project by running:</p>
<pre lang="bash"><code>git clone https://github.com/datastaxdevs/workshop-IOS-Swift-Astra.git
</code></pre>
<p>This is all that is needed to strictly connect to the database. However, the sample app uses ML Kit Text Recognition API to decipher prices from receipts.</p>
<p>The Pods required for this are way too big to be stored on Github, so either follow the steps to integrate them in your project by <a href="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra#integrate-pods-in-project" target="_blank">clicking here</a> or remove them from project by <a href="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra#remove-pods-from-project">clicking here</a>.</p>
<h4><a class="anchor" aria-hidden="true" id="integrate-pods-in-project"> </a>Integrate Pods in Project:</h4>
<ol>
<li>In the same window, go to your project directory by running</li>
</ol>
<pre lang="bash"><code>cd workshop-IOS-Swift-Astra
</code></pre>
<ol start="2">
<li>To install CocoaPods, run (if a password is required, use the one you use to log in to your laptop):</li>
</ol>
<pre lang="bash"><code>sudo gem install cocoapods
</code></pre>
<ol start="3">
<li>To install the Pods directory, run:</li>
</ol>
<pre lang="bash"><code>pod install
</code></pre>
<p>Now the pods are installed and the project will build once opened on Xcode!</p>
<h4><a class="anchor" aria-hidden="true" id="remove-pods-from-project"> </a>Remove Pods from project:</h4>
<ol>
<li>After cloning the git repo, go to your project directory by running:</li>
</ol>
<pre lang="bash"><code>cd workshop-IOS-Swift-Astra
</code></pre>
<ol start="2">
<li>Run these commands to remove the pods from the project (if a password is required, use the one you use to log in to your laptop):</li>
</ol>
<pre lang="bash"><code>sudo gem install cocoapods-deintegrate cocoapods-clean
pod deintegrate
pod cache clean --all
rm Podfile
</code></pre>
<ol start="3">
<li>Make sure to comment out the whole <em>MLTextRecognizer.swift</em> file once you are in Xcode because the import statements will cause problems if the Pods were deleted successfully. Also comment out this line in the <em>PictureReceipt.swift</em> file:</li>
</ol>
<pre lang="swift"><code>prices = try await getPricesAsArray(image: image)
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="whether-you-choose-to-remove-the-pods-or-keep-them-now-follow-the-steps-below"> </a>!! Whether you choose to remove the Pods or keep them, now follow the steps below !!</h3>
<ol>
<li>
<p>Launch the Xcode app and select <em>Open a project or file</em><br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-06-30%20at%204.45.29%20PM.png" alt="" /></p>
</li>
<li>
<p>Click on the <em>GroceryHandler.xcworkspace</em> file and select <em>Open</em><br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-18%20at%2011.24.10%20AM.png" alt="" /></p>
</li>
<li>
<p>Now make sure the project builds successfully by doing <kbd>command</kbd> + <kbd>B</kbd> in Xcode.</p>
</li>
<li>
<p>To test the app, you will have to change the environment variables in Xcode and create the collections <em>orders</em> and <em>userInfo</em>. The instructions can be found <a href="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra#how-to-connect-to-your-own-database-in-the-app" target="_blank">here</a>.</p>
</li>
<li>
<p>Make sure that the app will run on the iPhone 13 Pro Simulator:<br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-19%20at%201.36.11%20PM.png" alt="" /></p>
</li>
<li>
<p>Build the project and run the app by clicking the big play button at the top left of the Xcode window or by doing <kbd>command</kbd> + <kbd>R</kbd>.<br />
An iPhone Simulator window should pop up:<br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-20%20at%2011.20.18%20AM.png" alt="" /></p>
</li>
</ol>
<p><a href="https://developer.apple.com/documentation/xcode/running-your-app-in-the-simulator-or-on-a-device" target="_blank">Click here</a> or <a href="https://www.twilio.com/blog/2018/07/how-to-test-your-ios-application-on-a-real-device.html">here</a> to run it on your personal device instead. You will need a <a href="https://www.apple.com/shop/product/MQGH2AM/A/usb-c-to-lightning-cable-2-m">cable that connects to your laptop</a>.</p>
<p>If you get an error when trying to sign in, create an account, delete an account, or change password, it may be because you missed step 4. Make sure to finish that step before testing the app.</p>
<p>That's it! You can now create accounts and post orders to your database! If you would like to populate your database with fake accounts and random orders, uncomment the DEV button in the <em>ContentView.swift</em> file by removing the <em>/</em>* and *<em>/</em> that surrounds this code:</p>
<pre lang="swift"><code>Button(&quot;DEV&quot;){
    print(&quot;DEV&quot;)
    //This is where you can test functions by running the app and clicking on this button
    Task{
        await populateUserInfoDB()
        await populateOrdersDB(numNewOrders: 300)
    }
}
.buttonStyle(CustomButton(color:Color(red: 0, green: 0, blue: 0.5)))
.padding(.all, 20)
</code></pre>
<p>Run the app on your phone and click this button!</p>
<h2><a class="anchor" aria-hidden="true" id="how-to-connect-to-your-own-database-in-the-app"> </a>How to connect to your own database in the app:</h2>
<p>If you would like to connect to your Astra DB from this app, you will need to change these environment variables in Xcode: <code>ASTRA_DB_ID</code>, <code>ASTRA_DB_REGION</code>, <code>ASTRA_DB_TOKEN</code>, and <code>ASTRA_DB_KEYSPACENAME</code>.</p>
<p>The <em>ASTRA_DB_ID</em> can be found in the dashboard of the astra website:<br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%204.17.34%20PM.png" alt="" /></p>
<p>To change the values of the environment variables in Xcode, first click on <em>Edit Scheme...</em><br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%209.25.48%20AM.png" alt="" /></p>
<p>This will open the following window in which you can change the values of the environment variables:<br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-15%20at%204.11.06%20PM.png" alt="" /></p>
<p>The app accesses the environment variables in the <em>GroceryHandlerApp.swift</em> file:</p>
<pre lang="swift"><code>//environment variables https://blog.eidinger.info/use-environment-variables-from-env-file-in-a-swift-package
public var ASTRA_DB_ID:String? {
    ProcessInfo.processInfo.environment[&quot;ASTRA_DB_ID&quot;]
}
public var ASTRA_DB_REGION:String? {
    ProcessInfo.processInfo.environment[&quot;ASTRA_DB_REGION&quot;]
}
public var ASTRA_DB_TOKEN:String? {
    ProcessInfo.processInfo.environment[&quot;ASTRA_DB_TOKEN&quot;]
}
public var ASTRA_DB_KEYSPACENAME:String? {
    ProcessInfo.processInfo.environment[&quot;ASTRA_DB_KEYSPACENAME&quot;]
}
</code></pre>
<p>Xcode sets up the environment variables, which means that the app can only be run from Xcode. Once you run it on your phone once, the icon will still be in your phone even when it isn't connected to your computer anymore. However, if you click the icon and try to log in or post orders, the app will crash because the environment variables will not be set up.</p>
<h4><a class="anchor" aria-hidden="true" id="now-you-should-create-your-own-collection-using-swagger-ui"> </a>Now you should create your own collection using Swagger UI:</h4>
<p><img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-06-30%20at%204.46.48%20PM.png" alt="" /></p>
<p>You can access Swagger UI from the Astra website:<br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%204.39.36%20PM.png" alt="" /></p>
<p>To create an empty collection named <em>newCol</em> in <em>keyspacename1</em> for example:<br />
<img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-07-13%20at%209.48.09%20AM.png" alt="" /></p>
<p>The collections for the sample app are named: <em>userInfo</em> and <em>orders</em>. They are both in the keyspace <em>gh_orders_userinfo</em>. If you want to customize the app by creating different collections, make sure to change using search and replace (in the <em>DBController.swift</em> file) the <em>userInfo</em> and <em>orders</em> to whatever you named them.</p>
<p>If you just want to test the app, you will have to create both of these collections in whatever keyspace you created.</p>
<p>The JSON to create the collection <em>userInfo</em> is the following:</p>
<pre lang="json"><code>{&quot;name&quot;:&quot;userInfo&quot;}
</code></pre>
<p>The JSON to create the collection <em>orders</em> is the following:</p>
<pre lang="json"><code>{&quot;name&quot;:&quot;orders&quot;}
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="creating-your-own-model"> </a>Creating your own model</h3>
<p>To customize your app, you will need to come up with a model of what the data will look like in the database.<br />
Here is what the model looks like for a <em>UserInfo</em>: (this can be found in the <em>GroceryHandlerApp.swift</em> file)</p>
<pre lang="swift"><code>struct UserInfo : Codable {
    let userName : String
    let password : String
}
</code></pre>
<p>Here is what the model looks like for an order:</p>
<pre lang="swift"><code>struct Order : Codable {
    let userName : String
    let receipt : [Item]
    var paid : Bool
    let time : String
}

struct Item : Codable {
    let price : Double
    let users : [String]
}
</code></pre>
<p>The <em>Codable</em> makes it so that instances of these structs can be converted to JSON data objects, which is needed to post them to the database.<br />
To be explicitly clear, an <em>Order</em> is posted to the collection <em>orders</em> and a <em>UserInfo</em> is posted to the collection <em>userInfo</em>.</p>
<h2><a class="anchor" aria-hidden="true" id="additional-information"> </a>Additional Information</h2>
<h3><a class="anchor" aria-hidden="true" id="for-beginners-to-swift"> </a>For beginners to Swift:</h3>
<p><a href="https://developer.apple.com/tutorials/swiftui" target="_blank">Click here</a></p>
<h3><a class="anchor" aria-hidden="true" id="interested-in-using-the-ml-in-your-own-app"> </a>Interested in using the ML in your own app?</h3>
<p><a href="https://developers.google.com/ml-kit/vision/text-recognition/ios" target="_blank">Click here</a> and/or look at the <em>MLTextRecognizer.swift</em> file</p>
<h3><a class="anchor" aria-hidden="true" id="intro-to-document-api"> </a>Intro to Document API</h3>
<p>Using the Document API for Astra means that data is stored in <em>keyspaces</em>. A <em>keyspace</em> can have multiple <em>collections</em> and a <em>collection</em> stores a list of <em>JSON documents</em>.</p>
<p>The picture below gives a graphical view of how data is stored for this sample app. There is only one <em>keyspace</em> and two <em>collections</em>. A JSON doc can be identified by its orange color.</p>
<p><img src="https://github.com/datastaxdevs/workshop-IOS-Swift-Astra/raw/master/READMEPictures/Screen%20Shot%202022-08-08%20at%202.32.24%20PM.png" alt="" /></p>
<p>Check out the <a href="https://docs.datastax.com/en/astra/docs/develop/dev-with-doc.html" target="_blank">Astra DB documentation</a> for more information.</p>
<h3><a class="anchor" aria-hidden="true" id="for-beginners-to-databases"> </a>For beginners to databases:</h3>
<p>The following will help you become comfortable with HTTP requests, URLs, and JSON.</p>
<p>First off, what does HTTP stand for? From <a href="https://www.codecademy.com/article/http-requests" target="_blank">CodeAcademy</a>:</p>
<pre><code>&quot;HTTP stands for Hypertext Transfer Protocol and is used to structure requests and responses over the internet.
HTTP requires data to be transferred from one point to another over the network.” 
</code></pre>
<p>The HTTP request methods that we will be using in this app are GET, POST, PATCH, and DELETE.<br />
GET and DELETE are self explanatory. POST is used to persist data to the database and PATCH is used to update data that is already in the database.</p>
<p>To connect to Datastax astra using the Document API, a specific URL, which includes the database specific properties is needed as below:</p>
<pre><code>https://ASTRA_DB_ID-ASTRA_DB_REGION.apps.astra.datastax.com/api/rest/v2/namespaces/ASTRA_DB_KEYSPACENAME/collections/{collection-id}
</code></pre>
<p>The <em>api/rest</em> in the URL is what triggers the Document API. There are other methods of access (including CQL, GraphQL, etc.)</p>
<p>This URL might be followed by something called a <em>Query String</em>. The URL and query string are separated by a question mark -&gt; ?</p>
<p>We will see an example of a query string in the examples below.</p>
<p>However, an HTTP request is more than just a URL. It is a URL, headers, a request method (GET, POST, DELETE, PATCH), and depending on the request method a JSON body.</p>
<p>We can perform HTTP requests in the terminal app using a command line tool called cURL, or client URL.</p>
<p>Before using cURL, run these commands in your Terminal window so that you won't have to copy these values more than once:</p>
<pre lang="bash"><code>export ASTRA_DB_ID=REPLACE_ME
export ASTRA_DB_REGION=REPLACE_ME
export ASTRA_DB_TOKEN=REPLACE_ME
export ASTRA_DB_KEYSPACENAME=REPLACE_ME
</code></pre>
<p>Make sure the variables were properly exported by running this command:</p>
<pre lang="bash"><code>printenv | grep ASTRA_DB
</code></pre>
<p>Or if you want to do it one variable at a time:</p>
<pre lang="bash"><code>echo $ASTRA_DB_REGION
</code></pre>
<p>Now let's go through a few examples.</p>
<h4><a class="anchor" aria-hidden="true" id="1-how-to-get-all-orders-max-of-20-from-the-collection-em-orders-em-for-the-username-em-andy1-em"> </a>1. How to GET all orders (max of 20) from the collection <em>orders</em> for the username <em>Andy1</em>:</h4>
<p>Notice that the collection “orders” has to have been created in your database.</p>
<p>Run this command in your Terminal:</p>
<pre lang="bash"><code>curl -X 'GET' &quot;https://$ASTRA_DB_ID-$ASTRA_DB_REGION.apps.astra.datastax.com/api/rest/v2/namespaces/$ASTRA_DB_KEYSPACENAME/collections/orders&quot;'?where=\{&quot;userName&quot;:\{&quot;$eq&quot;:&quot;Andy1&quot;\}\}&amp;page-size=20' -H 'accept: application/json' -H &quot;X-Cassandra-Token: $ASTRA_DB_TOKEN&quot;
</code></pre>
<p>As we can see, the HTTP method (GET), URL, query string, and headers (-H) are all there.</p>
<p>The query string is :</p>
<pre><code>where=\{&quot;userName&quot;:\{&quot;$eq&quot;:&quot;Andy1&quot;\}\}&amp;page-size=20
</code></pre>
<p><em>where</em> and <em>page-size</em> are parameters. The <em>&amp;</em> is a query string separator to pass multiple parameters in the URL.</p>
<p>The <em>page-size=20</em> is to specify that we want to GET a maximum of 20 orders (page-size cannot be greater than 20).</p>
<p>The header <em>accept: application/json</em> is to specify that we are expecting the format of the data to be retrieved to be in JSON format. If you are not familiar with JSON, a quick online research will be enough, it is simply a way of storing information.</p>
<p>The header <em>X-Cassandra-Token: $ASTRA_DB_TOKEN</em> is to specify the token generated by the person who created the database for security reasons. Only people with the token will be able to interact with the database.</p>
<h4><a class="anchor" aria-hidden="true" id="2-how-to-get-the-user-info-for-the-username-em-andy1-em-in-the-collection-em-userinfo-em"> </a>2. How to GET the user info for the username <em>Andy1</em> in the collection <em>userInfo</em>:</h4>
<p>Notice that the collection <em>userInfo</em> has to have been created in your database.</p>
<p>Run this command in your Terminal:</p>
<pre lang="bash"><code>curl -X 'GET' &quot;https://$ASTRA_DB_ID-$ASTRA_DB_REGION.apps.astra.datastax.com/api/rest/v2/namespaces/$ASTRA_DB_KEYSPACENAME/collections/userInfo&quot;'?where=\{&quot;userName&quot;:\{&quot;$eq&quot;:&quot;Andy1&quot;\}\}' -H 'accept: application/json' -H &quot;X-Cassandra-Token: $ASTRA_DB_TOKEN&quot;
</code></pre>
<p>Notice there are only 2 differences between this cURL command and the one from the first example: There is no <em>page-size</em> (since there is a max of 1 user info per person no need to specify how many docs we want to retrieve) and the collection-id is changed from <em>orders</em> to <em>userInfo</em>.</p>
<p>The JSON that is returned is of the following form:</p>
<pre lang="json"><code>{&quot;data&quot;:{&quot;ec47a067-d0a7-4f3b-8606-966aa39ce8e9&quot;:{&quot;password&quot;:&quot;itsdrewnow&quot;,&quot;userName&quot;:&quot;Andy1&quot;}}}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="3-how-to-post-a-new-user-info-with-username-em-testusername-em-and-password-em-testpassword-em-in-the-em-userinfo-em-collection"> </a>3. How to POST a new user info with username <em>testUsername</em> and password <em>testPassword</em> in the <em>userInfo</em> collection:</h4>
<p>Run this command in your Terminal:</p>
<pre lang="bash"><code>curl -X 'POST' &quot;https://$ASTRA_DB_ID-$ASTRA_DB_REGION.apps.astra.datastax.com/api/rest/v2/namespaces/$ASTRA_DB_KEYSPACENAME/collections/userInfo&quot; -H 'accept: application/json' -H &quot;X-Cassandra-Token: $ASTRA_DB_TOKEN&quot; -H 'Content-Type: application/json' --data '
    {
        &quot;userName&quot;:&quot;testUsername&quot;,
        &quot;password&quot;:&quot;testPassword&quot;
    }'
</code></pre>
<p>The main difference between this command and the ones in the other examples is the HTTP method, which is POST.</p>
<p>There is also an additional header <em>Content-Type: application/json</em> which is to specify that the data to be persisted to the database is in JSON format.</p>
<p>The data itself is passed after the <em>--data</em></p>
<p>This cURL command can be used to POST an order as well. All that has to be changed is the collection-id from <em>userInfo</em> to <em>orders</em> as well as the data itself.</p>
<p>By now you should be able to perform HTTP requests and interact with your Astra Database from the command line. Doing this from a Swift app is very similar so understanding the cURL commands is going to be extremely helpful.</p>
<p>The structs/classes needed to perform HTTP requests from a Swift app are JSONEncoder, URLRequest, and URLSession.</p>
<p>The <a href="https://developer.apple.com/documentation/foundation/jsonencoder" target="_blank">JSONEncoder</a> class makes it easy to convert a struct into a JSON type which can then be posted to a collection of the Astra DB. The <a href="https://developer.apple.com/documentation/foundation/urlrequest">URLRequest</a> struct encompasses the information regarding the HTTP request. This entails the URL, the HTTP method, and the HTTP headers. The <a href="https://developer.apple.com/documentation/foundation/urlsession">URLSession</a> class handles actually performing the request to the server.</p>
<p>Check out the <a href="https://docs.datastax.com/en/astra/docs/develop/dev-with-doc.html" target="_blank">Astra DB documentation</a> for more information and lots more examples of using cURL to connect to your database using the Document API.</p>
<h2><a class="anchor" aria-hidden="true" id="the-end"> </a>The End</h2>
<p>Congratulations, you made it to the end!</p>
<p>See you next time!</p>
<blockquote>
<p>DataStax Developers</p>
</blockquote>

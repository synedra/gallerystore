<h1><a class="anchor" aria-hidden="true" id="getting-started-with-apache-cassandratm-and-c-using-datastax-astra"> </a>Getting Started with Apache Cassandra™ and C# using DataStax Astra</h1>
<p>This provides an example REST backend built in C# using .NET Core 2.1 for use with the <a href="https://github.com/DataStax-Examples/getting-started-with-astra-ui" target="_blank">Getting Started with Astra UI</a>.</p>
<p>Create a free-forever Cassandra Database with DataStax Astra: <a href="https://astra.datastax.com/register?utm_source=devplay&amp;utm_medium=github&amp;utm_campaign=getting-started-with-astra-csharp" target="_blank">click here to get started</a> 🚀</p>
<p>Contributors:</p>
<ul>
<li><a href="https://github.com/bechbd" target="_blank">bechbd</a></li>
<li><a href="https://github.com/msmygit" target="_blank">msmygit</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>How to connect to Astra via the Secure Connect Bundle</li>
<li>How to manage a Cassandra Session within a .NET web application</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="project-layout"> </a>Project Layout</h2>
<p>This sample also contains several interesting files that worth noting specifically:</p>
<ul>
<li><a href="Services/AstraService.cs" target="_blank">Services/AstraService.cs</a> - This file contains all the logic for connecting to the Astra database using the secure connect bundle.</li>
<li><a href="Startup.cs" target="_blank">Startup.cs</a> - This file contains the logic for adding a singleton for the Session object for reuse across our application.</li>
</ul>
<p>See <a href="https://docs.datastax.com/en/devapp/doc/devapp/driversBestPractices.html#Useasinglesessionobjectperapplication" target="_blank">here</a> for additional details on how the session object in Cassandra works and why it is best practice to only have a single Session object per application</p>
<ul>
<li>
<p><a href="schema.cql" target="_blank">schema.cql</a> - The database schema required for the Astra keyspace</p>
</li>
<li>
<p><a href="Controllers/InstrumentsController.cs" target="_blank">Controllers/InstrumentController.cs</a> - If you would like to see how to implement paging in C# then this would be the place to look.  Paging in Cassandra is different than what you are likely used to so it is beneficial to read <a href="https://docs.datastax.com/en/devapp/doc/devapp/driversResultPaging.html">this</a> article describing how paging works with Cassandra.</p>
</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="how-this-sample-works"> </a>How this Sample Works</h2>
<p>This is am example .NET Core Web API backend for use with the Astra Getting Started UI which is found <a href="https://github.com/DataStax-Examples/getting-started-with-astra-ui" target="_blank">here</a>.</p>
<p>This application serves as the connection between the UI website and an underlying Astra database.</p>
<p>It has Swagger installed so once it is running you can look at the Swagger UI here:</p>
<p><code>http://localhost:5000/swagger/index.html#/</code></p>
<h3><a class="anchor" aria-hidden="true" id="connecting-to-astra-with-a-secure-connect-bundle"> </a>Connecting to Astra with a Secure Connect Bundle</h3>
<p>To see how to connect to Astra using the Secure Connect Bundle you can look at the <code>ConnectToAstra()</code> method in <a href="Services/AstraService.cs" target="_blank">Services/AstraService.cs</a>.  In this method you will find the code which:</p>
<ol>
<li>
<p>Creates a <code>Cluster</code> instance using the builder.</p>
<p><code>var session = Cluster.Builder()</code></p>
</li>
<li>
<p>Specifies the local file path to the Secure Connect Bundle ZIP file that has been downloaded from your Astra Database.</p>
<p><code>.WithCloudSecureConnectionBundle(secureConnectBundlePath)</code></p>
</li>
<li>
<p>Set the username and password for your Astra Database</p>
<p><code>.WithCredentials(username, password)</code></p>
</li>
<li>
<p>Set the default Consistency Level to <code>LOCAL_QUORUM</code>.  <code>LOCAL_QUORUM</code> is the only supported consistency level for Astra queries.</p>
<p><code>.WithQueryOptions(new QueryOptions().SetConsistencyLevel(ConsistencyLevel.LocalQuorum))</code></p>
</li>
<li>
<p>Build the <code>Cluster</code> object then connect to your Astra database specifying the keyspace to use.</p>
<p><code>.Build().Connect(keyspace);</code></p>
</li>
</ol>
<p>Once you have completed all these steps you will now have a fully configured, connected, and ready to run CQL queries.</p>
<h3><a class="anchor" aria-hidden="true" id="managing-cassandra-session-within-a-net-web-application"> </a>Managing Cassandra Session Within a .NET Web Application</h3>
<p>Creation of <code>Session</code> objects within an application is an expensive process as they take awhile to initialize and become aware of the clusters topology.  Due to this it is a best practice to create a <code>Session</code> object once per application and reuse it throughout the entire lifetime of that application.  When building an ASP.NET Core application as shown this is easily supported through the use of singleton and .NET Core's built in Dependency Injection mechanisms.</p>
<p>For our Web API endpoints we created a singleton instance of our <code>AstraService</code> object inside the <code>ConfigureServices()</code> method in <a href="Startup.cs" target="_blank">Startup.cs</a> using the following code:</p>
<p><code>services.AddSingleton(typeof(Interfaces.IDataStaxService), typeof(Services.AstraService));</code></p>
<p>This code specifies that we are adding a singleton instance of <code>AstraService</code> for any dependency requiring an object instantiating the <code>Interfaces.IDataStaxService</code> interface.</p>
<p>To use this within our controllers, we need to specify a property on the constructor of the controller that requires the <code>Interfaces.IDataStaxService</code> interface as shown below.</p>
<p><code>        public CredentialsController(IDataStaxService service) { Service = service; }</code></p>
<p>With each call to the <code>CredentialsController</code> the <code>AstraService</code> singleton we created at startup will be passed to the constructor.  This mechanism of dependency injection allows us a simple mechanism to use a single <code>Session</code> object throughout the entirety of the application lifecycle.</p>
<h2><a class="anchor" aria-hidden="true" id="setup-and-running"> </a>Setup and Running</h2>
<h3><a class="anchor" aria-hidden="true" id="prerequisites"> </a>Prerequisites</h3>
<ul>
<li>.NET Core 2.1</li>
<li>An Astra compatible C# driver, instructions may be found <a href="https://helpdocs.datastax.com/aws/dscloud/astra/dscloudConnectCsharpDriver.html" target="_blank">here</a> to install this locally.</li>
<li>An Astra database with the CQL schema located in <a href="schema.cql" target="_blank">schema.cql</a> already added.</li>
<li>The username, password, keyspace name, and secure connect bundle downloaded from your Astra Database.  For information on how to obtain these credentials please read the documentation found <a href="https://helpdocs.datastax.com/aws/dscloud/astra/dscloudObtainingCredentials.html" target="_blank">here</a>.</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="running"> </a>Running</h3>
<p>This application is a .NET 2.1 web application configured to serve it's web application via the Kestrel web server.  This sample can be run from the root directory using:</p>
<p><code>dotnet run</code></p>
<p>This will startup the application running on <code>http://localhost:5000</code></p>
<p>You will know that you are up and working when you get the following in your terminal window:</p>
<pre><code>Hosting environment: Development
Content root path: /Users/dave.bechberger/Documents/projects/bechbd/getting-started-with-astra-csharp
Now listening on: http://localhost:5000
Application started. Press Ctrl+C to shut down.
</code></pre>

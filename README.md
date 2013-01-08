Maven coordinates
-----------------

&lt;dependency>
   &lt;groupId>org.glassfish.samples&lt;/groupId>
   &lt;artifactId>twitter-api&lt;/artifactId>
   &lt;version>1.0-SNAPSHOT&lt;/version>
&lt;/dependency>

## Additional Dependencies 

The implementation of this API uses Jersey OAuth Filters for authentication with Twitter. 
The following additional dependencies are required if any API that requires 
authentication is used.

    &lt;dependency>
        &lt;groupId>com.sun.jersey.contribs.jersey-oauth&lt;/groupId>
        &lt;artifactId>oauth-client&lt;/artifactId>
        &lt;version>1.11&lt;/version>
    &lt;/dependency>
    &lt;dependency>
        &lt;groupId>com.sun.jersey.contribs.jersey-oauth&lt;/groupId>
        &lt;artifactId>oauth-signature&lt;/artifactId>
        &lt;version>1.11&lt;/version>
    &lt;/dependency> 


## How to get started ?

    @Inject Twitter twitter;

in a Java EE managed component (such as Servlet).

A non-secure invocation of the API looks like

    SearchResults result = twitter.search("glassfish", SearchResults.class);
    for (SearchResultsTweet t : result.getResults()) {
       out.println(t.getText() + "&lt;br/>");
    }


## How to view the REST payload ?

Implementation of the API uses JDK logging. The logger name is:

org.glassfish.samples.twitter.api

If the project is deployed on GlassFish 3.x, then add the following line to 
glassfish/domains/domain1/config/logging.properties

org.glassfish.samples.twitter.api.level=&lt;LEVEL>

where &lt;LEVEL> can be SEVERE, WARNING, INFO, CONFIG, FINE, FINER, FINEST



# BasicAuthentication.WebAPI

# What Is Basic Authentication?

When we are trying to protect some resources (for example, an operation on a backend API, or maybe access to some data), we require some kind of authentication to secure this access. This requires the consumer to identify themselves to the target server, to gain access to the resource it requires. It does this via the Authorization header in the HTTP Request.

# A sample Basic Authentication header might look like this:

Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=

The value comprises the word Basic (to identify the scheme), followed by a space, followed by a Base-64 encoded value of a username/password combination, in the format of username:password. 

# Comparing Basic Authentication to Other Authentication Schemes

Since Base-64 is a very simple algorithm with no encryption which is easy to reverse, any attacker could easily figure out the username and password and issue that same request to gain access. Furthermore, since the credential is passed in every request, it’s very simple for an attacker to impersonate the real user. 


## Usage/Examples

Both client and server apps utilise a user secrets file :

{
  "BasicAuthenticationUsername": "basicUsername",
  "BasicAuthenticationPassword": "basicPassword"
}

## Correct Use of HttpClient

Often seen static instances of HttpClient expose several issues, including DNS caching issues, repeating configuration code and incorrectly disposing of resources to name a few. (https://learn.microsoft.com/en-us/dotnet/fundamentals/networking/http/httpclient-guidelines) .A beeter approach is to use the HttpClientFactory. 



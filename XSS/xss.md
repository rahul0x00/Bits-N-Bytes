# What is XSS?

XSS also knows as Cross-site scripting occurs when attackers or malicious users can manipulate a web site or web application to return malicious JavaScript to users. When this malicious JavaScript is executed in the user’s browser, all of the user’s interactions with the site (including but not limited to authentication and payment) can be compromised by the attacker.


## Types of XSS

There are primarily 3 types of XSS:

### 1.DOM-bases XSS

This type of XSS occurs when user input is manipulated in an unsafe way in the DOM (Document Object Map) by JavaScript. For example, this can occur if you were to read a value from a form, and then use JavaScript to write it back out to the DOM. If an attacker can control the input to that form, then they can control the script that will be executed. Common sources of DOM-based XSS include the eval() function and the innerHTML attribute, and attacks are commonly executed through the URL. PortSwigger has a great article on this. I've included an example below:

    const username = document.getElementById('username_input');
    const username_box = document.getElementById('username_box');
    user_name_box.innerHTML = username;

To exploit this vulnerability, you could insert a malicious script into the input that would be executed:

    <script>window.alert("Cross site scripting has occurred!");</script>
    
### 2.Reflected XSS

Reflected XSS is similar to DOM-based XSS: Reflected cross-site scripting (or XSS) arises when an application receives data in an HTTP request and includes that data within the immediate response in an unsafe way.  An example would be where the server will place the requested application route/URL in the page that is served back to the user. An attacker can construct a URL with a malicious route that contains JavaScript, such that if a user visits the link, the script will execute.

Malicious URLs containing cross-site scripting are commonly used as social engineering helpers in phishing emails or malicious links online.

Here’s an example — given a route that will 404,

    GET https://example.com/route/that/will/404
a vulnerable server might generate the response like so:

    <h1>404</h1>
    <p> Error: route "/route/that/will/404 was not found on the server</p>

An attacker could exploit this by constructing a URL like this:

    https://example.com//route/that/will/404/<script>alert('XSS!');
    
When the user loads the page, the URL will be templated into the page, the script tags will be interpreted as HTML, and the malicious script will execute. PortSwigger has a great article[! https://portswigger.net/web-security/cross-site-scripting/reflected] on this as well.



    

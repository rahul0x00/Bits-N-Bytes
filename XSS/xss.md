# What is XSS?

XSS also knows as Cross-site scripting occurs when attackers or malicious users can manipulate a web site or web application to return malicious JavaScript to users. When this malicious JavaScript is executed in the user’s browser, all of the user’s interactions with the site (including but not limited to authentication and payment) can be compromised by the attacker.


## Types of XSS

There are primarily 3 types of XSS:

### 1.DOM-bases XSS

This type of XSS occurs when user input is manipulated in an unsafe way in the DOM (Document Object Map) by JavaScript. For example, this can occur if you were to read a value from a form, and then use JavaScript to write it back out to the DOM. If an attacker can control the input to that form, then they can control the script that will be executed. Common sources of DOM-based XSS include the eval() function and the innerHTML attribute, and attacks are commonly executed through the URL. PortSwigger has a great article on this. I've included an example below:

    const username = document.getElementById('username_input');
    const username_box = document.getElementById('username_box');
    user_name_box.innerHTML = username;


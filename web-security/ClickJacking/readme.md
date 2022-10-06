# ClickJacking

ClickJacking also known as UI Redress attack is an attack that tricks, user into thinking they are clicking on one thing 
when they are actually clicking on malacious button. The attacker achieve this using opaque layers to hide the one web 
page onto another(Thanks to HTML iframes).

ClickJacking is done by using a HTML feature named <iframe>. This <iframe> tag is helpful when you want to embed a page 
within another page.

### How Clickjacking is Dangerous?

* An attacker is basically "Hijacking" the clicks that were meant for the original website.
            
* Assume on a website there's a button to download the executable file,what if hackers overlay
  that button and trick the user to download the malware.           

* KeyStrokes can also be Hijacked   
    
#### Scenario:   
            
For example, imagine an attacker who builds a web site that has a button on it that says “click here for a free iPod”.
However, on top of that web page, the attacker has loaded an iframe with your mail account, and lined up
exactly the “delete all messages” button directly on top of the “free iPod” button. The victim tries to 
click on the “free iPod” button but instead actually clicked on the invisible “delete all messages” button.
In essence, the attacker has “hijacked” the user’s click, hence the name “Clickjacking”.
            

Clickjacking also made the news in the form of a Twitter worm. This clickjacking attack convinced users to click on a button which caused them to re-tweet the location of the malicious page, and propagated massively.            

#### Prevention

* Another option is to use the X-Frame-Options HTTP header. It allows an application to specify whether frame use is simply denied, via the DENY value, or the use of frames is allowed, by the SAMEORIGIN or ALLOW-FROM values. Mainstream modern browsers do support this header option, but other browsers may not.

Possible X-Frame-Options:

            X-Frame-Options: DENY
            X-Frame-Options: SAMEORIGIN
            X-Frame-Options: ALLOW-FROM https://example.com/

* The iften method for clickjacking defense is to use Content Security Policy (CSP) and its frame-ancestors directive. 
  This directive allows the application developer to disallow all frame use or specify where it is allowed, similar to X-Frame-Options. 
  CSP is not available in all browsers, and browser plugins and add-ons may be able to bypass the policy. If both the X-Frame-Options 
  header and CSP frame-ancestors are used, browsers are supposed to prefer CSP’s directives, but not all will.

        Possible CSP frame-ancestor settings:

            Content-Security-Policy: frame-ancestors 'none'
            Content-Security-Policy: frame-ancestors 'self'
            Content-Security-Policy: frame-ancestors example.com

Because none of these defenses are perfect, defense-in-depth is a good practice, and there is nothing wrong with using all three defenses on your websites.
  

#### Other Resources
  
https://owasp.org/www-community/attacks/Clickjacking <br>
https://www.synopsys.com/glossary/what-is-clickjacking.html  
  

#### Credits
            
[@OWASP](https://owasp.org/www-community/attacks/Clickjacking)      
[@synopsis](https://www.synopsys.com/glossary/what-is-clickjacking.html)
      
  


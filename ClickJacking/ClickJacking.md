# ClickJacking

ClickJacking also known as UI Redress attack is an attack that tricks, user into thinking they are clicking on one thing 
when they are actually clicking on malacious button. The attacker achieve this using opaque layers to hide the one web 
page onto another(Thanks to HTML iframes).

ClickJacking is done bby using a HTML feature named <iframe>. This <iframe> tag is helpful when you want to embed a page 
within another page.

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
  
https://owasp.org/www-community/attacks/Clickjacking
https://www.synopsys.com/glossary/what-is-clickjacking.html  
  

#### Credits
  
      * [@synopsis](https://www.synopsys.com/glossary/what-is-clickjacking.html)
      
  


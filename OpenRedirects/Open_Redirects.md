# Open Redirects

Open Redirect makes easier for Hacker/Attacker to direct Users to Malcious resources. This vulnerability also known as Open URL Redirects.

Websites often automatically redirect users. It happens all the time for simple reasons like redirecting from the HTTP version of a website to the encrypted HTTPS version, or when sites 
change their endpoint location.

##### One Scenario:

For example when an unauthenicated user try to access a page that requires logging in ,
Then the website automatically redirects the user to Login Page and then returns to the original page if the user gets authenicated.

For example, a user goes to https://www.example.com/dashboard and if the user is not authenticated the website might redirect them 
to https://www.example.com/login. To later redirect to the previous location, the website needs to remember which page they intended 
to access before they were redirected to login page.And the previous location(or original location) is appended to the url.

*For example url  would look like this
          
    https://example.com/login/?redir=https://example.com/dashboard
    
#### How dangerous is Open Redirects
* An attacker can trick the user to redirect to their controlled domain somewhere else.
* An attacker can deliver malware to user and the user will download it knowing that it was from a legitimate website.
* Can steal the credentials of the user

##### Some of the URL Redirect are as :

/url?q=
login.aspx?redirect=
login?redir=
login?redirect-url=
login?next=
login?u=
/url?sa=t&url=
/external-link.jspa?url=
/proxy.php?link=
/redir.asp?url=
/page/pmv?url=
/exit.aspx?url=
/bitrix/redirect.php?event1=&event2=&event3=&goto=
/register/crowdsupport?gotoURL=

### Prevention

* Website often validates either by whitelisting or blacklisting by implementing URL validators to ensure that the provided URL is legimitate. 
* Check the Referrer When Doing Redirects
* Disallow Offsite Redirects

##### Other Resources 

https://www.acunetix.com/blog/web-security-zone/what-are-open-redirects/

##### Credits

    [@rahul0x00](https://twitter.com/rahul0x00)
   

# WHMCS Hooks and Modules
A collection of free hooks and modules for WHMCS.

## List of hooks

- [Fix IntoDNS URLs](#fix-intodns-urls)
- [Prevent spoofing URL for knowledgebase articles](#prevent-spoofing-url-for-knowledgebase-and-announcement-articles)
- [Force user login](#force-user-login)

## List of modules

- [Password Change for WHMCS](#password-change-for-whmcs)

## WHMCS Hooks
### Fix IntoDNS URLs
IntoDNS removed the DNS records for www.intodns.com. All links to IntoDNS in the WHMCS Admin Area are hardcoded
with the www subdomain.
This hook removes 'www' from the URLs when viewing a client's services or domains.
**Note** It seems that IntoDNS added DNS records for www again (at least as of 7th of August 2023). Unless they remove it again, there's no need to use this hook.

[🔗 Check the code](hooks/FixIntoDNSURLs.php)
___
### Prevent spoofing URL for knowledgebase and announcement articles
As long as you leave the ID for the knowledgebase or announcement article in the URL, you can change the URL to whatever you want. 
The following is an example of how the URL can be spoofed:<br>
Original: https://example.com/client/knowledgebase/129/How-do-I-add-another-domain-to-my-webhosting-account.html <br>
Changed URL: https://example.com/client/knowledgebase/129/This-URL-will-stil-work.html

That could potentially be bad for your website's SEO. 

This hook prevents that behaviour and will always redirect back to the original URL.

[🔗 Check the code](hooks/FixURLSpoofing.php)
___
### Force user login
Force the user to login before they are able to access any content on the WHMCS installation. 
The user will be redirected to the login form unless they are already trying to log in or register an account.

[🔗 Check the code](hooks/ForceUserLogin.php)

---
## WHMCS Modules
### Password Change for WHMCS
Allows admins to set a specific password for a client account. New password can be sent to the client.

[🔗 Check the code](modules/addons/WHMCSPasswordChange)

---
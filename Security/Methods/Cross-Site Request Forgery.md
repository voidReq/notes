# BASICS
- Making HTTP(S) requests on behalf of the victim, carrying out unwanted actions
- Attackers can host their own action item on a website that, upon being called, will make a request from another site carrying out some request
	- Could be an iframe with a form inside it, and the form is executed as soon as the site loads
- For instance, let's say xyz site has a button:
```html
<form method="POST" action="https://goonsite.org/do_action">
	<input type="text" name="msg" value="val">
	<input type="submit" value="Submit">
</form>
```
- it will make a request like so:
```
POST /do_action
Host: goonsite.org
Cookie: cookie=%insert_a_cookie%

(POST request body)
content="val"
```
- If a hacker makes their own input box that makes this same post, they can execute the request on behalf of the site visitor

# PREVENTION & BYPASSING
- Sites will typically include CSRF tokens somewhere in their webpage, that will be included in the POST and then validated
	- Included by default with most frameworks
	- Can try to exploit improper authentication
		- Delete token parameter from request
		- Blank CSRF parameter in request
		- Try to see if CSRF token is always the same
		- Try using your token instead of the victim's token, in their request
		- See if CSRF token can be reverse engineered
	- Sometimes sites use Double-Submit CSRF Tokens
		- Once in the cookie, once in the request body
		- Often checks if the token in cookies is same as token in request
- `SameSite` cookies ensures that requests must originate from the host site
	- However, you can still make GET requests on some websites
	- Sometimes, you can explicitly set `SameSite` in a session cookie to `None`
- You can try to create an iframe of the page, and see if it works.
	- If so, the website may be vulnerable to clickjacking
- Sites will occasionally check the referrer header to ensure sam-esite
	- Try to remove
		```html
		<!-- Meta tag will tell browser not to include referrer in the request -->
		<meta name="referrer" content="no-referrer">
		<!-- Rest of the CSRF attacker's page -->
		```
	- Can try to include victim's name in the request
		- As a subdomain
			- `Referer: goonsite.org.attacker.com`
		- As a page
			- `Referer: attacker.com/goonsite.org`
- XSS can also act as a vector toward bypassing CSRF protections, by stealing the CSRF token and allowing crafting of forged requests
# OTHER
- 
![[Pasted image 20241028125326.png]]

![[Pasted image 20241028125808.png]]

For cookies, when we try to sign in the server verifies the credentials and then send a 'set-cookie' header in the response that sets the cookie in the client's browser, once the cookie is set it will be automatically send with every subsequent request that goes to the server. we don't need to attach any additional headers like auth header how we used to do with localstorage JWT tokens.


![[Pasted image 20241028132247.png]]


CSRF Attacks

![[Pasted image 20241028134310.png]]


We use useState hook to do state management in react. Basically for example if we are defining a login page we create a state variable for email and one for password and update the states of both of those variables when user enters the email and password.

![[Pasted image 20240403141337.png]]

As you can see in this code, we set a state variable called email with a default null value `" "`.  Then on the TextField code we added the `onChange` function in which we updated the value of email variable using set variable using setEmail.

e.target is the same as writing document.getElementById

![[Pasted image 20240403142727.png]]

This is how we send the token as a bearer header from local storage to verify whether the user is authenticated or not.

This is the code for middleware we are using:

![[Pasted image 20240404111117.png]]




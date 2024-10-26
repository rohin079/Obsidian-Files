## Checkout Payment Architecture

![[Pasted image 20241026113422.png]]

1. Send a request to PayU provided API with correct payload to initiate a payment that will redirect to payU's website from merchant's website.
   
   Sample request :

curl -X POST "https://test.payu.in/_payment" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "key=JP***g&txnid=PQI6MqpYrjEefU&amount=10.00 &firstname=PayU User&email=test@gmail.com&phone=9876543210 &productinfo=iPhone&surl= https://apiplayground-response.herokuapp.com/ &furl=https://apiplayground-response.herokuapp.com &hash=05a397501918ec5c36ae52daa3b3e49b43e986b86940e109d060076e467c3ea7536617df7420e0e6863dced8c5b45f9fff15c13bdf0335512c05f0210b31b072"

Example payment :
![[Pasted image 20241026122430.png]]

![[Pasted image 20241026122457.png]]







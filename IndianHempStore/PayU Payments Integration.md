## Checkout Payment Architecture

![[Pasted image 20241026113422.png]]

1. Send a request to PayU provided API with correct payload to initiate a payment that will redirect to payU's website from merchant's website.
   
   Sample request :

curl -X POST "https://test.payu.in/_payment" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "key=JP***g&txnid=PQI6MqpYrjEefU&amount=10.00 &firstname=PayU User&email=test@gmail.com&phone=9876543210 &productinfo=iPhone&surl= https://apiplayground-response.herokuapp.com/ &furl=https://apiplayground-response.herokuapp.com &hash=05a397501918ec5c36ae52daa3b3e49b43e986b86940e109d060076e467c3ea7536617df7420e0e6863dced8c5b45f9fff15c13bdf0335512c05f0210b31b072"

Example payment :
![[Pasted image 20241026122430.png]]

![[Pasted image 20241026122457.png]]


Integration security

](https://docs.payu.in/docs/handling-the-redirect-urls)[](https://docs.payu.in/docs/integrate-with-payu-hosted-checkout#integration-security)

[After receiving a response from PayU, you must calculate the hash again and validate it against the hash that you sent in the request to ensure the transaction is secure. PayU recommends implementing the transaction details APIs and webhook/callback as an extra security measure. For more information on this process, refer to](https://docs.payu.in/docs/handling-the-redirect-urls) [Get Transaction Details API](https://docs.payu.in/reference/get_transaction_details_api) APIs and [Webhooks](https://docs.payu.in/docs/webhooks) documentation.

https://docs.payu.in/docs/generate-hash-payu-hosted


payment process - 

1. Take necessary details from the client like amount, productinfo, firstname, lastname, email, phone 
   
2. Send a post request to backend with that req body when, in the backend with that info generate : a) transactionID b) hash 

3. after generating the hash, return the hashed string, transaction id, along with merchant key to the client and form action in form of JSON object
   
   
![[Pasted image 20241026162216.png]]


**Payment Flow**:

1. User fills out payment form
2. Form submission is intercepted by JavaScript
3. Data is sent to your server's `/initiate-payment` endpoint
4. Server generates transaction ID and hash
5. Server returns payment data
6. JavaScript creates a new form with PayU fields
7. Form is automatically submitted to PayU
8. PayU processes payment and redirects to success/failure URL
9. Your server verifies the payment response
10. User sees success/failure message

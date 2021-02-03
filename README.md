# payments
###### author : Abhijeet Kumar
###### email : abhi1998thebond@gmail.com
###### Operating system used: Windows 10

Assignment Given:

Write a Flask Web API with only 1 method called “ProcessPayment” that receives a request like this

    -CreditCardNumber(mandatory, string, it should be a valid credit card number)
    -CardHolder (mandatory, string)
    -ExpirationDate (mandatory, DateTime, it cannot be in the past)
    -SecurityCode (optional, string, 3 digits)
    -Amount (mandatoy decimal, positive amount)

The response of this method should be 1 of the followings based on

    -Payment is processed: 200 OK
    -The request is invalid: 400 bad request
    -Any error: 500 internal server error
    
The payment could be processed using different payment providers (external services)called:

    -PremiumPaymentGateway
    -ExpensivePaymentGateway
    -CheapPaymentGateway.

The payment gateway that should be used to process each payment follows the next set of business rules:

    a)If the amount to be paid is less than £20, use CheapPaymentGateway.
    b)If the amount to be paid is £21-500, use ExpensivePaymentGateway if available. Otherwise, retry only once with CheapPaymentGateway.
    c)If the amount is > £500, try only PremiumPaymentGateway and retry up to 3 times in case payment does not get processed.
    
    
### How to run the project

Run the following command to do so.
    1. clone the project from git on your system 
    
    git clone https://github.com/abhi092/payments.git
    
   2. cd `payments`
   3. run command `pip env install`
   4. run to go in virtual environment, inside the project run command `pip env shell`
   5. run command to run the flask server `flask run`
   6. To exit server run `ctrl+c`
   7. To exit the virtual env run command in terminal `deactivate`
   
 ## How to test the application
 
   1. run the server first using above step
   2. in seperate terminal, run `cd application/test` ie go to test folder
   3. run to go in virtual environment, inside the project run command `pip env shell`
   4. Activate the virtual environment 
   4. run command: `pytest test12.py`
   
 ### Shortcoming OR consideration 
 
 1. ExpirationDate format is `yyyy/mm/dd` not `mm/dd` as found in the credit card usually.
 2. Testing of external payment gate should be done with there api (i don't know how to test that part without there api, if anyone know i would learn to do that).
 
 ### Note
 
 if you find this project help you to create the assignment in anyway, please fork or click on watch this project.

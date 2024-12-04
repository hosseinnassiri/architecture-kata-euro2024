
# Actors
- customer
- back office user
- teller 
- manager 

# Scenarios 
- Registration
- Request fund transfer
- Manual matching
- Transaction report for customer
- Settlement
- Cash in branch report

# Scenario Details 
## Registration 
- Customer provides identity documents
- Teller validates the documents and creates an account for the customer

## Request fund transfer by cash
- Customer requests fund transfer and provides amount, country, receiver information, source currency, destination currency, date.
  - Customer may determine the conditions for payments to receiver such as amount in each payment and so on.    
- Teller negotiates the rate with the customer. Teller uses the rate the already provided by the manager or asks the back office.
- Csutomer accepts the rate. 
- Teller validated the request's information and writes the rate and converted amount. 
- Teller receives the money in cash from the customer.
  - Customer could pay the money by installment.
  - Tellers issues the slips for each payment to the customer 

- Teller converts the fund to the destination currency. Teller uses the rate the already provided by the manager or asks the back office.
- Backoffice empoloyee calls the branch in the destination country and asks to transfer the moeny to the receiver and gives them the receiver's information.
- 

  

# 




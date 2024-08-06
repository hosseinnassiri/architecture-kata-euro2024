
![system context diagram](system-context.png "system context diagram").
# System Context Diagram
```mermaid
   C4Context
   title System context for UEFA EURO 2024 Ticketing
   System(ticketingSystem, "Ticketing System", "Allows customers to view <br/>fixtures and request tickets.")
   System_Ext(paymentGateway, "Payment Gateway system", "Performs different methods <br/>of payments.")
   System_Ext(notificationSystem, "Notification system", "Sends emails and <br/>notifications to customers.")
   Person_Ext(user, "User", "A customer who's<br/>  interested in watching the<br/>  game in the stadium.")
   Person_Ext(admin, "Admin", "UEFA administrator user <br/>who takes care of fixtures, <br/>ticket approvals, lottery draw.")
   Person_Ext(ticketAdmin, "Ticket Admin", "Ticket administrator ")
  
   Rel(user, ticketingSystem, "Uses")
   Rel(admin, ticketingSystem, "Uses")
   Rel(ticketAdmin, ticketingSystem, "Uses")
   Rel(ticketingSystem, paymentGateway, "Sends payment requests")
   Rel(ticketingSystem, notificationSystem, "Sends e-mail using")
   Rel(ticketingSystem, user, "Sends e-mails to")


```

# Container Diagram

```mermaid
   C4Container
   title Container diagram for Internet Banking System

   System_Ext(paymentGateway, "Payment Gateway system", "Performs different methods <br/>of payments.")
   System_Ext(notificationSystem, "Notification system", "Sends emails and <br/>notifications to customers.")
   Person_Ext(user, "User", "A customer who's<br/>  interested in watching the<br/>  game in the stadium.")
   Person_Ext(admin, "Admin", "UEFA administrator user <br/>who takes care of fixtures, <br/>ticket approvals, lottery draw.")
   Person_Ext(ticketAdmin, "Ticket Admin", "Ticket administrator ")
  
   Container_Boundary(c1, "Ticketing ") {
       Container(portal, "Portal", "ReactJS", "")
       Container(mobileApp, "Mobile App", "ReactJS Native", "")
       Container(backOffice, "Web Application", "ReactJS", "")
       ContainerDb(database, "Database", "Postgres Database", "")
       Container(backend, "Backend Application", "NodeJS", "")
       Container(backendAPI, "Backend REST API", "", "")
   }
   Rel(user, portal, "Uses", "HTTPS")
   Rel(user, mobileApp, "Uses")
   Rel(ticketAdmin, backOffice, "Uses")
   Rel(admin, backOffice, "Uses")

   Rel(portal, backendAPI, "User")
   Rel(mobileApp, backendAPI, "Uses", "")
   Rel(backOffice, backendAPI, "Uses", "")
  
   Rel_Back(database, backend, "Reads from and writes to", "sync, JDBC")

```

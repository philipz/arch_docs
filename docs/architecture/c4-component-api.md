# API Component Diagram

```mermaid
C4Component
    title Component diagram for Internet Banking System - API Application
    
    Container(spa, "Single-Page Application", "JavaScript and Angular", "Provides all of the Internet banking functionality")
    Container(ma, "Mobile App", "Xamarin", "Provides a limited subset of the Internet banking functionality")
    ContainerDb(db, "Database", "Oracle Database Schema", "Stores user registration information")
    
    Container_Boundary(api, "API Application") {
        Component(sign, "Sign In Controller", "Spring MVC Rest Controller", "Allows users to sign in")
        Component(accounts, "Accounts Summary Controller", "Spring MVC Rest Controller", "Provides customers with a summary of their bank accounts")
        Component(security, "Security Component", "Spring Bean", "Provides functionality related to signing in, changing passwords, etc.")
        Component(mbsfacade, "Mainframe Banking System Facade", "Spring Bean", "A facade onto the mainframe banking system")
        Component(emailComp, "E-mail Component", "Spring Bean", "Sends e-mails to users") // Renamed from email to avoid conflict with System_Ext(email)
    }
    
    System_Ext(mbs, "Mainframe Banking System", "Stores all core banking information")
    System_Ext(es, "E-mail system", "The internal Microsoft Exchange e-mail system")
    
    Rel(spa, sign, "Makes API calls to", "JSON/HTTPS")
    Rel(spa, accounts, "Makes API calls to", "JSON/HTTPS")
    Rel(ma, sign, "Makes API calls to", "JSON/HTTPS")
    Rel(ma, accounts, "Makes API calls to", "JSON/HTTPS")
    
    Rel(sign, security, "Uses")
    Rel(accounts, mbsfacade, "Uses")
    Rel(security, db, "Reads from and writes to", "JDBC")
    Rel(mbsfacade, mbs, "Makes API calls to", "XML/HTTPS")
    Rel(emailComp, es, "Sends e-mail using")
``` 
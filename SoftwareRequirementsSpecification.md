# cybuy - Software Requirements Specification 

## 1.	Introduction
![Landing Page](/mockups/Landing_Page.png)

### 1.1	Purpose
This Software Requirements Specification (SRS) describes all specifications for the webservice “cybuy”. It includes an overview about this project and its vision, detailed information about the planned features and boundary conditions of the development process.

### 1.2	Scope
Access to our webservice will be provided through a web interface on a website.
No standalone apps are planned.

Planned subsystems:
•	Account system:
Persistent accounts can be created, managed and deleted with the associated credentials.
User data is stored server side and if possible in hashed or encrypted form.
Exceptions may be made for image contents with third party hosting providers.

•	Marketplace infrastructure:
This core module of the webservice will allow users to add listings and view each other’s.
A suite of subpages will be used to visualize the listings filled with user provided data.

•	Messaging infrastructure:
An existing messaging framework is preferred alongside our own additions to allow for interactive messages to guide the flow of the negotiation process.

•	Payment subsystem:
A mask for payments will be provided, but this functionality will only be stubbed as this is not a commercial project.


### 1.3	Definitions, Acronyms, and Abbreviations
| Abbrevation | Explanation                            |
| ----------- | -------------------------------------- |
| SRS         | Software Requirements Specification    |
| n/a         | not applicable                         |
| tbd         | to be determined                       |

### 1.4	References
| Title                                                  | Organisation |
| ------------------------------------------------------ | ------------ |
| [Code Repository](https://github.com/Team-cybuy/cybuy) | Team cybuy   |
| [Blog](https://medium.com/@cybuysite)                  | Team cybuy   |

### 1.5	Overview
Over the following chapters a concrete vision for our project will form, starting with the Overall Description and slowly narrowing down to a more concrete idea.

## 2.	Overall Description

### 2.1	Vision
Inspired by platforms like “Shpock” and “eBay Kleinanzeigen” we strive to provide a more streamlined experienced with equal treatment of listings, opposed to the industry standard of offering commercial sellers preferred treatment. Ease of use and secure accounts are our top priority to ensure a good online negotiating experience.

### 2.2	Use Case Diagram
![Use Case Diagram](/resources/UseCaseDiagram.png)

### 2.3	Technology Stack
The technologies we will be using are:

Backend:
-	Spring Boot
-	PostgreSQL

Frontend:
-	Angular

IDE:
-	IntelliJ
-	Visual Studio Code

Project Management:
-	YouTrack
-	Github
-	Discord

Deployment:
-	Mono-/Modulithic Server

Testing:
-	JUnit

## 3.	Specific Requirements

### 3.1	Functionality
The following will detail the previously described Use Cases and their respective functionality.

-	Session Management System
    -   [Keep track of stats and reviews](/use_cases/KeepTrackOfStatsAndReviews.md)
    -   [Store your chats](/use_cases/StoreYourChats.md)
    -   [Populate profile page](/use_cases/PopulateProfilePage.md)
    -   [Staying logged in](/use_cases//StayingLoggedIn.md)
-	Social System
    -   [Send upfront offer](/use_cases/SendUpfrontOffer.md) (with Activity Diagram)
    -   [Chatting](/use_cases/Chatting.md)
    -   [Send offer during negotiation](/use_cases/SendOfferDuringNegotiations.md) (with Activity Diagram)
    -   [Update interactive message](/use_cases/UpdateInteractiveMessage.md)
    -   [Saving to favourites](/use_cases/SavingToFavourites.md)
    -   [Reporting](/use_cases/Reporting.md) (with Activity Diagram)
    -   [Manage own profile](/use_cases/ManageOwnProfile.md)
-	Account System
    -   [Account creation](/use_cases/AccountCreation.md) (UCRS [here](/use_cases/realization_specifications/UCRSAccountCreation.md))
    -   [Logging in](/use_cases/LoggingIn.md) (UCRS [here](/use_cases/realization_specifications/UCRSLoggingIn.md))
    -   [Logging out](/use_cases/LogginOut.md)
-	Inventory System
    -   [Searching](/use_cases/Searching.md)
    -   [Filtering](/use_cases/Filtering.md)
    -   [Create a listing](/use_cases/CreateAListing.md)
    -   [Manage own listing](/use_cases/ManageOwnListing.md)
-	Administration Subsystem
    -   [Manage users](/use_cases/ManageUsers.md)
    -   [Moderate reports](/use_cases/ModerateReports.md)
    -   [Manage listings](/use_cases/ManageListings.md)

### 3.2	Usability
In part fueled by our own frustration with the widely inconsistent looks across subpages of popular sites we plan to minimize clutter and make everything easy to read and use.

#### 3.2.1	Clutter free
We plan to not overwhelm the user with all sorts of buttons and hidden menus. Not much time should be needed to explore the site first. Components should act in an expected way.

#### 3.2.2	Easy on the eye
The scroll distance should be bigger and information density lower than on comparable sites, which are structured like social media websites without much regard for the single listing.

### 3.3	Reliability

#### 3.3.1	Availability
The plan is to have the service reachable for as much time as possible. Generally speaking, this can be accomplished by writing stable code and implement good sanitation of user inputs.
However, we must think about outside factors too, like DDOS attacks and spam bots. Mitigation for such threats could be accomplished with external services like “Cloudflare” however and will not be in scope for this project.

### 3.4	Performance
_Following soon_

#### 3.4.1	Capacity
Since Germans are our target audience and respecting the existing platforms, we aim to manage a few thousand requests in a short time at maximum. Further scalability can be discussed through the use of caching and more powerful hardware once response times start to get noticeable.
This fact combined with the relatively unknown task complexity strongly hints towards developing the website as a at least a Monolith and, if possible, at best a Modulith.

#### 3.4.2	Storage solutions
Text based listings should not be storage intensive, however accompanying images could be. This could be mitigated using external storage providers and resizing images before storing them.

#### 3.4.3	Response times
Response times should be fast wherever possible and offset by a clear loading indicator where necessary. It is important to minimize the number of round trips and to utilize asynchronous loading where possible.

### 3.5	Supportability
Readable code and comments are our goto way of ensuring this in the future. This repository and the weekly blog will function well as an additional resource. By working off of Spring Boot and Angular's wide use we also gain the support of our frameworks for the foreseeable future while the need to stick to something easier limits us in the realm of a mono-/modulith.

### 3.6	Design Constraints
Readability and usability come first for our general layout. As listings count as user generated content, we will try to provide simple guidelines for them too follow our lead.

No further constraints affecting our project are imposed by the use of Angular and Spring Boot.

### 3.7	On-line User Documentation and Help System Requirements
The interface itself should be intuitive to use, however it is not off the table to implement a first-time visitor tutorial and give hints while hovering over a button.

### 3.8	Purchased Components
No purchased components are planned to be used.

### 3.9	Interfaces

#### 3.9.1	User Interfaces
Check out [our Mockups](/mockups)!

#### 3.9.2	Software Interfaces
No native apps are planned, so the app should run well and consistent across the three major flavors of browsers.
Our API will be limited to use by our own Website only.

#### 3.9.3	Communications Interfaces
Communication will happen over API requests to our backend.

### 3.10	Licensing Requirements
No license has been decided as of yet. At worst the project will stay source available and at best receive a proper open source license.

### 3.11	Legal, Copyright, and Other Notices
No infringement on any other party also named “cybuy” or a variation thereof is intended, this is not a commercial product or storefront and will not generate revenue of any sort. The software is provided as is and without any warranty. The code is at least source available and at best open source. Licensing will be decided in the future. Unless annotated otherwise all code is © Team cybuy. Likewise our name and logo cannot be used in any commercial way except ad supported news coverage.

### 3.12	Applicable Standards
Clean code standards are desirable and may be followed wherever they don't hinder progress or limit our own styles.

## 4.	Supporting Information
For further information please reach out to the team via the associated blog, our e-mail or via the websites contact form.
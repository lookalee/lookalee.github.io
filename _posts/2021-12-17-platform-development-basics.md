---
layout: single
title: "Platform Development Basics"
tags: [salesforce, cloud]
categories: salesforce


---

## Platform Development Intro

- The salesforce platform supports development of other technologies on top of it, making it unique by the fact that it supports custom functions built by customers and partners. 
  - You can either customize existing Salesforce offerings or build something from scratch

- **Core platform**: allows development of custom apps, either mobile or desktop
- **Heroku platform**: allows development of highly scalable web apps and back-end services. Can sync with Salesforce easily.
- **Salesforce APIs**: allows developer to integrate data.
- **Mobile SDK**: Lets you build native, HTML5, and hybrid apps.

#### Developing without code

- The metadata-driven development model is one of the key differences between developing on platform (without code) and developing outsider of salesforce
  - The metadata, such as field names, type, account number, etc can be seen on record detail pages. 
  - This pre-built functionality frees up development time
- You can use Schema Builder to visualize and configure an app's data model without code.

#### Coding with Salesforce Languages

###### Lightning Components

- The lightning component framework is a user interface development framework used for both desktop and mobile. 
  - You can think of it as other frameworks like Angular JS, React, etc, except that Lightning Components are ready to integrate with Salesforce's business data.
- The developer console is a Salesforce integrated development environment that can be used to develop, debug, and test code. 
  - Navigation: Setup -> Lightning Components -> Map -> Developer Console
  - It is XML markup
  - Contains Aura-specific and static HTML tags 
  - Uses <namespace:tagName> convention for its tags
  - Uses client side Javascript controllers and server side Apex controllers.

###### Apex

- ex) Extending functionality of the low-code Process Builder by writing a little code to change how push notification works:
  - Navigation: Setup -> Process Builder -> Price Change Push Notification -> Push Notification -> Developer Console (from upper gear menu) -> File | Open -> Use filter bar to find PushPriceChangeNotification. -> Double click to open in developer console.
    - ![image-20211217180909238](/assets/images/image-20211217180909238.png)
    - The @InvocableMethod annotation is used to allow other tools (like Process Builder) to execute this method.
    - SOQL(Salesforce Object Query Language) is used to read records from database.

###### Visualforce

- Allows reation and customization of Salesforce pages and integration with other web tech such as HTML, CSS, JS.
- Lightning Components develop components that can be pieced together to create pages, while Visualforce develop entire pages at once. 

###### APIs

- There are various APIs provided by Salesforce, such as SOAP API, REST API, etc.

###### Heroku

- Heroku is a web dev platform that lets developers quickly build and deploy web apps.
- Provides lots of flexibility in how apps are written (can use Java, Python, etc)

###### IoT, Bots, etc

- Salesforce's IoT capabilities lets you collect and manage data about devices easily.
- Chatbots can be used to help navigate employees or customers.



###### **References**

- trailhead.salesforce.com's Platform Development Basics module
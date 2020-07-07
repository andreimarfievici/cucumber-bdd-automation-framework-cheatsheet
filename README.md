# cucumber-bdd-automation-framework-cheatsheet
How to build a Cucumber BDD web/mobile automation framework (principles and practices)

# Level 1: Features and Scenarios

- Start with Happy Path and then diverge
- Use reusable steps
- Use more declarative steps (leave details for step defs)
- Describe the WHAT, not the HOW
- Scenarios should be reusable on different devices, browsers etc.

# Level 2: DSL

- Use imperative fluent Domain Specific Language in step definitions
- Don’t hardcode anything, use modelling classes
- Think about your Data Model (Customer)
- Thing about your Page Domain (use Page Model)
- Assert a lot of stuff here (in your “should” assertion steps)
- This is where the models interact with each other (keep it abstract)

# Level 3: Domains

- Data Domain
- Page Domain
- Driver Domain

## Level 3.1: Data Domain

- A domain class is like an API
- A data model class has only attributes, it’s a view layer
- Use OOP (inheritance etc.)
- Use factories (builders) for creating different test data

## Level 3.2: Page Domain

- Use Page and Component Model design
- A page is a class in itself and has attributes (web elements) and actions with these attributes
- If a page gets too big, create sub components 
- Also, create reusable components (for forms, drop downs, header, footer etc.)
- Use OOP here (Main Page etc., abstract, interfaces for web/mobile)
- Use Finders to interact with elements

## Level 3.3: Driver domain

- This is where you customize your web driver that you use to interact with Pages
- Things like User Agent, Screen Sizes, Browser Types are all handled in here

# Level 4: The nitty gritty

- Finders
- Helpers
- etc.

## Level 4.1: Finders

- This is where you customize your browser interactions into more human readable generic methods
- Eg: searchByInnerText(), searchWithTimeout(), fillAllFormFields(), scrollIntoMiddle(), hoverOver() etc.
- Mix-up javascript, jquery, selenium etc. into easy methods
- You reuse finders in all other Pages

## Level 4.2: Helpers

- Helper methods to randomize data, sort, filter, deal with time, dates, databases, anything you can imagine

# General Observations

- Scenario tests should be agnostic to: Browser, Screen Sizes, Environments, Data types
- For this use configuration and resources files and create different running config profiles
- Folder structure and naming should be relevant eg: LoginFeature, LoginSteps, LoginPage, login() method
- Once you have implemented your first step, _RUN IT IN A PIPELINE!!!_






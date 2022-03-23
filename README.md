
# Angular Best Practices

All Best Practices Angular Projects


## Documentation


Angular development best practices indicate we should break our applications into modules.

## Modules
In Angular refer to a place where we group like components, services, directives, pipes, etc for our applications.
Feature Modules are the easiest to think about, we simply break these up by feature or domain. But what about the App Module, Core Module, & Shared Module?

### What should we put into each of them? What components should live in each of them? Why do we need all of them? Let's take a look at each of the types of modules and what they are used for.


### App Module

Lets first take a look at the App Module in Angular. The App Module can also be called the root module.

> Every app must have an App Module. We launch our applications by bootstrapping the App module.

We want to keep our App Module pretty compact. There should not be a lot of content in the App Module or App Component. We want to encapsulate our application into domain-specific modules, the Core Module, & the Shared Module, which we will look into now.

---

### Core Module

The Core Module is where we want to put our shared singleton services. So the services that we want only one instance of while having them shared among multiple modules should live here.

The Angular injector creates a new instance of a service for each lazily loaded module that it is provided.

> We want to keep our singleton services in the core module so only one instance is ever created. We do not want to spread them out in our feature modules.
Another piece of our application that should live in the Core Modules are app-level components. A good example of an app-level component would be the navigation bar. Only the app needs to know about our navigation component.

We do not want to put, are components used throughout the application inside of the Core Module. We have the Shared Module for that and we will look at that now.

---

### Shared Module

The Shared Module is where we want everything to live that is shared throughout the application. Components, directives, guards, & pipes can all live in the Shared Module.

>A loading spinner is something commonly found in the shared module. This is something you will want shared throughout your application.

It is also common to import and export Angular built modules inside your Shared Module if you need to access them in multiple locations. Because Shared is imported into many of your Feature Modules it's common to import/export Common Module or Angular Material modules. Import/Export the modules once in Shared Module and now anyone that imports Shared will have access to them.

---

### Feature Modules

Applications commonly have multiple Feature Modules. Depending on the size of your application you may have A LOT of Feature Modules. Breaking things up into domain-specific areas can help in the long run for development.

>Lazy loading is the main reason to break up your application into Feature Modules. You can load them as needed. If you want to learn more about lazy loading check out the Angular documentation on Lazy Loading Feature Modules.

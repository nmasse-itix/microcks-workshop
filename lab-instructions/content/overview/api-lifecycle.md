---
title: "The API Lifecycle"
weight: 1
---

*This post was originally published on the [Red Hat Developer Blog](https://developers.redhat.com/blog/2019/02/25/full-api-lifecycle-management-a-primer/)*.

As shown below, the API lifecycle is two-fold. The leftmost cycle covers the producer activities, while the rightmost cycle covers the consumer activities.

![Steps of the API Lifecycle](steps.png)

## What are the goals for your APIs?

Any API program has to start with a **Strategy** phase where you will have to define the goals you want to achieve with your APIs. It also specifies which markets you need to address, which resources you have at your disposal, the time frame you have in which to achieve your goals, and so on. This is a critical step to help you put effort where it matters the most.

The **Design** phase will ensure your organization uses a contract-first approach. This phase entails gathering feedback early, breaking the dependencies between projects, and reducing risks. Also, a contract-first approach is known to reduce the time to market.

In the **Design** phase, you design the contract of your API and share it with your future consumers. The outcome of the **Design** phase is an API contract that describes the messages that can be exchanged with your APIs.

## Specify your APIs

In the **Mock** phase, you will define meaningful payload examples of your APIs and try to refine your specifications with business expectations for common and edge cases. Those examples are then turned into a live mock that can be exposed to your first consumers. “Business expectations” entail everything that cannot be specified using a formal schema. An example could be that when querying items by status, all returned items must have the desired status. You could also think about mutually exclusive options or dependencies between fields: for example, if the field companyName is set, then the field accountType needs to be “enterprise.”

In an acceptance test-driven development approach, you will have to define your test cases, based on examples, before implementing your APIs. This will help refine the business expectations about your APIs; share them between developers, testers, and business customers; and later ensure your APIs conform to those expectations.

Here’s an example that will highlight the importance of the **Mock** and **Test** phases. If you are a retail company, you will have to return an error if someone under 21 tries to buy alcohol. That’s not something you can formally model in an API contract, but it will instead be reflected in your mocks and your tests.

## Develop and Deploy your APIs

Then, in the **Implement** phase, the actual API is **developed** using either an integration framework such as Red Hat Fuse or using the development language of your choice. Using an integration framework should be a key part of your APIs’ lifecycle to promote reuse, fast iterations, and value additions through orchestration. It also helps to modernize the existing parts of your information system. The usual agile development practices apply here.

In the **Deploy** phase, you will make sure you have a Continuous Integration/Continuous Deployment (CI/CD) pipeline that automates the delivery of your APIs to the production environment. The CI/CD pipeline reuses the tests you defined earlier to ensure the APIs to be deployed do not violate your specifications. Those integration tests are automated and run automatically as part of the pipeline.

The automated integration tests should also ensure the backward compatibility of your APIs. If a 1.2 version of an API is released, it must be backward compatible with any release of the 1.x branch (1.0, 1.1, and so on).

The **Secure** phase is a reminder that security is a key step in the API lifecycle. Automated security testing, such as static analysis or vulnerability testing, should be part of your CD pipeline. Secure development practices, such as code reviews, a security development lifecycle, or OWASP Top 10 should also be part of your development lifecycle.

In the **Manage** phase, after the APIs are deployed and secured, they need to be managed. This activity encompasses versioning, deprecation, and retirement. As a best practice, versioning should follow the semantic versioning scheme. This means when it is deployed, any new minor version of an API replaces the previous version. All consumers that were using the previous version are then using the latest version. When a breaking change occurs, a major version is released and deployed side by side with the previous one. Consumers can migrate from the previous version to the current one. They migrate at their own pace by adapting their code to the new version.

This concludes the producer cycle of full API lifecycle management, and we can now speak about the consumer cycle.

## Promote your APIs

When your APIs are deployed in production and they are “live,” you enter the **Discover** phase. In this phase, you need to help your partners and other third parties discover your APIs. Just like your corporate website is the showroom for your products and offerings, an API developer portal is a showroom for your APIs. Make sure you put as much effort into this showroom as you do for your corporate website if you want to drive revenue through APIs!

In the **Develop** phase, third parties will start discovering your APIs and developing applications based on your APIs. The user experience of those applications will depend on the quality of your APIs but also on the client applications. Make sure you are providing enough resources for developers to get the most out of your APIs. Those resources can be best practices, information on how to handle security and retries on errors, and so on.

In the **Consume** phase, client applications will start consuming your APIs and you might want to have staged plans to match their growing consumption. To ensure a high-quality user experience, you might also want to set up an application validation process to reach your production APIs—if this is part of your API strategy, of course.

## Refine your APIs

After your first version has been released, you will need to prepare the next version and the one after that. This requires you to set up a kind of feedback loop to know what to improve next. This is the **Monitor** phase.

To get accurate data in your feedback loop, you will have to monitor various aspects of your APIs. This ranges from developer engagement to API health, to API usage, and so on. The “Time to first Hello, World!” is a useful metric to track to know if your APIs are easy enough to be learned quickly by new developers.

As your APIs mature, so does your business model. At some point, you might be interested in billing your consumers according to their usage of your APIs; if so, this is the **Monetize** phase. A desire to monetize is especially likely if you are targeting a myriad of small third parties to benefit from a mass effect. In that case, you definitely want to have monetization with billing and payment built in.

## An API strategy to ensure the cycles repeat

The cycles repeat, and this is at the center of both cycles. This is not by coincidence: an **API strategy** is the cornerstone of a successful API program. Knowing which goals you need to reach will help you to focus on what matters the most.

Red Hat technologies and communities can help with full API lifecycle management. The diagram below shows tools for full API lifecycle management:

![Tools for the API Lifecycle](tools.png)

Communities such as Apicurio and Microcks will help you with the design, mock, and tests. A whole development offering such as Red Hat Fuse, Red Hat OpenShift Application Runtimes, or Red Hat CodeReady Workspaces can help you develop reliable API back ends. Red Hat Ansible Automation can help you with the Continuous Delivery of your APIs. Red Hat Single Sign-On can help secure your APIs, and Red Hat 3scale API Management handles the rest of the API lifecycle. Last but not least, Red Hat can help you define your API strategy through a service offering: the API Model Canvas.

Red Hat OpenShift Container Platform is a the core of this lifecycle, since it is the component that brings agility and makes this approach flow more easily.


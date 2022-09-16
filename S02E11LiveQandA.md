## 2022-09-15 - Series 2 - Episode 11: Event driven architectures and the power of asynchronous communications - Q&A

During the live session we did a live Q&A spot where attendees could ask questions. If you didn't manage to make it along, here are the ones that came up. We've included answers where possible.

### ❔ Q1: I have an Azure Function returning custom response status_code and messages. I want to have an API gateway in front of the Azure Function and surface the custom status and messages. Is Azure API Management the easiest option? The policy configuration seems a bit complex. Is there any easier option?

You could consider using Azure Functions proxies to do this. You can find more information about Azure Functions Proxies [on Microsoft Docs](https://docs.microsoft.com/azure/azure-functions/functions-proxies). However, Proxies may not fill all your needs because they are not designed to be a full API gateway. If you need more advanced features, then API Management is a good option. Even if you don't need all the features, it's still a good option because it's a managed service and you don't have to worry about the infrastructure and you can always pass your responses back to clients without having to apply any policies to them.

### ❔ Q2: How much do you love Udi and Clemens?

We love them a lot! 😍

### ❔ Q3: What is a great way to publish events in an event-driven architecture and have other users inside network subscribe, ie through tools like Power Automate?

Answer coming soon!

### ❔ Q4: My BI Developers do not like my event-drive architectures as they don't like that I have 100 databases and not one monolith. Any advice on how to handle that relationship?

Answer coming soon!

### ❔ Q5: Is there a canonical event source pattern in Azure? I built my own inspired by Greg Young aka EventStore. I don't want to migrate to cloud. I also don't want to take on eventstore as a dependcy

The best place to start is on the Azure Architecture Centre, with the [Event Driven Architecture](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/event-driven) page. This will give you a good overview of the different options available to you. You can also find more information about the different event sources available in Azure [on Microsoft Docs](https://docs.microsoft.com/azure/architecture/guide/technology-choices/event-sources). It's likely you will need to dive into [each pattern](https://docs.microsoft.com/azure/architecture/patterns/category/messaging?source=recommendations) (choreography, pub/sub, sequential convoy, etc) to see which one is best for your use case.

### ❔Q6: Don't you need 'out of band' reconciliation processes to detect 'lost' events ?

Answer coming soon!

### ❔Q7: What is the difference between Azure Event Hub, Event Grid and Service Bus? Which one to use in which scenario?

Microsoft Docs contains a great introduction to the differences between Eventing and Messaging, and the services to choose based on your scenario. More recently, Clemens Vasters wrote a great blog on this exact topic which includes some good additional information above and beyond our standard documentation. Check his blog out [here](https://cloudblogs.microsoft.com/opensource/2021/09/15/azure-eventing-and-messaging-services/).

### ❔Q8: What's the best approach to manage Dead Letter Queue messages as the alerting out of Azure is fairly limited - we've built functions\logic apps in the past to send alerts or fix messages - is there a better way?

Answer coming soon!

### ❔Q9: How do you avoid cycles of events (where - in a minimal example - Event A leads to Event B which leads to Event A and so on for ever? Also how to approach reversability?

Answer coming soon!

### ❔Q10: What if event processing server dies, is it a single point of failure? How to work around it?

Answer coming soon!

### ❔Q11: Does Event Grid match to Message Queue while Event Hub match to Event Streaming concept? Thanks.

It's probably best to take a read of the linked blog and documentation from Clemens Vasters above. It's a great introduction to the differences between Eventing and Messaging, and the services to choose based on your scenario. 

### ❔Q12: My question is around building the foundation for event-driven architecture (EDA) in an enterprise. How do you go about building a case for EDA? Also any white paper around this?

Answer coming soon!

### ❔Q13: Is there anything on the Azure roadmap that will provide realtime monitoring / insights of messages on service bus queues?

Depending on your specific needs you can look at the existing Azure Monitor metrics and logs for Service Bus. Check out the [official documentation to learn more](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-insights).

### ❔Q14: Any guidance on contract sharing/documentation tools?

Answer coming soon!

### ❔Q15: We have a producer that produces more than 2k messages per seconds and to process that we are planning to use multiple instances of our consumer to process that; however, we would like to process messages in sequence and exactly once. Should this responsibility be on consumer or we can share this with message queuing system and for this we are thinking of using Rabbit MQ. What's your take on this?

Answer coming soon!

### ❔Q16: Any update to Logic Apps having to poll service bus for msgs instead of receiving a callback?

At this stage, no updates. If you are reading this and are not aware of the existing implementation you can read more about it on [Microsoft Docs](https://docs.microsoft.com/azure/connectors/connectors-create-api-servicebus?tabs=consumption#service-bus-triggers).
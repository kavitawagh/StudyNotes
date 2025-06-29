Lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing.

```
ISubscriber
+ update(context)

SubscriberA
+ update(context)

Publisher
- listebers[]
+ subscribe(listener)
+ upsubscribe(listener)
+ notify()

// client code
subA = SubscriberA()
publisher.subscribe(subA)
```

Publisher can have different lists of subscribers for different events and publisher can pass any data to notify method so that subscriber can use it.

```
ISubscriber
+ update(data)

SubscriberA
+ update(data)

Publisher
- listebers: map<eventtype, listener[]>
+ subscribe(eventType, listener)
+ upsubscribe(eventType, listener)
+ notify(eventType, data)
```

# Actor Context 的作用 and Thread Safety
- Spawning child actors and supervision
- Watching other actors to receive a Terminated(otherActor) event should the watched actor stop permanently
- Logging
- Creating message adapters
- Request-response interactions (ask) with another actor
- Access to the self ActorRef

```
ActorContext Thread Safety
Many of the methods in ActorContext are not thread-safe and

Must not be accessed by threads from java.util.concurrent.CompletionStage callbacks
Must not be shared between several actor instances
Must only be used in the ordinary actor message processing thread
```


# Actor Lift Cycle
ActorSystem (System Actor)
|/
The Guardian Actor (User Root Actor)
|/

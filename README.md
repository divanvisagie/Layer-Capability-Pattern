# Layer-Capability Pattern
A new design pattern for Extended Intelligence systems


 Here's a draft for what this pattern might look like:

**1. Request-Response Pattern:**
All interactions with services in the system are based on a request-response model. Every service must be able to accept a `RequestMessage` and return a `ResponseMessage`.

**2. Capability Registration and Discovery:**
Each service must be able to register itself with a central registry (like Askur), providing details about the capabilities it provides. The registry can then route `RequestMessage`s to the appropriate service based on its capabilities.

**3. Layered Architecture:**
Services are built using a layered architecture, where each layer has the opportunity to inspect, modify, or reject a `RequestMessage` or `ResponseMessage`. This allows for modular addition of features like logging, caching, security, and more.

**4. Capability Scoring:**
Each capability must be able to provide a score indicating how well it can handle a given `RequestMessage`. This allows the system to intelligently route requests to the most appropriate capability.

**5. Health Checking:**
Each service should implement a `/health` endpoint that allows the central registry to monitor the health and availability of the service.

**6. Message Embedding:**
To enhance the system's intelligence, `RequestMessage`s may be converted into a text or data embedding. This allows for more sophisticated routing and handling of requests, such as using machine learning models.

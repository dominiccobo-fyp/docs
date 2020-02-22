+++
title = "Overview"
weight = 1
+++

## High Level

{{<mermaid>}}
    graph LR
        A["IDE A"]
        AA["IDE B"]
        AB["IDE C"]
        B["Local Context  Daemon"]
        C(("Message Bus"))
        D[("Documentation Provider")]
        E[("Experts Provider")]
        F[("Work Items Provider")]
        X["Data sources"]
        subgraph Client
            A --> B;
            AA --> B;
            AB --> B;
        end
        subgraph Server
            B --> C;
            C -- 1 * --> D;
            C -- 1 * --> E;
            C -- 1 * --> F;
        end
        D --> X;
        E --> X;
        F --> X;
        
{{< /mermaid >}}

## Low Level

{{<mermaid>}}
sequenceDiagram
        IDE->>+Daemon: Here's a context, answer this?

        Daemon->>+Message Bus: Send this request to\nto subscribed parties 

        Message Bus ->>+Providers: Here's a query

        Note right of Providers: Scatter query

        Daemon->>+IDE: Here's a collection identifier

        loop Poll
            IDE->>+Daemon: Any new results for this identifier!
            Daemon->>+IDE: Paged Results, if any
        end								

        Note right of Providers: Empty result set <br/> returned for lack of <br/> understanding.

        Providers ->>+Message Bus: Return results to requester

        Message Bus ->>+Daemon: Here's a new result

        Note left of Message Bus: Add to collection
{{< /mermaid >}}

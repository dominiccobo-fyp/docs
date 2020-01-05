+++
title = "Architecture"
weight = 15
+++

There architecture follows a traditional client-server approach. The client-side is composed of an interfacing server
which implements the reusable logic and an IDE specific extension.

The server side is a cluster of different resolvers which act on a message-bus to resolve queries which they understand. 
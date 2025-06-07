# Auction-System-Documentation

This project is an **online auction system** where users can **register**, **log in**, and **place bids** on items.
It features **real-time bid updates** using messaging and WebSockets, manages user sessions securely, and includes an **administrator panel** to monitor activity and sessions.
Auctions are **managed** through EJBs and automatically **closed** when they expire.


## Visual Overview

```mermaid
flowchart TD
    A0["Entities (User, Auction, Bid)
"]
    A1["Service EJBs (Auction, Bid, User)
"]
    A2["User Session Management
"]
    A3["JMS Messaging (Bid Notifications)
"]
    A4["WebSocket Endpoint
"]
    A5["Servlets (Auction, SessionAdmin)
"]
    A6["Filters (Session, Admin, Encoding)
"]
    A7["AuctionManagerSingleton
"]
    A1 -- "Manages Entities" --> A0
    A5 -- "Calls Services" --> A1
    A5 -- "Uses Session Manager" --> A2
    A6 -- "Validates Sessions" --> A2
    A6 -- "Uses User Service" --> A1
    A1 -- "Sends Messages" --> A3
    A3 -- "Broadcasts via WebSocket" --> A4
    A7 -- "Updates Entity State" --> A0
    A5 -- "Gets Stats" --> A7
    A2 -- "Manages State" --> A2
    A4 -- "Manages Connections" --> A4
```

## Chapters

1. [User Session Management
](01_user_session_management_.md)
2. [Entities (User, Auction, Bid)
](02_entities__user__auction__bid__.md)
3. [Service EJBs (Auction, Bid, User)
](03_service_ejbs__auction__bid__user__.md)
4. [Filters (Session, Admin, Encoding)
](04_filters__session__admin__encoding__.md)
5. [AuctionManagerSingleton
](05_auctionmanagersingleton_.md)
6. [Servlets (Auction, SessionAdmin)
](06_servlets__auction__sessionadmin__.md)
7. [JMS Messaging (Bid Notifications)
](07_jms_messaging__bid_notifications__.md)
8. [WebSocket Endpoint
](08_websocket_endpoint_.md)

---

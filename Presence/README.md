# Presence

The XMPP's *Presence* feature is useful to share information about a user's network availability with others.

### Voluntary Usage

The usage of the *presence* feature is voluntary and an XMPP user need not share about the information of their presence to anyone else. 

Presence is accessed bidirectionally.

### The Subscription Handshake

If "Keith" is interested in subscribing for "Bob's" presence, Keith sends Bob a subscription request shown below

```
<presence from="keith@superchat.com" to="bob@superchat.com" type="subscribe"/>
```


# Presence

The XMPP's *Presence* feature is useful to share information about a user's network availability with others.

### Voluntary Usage

The usage of the *presence* feature is voluntary and an XMPP user need not share about the information of their presence to anyone else. 

**Bidirectional Presence**

Presence is usually accessed bidirectionally i.e. If "Alice" allows to "Bob" to see her presence, then "Bob" allows "Alice" to see his presence. This is established during the subscription handshake. 

### The Subscription Handshake

**Subscription**

If "Alice" is interested in subscribing for "Bob's" presence, Alice sends Bob a subscription request by sending the *\<presence/\>* stanza of type *subscribe*.

```xml
<presence from="alice@superchat.com" to="bob@superchat.com" type="subscribe"/>
```

When Bob receives the subscription request, he can either approve it or deny it.

**approval**

Bob can approve the subscription request by sending the *\<presence/\>* stanza of type *subscribed*.

```xml
<presence from="bob@superchat.com" to="alice@superchat.com" type="subscribed"/>
```

**denial**

Bob can deny the subscription request by sending the *\<presence/\>* stanza of type *unsubscribed*.

```xml
<presence from="bob@superchat.com" to="alice@superchat.com" type="unsubscribed"/>
```

**Establishing a Bidirectional Presence**

To establish a bidirectional presence, the person who approved the original subscription request, Bob, needs to send his own subscription request by sending the *\<presence/\>* stanza of type *subscribe*.

```xml
<presence from="bob@superchat.com" to="alice@superchat.com" type="subscribe"/>
```

This requires the sender of the original subscription request, Alice, to manually approve the reverse request from Bob. This additional step can be avoided if the person who approved the original subscription request, Bob, sends an auto-reply with *\<presence/\>* stanza of type *subscribed*.

**Auto Reply**

```xml
<presence from="bob@superchat.com" to="alice@superchat.com" type="subscribed"/>
```

### Post Subscription Handshake

After a successful bidirectional presence subscription, the XMPP servers

* add Bob to Alice's roster and Alice to Bob's roster
* manage a state machine of subscription states



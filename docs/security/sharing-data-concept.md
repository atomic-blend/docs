---
icon: share-nodes
---

# Sharing Data Concept

## Overview

As of now, sharing data is not supported. However, following the same principle as we use in the single user encryption concept, we can also do it with shared keys amongst the users that needs sharing.



## Concept

To share an item, for the first time (for example, a list of tasks) :&#x20;

* Generate a random shared data key and a salt
* Generate a random key vault key and salt
* encrypt the shared data key with the vault data key (so other admins can share the key to the user)
* encrypt the vault data key with the user data key (so he have access to the data)
* store the vault salt and encrypted shared data key in database
* re-encrypt all the items with the shared data key and sync with backend
* current admin user have access to the data AND can share the shared data key with anyone he wants



To add a new admin :&#x20;

* add the new admin to the item
* he registers, then accepts the invite
* admin confirm the join (ie. encrypt the decrypted shared data (with his vault key) with the accepted user public key)
* the new admin have access to the shared item (he decodes the shared data key with his private key)



This is probably incomplete as of now, but it's just to give an idea on how it could work and reassure you that the platform have been designed to accommodate sharing and community stuff.

I've not gone into details of the sharing processes here but diagrams and documentation will be written here as we go.


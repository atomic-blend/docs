---
icon: megaphone
---

# Encrypted Notifications

## Introduction

As you might know, end-to-end encryption can be tough to maintain and certain services resort to not storing all the data in a secure and encrypted way : for example, a famous mail provider only store the content of their mails and not objects and other metadata, so they can perform search and send notifications.

In Atomic Blend, we wanted to focus on total privacy, and we are willing to compromise / make sacrifices to reach this goal.



## Encrypted notifications

To send notifications, you need to go through either the Store APIs or Firebase or a third party notification provider. Even if some of them are open source solutions, like Novu, we didn't want to send plain data.&#x20;

This will have resulted in almost no data for a task or a habit being encrypted, as the important content is mostly in the title and description.



So, **all notifications sent to the app in the App Store and Play store are end-to-end encrypted.**

We only store in plain the data that we need to send the notification at the right time : dates, reminders, etc…

The content of the notification AND any other information regarding the notifications sent are as encrypted as they are in database, and are **decrypted on the fly by the device**, before sending the notification to the OS.

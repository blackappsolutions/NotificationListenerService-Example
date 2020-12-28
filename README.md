WhatsApp-NotificationListener and External Display Pusher
=========================================================

This is a fork of https://github.com/kpbird/NotificationListenerService-Example which has the
following modifications/additions:

* Ability to send/view/delete own notifications were removed.
* PreferenceActivity to set an IP address of an external display was added.
* This display will be accessed with the HTTP-POST-Request `http://IP_ADDRESS//sendToPixBlock` and
* the the parameter `message`, which holds the text the display should present.
* Currently this message is hard-coded to "Handy-Nachricht" and sent, when a WhatsApp-Notification
  was detected.
* When the WhatsApp-Message was read, the message is reset to an empty string, to blank the display.

## Background-Technology

NotificationListenerService is introduced in Android 4.3 (API 18). It allows an application to receive information about notifications as it creates or removes. NotificationListenerService class is derived from the Service class. It has two abstract methods namely 1. onNotificationPosted 2. onNotificationRemoved.
To use NotificationListenerService, we need to create a java file which extends NotificationListenerService and implement two callback methods. Both methods have a parameter named "sbn", which is an object of StatusBarNotification class. StatusBarNotification provides necessary information about Notifications.
NotificationListenerService provides facility to fetch active notifications using getActiveNotifications and also provides a feature to remove notifications using cancelAllNotifications.

## Note
User require to enable notification permission from "Settings > Security > Notification access".

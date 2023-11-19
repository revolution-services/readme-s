# Revolution Notify Pack README

This document provides the documentation for the Revolution Notify Pack.

## Features

The FiveM Notify Pack module includes the following main features:

- Push Notifications
- Announcements
- Help Notifications
- Progress Bars

## Event Descriptions

### 1. Push Notifications

`revolution_notifypack:pushNotification` 

This event is used to push notifications to the Notify Pack. It takes four arguments:

- `text`: The main text of the notification.
- `title`: The title of the notification.
- `type`: The type of notification. This can be "success", "error", "warning", or "teamchat".
- `time`: The duration the notification will be displayed for in milliseconds.

Example:

```lua
TriggerEvent("revolution_notifypack:pushNotification", "SUCCESS", "SUCCESS", "success", 5000)
```

### 2. Announcements

`revolution_notifypack:pushAnnouncement` 

This event is used to push announcements to the Notify Pack. It takes four arguments:

- `text`: The main text of the announcement.
- `title`: The title of the announcement.
- `author`: The author of the announcement.
- `time`: The duration the announcement will be displayed for in milliseconds.

Example:

```lua
TriggerEvent("revolution_notifypack:pushAnnouncement", "Announce", "Announce", GetPlayerName(PlayerId()), 10000)
```

### 3. Help Notifications

`revolution_notifypack:pushHelpNotify`

This event is used to push help notifications to the Notify Pack. It takes three arguments:

- `text`: The main text of the help notification.
- `key`: The key related to the help notification.
- `time`: The duration the help notification will be displayed for in milliseconds.

Example:

```lua
TriggerEvent("revolution_notifypack:pushHelpNotify", "Press E to interact", "E", 5000)
```

### 4. Progress Bars

`revolution_notifypack:pushProgressbar`

This event is used to push progress bars to the Notify Pack. It takes two arguments:

- `text`: The main text of the progress bar.
- `time`: The duration the progress bar will be displayed for in milliseconds.

Example:

```lua
TriggerEvent("revolution_notifypack:pushProgressbar", "Progressbar", 10000)
```

## Usage

To use these events, you can use the `TriggerEvent` function provided by FiveM, passing in the event name and the required arguments. Here is an example of how to use each event:

```lua
-- Pushing notifications
TriggerEvent("revolution_notifypack:pushNotification", "SUCCESS", "SUCCESS", "success", 5000)
TriggerEvent("revolution_notifypack:pushNotification", "ERROR", "ERROR", "error", 5000)
TriggerEvent("revolution_notifypack:pushNotification", "WARNING", "WARNING", "warning", 5000)
TriggerEvent("revolution_notifypack:pushNotification", "TEAMCHAT", "TEAMCHAT", "teamchat", 5000)

-- Pushing an announcement
TriggerEvent("revolution_notifypack:pushAnnouncement", "Announce", "Announce", GetPlayerName(PlayerId()), 10000)

-- Pushing a help notification in a loop
local helpNotifyActive = true
CreateThread(function()
    while helpNotifyActive do
        TriggerEvent("revolution_notifypack:pushHelpNotify", "Press E to interact", "E", 5000)
        Wait(500)
    end
end)

-- Pushing a progress bar
TriggerEvent("revolution_notifypack:pushProgressbar", "Progressbar", 10000)
```

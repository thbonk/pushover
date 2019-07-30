# 📌 Pushover

Simple little wrapper for the [Pushover](https://pushover.net) API. Use it to send push notifications from your tools to your or your user's devices.

## Example

```swift
// Create a pushover object with your API token.
let pushover = Pushover(token: "YOUR_TOKEN")

// Send a simple message directly.
pushover.send("Lorem ipsum dolor sit amet.", to: "USER_OR_GROUP_KEY")

// Use `Notification`s to use more of Pushover's features.
let notification = Notification(message: "Lorem ipsum.", to: "USER")
    .devices(["iPhone"])
    .url("https://example.com")
    .urlTitle("Dolor sit amet")
    .priority(.high)
    .sound(.intermission)

pushover.send(notification)

// Use the callback to define actions based on error or success cases.
pushover.send(notification) { result in
    // A .success result case means that there were no network, server or decoding errors.
    // The request might still have failed due to a wrong API token, exceeded limits or
    // other problems. Be sure to check the response value for more information.
}
```

## Requirements

You're going to need an API token, you can register for one [here](https://pushover.net/apps/build).

Also please read the *[Being Friendly to our API](https://pushover.net/api#friendly)* section in the Pushover API docs.

## Installation

Pushover is available via Swift Package Manager.

Package.swift:

```swift
.package(url: "https://github.com/kiliankoe/pushover", from: "<#latest#>")
```

## Contributors

Kilian Koeltzsch, [@kiliankoe](https://github.com/kiliankoe)

## License

Pushover is available under the MIT license. See the LICENSE file for more info.

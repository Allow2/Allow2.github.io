# Allow2

The What and Why of Allow2.

Why should Software and Firmware Developers, Web Site Owners and Device Manufacturers use Allow2?

## Meet Your Customer Needs

With the explosion of web and social media, the proliferation of devices and children gaining 24 x 7 access to the screens,
Parents are genuinely concerned about gaming and social media addictions. Broader access to materials is making children harder to mentor and less likely to
feel they have anything to learn from their parents, teachers and general authority.

Parents are looking more and more for products that have sensible, helpful and useful parental controls. They need to be able to easily setup and reconfigure
* Time Limits on different Days
* Banning activities is children misbehave
* Providing rewards for doing chores

But ALL other systems suffer from a fatal flaw, they require you to set controls based on the day of the week! While this approach seems to be sensible in theory,
life is really about exceptions: Holidays, Sick Days, Sporting events, and more.
So when systems then require parents to repeatedly reconfigure devices and apps to cater for these frequent events, AND they have to do this on different sites,
apps and devices, they quickly give up in frustration.

So what is needed is a parental control platform that:
* Allows the parent to set up "Day Types" and easily attach them as defaults to days (mondays = school days) and easily schedule overrides (next 2 weeks are a vacation),
* Allows device manufacturers, app developers, web site owners and others easily include powerful parental controls with little to no work using a free platform, and
* Allows parents to manage all their devices, apps and services with one simple, powerful and minimal interface.

Allow2 is _THE ONLY_ system that specifically takes away all the complexity for parents and developers alike. By using our _Patented_ approach of wrapping
configurations in "Day Types", we avoid all the problems every other parental control system has!

The Allow2 platform provides free to use developer SDKs for both "devices" and "services"

* Devices - Any "User owned" apps and devices, games, gaming consoles, TVs, PVRs, etc, designed to be paired with 1 owner account per instance
* Services - Any multi-user API connected instances. Facebook, web sites, twitter, group services, shared devices in public places, etc.
* Request Interface - Users on each device/service can create and submit access or change requests to the parent using this interface directly in the device/service.

## Simple to integrate

example taken from: [https://github.com/Allow2/Allow2iOS](https://github.com/Allow2/Allow2iOS)

add the cocoapod:

```ruby
pod 'Allow2iOS'
```

With Allow2 all you have to do to check if something can be used and record it's usage is:

```swift
let allow2Activities = [
    Allow2.Allow2Activity(activity: Allow2.Activity.Internet, log: true), // this is an internet based app
    Allow2.Allow2Activity(activity: Allow2.Activity.Gaming, log: true),   // and it's gaming related, can also use "Messaging", "Social", "Electricity" and more...
]
Allow2.shared.check(allow2Activities)
```

And don't worry about having to tell other parts of your app. It's done for you automatically (just listen for the Allow2CheckResultNotification)!

```swift
func Allow2CheckResultNotification(notification:NSNotification) {
    guard let userInfo = notification.userInfo,
    let result  = userInfo["result"] as? Allow2CheckResult else {
        print("No Allow2CheckResult found in notification")
        return
    }

    dispatch_async(dispatch_get_main_queue()) {
        self.allow2View.hidden = result.allowed

        if (!result.allowed) {
            // configure the block screen to explain the issue
            self.allow2View.result = result
        }
    }
}
```


## Current production-ready SDKs:

These SDKs can be embedded in production apps:

* [https://github.com/Allow2/Allow2iOS](https://github.com/Allow2/Allow2iOS) - iOS App SDK

## Alpha/Beta stage:

These SDKs are still in development:

* [https://github.com/Allow2/Allow2php](https://github.com/Allow2/Allow2php) - Service SDK (PHP)
* [https://github.com/Allow2/Allow2node](https://github.com/Allow2/Allow2node) - Device SDK (Node.js)
* [https://github.com/Allow2/Allow2python](https://github.com/Allow2/Allow2python) - Device SDK (Python)

## Need to port/develop

These SDKs are yet to be ported, please feel free to get started:

* [https://github.com/Allow2/Allow2csharp](https://github.com/Allow2/Allow2csharp) - Device SDK (C#)
* [https://github.com/Allow2/Allow2java](https://github.com/Allow2/Allow2java) - Device SDK (Java)

If you need another language, please let us know, or feel free to get started and contribute your port.

# Allow2

The What and Why of Allow2.

Why should Software and Firmware Developers, Web Site Owners and Device Manufacturers use Allow2?

## A Rapidly Growing Need

[OPEN LETTER FROM JANA PARTNERS AND CALSTRS TO APPLE INC](https://thinkdifferentlyaboutkids.com/)

With the explosion of web and social media, the proliferation of devices and children gaining 24 x 7 access to screens,
parents are genuinely concerned about gaming and social media addictions. Broader access to materials is making children harder to mentor and less likely to
feel they have anything to learn from their parents, teachers and general authorities.

Parents are looking more and more for products that have sensible, helpful and useful parental controls. They need to be able to easily:
* Setup and manage time limits on different days
* Ban activities when children misbehave
* Provide rewards for chores and good behaviour

But **ALL other systems** suffer from a **number of fatal flaws**:
* They **ALL** require you to set controls based on the day of the week (Monday, etc) which is **not how the world works**.
* Manufacturers and developers cannot expend a disproportionate amount of resource developing complex and comprehensive parental controls, so they typically
**create rudimentary and useless solutions** or **just do not bother**.
* All systems are siloed and independent, creating an immense and ever growing burden on the billions of time-poor parents around the world.
* Parents are now becoming **reluctant to spend** on devices, games and service subscriptions as they know they have no tools to help them teach responsible use.
* With electricity prices souring, greenhouse emissions growing and the rapidly growing carbon footprint, parents are forever paying more and damaging the planet
more each day when children are constantly leaving their lights and fans on.

**Life is really about exceptions**: Holidays, Sick Days, Sporting events, and more.
Parents need to **spend less time managing child time limits** and they need a simple interface to do so across everything.

So when systems then require parents to repeatedly reconfigure devices and apps to cater for these frequent events, AND they have to do this on different sites,
apps and devices, they quickly give up in frustration.

## Why Use Allow2?

Analytics, conversation channels and Helpdesk are all platforms that developers can **integrate in hours** (not months), so why not quota management and parental controls?

So what is needed is a parental control platform that:
* Allows the parent to set up "Day Types" and easily attach them as defaults to days (mondays = school days) and easily schedule overrides (next 2 weeks are a vacation),
* Allows device manufacturers, app developers, web site owners and others easily include powerful parental controls with little to no work using a free platform, and
* Allows parents to manage all their devices, apps and services with one simple, powerful and minimal interface.

**Allow2** is **THE ONLY** system that specifically takes away all the complexity for parents and developers alike. By using our _Patented_ approach of wrapping
configurations in **"Day Types"**, we avoid all the problems every other parental control system has!

The **Allow2** platform provides free to use developer SDKs for both "devices" and "services"

* Devices - Any "User owned" apps and devices, games, gaming consoles, TVs, PVRs, etc, designed to be paired with 1 owner account per instance
* Services - Any multi-user API connected instances. Facebook, web sites, Twitter, group services, shared devices in public places, etc.
* Request Interface - Users on each device/service can create and submit access or change requests to the parent using this interface directly in the device/service.

## Allow2 Usage Examples

* Place limits on gaming time, be it on device, web site or gaming console
* Implement electricity usage quotas, if children forget to turn off their fan or light, they run out of quota for the day and the devices turn off.

## Simple to integrate

example taken from: [https://github.com/Allow2/Allow2iOS](https://github.com/Allow2/Allow2iOS)

add the cocoapod:

```ruby
pod 'Allow2iOS'
```

With Allow2 all you have to do to check if something can be used and record its usage:

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

-

# Current production-ready APIs/SDKs:

These SDKs can be embedded in production apps:

| Project Title   | URL | Language | Notes |
| -------------   | --- | -------- | ----- |
| Allow2iOS       | [https://github.com/Allow2/Allow2iOS](https://github.com/Allow2/Allow2iOS) | Swift | |


## Alpha/Beta APIs/SDKs:

These SDKs are still in development:

| Project Title   | URL | Language | Notes |
| -------------   | --- | -------- | ----- |
| Allow2node       | [https://github.com/Allow2/Allow2node](https://github.com/Allow2/Allow2node) | Node.js | |
| Allow2python    | [https://github.com/Allow2/Allow2python](https://github.com/Allow2/Allow2python) | Python | |


## Using on a server/service/web site

These SDKs are specifically used on connecting at the service level (that is, not for individual accounts).

This demonstrates the basis of using Allow2 on Facebook, Wordpress, Twitter, WhatsApp, etc:

| Project Title   | URL | Language | Notes |
| -------------   | --- | -------- | ----- |
| Allow2php       | [https://github.com/Allow2/Allow2php](https://github.com/Allow2/Allow2php) | PHP | Service SDK |


## Work needed to port/develop

These SDKs are yet to be ported, please feel free to get started:

| Project Title   | URL | Language | Notes |
| -------------   | --- | -------- | ----- |
| Allow2csharp    | [https://github.com/Allow2/Allow2csharp](https://github.com/Allow2/Allow2csharp) | C# |  |
| Allow2java      | [https://github.com/Allow2/Allow2java](https://github.com/Allow2/Allow2java) | Java | |

If you need another language, please let us know, or feel free to get started and contribute your port.

# Example open-source projects using Allow2

Here are just a few of the open-source projects using Allow2, they are in various stages of development

| Project Title   | URL | Language | Notes |
| -------------   | --- | -------- | ----- |
| Brave Browser iOS | [https://github.com/Allow2CEO/browser-ios](https://github.com/Allow2CEO/browser-ios) | Swift | Open-source browser [https://www.brave.com](https://www.brave.com) |
| Provenance    | [https://github.com/Allow2/Provenance](https://github.com/Allow2/Provenance) | Swift | An iOS/tvOS Frontend for multiple gaming emulators |

# Internal Projects

These projects are not yet open-source and are currently invitation-only.
Please email [ceo@allow2.com](mailto:ceo@allow2.com) if you are interested in getting involved in these projects.

| Project Title   | URL | Language | Notes |
| -------------   | --- | -------- | ----- |
| allow2openWRT   | [https://github.com/Allow2CEO/allow2openwrt](https://github.com/Allow2CEO/allow2openwrt) | C | Router Firmware module for Allow2 Access Controls |
| allow2deviceAPI | [https://github.com/Allow2CEO/allow2deviceAPI](https://github.com/Allow2CEO/allow2deviceAPI) | C | Fully Offline Cached C API Library |
| allow2mac       | [https://github.com/Allow2/allow2mac](https://github.com/Allow2/allow2mac) | Swift | Allow2 enabled OSX account control |
| allow2windows   | [https://github.com/Allow2/allow2windows](https://github.com/Allow2/allow2windows) | C# | Allow2 enabled windows time control |
| Allow2wemo      | [https://github.com/Allow2/Allow2wemo](https://github.com/Allow2/Allow2wemo) | Node.js | Allow2 enabled wemo lightswitch and fan/device/etc controller |
| Allow2kodi      | [https://github.com/Allow2/Allow2kodi](https://github.com/Allow2/Allow2kodi) | Node.js | Allow2 plugin/controller for Kodi media player |

# Other Uses

Allow2 currently has an Alexa skill in Beta (releasing shortly), which will also be offered on Google Assistant.

We see immense opportunity to utilise this platform in IoT, automation and enterprise. There are already a number of projects
popping up around these applications, so if you are working on novel applications, new ports or enhancements of the SDKs,
or enterprise applications, please contact us so we can assist you [ceo@allow2.com](mailto:ceo@allow2.com).
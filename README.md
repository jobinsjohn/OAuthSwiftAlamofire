# OAuthSwiftAlamofire

<img  src="https://raw.githubusercontent.com/OAuthSwift/OAuthSwift/master/Assets/OAuthSwift-icon.png" alt="OAuthSwift" hspace=20 /> <img  src="https://raw.githubusercontent.com/Alamofire/Alamofire/master/alamofire.png" alt="Alamofire" width = "400"/>

[![Join the chat at https://gitter.im/OAuthSwift/OAuthSwift](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/OAuthSwift/OAuthSwift?utm_campaign=pr-badge&utm_content=badge&utm_medium=badge&utm_source=badge)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat
            )](http://mit-license.org) [![Platform](https://img.shields.io/badge/platform-iOS_OSX_TVOS-lightgrey.svg?style=flat
             )](https://developer.apple.com/resources/) [![Language](https://img.shields.io/badge/language-swift-orange.svg?style=flat
             )](https://developer.apple.com/swift) [![Cocoapod](https://img.shields.io/cocoapods/v/OAuthSwiftAlamofire.svg?style=flat)](http://cocoadocs.org/docsets/OAuthSwiftAlamofire/)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)

Utility methods to use [OAuthSwift](https://github.com/OAuthSwift/OAuthSwift) to sign [Alamofire](https://github.com/Alamofire/Alamofire) request.

## How to use
This framework provide a `RequestInterceptor` to set into alamofire `Session`
```swift
let interceptor = oauthswift.requestInterceptor
let session = Session(interceptor: interceptor)
```
Then you can make you request as usual
```swift
session.request("http://oauthbin.com/v1/echo")
```

or pass the `interceptor` as argument of `request` function
```swift
session.request("http://oauthbin.com/v1/echo", interceptor: interceptor)
```

:warning: you must have call `authorize` function on your `OAuthSwift` or nothing will be signed.

### Refresh token

The OAuth2 interceptor will also automatically refresh the access token, using the Alamofire `RequestRetrier` mechanism.

## Installation

### Support Carthage

* Install Carthage (https://github.com/Carthage/Carthage)
* Create Cartfile file
```
github "OAuthSwift/OAuthSwiftAlamofire"
```
* Run `carthage update`.
* On your application targets’ “General” settings tab, in the “Embedded Binaries” section, drag and drop OAuthSwift.framework from the Carthage/Build/iOS folder on disk.

### Support CocoaPods

* Podfile

```
use_frameworks!

pod 'OAuthSwiftAlamofire'
```

### LICENSE
OAuthSwiftAlamofire is released under the MIT license. See [LICENSE](https://github.com/OAuthSwift/OAuthSwiftAlamofire/blob/master/LICENSE) for details.

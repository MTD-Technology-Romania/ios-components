# Components

![Swift Version](https://img.shields.io/badge/Swift-5.5-orange.svg)
![Platform](https://img.shields.io/badge/Platform-iOS%20%7C%20macOS%20%7C%20tvOS-lightgrey.svg)
[![GitHub License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Overview

UIComponents is a Swift Package Manager (SwiftPM) package that provides a collection of SwiftUI elements and design helpers to enhance the development of your SwiftUI-based projects.

## Features

### Views
- [ ] `ImageContentView`
- [ ] `InputView`
- [ ] `Toast`
- [ ] `GenericTextField`
- [ ] `PrimaryButton`

### ButtonStyle
- [ ] `ActionButtonStyle`
- [ ] `FullButtonStyle`
- [ ] `SocialButtonStyle`

### ViewModifiers
- [ ] `FullButtonStyle`
- [ ] `CardModifier`
- [ ] `ToastView`
- [ ] `BorderModifierTextField`

### Error 
- [ ] `Alert`
- [ ] `InterfaceError`

### Localization

- [ ] `Localization` using `swiftgen`

## Installation

### Swift Package Manager

To integrate `UIComponents` into your Xcode project, add it as a dependency in your `Package.swift` file:

```swift
.package(url: "https://github.com/MTD-Technology-Romania/swiftui-components)", from: "1.0.0")
```

Then, add `Components` to your target's dependencies.

```swift
.target(
    name: "Components",
    dependencies: ["Components"]
),
```

### Usage

Here's a simple example demonstrating how to use a component from UIComponents in your SwiftUI code:

```swift
import Components

struct ContentView: View {
    var body: some View {
        VStack {
            InputView(title: "Email", color: .gray, systemImage: "envelope", inputBackground: .white, inputOverlay: .gray) {
                TextField("Enter your email here", text: .constant(""))
                  .textContentType(.emailAddress)
                  .keyboardType(.emailAddress)
                  .foregroundColor(.gray)
            }
            .padding()
            // Add more components as needed
        }
    }
}
```

### Usage `LargeTitleView`

```swift

import SwiftUI
import Components

struct ContentView: View {
    var body: some View {
        NavigationView {
            List {
                ForEach(1..<50) { index in
                    Text("Sample Row \(String(index))")
                }
            }
            .navigationTitle("Navigation")
            .navigationLargeTitleItems(trailing: ProfileIcon())
        }
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}

struct ProfileIcon: View {
    var body: some View{
        Button(action: {
            print("Profile button was tapped")
        }) {
            Image(systemName: "person.circle.fill")
                .resizable()
                .aspectRatio(contentMode: .fit)
                .foregroundColor(.red)
                .frame(width: 36, height: 36)
        }
        .padding([.trailing], 20)
        .padding([.top], 5)
    }
}

```

## Documentation

For detailed documentation and examples, refer to the [Documentation folder](Documentation/) in this repository.

## Contributing

Contributions are welcome! Please follow our [Contribution Guidelines](CONTRIBUTING.md).

## License

YourPackageName is available under the MIT license. See the [LICENSE](LICENSE) file for more info.

# 📡 NetworkManager - Swift HTTP Request Utility

A simple, reusable Swift utility class for making HTTP GET and POST requests using `URLSession`.

## 🚀 Features

- Lightweight and easy to integrate
- Supports GET and POST requests
- Built with Swift Concurrency (`Result` type)
- Centralized network handling logic

## 📂 How to Use

### ➕ Add to Your Project

1. Drag `NetworkManager.swift` into your Xcode project.
2. Ensure "Copy items if needed" is checked.
3. Add it to your app target.

---

## ⚙️ Usage Example

### 🔍 GET Request

```swift
NetworkManager.shared.getRequest(urlString: "https://api.example.com/data") { result in
    switch result {
    case .success(let data):
        print("✅ Data received: \(data)")
    case .failure(let error):
        print("❌ Error: \(error)")
    }
}
```

### 🔍 Post Request

```swift

let parameters = [
    "email": "user@example.com",
    "password": "123456"
]

NetworkManager.shared.postRequest(
    urlString: "https://api.example.com/login",
    parameters: parameters
) { result in
    switch result {
    case .success(let data):
        print("✅ Login Success: \(data)")
    case .failure(let error):
        print("❌ Login Failed: \(error)")
    }
}


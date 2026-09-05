# IATA Air Cargo AWB & Aviation Validator — .NET / C# SDK

[![NuGet version](https://img.shields.io/nuget/v/StanzaApi.IataValidator.svg)](https://www.nuget.org/packages/StanzaApi.IataValidator/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stanza API](https://img.shields.io/badge/Powered%20by-Stanza-blue)](https://stanzaapi.com)

> Validate IATA Resolution 600a Air Waybills (11-digit MOD-7), e-tickets, and airline accounting prefixes in sub-5ms.

Official high-performance .NET client library for **IATA Air Cargo AWB & Aviation Validator**, built on the [Stanza Micro-API Network](https://stanzaapi.com). Fully compatible with .NET Standard 2.0, .NET 6.0, .NET 7.0, and .NET 8.0+.

* 🌐 **Online Interactive Sandbox:** [Test your inputs live](https://stanzaapi.com/tools/iata-validator)
* 📚 **API Reference & Schemas:** [View documentation on Stanza](https://stanzaapi.com/tools/iata-validator)
* ⚡ **Platform Overview:** [Explore the Stanza Developer Network](https://stanzaapi.com)

---

## 📦 Installation

```bash
dotnet add package StanzaApi.IataValidator
```

---

## 🚀 Quickstart

```csharp
using System;
using System.Threading.Tasks;
using StanzaApi.IataValidator;

class Program
{
    static async Task Main()
    {
        // Initialize client (reads STANZA_API_KEY from environment if not passed)
        var client = new IataValidatorClient();

        // Perform deterministic verification
        string responseJson = await client.ValidateAsync("020-12345675");
        Console.WriteLine(responseJson);
    }
}
```

---

## 📄 Example Response

```json
{
  "success": true,
  "data": {
    "valid": true,
    "prefix": "020",
    "airline": "Lufthansa Cargo",
    "serial_number": "1234567",
    "check_digit": 5
  }
}
```

---

## ⚙️ Configuration

Pass options directly to the `IataValidatorClient` constructor:

```csharp
var client = new IataValidatorClient(
    apiKey: "your_api_key_here",
    baseUrl: "https://stanzaapi.com"
);
```

---

## 🔗 Useful Links

* [IATA Air Cargo AWB & Aviation Validator Interactive Sandbox](https://stanzaapi.com/tools/iata-validator)
* [Stanza Developer Directory](https://stanzaapi.com)
* [Source Code & Issue Tracker](https://github.com/stanzaapi/iata-validator-csharp)

## 📄 License

MIT © Stanza — Powered by [Stanza](https://stanzaapi.com).

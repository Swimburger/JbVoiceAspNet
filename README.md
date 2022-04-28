# Twilio Voice for .NET demos for JetBrains Webinar
Watch the webinar: [Calls with .NET and Twilio](https://www.youtube.com/watch?v=n4jnwgT2oJA).

## How to run these samples
1. Create a free Twilio account, or log into your existing Twilio account. If you register here, you'll receive $10 in Twilio credit when you upgrade to a paid account!
2. Create a Twilio API key ([more info on creating API Keys here](https://www.twilio.com/blog/better-twilio-authentication-csharp-twilio-api-keys))
3. [Create a TwiML Application and take not of the Application SID](https://support.twilio.com/hc/en-us/articles/223180928-How-Do-I-Create-a-TwiML-App-) (leave configuration empty)
4. Buy a Twilio phone number using the Twilio CLI or [Twilio Console](https://support.twilio.com/hc/en-us/articles/223135247-How-to-Search-for-and-Buy-a-Twilio-Phone-Number-from-Console)
5. Download or clone the source code
6. Open a terminal and navigate to the CallPhoneNumber project `cd MakePhoneCalls/CallPhoneNumber`
7. Configure the Twilio Account SID, API Key SID, API Key Secret, Phone Number, and Application SID using the .NET Secrets Manager:
```bash
dotnet user-secrets set Twilio:AccountSid [YOUR_ACCOUNT_SID]
dotnet user-secrets set Twilio:ApiKeySid [YOUR_API_KEY_SID]
dotnet user-secrets set Twilio:ApiKeySecret [YOUR_API_KEY_SECRET]
dotnet user-secrets set Twilio:PhoneNumber [YOUR_TWILIO_PHONE_NUMBER]
dotnet user-secrets set Twilio:ApplicationSid [YOUR_TWIML_APPLICATION_SID]
```
This configuration will be applied and are shared across all projects that need them.
8. Install and authenticate the `ngrok` CLI

### MakePhoneCalls.sln

Run the console application and provide your Twilio Phone Number to the `from: ` prompt, and your private phone number to the `to: ` prompt.
If you want to change the TwiML instructions to use the WebhookService:
1. Start the WebhookService application
2. Create an ngrok tunnel using `ngrok http [YOUR_WEBHOOK_SERVICE_LOCALHOST_URL]`
3. Grab the ngrok forwarding URL and replace `http://demo.twilio.com/docs/voice.xml` with the forwarding URL.
4. Run the console project

### VoiceAspNet.sln

Run all the projects in the solution and browse to https://localhost:7000.

## Useful links
- [Twilio blog .NET tag](https://www.twilio.com/blog/tag/net)
- [Twilio SDK for C# and .NET](https://www.twilio.com/docs/libraries/csharp-dotnet)
- [Twilio helper library for ASP.NET](https://github.com/twilio-labs/twilio-aspnet/)
- [Twilio Docs](https://www.twilio.com/docs)
- [Integrate ngrok into ASP.NET Core startup and automatically update your webhook URLs](https://www.twilio.com/blog/integrate-ngrok-into-aspdotnet-core-startup-and-automatically-update-your-webhook-urls)
- [Better Twilio Authentication with API Keys](https://www.twilio.com/blog/better-twilio-authentication-csharp-twilio-api-keys)
- [How to use Twilio SMS and Voice with a .NET 6 Minimal API](https://www.twilio.com/blog/sms-voice-dotnet-6-minimal-api)
- [How to make Phone Calls from Blazor WebAssembly with Twilio Voice](https://www.twilio.com/blog/making-phone-calls-from-blazor-webassembly-with-twilio-voice)


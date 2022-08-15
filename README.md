# Validate Callback Request event from Sinch Verification using dotnet

This project validates a Verification Event callback received from the Sinch platform when using the [Sinch Verification](https://dashboard.sinch.com/verification/overview) product with callbacks enabled.

## Requirements

- dotnet 6.*
- ngrok

## Install

- replace the required values in the `./VerificationEventHandler/Controllers/VerificationEventsController.cs` file
- run the server using `dotnet run --project VerificationEventHandler`
- start ngrok `ngrok http 5000` (port 5000 is used by default by Kestrel)
  - copy the ngrok url to the Verification App that you will receive Verification Events from to your [Sinch Dashboard](https://dashboard.sinch.com/verification/apps)
  - make sure to append the following URI at the end of the URL, `/api/verification/events`
  - example `https://df6a-143-177-206-33.ngrok.io/api/verification/events`
- test using the SMS PIN Verification script found in the project
  - replace the required values in the `./SMSVerificationTestScript/Program.cs` file
  - `dotnet build --project SMSVerificationTestScript`
  - `dotnet run --project SMSVerificationTestScript`

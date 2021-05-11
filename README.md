---
page_type: sample
languages:
  - csharp
products:
  - azure
  - azure-media-services
description: "The samples in this repo show how to encode, package, protect, analyze your videos with Azure Media Services v3 using .NET SDK. You also learn how to perform live ingest in order to broadcast your events."  
---
 
# Azure Media Services v3 samples using .NET

The samples in this repo show how to encode, package, protect your videos with Azure Media Services v3 using .NET SDK. The repo also contains samples that demonstrate how to analyze videos and perform live ingest in order to broadcast your events.  

To install the latest version of the Microsoft.Azure.Management.Media client SDK go to the Nuget package [Microsoft.Azure.Management.Media](https://www.nuget.org/packages/Microsoft.Azure.Management.Media)

## .NET solution files and how to launch projects

Open the root /Media-services-v3-dotnet.sln (or just open the folder in VS Code).
The main solution contains all of the projects.  You can select the active project to launch in Visual Studio.

When using VS Code, select the project you wish to Launch in the Debugger console (Ctrl-shift-D).

There is a separate solution file provided for the [HighAvailabilityEncodingStreaming](/HighAvailabilityEncodingStreaming/Readme.md) sample. Please switch to this solution, or open it in a new Visual Studio instance.

## Contents

| Folder | Description |
|-------------|-------------|
| [VideoEncoding/Encoding_PredefinedPreset](/VideoEncoding/Encoding_PredefinedPreset)|The sample shows how to submit a job using a built-in preset and an HTTP URL input, publish output asset for streaming, and download results for verification.|
| [VideoEncoding/Encoding_H264](/VideoEncoding/Encoding_H264)|The sample shows how to submit a job using a custom H.264 encoding preset and an HTTP URL input, publish output asset for streaming, and download results for verification.|
| [VideoEncoding/Encoding_HEVC](/VideoEncoding/Encoding_HEVC)|The sample shows how to submit a job using a custom HEVC encoding preset and an HTTP URL input, publish output asset for streaming, and download results for verification.|
| [VideoEncoding/Encoding_StitchTwoAssets](/VideoEncoding/Encoding_StitchTwoAssets)|The sample shows how to submit a job using the JobInputSequence to stitch together 2 or more assets that may be clipped by start or end time. The resulting encoded file is a single video with all assets stitched together.  The sample will also  publish output asset for streaming and download results for verification.|
| [VideoEncoding/Encoding_SpriteThumbnail](/VideoEncoding/Encoding_SpriteThumbnail)|The sample shows how to submit a job using a custom preset with a thumbnail sprite and an HTTP URL input, publish output asset for streaming, and download results for verification.|
| [Live/LiveEventWithDVR](/Live/LiveEventWithDVR)|This sample first shows how to create a LiveEvent with a full archive up to 25 hours and an filter on the asset with 5 minutes DVR window, then it shows how to use the filter to create a locator for streaming.|
| [VideoAnalytics/VideoAnalyzer](/VideoAnalytics/VideoAnalyzer)|This sample illustrates how to create a video analyzer transform, upload a video file to an input asset, submit a job with the transform and download the results for verification.|
| [AudioAnalytics/AudioAnalyzer](/AudioAnalytics/AudioAnalyzer)|This sample illustrates how to create a audio analyzer transform, upload a media file to an input asset, submit a job with the transform and download the results for verification.|
| [ContentProtection/BasicAESClearKey](/ContentProtection/BasicAESClearKey)|This sample demonstrates how to create a transform with built-in AdaptiveStreaming preset, submit a job, create a ContentKeyPolicy using a secret key, associate the ContentKeyPolicy with StreamingLocator, get a token and print a url for playback in Azure Media Player. When a stream is requested by a player, Media Services uses the specified key to dynamically encrypt your content with AES-128 and Azure Media Player uses the token to decrypt.|
| [ContentProtection/BasicWidevine](/ContentProtection/BasicWidevine)|This sample demonstrates how to create a transform with built-in AdaptiveStreaming preset, submit a job, create a ContentKeyPolicy with Widevine configuration using a secret key, associate the ContentKeyPolicy with StreamingLocator, get a token and print a url for playback in a Widevine Player. When a user requests Widevine-protected content, the player application requests a license from the Media Services license service. If the player application is authorized, the Media Services license service issues a license to the player. A Widevine license contains the decryption key that can be used by the client player to decrypt and stream the content.|
| [ContentProtection/BasicPlayReady](/ContentProtection/BasicPlayReady)|This sample demonstrates how to create a transform with built-in AdaptiveStreaming preset, submit a job, create a ContentKeyPolicy with PlayReady configuration using a secret key, associate the ContentKeyPolicy with StreamingLocator, get a token and print a url for playback in a Azure Media Player. When a user requests PlayReady-protected content, the player application requests a license from the Media Services license service. If the player application is authorized, the Media Services license service issues a license to the player. A PlayReady license contains the decryption key that can be used by the client player to decrypt and stream the content.|
| [ContentProtection/OfflinePlayReadyAndWidevine](/ContentProtection/OfflinePlayReadyAndWidevine)|This sample demonstrates how to dynamically encrypt your content with PlayReady and Widevine DRM and play the content without requesting a license from license service. It shows how to create a transform with built-in AdaptiveStreaming preset, submit a job, create a ContentKeyPolicy with open restriction and PlayReady/Widevine persistent configuration, associate the ContentKeyPolicy with a StreamingLocator and print a url for playback.|
| [Streaming/AssetFilters](/Streaming/AssetFilters)|This sample demonstrates how to create a transform with built-in AdaptiveStreaming preset, submit a job, create an asset-filter and an account-filter, associate the filters to streaming locators and print urls for playback.|
| [Streaming/StreamHLSAndDASH](/Streaming/StreamHLSAndDASH)|This sample demonstrates how to create a transform with built-in AdaptiveStreaming preset, submit a job, publish output asset for HLS and DASH streaming.|
| [HighAvailabilityEncodingStreaming](/HighAvailabilityEncodingStreaming/) | This sample provides guidance and best practices for a production system using on-demand encoding or analytics. Readers should start with the companion article [High Availability with Media Services and VOD](https://docs.microsoft.com/azure/media-services/latest/media-services-high-availability-encoding). There is a separate solution file provided for the [HighAvailabilityEncodingStreaming](/HighAvailabilityEncodingStreaming/Readme.md) sample. |
| [Common_Utils](/Common_Utils/) | Library used by the samples for the authentication using MSAL and other shared code. |

## Prerequisites

- A Windows 10 PC, Mac or Linux
- Visual Studio 2019 (Windows 10), or optional Visual Studio Code (Windows, Mac or Linux)

## Setup

- Clone or download this sample repository.
- Open the solution file media-services-v3-dotnet.sln in Visual Studio 2019, or open the folder in Visual Studio Code.
- Read sample's README.md to see what key concepts to review and how to set up and run the sample.
- Select the project to Run in the Debugger (ctrl-shift-D in VS Code on Window) and press F5 to launch

## Troubleshooting and known issues

| Issue or Error message | Notes |
|-------------|-----------|
|"Encountered error while fetching the list of EventHub PartitionIds" | Make sure that you are using the SAS policy for the EventHub and not the EventHub namespace. Also make sure that your .env or appsettings.json file is pointing to the name of the EventHub (instance) and not the EventHub namespace (which is higher level entity in the portal).|

## See also

Nodejs samples : <https://github.com/Azure-Samples/media-services-v3-node-tutorials>
Java samples: <https://github.com/Azure-Samples/media-services-v3-java>

## Next steps

- Azure Media Services documentation: <https://docs.microsoft.com/en-us/azure/media-services/>
- Azure Media Services pricing: <https://azure.microsoft.com/en-in/pricing/details/media-services/>

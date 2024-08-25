Here's the documentation for the MIT App Inventor extension based on the provided screenshots and description of the blocks:

---

# MIT App Inventor Extension: InstallReferrer

## Overview
The InstallReferrer extension for MIT App Inventor allows you to interact with the Google Play Store to retrieve install referrer information. This includes details about the referrer URL, click timestamp, install timestamp, and whether the app was installed via Google Play Instant. The extension also supports automatic retry logic for handling service unavailability.

## Methods

### FetchAppInstallTime
- **Description**: Retrieves the app install time in seconds since the Unix epoch. This indicates when the app was first installed.
- **Return Type**: Number
- **Block Screenshot**: ![FetchAppInstallTime Block](https://i.postimg.cc/k4x38r0F/Fetch-App-Install-Time-Block.png)

### FetchGooglePlayInstantParam
- **Description**: Checks if the app was installed via Google Play Instant. Returns `true` if installed via Google Play Instant, otherwise `false`.
- **Return Type**: Boolean
- **Block Screenshot**: ![FetchGooglePlayInstantParam Block](https://i.postimg.cc/kGmChMQp/Fetch-Google-Play-Instant-Param-Block.png)

### FetchReferrerClickTime
- **Description**: Retrieves the referrer click time in seconds since the Unix epoch. This indicates when the referrer URL was clicked.
- **Return Type**: Number
- **Block Screenshot**: ![FetchReferrerClickTime Block](https://i.postimg.cc/NFkthhbf/Fetch-Referrer-Click-Time-Block.png)

### FetchReferrerDetails
- **Description**: Fetches install referrer details from the Play Store. Includes referrer URL, referrer click timestamp, app install timestamp, and Google Play Instant status. Should be called only once after app installation.
- **Block Screenshot**: ![FetchReferrerDetails Block](https://i.postimg.cc/wxXgRJH8/Fetch-Referrer-Details-Block.png)

### GetDeepLinkUrl
- **Description**: Retrieves the deep link URL from the referrer details if available. Assumes the deep link is part of the referrer URL.
- **Return Type**: Text
- **Block Screenshot**: ![GetDeepLinkUrl Block](https://i.postimg.cc/HsTHwxsJ/Get-Deep-Link-Url-Block.png)

### InitiateConnection
- **Description**: Initiates a connection to the Google Play Store to retrieve install referrer information. Includes automatic retry logic. On success, the `OnConnectionEstablished` event is triggered.
- **Block Screenshot**: ![InitiateConnection Block](https://i.postimg.cc/WbSVXvh5/Initiate-Connection-Block.png)

### IsReferrerDetailsFetched
- **Description**: Checks if the referrer details have already been fetched. Returns `true` if details have been fetched, otherwise `false`.
- **Return Type**: Boolean
- **Block Screenshot**: ![IsReferrerDetailsFetched Block](https://i.postimg.cc/2S6DtKWr/Is-Referrer-Details-Fetched-Block.png)

### IsReferrerFeatureSupported
- **Description**: Checks if the Install Referrer API is supported on the device. Returns `true` if supported, otherwise `false`.
- **Return Type**: Boolean
- **Block Screenshot**: ![IsReferrerFeatureSupported Block](https://i.postimg.cc/XYzb6kKF/Is-Referrer-Feature-Supported-Block.png)

### ResetFetchedState
- **Description**: Resets the fetched state to allow fetching referrer details again. Use with caution, as referrer details are typically only fetched once after installation.
- **Block Screenshot**: ![ResetFetchedState Block](https://i.postimg.cc/nL9tF9TW/Reset-Fetched-State-Block.png)

### TerminateConnection
- **Description**: Ends the connection to the Google Play Store. Should be called to release resources once referrer details are retrieved.
- **Block Screenshot**: ![TerminateConnection Block](https://i.postimg.cc/d1McLQxV/Terminate-Connection-Block.png)

### WasReferrerClickedRecently
- **Description**: Checks if the install referrer was clicked within the last 24 hours. Returns `true` if the click occurred within the last 24 hours, otherwise `false`.
- **Return Type**: Boolean
- **Block Screenshot**: ![WasReferrerClickedRecently Block](https://i.postimg.cc/RZsMVBmW/Was-Referrer-Clicked-Recently-Block.png)

## Events

### OnConnectionEstablished
- **Description**: Triggered when the connection to the Play Store is established or fails. The success parameter indicates if the connection was successful.
- **Parameter**: 
  - `success` (Boolean)

- **Block Screenshot**: ![OnConnectionEstablished Block](https://i.postimg.cc/HksYgLqG/On-Connection-Established-Block.png)

### OnDisconnected
- **Description**: Triggered when the connection to the Play Store is unexpectedly disconnected.
- **Block Screenshot**: ![OnDisconnected Block](https://i.postimg.cc/TPKTK42C/On-Disconnected-Block.png)

### OnReferrerDetailsFetchFailed
- **Description**: Triggered when there is an error fetching the referrer details. Provides an error message describing the failure.
- **Parameter**: 
  - `error` (Text)

- **Block Screenshot**: ![OnReferrerDetailsFetchFailed Block](https://i.postimg.cc/Xvt4dkp3/On-Referrer-Details-Fetch-Failed-Block.png)

### OnReferrerDetailsFetched
- **Description**: Triggered when referrer details are successfully retrieved. Provides referrer URL, referrer click timestamp, app install timestamp, and Google Play Instant status.
- **Parameters**:
  - `referrerUrl` (Text)
  - `referrerClickTime` (Number)
  - `appInstallTime` (Number)
  - `googlePlayInstant` (Boolean)

- **Block Screenshot**: ![OnReferrerDetailsFetched Block](https://i.postimg.cc/JnJmqHkX/On-Referrer-Details-Fetched-Block.png)

## Notes
- Referrer details can typically only be fetched once after installation.
- Ensure that `InitiateConnection` is called to establish a connection before attempting to fetch referrer details.
- Use `TerminateConnection` to properly close the connection and release resources.

This documentation is generated using [Riad Developer Documentation Generator](https://riaddeveloper.000.pe).

--- 

Feel free to adjust or add any additional details specific to your application or use case!


# InstallReferrer Extension Documentation

The InstallReferrer extension for MIT App Inventor allows you to retrieve Install Referrer information from Google Play. It provides methods to fetch various referrer details and events related to the connection with the Play Store.

## Methods

### 1. **FetchAppInstallTime**

- **Description:** Retrieves the app install time in seconds since the Unix epoch. This is the timestamp when the app was first installed.
- **Return Type:** `number`
- **Block Screenshot:**
  ![FetchAppInstallTime](https://i.postimg.cc/FzssX63M/Fetch-App-Install-Time-Block.png)

### 2. **FetchGooglePlayInstantParam**

- **Description:** Checks if the app was installed via Google Play Instant. Returns `true` if the app was installed via Google Play Instant, `false` otherwise.
- **Return Type:** `boolean`
- **Block Screenshot:**
  ![FetchGooglePlayInstantParam](https://i.postimg.cc/Y0n2rxxh/Fetch-Google-Play-Instant-Param-Block.png)

### 3. **FetchReferrerClickTime**

- **Description:** Retrieves the referrer click time in seconds since the Unix epoch. This is the timestamp when the referrer URL was clicked.
- **Return Type:** `number`
- **Block Screenshot:**
  ![FetchReferrerClickTime](https://i.postimg.cc/1RJ3r9Zs/Fetch-Referrer-Click-Time-Block.png)

### 4. **FetchReferrerDetails**

- **Description:** Fetches install referrer details from the Play Store, including the referrer URL, the timestamp when the referrer was clicked, the timestamp when the app was installed, and whether the app was installed via Google Play Instant. This method should be called only once after the app is installed, as referrer details can only be fetched once.
- **Block Screenshot:**
  ![FetchReferrerDetails](https://i.postimg.cc/0245hcQ4/Fetch-Referrer-Details-Block.png)

### 5. **GetDeepLinkUrl**

- **Description:** Retrieves the deep link URL from the referrer details, if available. This method assumes the deep link is part of the referrer URL.
- **Return Type:** `text`
- **Block Screenshot:**
  ![GetDeepLinkUrl](https://i.postimg.cc/GhthMZcY/Get-Deep-Link-Url-Block.png)

### 6. **InitiateConnection**

- **Description:** Initiates the connection to the Google Play Store to retrieve install referrer information. This method includes automatic retry logic to handle cases where the Play Store service is unavailable. If the connection is successful, the `OnConnectionEstablished` event will be triggered.
- **Block Screenshot:**
  ![InitiateConnection](https://i.postimg.cc/Hk7WmX8k/Initiate-Connection-Block.png)

### 7. **IsReferrerDetailsFetched**

- **Description:** Checks if the referrer details have already been fetched. Returns `true` if the details have been fetched, `false` otherwise.
- **Return Type:** `boolean`
- **Block Screenshot:**
  ![IsReferrerDetailsFetched](https://i.postimg.cc/7L8HZhSM/Is-Referrer-Details-Fetched-Block.png)

### 8. **IsReferrerFeatureSupported**

- **Description:** Checks if the Install Referrer API is supported on this device. Returns `true` if supported, `false` otherwise.
- **Return Type:** `boolean`
- **Block Screenshot:**
  ![IsReferrerFeatureSupported](https://i.postimg.cc/YS6pG73c/Is-Referrer-Feature-Supported-Block.png)

### 9. **ResetFetchedState**

- **Description:** Resets the fetched state to allow fetching referrer details again. Use this function with caution as referrer details are typically only fetched once after install.
- **Block Screenshot:**
  ![ResetFetchedState](https://i.postimg.cc/YqDjMtXb/Reset-Fetched-State-Block.png)

### 10. **TerminateConnection**

- **Description:** Ends the connection to the Google Play Store. This should be called to release resources once the referrer details have been successfully retrieved.
- **Block Screenshot:**
  ![TerminateConnection](https://i.postimg.cc/W3V1Xz3b/Terminate-Connection-Block.png)

### 11. **WasReferrerClickedRecently**

- **Description:** Checks if the install referrer was clicked within the last 24 hours. Returns `true` if the click occurred within the last 24 hours, `false` otherwise.
- **Return Type:** `boolean`
- **Block Screenshot:**
  ![WasReferrerClickedRecently](https://i.postimg.cc/Y9xqV7GN/Was-Referrer-Clicked-Recently-Block.png)

## Events

### 1. **OnConnectionEstablished**

- **Description:** Triggered when the connection to the Play Store is either established successfully or fails. The `success` parameter indicates whether the connection was successful (`true`) or not (`false`).
- **Parameter:**
  - `success` (`boolean`)
- **Block Screenshot:**
  ![OnConnectionEstablished](https://i.postimg.cc/Pr5NgCMC/On-Connection-Established-Block.png)

### 2. **OnDisconnected**

- **Description:** Triggered when the connection to the Play Store is unexpectedly disconnected.
- **Block Screenshot:**
  ![OnDisconnected](https://i.postimg.cc/HkJnLFRH/On-Disconnected-Block.png)

### 3. **OnReferrerDetailsFetched**

- **Description:** Triggered when the referrer details are successfully retrieved. The event provides the referrer URL, the timestamp of the referrer click, the timestamp of the app install, and whether the app was installed via Google Play Instant.
- **Parameters:**
  - `referrerUrl` (`text`)
  - `referrerClickTime` (`number`)
  - `appInstallTime` (`number`)
  - `googlePlayInstant` (`boolean`)
- **Block Screenshot:**
  ![OnReferrerDetailsFetched](https://i.postimg.cc/SKCK6Cmv/On-Referrer-Details-Fetched-Block.png)

### 4. **OnReferrerDetailsFetchFailed**

- **Description:** Triggered when there is an error while fetching the referrer details. The `error` parameter provides a message describing the failure.
- **Parameter:**
  - `error` (`text`)
- **Block Screenshot:**
  ![OnReferrerDetailsFetchFailed](https://i.postimg.cc/CxW1nmp8/On-Referrer-Details-Fetch-Failed-Block.png)

---

This documentation should help you understand and utilize the InstallReferrer extension in MIT App Inventor. If you need further assistance or have additional questions, feel free to ask!

# Welcome!

### Base URL
The DebtPayPro API is served over HTTPS. All URLs referenced in the documentation have the following base:
<div>
  <code>https://api.debtpaypro.com/v1</code>
</div>

</br>


### Authentication Methods

Access to All API endpoints provided through the DebtPayPro API requires authentication. A valid **_API Key_** must be included when sending a Request. If you do not have an API Key or your previous Key has expired, then you will need to obtain a new one by completing the following steps:

1.  Log-in to the CRM and navigate to the [API Credentials Page](https://login.debtpaypro.com/index.php?module=administration&page=api).
2.  On the _API Credentials Page_ select a Company, select a User, then click the _Generate Key_ Button.
3.  A _Credential Creation Modal_ will appear displaying an **API Secret** and **Key ID**. Copy and save both values in a secure location.
4.  Now you must navigate to the [Auth API Request](https://debtpaypro.stoplight.io/docs/dpp-api/branches/devQA/b3A6MjU2NTAwNDA-get-api-authorization-token). Enter the **API Secret** and **Key ID** in the appropriate input fields, then click the _Send Request_ Button.
5.  If your request is successful an Api-Key will be returned with the response. Stoplight will automatically retain and pass this Api-Key into your future API Requests.

</br>


### Rate Limiting

Use of the DebtPayPro API is subject to rate limiting. The current **Request Rate Limit** is set to *20 Requests/Second* for either a unique *Session ID* or *IP Address*. If the Request Rate Limit is reached you will be sent a standard HTTP Code indicating you have exceeded this limit and your API use is now being throttled. 


---
tags: [Authentication]
---

### Authentication

<p>Access to All API endpoints provided through the DebtPayPro API requires   authentication. A valid <b><em>API Key</em></b> must be included when sending a Request. If you do not have an API Key or your previous Key has expired, then you will need to obtain a new one by completing the following steps:</p> 
        <ol>
          <li>Log-in to the CRM and navigate to the <a href="https://login.debtpaypro.com/index.php?module=administration&page=api">API Credentials Page</a>.</li>
          <li>On the <i>API Credentials Page</i> select a Company, select a User, then click the <em>Generate Key</em> Button.</li>
          <li>A <i>Credential Creation Modal</i> will appear displaying an <b>API Secret</b> and <b>Key ID</b>. Copy and save both values in a secure location.</li>
          <li>Now you must navigate to the <a href="https://debtpaypro.stoplight.io/docs/dpp-api/branches/devQA/b3A6MjU2NTAwNDA-get-api-authorization-token">Auth API Request</a>. Enter the <b>API Secret</b>
          and <b>Key ID</b> in the appropriate input fields, then click the <em>Send Request</em> Button.</li>
          <li>If your request is successful an Api-Key will be returned with the response. Stoplight will automatically retain and pass this Api-Key into your future API Requests.</li>
        </ol>

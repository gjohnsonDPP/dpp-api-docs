 # API Documentation Guide
 1. Make a branch off of the **Development Branch**.
 2. Goto the [DebtPayPro API](https://debtpaypro.stoplight.io/docs/dpp-api/ZG9jOjQ2NDA2-introduction) Stoplight Documentation.
 3. Access the web version of *Stoplight Studio* by selecting the **Edit Button**.
 4. ⚠️Before editing any content, make sure that you are editing YOUR Branch. At the top-center of the page you will see the name of the branch you are editing displayed after the text **DebtPayPro API /**. If you are on the wrong branch you can select the current branch name shown and switch to the correct one.
 5. The general components of every API Request Documentation include:
    - Paths
    - Models
    - Bodies
    - Examples
 6. The first component to document is the API Request Path. In *Stoplight Studio*, right-click the **Paths** directory and create a new Path.
 7. To assist in the documentation of the API Path, refer to the section below: ***API Request Path Templates***. When finished with created the API Path, continue to Step 8.  
 
 ## API Request Path Templates
 #### POST REQUEST TEMPLATE
  ```yaml
  /demos:
    post:
      summary: Create a <demo> Record
      description: |-
        Creates a Call Record and log the call to a client.

        <span><i class="fa fa-info-circle"></i><i style="font-size:12px"> Select the `'Examples'` option to change the content of the request's Body to ONLY contain the required POST Parameters.</i></span>
      operationId: demoCreate
      tags:
        - Demos
      requestBody:
        description: ""
        required: true
        content:
          application/json:
            schema:
              $ref: <path to Demo Model>
            examples:
              Request:
                $ref: <path to Demo POST Example>
              Required Parameters Only:
                $ref: <path to Demo POST Required Parameters ONLY>
      responses:
        '200':
          description: Successfully created a <Demo> Record
          content:
            application/json:
              schema:
                type: object
                properties:
                  response:
                    type: object
                  status:
                    $ref: models/SuccessStatus.yaml
              examples:
                <Demo> POST 200 Response Example:
                  value:
                    response:
                      id: <123456789>
                    status:
                      code: 200
        '400':
          description: Error
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    $ref: models/ErrorStatus.yaml
              examples:
                <Demo> POST 400 Response Example:
                  value:
                    status:
                      code: 400
                      message: Bad Request - The system encountered an error
                  ```

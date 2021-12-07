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
 #### GET REQUEST TEMPLATE
 ```yaml
   '/demos/{id}':
    get:
      tags:
        - Demos
      summary: Find a <demo> Record by ID
      description: Returns a <demo> Record
      operationId: demoRead
      parameters:
        - name: id
          in: path
          description: Id of Demo Record to return
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: Successfully retrieved a <Demo> Record
          content:
            application/json:
              schema:
                type: object
                properties:
                  response:
                    $ref: <path to Demo Model>
                  status:
                    $ref: models/SuccessStatus.yaml
              examples:
                <Demo> GET 200 Response Example:
                  $ref: <path to example>
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
                <Demo> GET 400 Response Example:
                  value:
                    status:
                      code: 400
                      message: Bad Request - The system encountered an error.
  ```
  #### PUT REQUEST TEMPLATE
  ```yaml
      put:
      tags:
        - Demos
      summary: Update a <Demo> Record by ID
      description: Updates a <Demo> Record
      operationId: demoUpdate
      requestBody:
        content:
          application/json:
            schema:
              $ref: <path to Demo Response Model>
      parameters:
        - name: id
          in: path
          description: Id of <Demo> Record to update
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: Successfully Updated a <Demo> Record
          content:
            application/json:
              schema:
                type: object
                properties:
                  response:
                    $ref: <path to Demo Response Model>
                  status:
                    $ref: models/SuccessStatus.yaml
              examples:
                <Demo> PUT 200 Response Example:
                  $ref: <path to example>
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
                <Demo> PUT 400 Response Example:
                  value:
                    status:
                      code: 400
                      message: Bad Request - The system encountered an error.
  ```
  #### DELETE REQUEST TEMPLATE
  ```yaml
      delete:
      tags:
        - Demos
      summary: Delete <Demo> Record by ID
      description: Deletes a <Demo> Record
      operationId: demoDelete
      parameters:
        - name: id
          in: path
          description: Id of <Demo> Record to be deleted
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: Successfully Deleted a <Demo> Record
          content:
            application/json:
              schema:
                type: object
                properties:
                  status:
                    $ref: models/SuccessStatus.yaml
              examples:
                <Demo> DELETE 200 Response Example:
                  value:
                    status:
                      code: 200
                      message: Successfully Deleted object.
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
                <Demo> PUT 400 Response Example:
                  value:
                    status:
                      code: 400
                      message: Bad Request - The system encountered an error.
   ```

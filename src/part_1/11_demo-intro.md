# Demo

<p class="text-xl">Lorem Ipsum Dolor</p>

---

<details open>
  <summary class="w-60 m-t-24 m-b-12 p-b-8 text-2xl font-bold" style="border-bottom: 2px solid var(--aruna-highlight)">Info Endpoint</summary>

  <div class="flex flex-row gap-12">
    <div class="flex flex-col flex-35">

  ### Get general info about a specific Node

  ```sh
  curl -X 'GET' \
       -H 'accept: application/json' \
       'http://localhost:8081/api/v3/info'
  ```
  </div>
  <div class="flex flex-45">
    <details class="m-y-12">
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "realm_id": "b4e63113c8f2d85f743841abecd8b10a873aa43207306d86c212967c9a8c1900",
    "node_id": "a16395bd7963f6c618fadb266e0f5f52b98cbeacade7cf80449c6ce42c61d7d1",
    "node_addr": {
      "node_id": "a16395bd7963f6c618fadb266e0f5f52b98cbeacade7cf80449c6ce42c61d7d1",
      "relay_url": null,
      "direct_addresses": [
        "134.176.138.7:1231",
        "172.17.0.1:1231",
        "172.18.0.1:1231"
      ]
    }
  }
  ```
  </details>
  </div>
  </div>

  ---

  <div class="flex flex-row gap-12">
    <div class="flex flex-col flex-35">
  
  ### Get general info about a specific realm

  ```sh
  curl -X 'GET' \
       -H 'accept: application/json' \
       'http://<node-host>/api/v3/info/realm'
  ```
  </div>
  <div class="flex flex-45">
    <details class="m-y-12">
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "realm_id": "b4e63113c8f2d85f743841abecd8b10a873aa43207306d86c212967c9a8c1900",
    "node_id": "8e5c2c3e4771f91e7af9dd70a48cee50cb67070c3bef6ed9fcad821c85874b0f",
    "node_addr": {
      "node_id": "8e5c2c3e4771f91e7af9dd70a48cee50cb67070c3bef6ed9fcad821c85874b0f",
      "relay_url": null,
      "direct_addresses": [
        "134.176.138.7:1230",
        "172.17.0.1:1230",
        "172.18.0.1:1230"
      ]
    }
  }
  ```
  </details>
  </div>
  </div>

  ---

  <div class="flex flex-row gap-12">
    <div class="flex flex-col flex-35">

  ### Search for resources by keyword(s)

  ```sh
  curl -X 'GET' \
      -H 'accept: application/json' \
      'http://localhost:8081/api/v3/info/search?query=ecoli'
  ```
  </div>
  <div class="flex flex-45">
  <details class="m-y-12">
  <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "resources": [
      {
        "authors": [
          {
            "id": "string",
            "first": "string",
            "last": "string"
          }
        ],
        "content_len": 9007199254740991,
        "count": 9007199254740991,
        "created_at": "2025-09-19T10:24:53.193Z",
        "data": [
          {
            "ContentHash": {
              "datahash": "string"
            }
          },
          {
            "Link": "string"
          }
        ],
        "deleted": true,
        "description": "string",
        "id": "string",
        "identifiers": [
          "string"
        ],
        "labels": [
          {
            "key": "string",
            "value": "string"
          }
        ],
        "last_modified": "2025-09-19T10:24:53.193Z",
        "license_id": "string",
        "locked": true,
        "name": "string",
        "revision": 9007199254740991,
        "title": "string",
        "variant": "Project",
        "visibility": "Public"
      }
    ]
  }
  ```
  </details>
  </div>
  </div>

</details>


<details>
  <summary class="w-60 m-t-24 m-b-12 p-b-8 text-2xl font-bold" style="border-bottom: 2px solid var(--aruna-highlight)">User Endpoint</summary>

  ### Add a new user

  **Request**

  ```sh
  curl -X 'POST' \
       -H 'accept: application/json' \
       -H 'Content-Type: application/json' \
       -d '{
         "name": "Jannis Schlegel"
       }' \
       'http://localhost:8081/api/v3/users'
  ```

  <details class="m-y-12">
  <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "token": "<your-initial-secret-token>",
    "user": {
      "id": "01K5EDZ8W7HRME69TM9SZ76YNB@b4e63113c8f2d85f743841abecd8b10a873aa43207306d86c212967c9a8c1900",
      "name": "Jannis Schlegel",
      "realm_key": [
        1073741824
      ]
    }
  }
  ```
  </details>

</details>



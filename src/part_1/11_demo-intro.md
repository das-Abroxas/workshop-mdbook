# Demo

<p class="text-xl">This section demonstrates how to interact with the API using practical command-line examples.</p>

<p class="text-xl">Explore the endpoints below to learn how to retrieve information and manage users.</p>


---



<!-- Info Endpoint -->
<details>
  <!--<summary class="w-60 m-t-24 m-b-12 p-b-8 text-2xl font-bold" style="border-bottom: 2px solid var(--aruna-highlight)">Info Endpoint</summary>-->
  <summary class="w-60 m-t-24 m-b-12 p-b-8 accordion-border text-2xl font-bold">Info Endpoint</summary>

<!-- Get Node Info -->
<div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
<div class="flex flex-col">

### Get general info about a specific Node
<p class="m-t-0">Use this endpoint to retrieve basic information about the requested node, including the Realm it belongs too, its id and network addresses.</p>
</div>

<div class="flex flex-row gap-12">
  <div class="flex flex-col flex-35">

  <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -H 'accept: application/json' \
       -X GET 'http://localhost:8081/api/v3/info'
  ```
  </div>

  <div class="flex flex-45">
    <details>
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
</div>
<!-- Get Node Info End -->

<!-- Get Realm Info -->
<div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
<div class="flex flex-col">

  ### Get general info about a specific Realm
<p class="m-t-0">Use this endpoint to retrieve basic information about the requested Realm.</p>
</div>

<div class="flex flex-row gap-12">
  <div class="flex flex-col flex-35">

  <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -H 'accept: application/json' \
       -X GET 'http://<node-host>/api/v3/info/realm'
  ```
  </div>

  <div class="flex flex-45">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "nodes": [
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
      },
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
      },
      {
        "realm_id": "b4e63113c8f2d85f743841abecd8b10a873aa43207306d86c212967c9a8c1900",
        "node_id": "d3d0a9d61994ca137542b7267e95bf5a00cc0b6d51170f5b2c3c8adbfcbd5a0f",
        "node_addr": {
          "node_id": "d3d0a9d61994ca137542b7267e95bf5a00cc0b6d51170f5b2c3c8adbfcbd5a0f",
          "relay_url": null,
          "direct_addresses": [
            "134.176.138.7:1232",
            "172.17.0.1:1232",
            "172.18.0.1:1232"
          ]
        }
      }
    ]
  }
  ```
  </details>
  </div>
</div>
</div>
<!-- Get Realm Info End -->

<!-- Get Search -->
<div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
<div class="flex flex-col">

  ### Search for resources by keyword(s)
<p class="m-t-0">Use this endpoint to search with keywords for metadata resources</p>
</div>

<div class="flex flex-row gap-12">
  <div class="flex flex-col flex-35">

  <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -H 'accept: application/json' \
       -X 'GET' 'http://localhost:8081/api/v3/info/search?query=ecoli'
  ```
  </div>

  <div class="flex flex-45">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "resources": [
      {
        "id": "string",
        "name": "string",
        "description": "string",
        "revision": 9007199254740991,
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
</div>
<!-- Get Search End -->

</details>
<!-- Info Endpoint End -->

<!-- Users Endpoint -->
<details>
  <summary class="w-60 m-t-24 m-b-12 p-b-8 accordion-border text-2xl font-bold">Users Endpoint</summary>

  <!-- Add User -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
    <div class="flex flex-col">

  ### Add a new user
  <p class="m-t-0">A new user needs to register via this endpoint. This returns a token, that can be
            used on any endpoint on the p2p network.</p>
    </div>
    <div class="flex flex-row gap-12">
      <div class="flex flex-col flex-35">
        <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -d '
    {
      "name": "Jannis Schlegel"
    }' \
       -H 'accept: application/json' \
       -H 'Content-Type: application/json' \
       -X POST 'http://localhost:8081/api/v3/users'       
  ```
  </div>
  <div class="flex flex-45">
    <details>
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
  </div>
  </div>
  </div>
  <!-- Add User End -->

  <!-- Authorize User -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
    <div class="flex flex-col">

  ### Query a user
  <p class="m-t-0">A user can be queried via this endpoint. In the future this endpoint can be used
            by group admins to query information about any group members or users with public
                information.</p>
    </div>
    <div class="flex flex-row gap-12">
      <div class="flex flex-col flex-35">
        <p class="m-y-0 font-bold highlight">Request</p>

  ```sh
  curl -H 'accept: application/json' \
       -X GET 'http://localhost:8083/api/v3/users?id={user-identity}'
  ```
  </div>
  <div class="flex flex-45 scroll">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "realm_id": "b4e63113c8f2d85f743841abecd8b10a873aa43207306d86c212967c9a8c1900",
    "user_id": "01K5EDZ8W7HRME69TM9SZ76YNB@b4e63113c8f2d85f743841abecd8b10a873aa43207306d86c212967c9a8c1900>",
    "user_name": "Jannis Schlegel"
  }
  ```
  </details>
  </div>
  </div>
  </div>
  <!-- Authorize User End -->
</details>
<!-- Users Endpoint End -->

<!-- Groups Endpoint -->
<details open>
  <summary class="w-60 m-t-24 m-b-12 p-b-8 accordion-border text-2xl font-bold">Groups Endpoint</summary>

  <!-- Add Group -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
    <div class="flex flex-col">

  ### Create a new Group
  <p class="m-t-0">This endpoint can be used to create a new group. Groups form the basis of
                authorization and authentication for resources in aruna.</p>
    </div>
    <div class="flex flex-row gap-12">
      <div class="flex flex-col flex-35">
        <p class="m-y-0 font-bold highlight">Request</p>

  ```sh
  curl -d '
    {
      "name": "my_group"
    }' \
       -H 'accept: application/json' \
       -H 'Content-Type: application/json' \
       -X POST 'http://localhost:8081/api/v3/groups'
  ```
  </div>
  <div class="flex flex-45 scroll">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "group": {
      "id": "01K60DD03CHA6ZZ3T01NDDPXN0",
      "realm_key": [180, 230, 49, ...],
      "name": "my_group",
      "roles": [
        "admin",
        "member"
      ],
      "members": {
        "01K60DC77A5YCZH1Q2SKX73C3M@b4e63113c8f2d85f743841abecd8b10a873aa43207306d86c212967c9a8c1900": [
          "admin"
        ]
      }
    }
  }
  ```
  </details>
  </div>
  </div>
  </div>
  <!-- Add Group End -->

  <!-- Get Group -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
    <div class="flex flex-col">

  ### Get info of a Group
  <p class="m-t-0">Group information can be queried on this endpoint.</p>
    </div>
    <div class="flex flex-row gap-12">
      <div class="flex flex-col flex-35">
        <p class="m-y-0 font-bold highlight">Request</p>

  ```sh
  curl -H 'accept: application/json' \
       -H 'Authorization: Bearer \
       -X GET 'http://localhost:8081/api/v3/groups?id=01K60DD03CHA6ZZ3T01NDDPXN0'
  ```
  </div>
  <div class="flex flex-45 scroll">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "group": {
      "id": "01K60DD03CHA6ZZ3T01NDDPXN0",
      "realm_key": [180, 230, 49, ...],
      "name": "my_group",
      "roles": [
        "admin",
        "member"
      ],
      "members": {
        "01K60DC77A5YCZH1Q2SKX73C3M@b4e63113c8f2d85f743841abecd8b10a873aa43207306d86c212967c9a8c1900": [
          "admin"
        ]
      }
    }
  }
  ```
  </details>
  </div>
  </div>
  </div>
  <!-- Get Group End -->

  <!-- Add User to Group -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
    <div class="flex flex-col">

  ### Add User to a Group
  <p class="m-t-0">Users can be added via AddUserRequests by group admins.</p>
    </div>
    <div class="flex flex-row gap-12">
      <div class="flex flex-col flex-35">
        <p class="m-y-0 font-bold highlight">Request</p>

  ```sh
curl -d '
  {
    "group_id": "01K60DD03CHA6ZZ3T01NDDPXN0",
    "user_roles": {
      "member": [
        "01K60DQTQSSW6CT7V6254XR91P@b4e63113c8f2d85f743841abecd8b10a873aa43207306d86c212967c9a8c1900"
      ]
    }' \
     -H 'accept: application/json' \
     -H 'Authorization: Bearer <your-secret-token>' \
     -H 'Content-Type: application/json' \
     -X POST 'http://localhost:8081/api/v3/groups/user'
  ```
  </div>
  <div class="flex flex-45 scroll">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {}
  ```
  </details>
  </div>
  </div>
  </div>
  <!-- Add User to Group End -->
</details>
<!-- Groups Endpoint End -->

<!-- Resources Endpoint -->
<details>
  <summary class="w-60 m-t-24 m-b-12 p-b-8 accordion-border text-2xl font-bold">Resources Endpoint</summary>


</details>
<!-- Resources Endpoint End -->

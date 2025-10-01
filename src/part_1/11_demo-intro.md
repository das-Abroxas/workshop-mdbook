# Demo

<p class="text-xl">This section demonstrates how to interact with the API using practical command-line examples.</p>

<p class="text-xl">Explore the endpoints below to learn how to easily communicate with any Aruna node.</p>

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
       -H 'Authorization: Bearer <your-secret-token>' \
       -X GET 'http://<node-host>:8081/api/v3/info'
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
       -H 'Authorization: Bearer <your-secret-token>' \
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
       -H 'Authorization: Bearer <your-secret-token>' \
       -X 'GET' 'http://<node-host>:8081/api/v3/info/search?query=ecoli'
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
       -H 'Authorization: Bearer <your-secret-token>' \
       -X POST 'http://<node-host>:8081/api/v3/users'       
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

  ```bash
  curl -H 'accept: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X GET 'http://<node-host>:8083/api/v3/users?id={user-identity}'
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
<details>
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

  ```bash
  curl -d '
    {
      "name": "my_group"
    }' \
       -H 'accept: application/json' \
       -H 'Content-Type: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X POST 'http://<node-host>:8081/api/v3/groups'
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

  ```bash
  curl -H 'accept: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X GET 'http://<node-host>:8081/api/v3/groups?id=01K60DD03CHA6ZZ3T01NDDPXN0'
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

  ```bash
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
       -X POST 'http://<node-host>:8081/api/v3/groups/user'
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
<!-- Info Endpoint -->
<details>
  <summary class="w-60 m-t-24 m-b-12 p-b-8 accordion-border text-2xl font-bold">Resources Endpoint</summary>

  <!-- Create Project -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
    <div class="flex flex-col">
  
  ### Create a new metadata project
  <p class="m-t-0">A metadata project is the root ro-crate for a metadata collection. There is no
    need to create nested resources, because multiple datasets cann be added and
    annotated in one single metadata resource. Nesting is still possible to further
    structure your metadata or to scale things up if metadata gets large.</p>
    </div>
    <div class="flex flex-row gap-12">
      <div class="flex flex-col flex-35">
        <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -X 'POST' 'http://<node-host>:8081/api/v3/resources/project' \
       -H 'accept: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -H 'Content-Type: application/json' \
       -d '
       {
        "authors": [
          {
            "first": "string",
            "id": "string",
            "last": "string"
          }
        ],
        "description": "string",
        "group_id": "string",
        "identifiers": [
          "string"
        ],
        "labels": [
          {
            "key": "string",
            "value": "string"
          }
        ],
        "license_id": "string",
        "name": "string",
        "title": "string",
        "visibility": "Public"
      }'
  ```

  </div>
    <div class="flex flex-45">
      <details>
        <summary class="font-bold highlight">Response</summary>
  
  ```json
  {
    "resource": {
      "id": "string",
      "name": "string",
      "title": "string",
      "description": "string",
      "revision": 0,
      "variant": "Project",
      "visibility": "Public",
      "content_len": 123456,
      "count": 0,
      "created_at": "2025-09-29T06:47:25.047Z",
      "last_modified": "2025-09-29T06:47:25.047Z",
      "license_id": "string",
      "locked": false,
      "deleted": false,
      "authors": [
        {
          "id": "string",
          "first": "string",
          "last": "string"
        }
      ],
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
      "identifiers": [
        "string"
      ],
      "labels": [
        {
          "key": "string",
          "value": "string"
        }
      ],
    }
  }
  ```

  </details>
  </div>
  </div>
  </div>
  <!-- Create Resource End -->

  <!-- Create Resource -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
    <div class="flex flex-col">
  
  ### Create a new metadata resource
  <p class="m-t-0">Nested metadata resources can be appended to already existing metadata projects.</p>
    </div>
    <div class="flex flex-row gap-12">
      <div class="flex flex-col flex-35">
        <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -d '
    {
      "authors": [
        {
          "id": "string",
          "first": "string",
          "last": "string"
        }
      ],
      "description": "string",
      "identifiers": [
        "string"
      ],
      "labels": [
        {
          "key": "string",
          "value": "string"
        }
      ],
      "license_id": "string",
      "name": "string",
      "parent_id": "string",
      "title": "string",
      "variant": "Folder",
      "visibility": "Public"
    }' \
       -H 'accept: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X POST 'http://<node-host>:8081/api/v3/resources'
  ```

  </div>
    <div class="flex flex-45">
      <details>
        <summary class="font-bold highlight">Response</summary>
  
  ```json
    {
      "resource": {
        "id": "string",
        "name": "string",
        "title": "string",
        "description": "string",
        "revision": 0,
        "variant": "Project",
        "visibility": "Public",
        "content_len": 123456,
        "count": 0,
        "created_at": "2025-09-29T06:47:25.047Z",
        "last_modified": "2025-09-29T06:47:25.047Z",
        "license_id": "string",
        "locked": false,
        "deleted": false,
        "authors": [
          {
            "id": "string",
            "first": "string",
            "last": "string"
          }
        ],
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
        "identifiers": [
          "string"
        ],
        "labels": [
          {
            "key": "string",
            "value": "string"
          }
        ],
      }
    }
  ```

  </details>
  </div>
  </div>
  </div>
  <!-- Create Resource End -->
  
  <!-- Get Resource -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
  <div class="flex flex-col">
  
  ### Get info of an existing metadata resource
  <p class="m-t-0">Any metadata object can be queried from any node with a simple get request and
    the resource id.</p>
  </div>
  
  <div class="flex flex-row gap-12">
    <div class="flex flex-col flex-35">
    <p class="m-y-0 font-bold highlight">Request</p>
  
  ```bash
  curl -H 'accept: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X GET 'http://<node-host>:8081/api/v3/resources?id=01K6AA6D7G48GNYMFD8G03QPWP'
  ```
  </div>
    <div class="flex flex-45">
      <details>
        <summary class="font-bold highlight">Response</summary>
  
  ```json
    {
      "resource": {
        "id": "string",
        "name": "string",
        "title": "string",
        "description": "string",
        "revision": 0,
        "variant": "Project",
        "visibility": "Public",
        "content_len": 123456,
        "count": 0,
        "created_at": "2025-09-29T06:47:25.047Z",
        "last_modified": "2025-09-29T06:47:25.047Z",
        "license_id": "string",
        "locked": false,
        "deleted": false,
        "authors": [
          {
            "id": "string",
            "first": "string",
            "last": "string"
          }
        ],
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
        "identifiers": [
          "string"
        ],
        "labels": [
          {
            "key": "string",
            "value": "string"
          }
        ],
      }
    }
  ```
  </details>
  </div>
  </div>
  </div>
  <!-- Get Resource End -->
  
  <!-- Get Resource History -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
  <div class="flex flex-col">
  
  ### Get change history of a metadata resource
  <p class="m-t-0">The change history of every action that was called on a specific resource can be
    displayed with a query in the history endpoint.</p>
  </div>
  
  <div class="flex flex-row gap-12">
    <div class="flex flex-col flex-35">
    <p class="m-y-0 font-bold highlight">Request</p>
  
  ```bash
  curl -H 'accept: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X GET 'http://<node-host>:8081/api/v3/resources/history?id=01K6AA6D7G48GNYMFD8G03QPWP'
  ```
  </div>
    <div class="flex flex-45">
      <details>
        <summary class="font-bold highlight">Response</summary>
  
  ```json
  {
    "history": [
      {
        "actor_id": {
          "node_id": "string",
          "realm_key": "string",
          "user_identity": "string"
        },
        "deps": [
          "string"
        ],
        "extra_bytes": [
          1073741824
        ],
        "hash": "string",
        "message": "string",
        "operations": [
          "string"
        ],
        "seq": 10,
        "start_op": 9007199254740991,
        "time": 9007199254740991
      }
    ]
  }
  ```

  </details>
  </div>
  </div>
  </div>
  <!-- Get Resource History End -->
  
  <!-- Update Resource Title -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
  <div class="flex flex-col">
  
  ### Update title of a metadata resource
  <p class="m-t-0">Metadata fields are currently updated with a specfic endpoint for each field.
    This will change over time to allow for more flexible json-based metadata edits</p>
  </div>
  
  <div class="flex flex-row gap-12">
    <div class="flex flex-col flex-35">
    <p class="m-y-0 font-bold highlight">Request</p>
  
  ```bash
  curl -d '
    {
      "id": "01K6AA6D7G48GNYMFD8G03QPWP",
      "title": "Some new title"
    }' \
       -H 'accept: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X POST 'http://<node-host>:8081/api/v3/resources/title'
  ```

  </div>
  <div class="flex flex-45">
    <details>
      <summary class="font-bold highlight">Response</summary>
  
  ```json
  {
    "resource": {
      "id": "01K6AA6D7G48GNYMFD8G03QPWP",
      "name": "string",
      "title": "Some new title",
      "description": "string",
      "revision": 0,
      "variant": "Project",
      "visibility": "Public",
      "content_len": 123456,
      "count": 0,
      "created_at": "2025-09-29T06:47:25.047Z",
      "last_modified": "2025-09-29T06:47:25.047Z",
      "license_id": "string",
      "locked": false,
      "deleted": false,
      "authors": [
        {
          "id": "string",
          "first": "string",
          "last": "string"
        }
      ],
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
      "identifiers": [
        "string"
      ],
      "labels": [
        {
          "key": "string",
          "value": "string"
        }
      ],
    }
  }
  ```

  </details>
  </div>
  </div>
  </div>
  <!-- Update Resource Title End -->
  
  <!-- Create credentials location -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
  <div class="flex flex-col">

  <!-- Create Credentials -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
    <div class="flex flex-col">

  ### Create s3 credentials 
  <p class="m-t-0">S3 Credentials for a user are always group specific. They can be created for any
            node in the registered realm.</p>
    </div>
    <div class="flex flex-row gap-12">
      <div class="flex flex-col flex-35">
        <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -d '
    {
      "group_id": "string"
    }' \
       -H 'accept: application/json' \
       -H 'Content-Type: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X POST 'http://<node-host>:8080/api/v3/users/credentials'
  ```
  </div>
  <div class="flex flex-45 scroll">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "access_key_id": "<your-access-key-id>",
    "secret_access_key": "<your-secret-access-key>""
  }
  ```
  </details>
  </div>
  </div>
  </div>
  <!-- Create Credentials End -->

  <!-- Get Credentials -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
    <div class="flex flex-col">

  ### Get S3 credentials 
  <p class="m-t-0">Your already created credentials can always be displayed with a 
  `GetCredentialsRequest`. Credentials are only valid for each individual node.</p>
    </div>
    <div class="flex flex-row gap-12">
      <div class="flex flex-col flex-35">
        <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -H 'accept: application/json' \
       -H 'Content-Type: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X GET 'http://<node-host>:8080/api/v3/users/credentials'
  ```
  </div>
  <div class="flex flex-45 scroll">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "access_key_id": "<your-access-key-id>",
    "secret_access_key": "<your-secret-access-key>""
  }
  ```
  </details>
  </div>
  </div>
  </div>
  <!-- Get Credentials End -->

  <!-- Delete Credentials -->
  <div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
    <div class="flex flex-col">

  ### Deleting S3 credentials 
  <p class="m-t-0">Credentials can be deleted on nodes with a `DeleteCredentialsRequest`.</p>
    </div>
    <div class="flex flex-row gap-12">
      <div class="flex flex-col flex-35">
        <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -H 'accept: application/json' \
       -H 'Content-Type: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X DELETE 'http://<node-host>:8080/api/v3/users/credentials' \
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
  <!-- Get Credentials End -->

<!-- Get data location -->
<div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
<div class="flex flex-col">

### Get data locations
<p class="m-t-0">Existing data locations can be queried by their respective content-hashes.
  In a flexible p2p system like aruna this is especially useful to automate actions based on
  resource locality.</p>
</div>

<div class="flex flex-row gap-12">
  <div class="flex flex-col flex-35">

  <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -H 'accept: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X GET 'http://<node-host>:8080/api/v3/data/location?hash=ebae78bcd5a3ef259a4da35b3ac39ea29b8e147eb288c69404dd1bfa58280df4'
  ```
  </div>

  <div class="flex flex-45">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "location": [
      {
        "direct_addresses": [
          "0.0.0.0:1230"
        ],
        "node_id": "",
        "relay_url": "null"
      }
    ]
  }
  ```
  </details>
  </div>
</div>
</div>
<!-- Get data location End -->

<!-- Register Data -->
<div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
<div class="flex flex-col">

### Register data from storage backend
<p class="m-t-0">Existing data sources you have access to can be registered via this endpoint. This
    currelntly only works for individual objects, but gets further extended in the
    future.</p>
</div>

<div class="flex flex-row gap-12">
  <div class="flex flex-col flex-35">

  <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  curl -d '
    {
      "backend_path": "/some-path/to/the/data.log",
      "bucket": "my_bucket",
      "create_s3_path": true,
      "group_id": "01K60DD03CHA6ZZ3T01NDDPXN0",
      "key": "<some-s3-key-id>"
    }' \
       -H 'accept: application/json' \
       -H 'Content-Type: application/json' \
       -H 'Authorization: Bearer <your-secret-token>' \
       -X POST http://<node-host>:8080/api/v3/users/credentials'
  ```
  </div>

  <div class="flex flex-45">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "access_key_id": "<some-ulid>>",
    "secret_access_key": "<some-secret-key>"
  }
  ```
  </details>
  </div>
</div>
</div>
<!-- Register Data End -->

</details>
<!-- Resources Endpoint End -->


<!-- S3 Endpoint -->
<details>
  <!--<summary class="w-60 m-t-24 m-b-12 p-b-8 text-2xl font-bold" style="border-bottom: 2px solid var(--aruna-highlight)">Info Endpoint</summary>-->
  <summary class="w-60 m-t-24 m-b-12 p-b-8 accordion-border text-2xl font-bold">S3 Endpoint</summary>
  <p class="text-xl">To interact with the s3 endpoint you need a s3 client. Our recommendation
        for this demo is the official <a href="https://aws.amazon.com/cli/">aws cli</a>. Other
        clients should work, but are not tested and most of them are not feature complete.
  </p>

<!-- Create bucket -->
<div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
<div class="flex flex-col">

  ### Creating s3 buckets
  
  A bucket can be created without any other restriction other than having valid S3 credentials
</div>

<div class="flex flex-row gap-12">
  <div class="flex flex-col flex-35">

  <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  aws --endpoint-url http://<node-s3-endpoint> \
      --profile <aws-credentials-profile> \
      --no-verify-ssl \
      s3 mb s3://<your-bucket-name>
  ```
  </div>

  <div class="flex flex-45">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```
  make_bucket: <your-bucket-name>
  ```
  </details>
  </div>
</div>
</div>
<!-- Create Bucket End -->

<!-- Create data -->
<div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
<div class="flex flex-col">

  ### Data uploads 

  Data uploads (single and multipart) are done with the s3 put convenience function.
</div>

<div class="flex flex-row gap-12">
  <div class="flex flex-col flex-35">

  <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  aws --endpoint-url http://<node-s3-endpoint> \
      --profile <aws-credentials-profile> \
      --no-verify-ssl \
      s3 cp <your-local-object> s3://<your-bucket-name>/<your-remote-name>
  ```
  </div>

  <div class="flex flex-45">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```
  upload: ./<your-local-object> to s3://<your-bucket-name>/<your-remote-name>
  ```
  </details>
  </div>
</div>
</div>
<!-- Create data End -->

<!-- Get data -->
<div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
<div class="flex flex-col">

  ### Data downloads 
  Data can be downloaded the same way data is uploaded.

<div class="flex flex-row gap-12">
  <div class="flex flex-col flex-35">

  <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  aws --endpoint-url http://<node-s3-endpoint> \
      --profile <aws-credentials-profile> \
      --no-verify-ssl \
      s3 cp s3://<your-bucket-name>/<your-remote-name> <your-local-object> 
  ```
  </div>

  <div class="flex flex-45">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```
  download: ./<your-local-object> to s3://<your-bucket-name>/<your-remote-name>
  ```
  </details>
  </div>
</div>
</div>
<!-- Get data End -->


<!-- Create replication rule -->
<div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
<div class="flex flex-col">

  ### Data replication
Data can be replicated to other nodes via the <a href="https://docs.aws.amazon.com/AmazonS3/latest/API/API_PutBucketReplication.html#API_PutBucketReplication_RequestSyntax">put-bucket-replication</a> interface of s3.

</div>

<div class="flex flex-row gap-12">
  <div class="flex flex-col flex-35">

  <p class="m-y-0 font-bold highlight">Request</p>

  ```python
  aws --endpoint-url http://<node-s3-endpoint> \
      --profile <aws-credentials-profile> \
      --no-verify-ssl \
      s3api put-bucket-replication \
      --bucket <your-bucket-name> \
      --replication-configuration '
      {
        "Role": "arn:aws:s3:::",
        "Rules": [
          {
            "ID": <your-replication-rule-name>,
            "Destination": {
              "Bucket": "arn:aws:s3:<target-node-id>:account_id:<target-bucket>"
            },
            "Status": "Enabled"
          }
        ]
      }'
  ```
  </div>

  <div class="flex flex-45">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {}
  ```
  </details>
  </div>
</div>
</div>
<!-- Create Bucket End -->

<!-- Create replication rule -->
<div class="m-y-8 p-8 rounded-8" style="border: 2px dotted var(--aruna-highlight)">
<div class="flex flex-col">

  ### Querying replication rules
Data replication rules can be viewed with this request.

</div>

<div class="flex flex-row gap-12">
  <div class="flex flex-col flex-35">

  <p class="m-y-0 font-bold highlight">Request</p>

  ```bash
  aws --endpoint-url http://<node-s3-endpoint> \
      --profile <aws-credentials-profile> \
      --no-verify-ssl \
      s3api get-bucket-replication \
      --bucket <your-bucket-name>
  ```
  </div>

  <div class="flex flex-45">
    <details>
      <summary class="font-bold highlight">Response</summary>

  ```json
  {
    "ReplicationConfiguration": {
      "Role": <your-user-id>,
      "Rules": [
        {
          "Status": "ENABLED",
          "ExistingObjectReplication": {
            "Status": "false"
          },
          "Destination": {
            "Bucket": <your-bucket-name>
          }
        }
      ]
    }
  }
  ```
  </details>
  </div>
</div>
</div>
<!-- Create Bucket End -->

</details>
<!-- Info Endpoint End -->

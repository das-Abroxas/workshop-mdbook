# Realms

<div class="flex flex-row gap-2 m-t-2 m-b-12">
  <div class="flex flex-col flex-40 text-2xl justify-center" style="padding: 0 15px; border: 2px dashed #00a0cc; border-radius: 4px">

  <ul class="text-2xl" style="">
    <li>A layer of trust between Nodes</li>
    <ul><li>Nodes with same private key form a realm</li></ul>
    <li>Can employ their own policies for data/metadata, etc.</li>
    <li>User Identity is always bound to a Realm</li>
  </ul>

  </div>
  <div class="flex flex-col flex-50" style="padding: 0 15px;">
    <p align="center">
      <img src="../assets/images/realms.drawio.png"/>
    </p>
  </div>
</div>

<details>
  <summary class="w-60 m-t-24 m-b-12 p-b-8 accordion-border text-2xl font-bold">More info</summary>

  <div class="flex flex-col aruna-border rounded-8 p-x-8 text-xl">

  Because realms share the same cryptographic key, nodes participating in realms trust each other.
  This ensures that a set of defined Nodes uses the same rules for authorization, authentication,
  policies and rules for metadata and data replication. By default access relevant information is
  shared with every other node in a realm. Data and metadata can be replicated by default to nodes
  inside a realm, while manual replication is still possibly with other nodes from other realms, but
  without the guarantee to use the same access restrictions. This flexible approach guarantees a
  **resilient** data storage system, where data and metadata can be dynamically transferred.
  Policies can for example, define how access should be managed or how data should be replicated.
  Rules can define which metadata standards need to be enforced or which fields need to be set on
  metadata, so that consistent metadata handling is ensured in a realm. Users that are registered in
  a realm can interact with other realms via the identity provider used by their home-realm,
  supporting interoperability between nodes and realms.

  </div>
</details>

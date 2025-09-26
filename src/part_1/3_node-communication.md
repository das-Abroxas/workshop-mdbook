# Node Communication

<div class="flex flex-row gap-2 m-t-2 m-b-12">
  <div class="flex flex-col flex-50 text-2xl justify-center" style="padding: 0 15px; border: 2px dashed #00a0cc; border-radius: 4px">

  <ul class="text-3xl" style="">
    <li>P2P network</li>
    <li>DHT to make data/metadata available to the network</li>
    <li>CRDTs are used for collaborative metadata editing</li>
    <li>Data and Metadata can be shared and replicated with other Nodes</li>
  </ul>

  </div>
  <div class="flex flex-col flex-50" style="padding: 0 15px;">
    <p align="center">
      <img src="../assets/images/node_comm.drawio.png"/>
    </p>
  </div>
</div>

<details>
  <summary class="w-60 m-t-24 m-b-12 p-b-8 accordion-border text-2xl font-bold">More info</summary>

  <div class="flex flex-col text-xl" style="padding: 0 15px; border: 2px dashed #00a0cc; border-radius: 4px">

  Nodes are connected via a P2P network and are organized into realms that share the same set of
  policies and rules. When data/metadata is registered at a node, it gets distributed via a
  DHT so every other node can associate a metadata/data entry with a node address. This guarantees a
  distributed system, where every resource is **findable** while still being managed and
  **access-controlled** by the original data holder. Nodes inside the same realm trust each other and
  can share resources by default with another (based on realm policies). Collaborative
  editing of metadata is made possible by CRDTs which asynchronously manage edits on metadata in our
  P2P system.

  </div>
</details>

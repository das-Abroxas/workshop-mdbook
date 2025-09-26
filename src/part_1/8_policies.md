# Policies

<div class="flex flex-row gap-2 m-t-2 m-b-12">
  <div class="flex flex-col p-x-6 aruna-border rounded-4 text-2xl justify-center">

  <ul class="">
    <!-- <li>Disclaimer: Unimplemented</li> -->
    <li>Basic build blocks for the different layers of trust</li>
    <li>Define which actions are allowed on which resources</li>
    <li>Can be defined realm wide or node specific</li>
    <li>Are programmatically evaluated</li>
  </ul>

  </div>
  <div class="flex flex-col flex-50 p-x-6">
    <p align="center">
      <img src="../assets/images/policies.drawio.png"/>
    </p>
  </div>
</div>

<details>
  <summary class="w-60 m-t-24 m-b-12 p-b-8 accordion-border text-2xl font-bold">More info</summary>

  <div class="flex flex-col aruna-border rounded-8 p-x-8 text-xl">

  Policies form the basis of autonomy for each resource and node. They define what needs to be done
  or what is permitted on specific resources and can be integrated on a resource, group, node or
  realm level. These form the building block of the different layers of trust inside a p2p network.
  Because different institutions or consortia have different constraints, a defined set of policies
  is defined for each realm. This can include replication policies for data or metadata and policies
  that deny for example specific actions for specific nodes. The resulting flexiblity allows for 
  example differentiation between higher-trust nodes, included in access-constrained compute
  environments that still can participate in a realm and the p2p network. Programmatic definition
  allows for maximum flexibility at the definition level and ensures that even complex scenarios are
  covered.

  </div>
</details>

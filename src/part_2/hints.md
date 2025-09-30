# What should I test?

Here are a few suggestions for what you can try out and experience in the hands-on part of the workshop.

In any case, if you want to interact with or join the workshop cluster, you should join the `OpenWrt` network. Wwe have set it up especially for this workshop and in which the cluster/realm we have provided is also accessible.

---

## Experiment with a local cluster on your laptop

This needs internet connection and `[docker|podman] compose` installed as you will download all needed containers to set up locally on your computer an Aruna cluster with 3 instances.

You'll find the [Docker Compose file here](https://das-abroxas.github.io/workshop-mdbook/assets/compose.yaml). Just download it and run `docker compose -f /path/to/the/compose.yaml up` to explore the Aruna ecosystem via the Swagger UIs of the spawned nodes.

This compose file spawns the following containers:
* A Keycloak which provides authentication 
* A Minio which is used as ephemeral backend storage
* 3 Aruna instances whose API endpoints are available under the following links after started:

  * **Metadata**: [http://localhost:8080](http://localhost:8080) / **Data:** [http://localhost:8081](http://localhost:8081) / **S3:** [http://localhost:1337](http://localhost:1337)

  * **Metadata**: [http://localhost:8082](http://localhost:8082) / **Data:** [http://localhost:8083](http://localhost:8083) / **S3:** [http://localhost:1338](http://localhost:1338)

  * **Metadata**: [http://localhost:8084](http://localhost:8084) / **Data:** [http://localhost:8085](http://localhost:8085) / **S3:** [http://localhost:1339](http://localhost:1339)

For initial login to get a valid token you have to visit the website [http://localhost:3000](http://localhost:3000) and use one of the following users `arunaadmin:arunadmin` or `regular:regular`.

After login you immediately receive an OIDC token. This can be used to authorize yourself in one of the Swagger UIs to start your journey.

The first step should be to create a Group. Since you created the group, you automatically receive admin rights for it. This means you are free to add additional users to this group, upload data, etc. as you wish. Feel free to explore the API documentation and test other requests.

**Hint:** S3 credentials have to be created for each node individually!

---

## Join the workshop Realm as User and distribute data

After joining the workshop network `OpenWrt` you can register yourself at [http://192.168.1.210:3000](http://192.168.1.210:3000) with any user data you like.

After registering, you will immediately receive your OIDC token. You can use this to authorize yourself in the Swagger UI of a node in order to register your user in the realm as a first step.

In the API response to the user's registration in Aruna, you will receive an Aruna token that can be used for authorization in the same way, but is valid for a longer period of time.

From here on you can create your own Group or ask others that they will add your user to their already existing Group to collaborate together.

Feel free to explore the API documentation and test other requests.

**Hint:** S3 credentials have to be created for each node individually!

---

## Join the workshop Realm as Node and be a vital part of the federated network

This is already advanced behavior, which requires a deeper understanding of how federated systems and Aruna v3 in particular work. Talk to the workshop leaders to get more information on the easiest way to deploy a node on your device and become an infrastructural part of the workshop realm.

If you feel confident, you can of course take a closer look at the [Docker Compose file](https://das-abroxas.github.io/workshop-mdbook/assets/compose.yaml) mentioned above and try it out for yourself.

---

## Join forces with some allies and create your own Realm

- Some commands with explanation

---

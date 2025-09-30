# What should I test?

Here are a few suggestions for what you can try out and experience in the hands-on part of the workshop.

In any case, if you want to interact with or join the workshop cluster, you should join the `OpenWrt` network. Wwe have set it up especially for this workshop and in which the cluster/realm we have provided is also accessible.

---

## Experiment with a local cluster on your laptop

This needs internet connection and `[docker|podman] compose` installed as you will download all needed containers to set up locally on your computer an Aruna cluster with 3 instances.

You'll find the Docker Compose file here. Just download it and run `docker compose -f /path/to/the/compose.yaml up` to explore the Aruna ecosystem via spawned Swagger UIs.

This compose file spawns the following containers:
* A Keycloak which provides authentication 
* A Minio which is used as ephemeral backend storage
* 3 Aruna instances whose API endpoints are available under the following links after started:
  * **Metadata**: http://localhost:8080 / **Data:** http://localhost:8081 / **S3:** http://localhost:1337
  * **Metadata**: http://localhost:8082 / **Data:** http://localhost:8083 / **S3:** http://localhost:1338
  * **Metadata**: http://localhost:8084 / **Data:** http://localhost:8085 / **S3:** http://localhost:1339

For initial login to get a valid token you have to visit the website `http://localhost:3000` and use the following user `regular:regular`.

---

## Join the workshop Realm as User and distribute data

- Some commands with explanation

---

## Join the workshop Realm as Node and be a vital part of the federated network

- Some commands with explanation

---

## Join forces with some allies and create your own Realm

- Some commands with explanation

---
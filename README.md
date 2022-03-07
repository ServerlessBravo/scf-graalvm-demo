## Demo of GraalVM for SCF


## Build

Notes: **should run on linux based system considering the compatibility**

```bash
gradle nativeCompile
```

Output:

```
build/native/
|-- generated
|   `-- generateResourcesConfigFile
|       `-- resource-config.json
`-- nativeCompile
    |-- demo
    `-- demo.build_artifacts.txt
```

## Zipped Artifacts

```bash
gradle buildZip
```

Artifacts:
```
build/distributions/
`-- demo-0.0.1-SNAPSHOT.zip
```

## Deploy

### Create Function

![Create Function](https://user-images.githubusercontent.com/251222/157045841-c29289bd-b4db-437e-bb0b-64cea82462be.png)

### Configure `scf_bootstrap`

![Configure](https://user-images.githubusercontent.com/251222/157045824-9268f861-00e2-4c25-b073-764d4bfda938.png)

### Deploy and Check APIGateway Address

![APIGW](https://user-images.githubusercontent.com/251222/157045843-46d344e1-0db8-41a7-b3ce-185b15afb986.png)

### Trigger Function

```bash
curl https://service-2vj0sheq-1253970226.gz.apigw.tencentcs.com/release/greeting
```

Sample Output:

```
{"id":2,"content":"Hello, World!"}%
```

### Check the log


![SCF Logs](https://user-images.githubusercontent.com/251222/157045850-a2b6915c-092c-4b4a-a1cb-f4af8f7dd108.png)
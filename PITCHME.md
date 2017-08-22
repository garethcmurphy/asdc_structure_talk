
#### ASDC Software, Structure, Impovements, Known Bugs
- Gareth Murphy
---

### ASDC pipeline is written in Python
- Datatypes are implemented as Django models

---
## Using the docker containers

To start the docker project you must first clone the repository

```
git clone git@gitlab.spacecenter.dk:asdc/asdc.git
```

```
docker-compose up --build
```

To log into individual container use the command 
```
docker exec -it <CONTAINER_NAME> /bin/bash 
```


where ```<CONTAINER_NAME>``` is one of:


asdc_level0_1 , asdc_level1_1 , asdc_level3_1 , asdc_web_1 , asdc_db_1 , asdc_filewriter_1
---
E.g. to run migrations use:

```
docker exec -it asdc_web_1 /bin/bash 
```

Then run

```
./manage.py makemigrations
./manage.py migrate
```

To access level0 scripts and functions
```
docker exec -it asdc_level0_1 /bin/bash 
 ```

Similarly for level1 
```
docker exec -it asdc_level1_1  /bin/bash 
```
---
1. Start a shell session in level0 container
```
docker exec -it dtuspaceasdcbuild_level0_1 /bin/bash
```

2. Run the level0 script
```
./RunLevel0
```
(To restore Pacts data run ./RunLevel0Pacts)

3. Start a shell session in level1 container
```
docker exec -it dtuspaceasdcbuild_level1_1 /bin/bash
```

4. Run the level1 script
```
./RunLevel1
```

---
### Structure


---
### Improvements

---
###
---
THANKS

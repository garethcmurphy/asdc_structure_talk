
## ASDC Software, Structure, Improvements, Known Bugs
Gareth Murphy


---

### ASDC pipeline 
- The pipeline is written in Python 3
- MDAP (MXGS Data Analysis Program) written in C++ (Paul Connell)
- Telemetry types are implemented as Django models

---
### Illustrative example of telemetry

```
class MXGSTGFObservation(ASIMBase):
    observation_id = models.IntegerField('Observation ID')
    utc_year = models.PositiveSmallIntegerField('UTC year')
    utc_seconds = models.PositiveIntegerField('UTC seconds')
    utc_msec = models.PositiveSmallIntegerField('UTC msec')
    tcp_count_dhpu = models.PositiveIntegerField()
    tcp_count_dpu = models.PositiveIntegerField()
    dpu_count = models.PositiveIntegerField()
    dpu_count_prereset = models.IntegerField()
    dau_bgo_1_int_tmon_chan1 = models.PositiveSmallIntegerField()
    dau_bgo_1_int_tmon_chan2 = models.PositiveSmallIntegerField()
    dau_bgo_1_int_tmon_chan3 = models.PositiveSmallIntegerField()
    dau_bgo_1_int_tmon_chan4 = models.PositiveSmallIntegerField()
    dau_bgo_2_int_tmon_chan1 = models.PositiveSmallIntegerField()
    dau_bgo_2_int_tmon_chan2 = models.PositiveSmallIntegerField()
    dau_bgo_2_int_tmon_chan3 = models.PositiveSmallIntegerField()
    dau_bgo_2_int_tmon_chan4 = models.PositiveSmallIntegerField()
    dau_bgo_3_int_tmon_chan1 = models.PositiveSmallIntegerField()
```
---
### Structure

- Divided into level0,1,2
- subdivided into SRD packages
- Each software requirement has its own directory
---
### Docker 
- all software configuration files stored as Dockerfiles

```
FROM ubuntu:16.04
MAINTAINER Gareth Murphy <gmurphy@space.dtu.dk>
RUN mkdir /code
WORKDIR /code
RUN apt-get update && apt-get install -y \
        cron \
        curl \
        gfortran \
        libncurses5-dev \
        libpq-dev \
        python3-astropy \
        python3-matplotlib \
        python3-numpy \
        python3-pip \
        python3-scipy \
        python3-ephem
COPY requirements.txt /code/
```

---
## Using the docker containers

To start the docker project you must first clone the repository

```
git clone https://gitlab.spacecenter.dk/asdc/asdc.git
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
### Improvements

- 
---
### Known Bugs

- Need to know every data structure

---
THANKS

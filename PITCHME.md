![LOGO](http://asdc.space.dtu.dk/static/asim/assets/ASDClogoTransparent.png)

#### Get the word out
<br>
<span style="color:gray">Markdown Presentations For Everyone</span>
<br>
<span style="color:gray">on</span>
<br>
<span style="color:gray">GitHub, GitLab, Bitbucket, Gitea, Gogs, and GitBucket</span>

---

### ASDC pipeline is written in Python
- Datatypes are implemented as Django models

---
## Quickstart guide to using the docker containers

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


where <CONTAINER_NAME> is one of:


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
### No more <span style="color: #666666">Keynote.</span>
### No more <span style="color: #666666">Powerpoint.</span>
<br>
### Just <span style="color: #e49436">Markdown</span>. Then <span style="color: #e49436">Git-Commit</span>.

---

<span style="color: #e49436">STEP 1. PITCHME.md</span>

![MARKDOWN](https://d1z75bzl1vljy2.cloudfront.net/hello-world/markdown.png)

Create GitPitch slideshow content using GitHub flavored Markdown in your favorite editor.

---

<span style="color: #e49436">KNOWN BUGS</span>

![TERMINAL](https://d1z75bzl1vljy2.cloudfront.net/hello-world/terminal.png)

Git-commit on any branch and push your PITCHME.md to GitHub, GitLab, Bitbucket, Gitea, Gogs, or GitBucket.

---

<span style="color: #e49436">STEP 3. GET THE WORD OUT!</span>

<br>

<span style="font-size: 1.3em;"><span style="color:white">htt</span><span style="color:white">ps://git</span><span style="color: #e49436">pitch</span><span style="color: white">.com/<span style="color: #e49436">user</span>/<span style="color: #e49436">repo</span>/<span style="color: #e49436">branch</span></span>

<br>

Instantly use your GitPitch slideshow URL to promote, pitch or present absolutely anything.

---

<span style="color: #e49436">GIT</span>PITCH DESIGNED FOR SHARING

![SOCIAL](https://d1z75bzl1vljy2.cloudfront.net/hello-world/gp-social.jpg)

- View any slideshow at its public URL
- Promote any slideshow using a GitHub badge
- Embed any slideshow within a blog or website
- Share any slideshow on Twitter, LinkedIn, etc
- Print any slideshow as a PDF document
- Download and present any slideshow offline

---

<span style="color: #e49436">GIT</span>PITCH FEATURE RICH SLIDESHOWS

- GitHub Flavored Markdown +
- Code Presenting for Blocks, Files, and GISTs
- Image and Video Slides
- Custom Logos and Backgrounds
- Multiple Themes And More
- <span style="color: #e49436">Plus...</span>
- Your Slideshow Is Part Of Your Project
- Under Git Version Control Within Your Git Repo


---

### Go for it.
### Just add <span style="color: #e49436; text-transform: none">PITCHME.md</span> ;)

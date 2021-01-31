#### How this repo works

This repo is a collection of my nginx configs across my sites. Originally I base64 encoded a zip file of the the nginx config directory and when building the docker file decoded it. This helped keep my directories clean as it was one less thing to worry about when building. The problem with this is it became cumbersome to make any changes to the configs, which is why I created this repo

---

#### How it's structured.

The structure of this repo is pretty simple. Each site I manage will have it's own branch. My dockerfile then pulls from the branch so it's unique for each. 

For example if I'm building the site for `anthony.bible`, my line in the docker file would like:
    RUN git clone -b anthony.bible https://github.com/Anthony-Bible/Nginx-config.git  /etc/nginx

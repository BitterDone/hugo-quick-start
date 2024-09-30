This is a basic Hugo app I'm having difficulty building into a Docker image.

I've created an empty repository in my Github and cloned it to my development machine:
git clone git@github.com:BitterDone/hugo-quick-start.git

I then followed the steps from this quickstart guide:
https://gohugo.io/getting-started/quick-start/

hugo new site quickstart
cd quickstart
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server

I'm able to see the basic, empty Ananke site at localhost:1313.
It has "My New Hugo Site" in the top left corner,
a centered h1 of "My New Hugo Site",
and "© My New Hugo Site 2024" as a footer in the bottom left

I then tried to build it into a Dockerfile with this blog post
https://medium.com/@lorique/howto-multi-stage-docker-builds-with-hugo-78a53565d567

but it fails on the "RUN hugo" step to build the site.

I've copied and slightly formatted the error logs into docker-build-errors.txt for reference

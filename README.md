# SelfHosted Overleaf

Late-night docker compose configuration to self-host [overleaf](https://github.com/overleaf/overleaf). They don't seem to be interested in keep their open-source documentation up-to-date, so some fustration was required to get things to work.

## Running 
```shell
docker compose up 
```

If it all goes well after a few **minutes** you'll be able to create the admin account at `http://<server_ip>:9153/launchpad`.

## What was the problem

Special configuration is required to access mongodb in the way the overleaf service wants to, the easiest way to solve this is by using the mongodb image from bitnami.

[This stackoverflow answer](https://stackoverflow.com/a/72916178) is my source, read the rest of the thread for context.

## Missing CTAN Packages

If you try to do anything useful, you'll find out that the texlive installation is very bare-bones so you'll need to install many packages. The list of those packages is available in `packages.txt`, although its not complete in relation to standard installation of texlive from package managers.

# caddy-forge

The goal of this repository is to guide you through setting up [Caddy]() in [Laravel Forge]() in order to route secure domains to your Docker containers.

Caddy is a tremendous webserver that provides SSL certificates by default with a super simple setup that allows you to run static files, server-side languages and even Docker containers on Laravel's worker server implementation.

Here are the steps to take.

1. Set up a worker server on your cloud service of choice.

2. Once you have an IP address issued, point your domain of choice to your new server and ensure it's propagated before you proceed.

> It's crucial that your domain is propagated throughout the DNS system, otherwise Caddy won't be able to obtain certificates for your domains.

3. Next create a new site on the new server in the Forge UI. For our example files here we'll use `example.com` throughout. Obviously you'll need to change this to your domain name wherever it occurs.

4. Creating example.com in the UI will create a directory on your server at:

```bash
/home/forge/example.com
```

5. ssh into your server and navigate to the public directory of your site:

```bash
$ cd example.com/public

# paste and save the index.html file from the repo in this dir.
$ vi index.html
# (paste the file) then type :wq! to save and exit vi
```

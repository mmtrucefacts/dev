# Simple Netlify Proxy 

This is a simple repo.

It's purpose it to create a proxy to a site you own.

## How does it work?

1.  You have a domain point to Netlify
2.  Netlify has a "redirect" rule that doesn't redirect instead proxies
3.  That's it

## What do I have to do?

Depends.  Do you use Netlify DNS? 

You're here because you want to know how.  

## Here's what you'll need.

1.  **Access to your DNS** for the domain.  Either to move to Netlify DNS, or to create appropriate records.
2.  A **Netlify account**.
3.  A **Git repository pointing to the proper domain [like this one](https://github.com/jacebenson/dev)**.

You can read the repo's readme, or follow along here.  Also there are at least two other ways to do this.  One is using [ServiceNow's custom URL feature](https://docs.servicenow.com/bundle/paris-platform-administration/page/integrate/authentication/concept/custom-url.html).  The other is some magic on Cloudflare.

## I use Netlify DNS

1. Copy/Fork/Clone this repo.  
2. Update the `netlify.toml` file to the site you want.
3. On Netlify, add this repository as a site.
4. Update the site's domain under "Custom domains" to the domain you want.

(You'll need your DNS set up to Netlify, here's the [docs on that](https://docs.netlify.com/domains-https/netlify-dns/).)

## I do not use Netlify DNS

1. Copy/Fork/Clone this repo.  
2. Update the `netlify.toml` file to the site you want.
3. On Netlify, add this repository as a site.
4. Update the site's domain under "Domain mangement=>Custom domains" to the domain you want.
5. If domain is a subdomain
   1. [On your DNS, add a CNAME record to the site name given in step 3.](https://docs.netlify.com/domains-https/custom-domains/configure-external-dns/)
6. [If the domain is a apex domain](https://docs.netlify.com/domains-https/custom-domains/configure-external-dns/#configure-an-apex-domain)
   1. If your DNS provider supports CNAME flattening, ANAME, or ALIAS records, set that appropriate type like you would a CNAME record to the site url.
   2. If your DNS provider doesn't support those special types of records
      1. Add an `A record` leave host field empty or enter `@`
      2. Point the record to Netlify's load balancer IP address `104.198.14.52`
      3. Save your settings
# Simple Netlify Proxy 

This is a simple repo.

It's purpose it to create a proxy to a site you own.

## How does it work?

1.  You have a domain point to Netlify
2.  Netlify has a "redirect" rule that doesn't redirect instead proxies
3.  That's it

## What do I have to do?

Depends.  Do you use Netlify DNS? 

## I use Netlify DNS

1. Copy/Fork/Clone this repo.  
2. Update the `netlify.toml` file to the site you want.
3. In netlify, add this repository as a site.
4. Update the site's domain under "Custom domains" to the domain you want.

(You'll need your DNS set up to Netlify, here's the [docs on that](https://docs.netlify.com/domains-https/netlify-dns/).)

## I do not use Netlify DNS

1. Copy/Fork/Clone this repo.  
2. Update the `netlify.toml` file to the site you want.
3. In netlify, add this repository as a site.
4. Update the site's domain under "Domain mangement=>Custom domains" to the domain you want.
5. On your DNS, add a CNAME record to the site name given in step 3.
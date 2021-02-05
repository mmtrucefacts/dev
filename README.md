# Simple Vercel Proxy 

This is a simple repo.

It's purpose it to create a proxy to a site you own.

## How does it work?

1.  You have a domain point to Vercel
2.  Vecel has a "redirect/rewrite" rule that doesn't redirect instead proxies
3.  That's it

## What do I have to do?

1.  **Access to your DNS** for the domain to create appropriate records.
2.  A **Vercel account**.
3.  A **Git repository pointing to the proper domain [like this one](https://github.com/jacebenson/dev)**.

You can read the repo's readme, or follow along here.  Also there are at least two other ways to do this.  One is using [ServiceNow's custom URL feature](https://docs.servicenow.com/bundle/paris-platform-administration/page/integrate/authentication/concept/custom-url.html).  The other is some magic on Cloudflare.

## Ok, I'm ready!

1. [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/git/external?repository-url=https%3A%2F%2Fgithub.com%2Fjacebenson%2Fdev)
2. Goto your git source where that button created the repo.
3. Update the `./_includes/layout/redirect.njk` file to the site you want.
4. Vercel should trigger a build and update index.html and 404.html to redirect to your site.
5. Now you need to set up the domain.  To do that goto "Domains", 
6. It'll ask what project you want to use, pick the one you made from #1.
7. It will show you, that your DNS is wrong.  Go forth and set the dns as depicted.
8. Comeback to Vercel's domain page and "Refresh" your domain entry.  You may need to wait for your DNS to propegate.
9. That's it.
# Writing an Uploader

Devy is based around "deploying" blog posts when user pushes markdown to a GitHub repository. Therefore, a big part of the critical functionality of Devy is a Git-based post uploader.

At a high-level, the uploader needs to do just a few things:

1. Clone the repository
2. Check what has changed since the last upload of this repository
3. Update all posts in the repository accordingly
4. Clean up after itself

I wrote the uploader for Devy about 3 times. Once each in TypeScript, Go, then finally Rust.

## The Next.JS Uploader

I created the first implementation when the site was still based on Next.js. It ran as a serverless function in Vercel. It worked well enough, but I decided to move away from it for two reasons.

First, I didn't have any guarantees that the Git binary I relied on would be present in the serverless runner. It was when I wrote the uploader, but there was no promise that it always would be. Second, I worried that uploading would take too long to work in a request/response fashion. I wanted to be able to kick off an upload in response to a webhook push from GitHub, but also schedule that upload "job" so that it wasn't blocking the response.

In retrospect, only the first concern had real merit. I still think if Devy ever takes off and were reliant on a Git binary that disappeared one day, it would be a real pain.

## The Go Uploader

## The Rust Uploader

# Writing an Uploader

Devy is based around "deploying" blog posts when user pushes markdown to a GitHub repository. Therefore, a big part of the critical functionality of Devy is a Git-based post uploader.

At a high-level, the uploader needs to do just a few things:

1. Clone the repository
2. Check what has changed since the last upload of this repository
3. Update all posts in the repository accordingly
4. Clean up after itself

A Little more!+

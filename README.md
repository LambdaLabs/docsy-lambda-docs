# Lambda docs

Welcome to the
[Lambda docs GitHub repository](https://github.com/LambdaLabs/lambda-docs),
the repository from which the [Lambda docs site](https://docs.lambdalabs.com/)
is built.

## Building

The Lambda docs site is built using the [Hugo](https://gohugo.io/) static site
generator and the [Docsy](https://github.com/google/docsy) Hugo theme. The
docs site is deployed using [Cloudflare Pages](https://pages.cloudflare.com/).

If you're making changes to the docs site and plan on creating a pull request,
you should first preview your changes by following the instructions, below.
### First-time setup

Begin hacking on the Lambda docs site by first
[forking the docs site repo](https://github.com/LambdaLabs/lambda-docs/fork).
Then,
[clone your forked repo](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories)
to your computer.

### Previewing your changes

The recommended way to preview your changes is to use
[Docker Compose](https://docs.docker.com/compose/).

While in the directory for your clone of the docs site repository, run:

```bash
docker-compose up --build
```

Then, in your browser, navigate to http://localhost:1313. You should see a
local build of the docs site with your changes.

## Submitting your changes

[Create a pull request](https://github.com/LambdaLabs/lambda-docs/pulls) to
submit your changes for consideration.

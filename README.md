# Lambda docs

Welcome to the
[Lambda docs GitHub repository](https://github.com/LambdaLabs/lambda-docs),
the repository from which the [Lambda docs site](https://docs.lambdalabs.com/)
is built.

## Contributing

All contributions to the docs are appreciated, no matter how small!

If you encounter a buggy or unclear instruction, but don't know how or don't
have the time to fix it, you can create a ticket by clicking **Create a
documentation issue** at the right-hand side of the page.

You can make a quick fix to a page by clicking **Edit this page** at the
right-hand side of the page.

You can create a new, simple page by clicking **Create child page** at the
right-hand side of the page that you want to create a new page under.

For complex fixes and complex new pages, you'll want to follow the
instructions, below, to:

1. Clone the repository and make your changes.
2. Preview your changes locally.
3. Create a pull request for review.

## Cloning the repository and making changes

Begin hacking on the Lambda docs site by first
[forking the docs site repo](https://github.com/LambdaLabs/lambda-docs/fork).
Then,
[clone your forked repo](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories)
to your computer.

Start making your changes!

## Building

The Lambda docs site is built using the [Hugo](https://gohugo.io/) static site
generator and the [Docsy](https://github.com/google/docsy) Hugo theme. The
docs site is deployed using [Cloudflare Pages](https://pages.cloudflare.com/).

If you're making changes to the docs site and plan on creating a pull request,
you should first preview your changes by following the instructions, below.

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

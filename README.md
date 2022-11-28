# Lambda docs

Welcome to the
[Lambda docs GitHub repository](https://github.com/LambdaLabs/lambda-docs),
the repository from which the [Lambda docs site](https://docs.lambdalabs.com/)
is built.

The Lambda docs site is built using the [Hugo](https://gohugo.io/) static site
generator and the [Docsy](https://github.com/google/docsy) Hugo theme. The
docs site is deployed using [Cloudflare Pages](https://pages.cloudflare.com/).

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

## Previewing your changes locally

You should preview your changes locally to make sure they're building as
expected. The recommended way to preview your changes is to use
[Docker Compose](https://docs.docker.com/compose/).

Depending on how you installed docker compose, there are two ways to run it.
If you installed it. If you installed it [manually](https://docs.docker.com/compose/install/linux/#install-the-plugin-manually),
then run the following while in the directory for your clone of the docs site
repository:

```bash
docker-compose up --build
```

If you installed docker compose [using docker's repository](https://docs.docker.com/compose/install/linux/#install-using-the-repository), then run the following
while in the directory for your clone of the docs site repository:

```bash
docker compose up --build
```

Then, in your browser, navigate to http://localhost:1313. You should see a
local build of the docs site with your changes. The site will automatically
rebuild each time changes are made.

## Creating a pull request

[Create a pull request](https://github.com/LambdaLabs/lambda-docs/pulls) to
submit your changes for review.

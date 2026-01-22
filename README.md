<div align="center">
  <a href="https://mockoon.com" alt="mockoon logo">
    <img width="200" height="200" src="https://mockoon.com/images/logo-square-app.png">
  </a>
  <br>
  <a href="https://mockoon.com/"><img src="https://img.shields.io/badge/Website-Go-green.svg?style=flat-square&colorB=1997c6"/></a>
  <a href="https://mockoon.com/newsletter/"><img src="https://img.shields.io/badge/Newsletter-Subscribe-green.svg?style=flat-square"/></a>
  <br>
  <br>
  <h1>@Mockoon/cli GitHub Action</h1>
</div>

Mockoon is the easiest and quickest way to design and run mock APIs. No remote deployment, no account required, free and open-source.

It combines a [desktop application](https://mockoon.com/download/) to design and run mock servers locally, and a [CLI](https://mockoon.com/cli/) to self-host your fake APIs. A [cloud](#subscribe-to-mockoon-cloud) is also available to collaborate with your team, keep your data in sync, and deploy your mock APIs.

API mocking helps you speed up development and third-party API integration by reducing dependency on external services and their limitations: rate limits, costs, availability, etc.
It also allows you to test your applications in a controlled environment with predictable responses, status codes, and latencies, and easily simulate edge cases and error scenarios.
Finally, you can onboard new team members faster by providing them with a consistent and reliable environment to test and develop their applications.

➡️ [Download](https://mockoon.com/download/)

<div align="center">
  <img width="50%" src="https://mockoon.com/images/hero-repo.png">
</div>

## GitHub Action Usage

Mockoon CLI, being a JavaScript application, can run on any environment where Node.js is installed, including continuous integration systems like GitHub Actions.

This GitHub Action allows you to run Mockoon CLI in your workflows.

Several parameters are available to customize the behavior of the action:

- The `version` of the CLI, default to `latest`.
- The `data-file`, pointing to one or more [Mockoon data file](https://mockoon.com/docs/latest/mockoon-data-files/data-files-location/) stored in the repository (or URLs), space separated: e.g., `file1.json file2.json`.
- One or more `port` on which the mock server(s) will run, default to `3000`: e.g., `3000 4000`.
- Additional `extra-args` to pass to Mockoon CLI: e.g., `--faker-locale en_GB --disable-routes users --env-vars-prefix MY_PREFIX_`.

```yaml
name: Mockoon CLI demo

on:
  push:
    branches:
      - main

jobs:
  mockoon-cli-demo:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
      - name: Run Mockoon CLI
        uses: mockoon/cli-action@v3
        with:
          # Mockoon CLI version, default to 'latest'
          version: "latest"
          # Mockoon local data file or URL
          data-file: "./mockoon-data.json"
          # port, default to 3000
          port: 3000
          # extra arguments to pass to Mockoon CLI
          extra-args: "--faker-locale en_GB"
      - name: Make test call
        run: curl -X GET http://localhost:3000/endpoint
```

## Mockoon version compatibility

This action is compatible with the following Mockoon CLI versions:

| Mockoon CLI version | Action version |
| ------------------- | -------------- |
| <6.0.0              | v1             |
| >=6.0.0             | >=v2           |

## CLI's documentation

Mockoon CLI is available as an [NPM package](https://www.npmjs.com/package/@mockoon/cli). Please check our [dedicated documentation](https://github.com/mockoon/mockoon/blob/main/packages/cli/README.md) to learn how to install and use it.

## Subscribe to Mockoon Cloud

With advanced features for solo developers and teams, Mockoon Cloud supercharges your API development:

- ☁️ [cloud deployments](https://mockoon.com/docs/latest/mockoon-cloud/api-mock-cloud-deployments/)
- 🔄️ [data synchronization and real-time collaboration](https://mockoon.com/docs/latest/mockoon-cloud/data-synchronization-team-collaboration/)
- 🤖 [AI powered API mocking](https://mockoon.com/ai-powered-api-mocking/)
- 📃 Access to dozens of [ready-to-use JSON templates](https://mockoon.com/templates/).
- 💬 Priority support and training.

Upgrade today and take your API development to the next level.

<div align="center" style="margin-top:20px;margin-bottom:20px;">
<a href="https://mockoon.com/cloud/"><img src="https://mockoon.com/images/cloud-btn.png?" width="250" alt="cloud button" /></a>
</div>

## Mockoon's documentation

You will find Mockoon's [documentation](https://mockoon.com/docs/latest/about/) on the official website. It covers Mockoon's most complex features. Feel free to contribute or ask for new topics to be covered.

## Changelogs

You will find Mockoon applications [changelogs](https://mockoon.com/releases/) on the official website.

## Support/feedback

You can discuss all things related to Mockoon and ask for help on the [official community](https://github.com/mockoon/mockoon/discussions). It's also a good place to discuss bugs and feature requests before opening an issue on this repository.

## Contributing

If you are interested in contributing to Mockoon, please take a look at the [contributing guidelines](https://github.com/mockoon/mockoon/blob/main/CONTRIBUTING.md).

Please also take a look at our [Code of Conduct](https://github.com/mockoon/.github/blob/main/CODE_OF_CONDUCT.md).

## Roadmap

If you want to know what will be coming in the next release you can check the global [Roadmap](https://mockoon.com/public-roadmap/) or [subscribe to our newsletter](https://mockoon.com/newsletter/).

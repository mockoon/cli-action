<div align="center">
  <a href="https://mockoon.com" alt="mockoon logo">
    <img width="200" height="200" src="https://mockoon.com/images/logo-square-github-action.png">
  </a>
  <br>
  <a href="https://mockoon.com/download/"><img src="https://img.shields.io/badge/Download%20app-Go-green.svg?style=flat-square&colorB=1997c6"/></a>
  <a href="https://mockoon.com/"><img src="https://img.shields.io/badge/Website-Go-green.svg?style=flat-square&colorB=1997c6"/></a>
  <a href="http://eepurl.com/dskB2X"><img src="https://img.shields.io/badge/Newsletter-Subscribe-green.svg?style=flat-square"/></a>
  <a href="https://twitter.com/GetMockoon"><img src="https://img.shields.io/badge/Twitter_@GetMockoon-follow-blue.svg?style=flat-square&colorB=1da1f2"/></a>
  <a href="https://discord.gg/MutRpsY5gE"><img src="https://img.shields.io/badge/Discord-go-blue.svg?style=flat-square&colorA=6c84d9&colorB=1da1f2"/></a>
  <br>
  <a href="https://www.npmjs.com/package/@mockoon/cli"><img src="https://img.shields.io/npm/v/@mockoon/cli.svg?style=flat-square&colorB=cb3837&label=CLI (npm)"/></a>
  <br>
  <br>
  <h1>@Mockoon/cli GitHub Action</h1>
</div>

Welcome to Mockoon official CLI's GitHub Action. Mockoon CLI is a lightweight and fast NPM package to deploy your mock APIs anywhere.

To learn more about Mockoon and Mockoon CLI, please visit the [official website](https://mockoon.com/).

![Mockoon CLI screenshot](https://mockoon.com/images/hero-repo.png)

## GitHub Action Usage

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
      - uses: actions/checkout@v3
      - name: Run Mockoon CLI
        uses: mockoon/cli-action@v1
        with:
          # Mockoon CLI version, default to 'latest'
          version: "latest"
          # Mockoon local data file or URL
          data-file: "./mockoon-data.json"
          # port, default to 3000
          port: 3000
      - name: Make test call
        run: curl -X GET http://localhost:3000/endpoint
```

## Changelogs

You will find Mockoon applications [changelogs](https://mockoon.com/releases/) on the official website.

## Mockoon's documentation

You will find Mockoon's [documentation](https://mockoon.com/docs/latest) on the official website. It covers the most complex features.

## Sponsors

Mockoon is an open-source project built by volunteer maintainers. If you like our application, please consider sponsoring us and join all the [Sponsors and Backers](https://github.com/mockoon/mockoon/blob/main/backers.md) who helped this project over time!

<div align="center">
<a href="https://github.com/sponsors/mockoon"><img src="https://mockoon.com/images/sponsor-btn.png" width="250" alt="sponsor button" /></a>
</div>

## Subscribe to Mockoon Pro

With advanced features for solo developers and teams, Mockoon Pro supercharges your API development:

- 🤖 [AI powered API mocking](https://mockoon.com/ai-powered-api-mocking/)
- 📃 Access to dozens of [ready to use JSON templates](https://mockoon.com/templates/).
- 💬 Priority support and training.

Upgrade today and take your API development to the next level.

<div align="center" style="margin-top:20px;margin-bottom:20px;">
<a href="https://mockoon.com/pro/"><img src="https://mockoon.com/images/pro-btn.png?" width="250" alt="pro button" /></a>
</div>

## Support/feedback

You can discuss all things related to Mockoon's CLI, and ask for help, on the [official community](https://github.com/mockoon/mockoon/discussions). It's also a good place to discuss bugs and feature requests before opening an issue on this repository. For more chat-like discussions, you can also join our [Discord server](https://discord.gg/MutRpsY5gE).

## Contributing

If you are interested in contributing to Mockoon, please take a look at the [contributing guidelines](https://github.com/mockoon/mockoon/blob/main/CONTRIBUTING.md).

Please also take a look at our [Code of Conduct](https://github.com/mockoon/mockoon/blob/main/CODE_OF_CONDUCT.md).

## Roadmap

If you want to know what will be coming in the next release you can check the global [Roadmap](https://mockoon.com/public-roadmap/).

New releases will be announced on Mockoon's [Twitter account @GetMockoon](https://twitter.com/GetMockoon) and through the newsletter to which you can subscribe [here](http://eepurl.com/dskB2X).

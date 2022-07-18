<h1 align="center">
  <div style="display:inline-block;vertical-align: middle;">
      <img src="" width="550"/>
  </div>
</h1>

![build](https://github.com/lasconic/openapi-finary/workflows/build/badge.svg)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)



## End goals


* Automated linting
* Online Documentation 
* Generate SDKs for a few languages (Python at least)


## Development tips:

* Useful tools to create schemas from data
https://www.liquid-technologies.com/online-json-to-schema-converter
https://json2yaml.com/
All in one ? https://github.com/swaggest/json-cli


* Generate Python SDK 
Tested with openapi-generator 6.0.1 and swagger-cli 3.0.34 
$ openapi-generator generate -i ../finary_api2/openapi/finary.yaml -g python -o codegen2 --skip-validate-spec

In my tests, the authentification doesn't work well... I choose to instantiate a client, signin, 
get the cookies from the Set-Cookie header and injects them in a second client for the other calls.
**To be investigated**


## TODO
In resources/user_institution_connections.yaml, we need crypto account description


## Getting started

### Requirements

* Node.js 16 (current)

### Installation

1. Clone the repository.

    ```
    git clone https://github.com/lasconic/openapi-finary.git
    ```

2. Install the project dependencies.

    ```
    npm install
    ```

3. Edit `openapi.yaml` to fit your API definition. If you’re not familiar with the OpenAPI Specification, read [Getting started with OAS](https://swagger.io/solutions/getting-started-with-oas/) first.

## Useful commands

The project will build, lint, and preview the OpenAPI document from the terminal, with the following commands:

### Build

The command bundles the spec as one `.yaml` file.

```
npm run build
```

The minified document is stored in `_build/openapi.yaml`.

### Test

The command checks if the document follows the OpenAPI 3.0 Specification.

```
npm run test
```

### Preview

The command builds a docs site so that you can view the rendering on your local browser.

```
npm run preview
```

The server starts on http://127.0.0.1:8080.

The site is generated with [ReDoc](https://github.com/Redocly/redoc).
Here's a preview of a site generated with this command: [Finary API reference documentation](https://lasconic.github.io/openapi-finary/).

## Ready-to-use workflows

The project uses [GitHub Actions](https://github.com/features/actions) for Continuous Integration (CI).

On every new pull request, the OpenAPI document is linted with [spectral](https://github.com/stoplightio/spectral). If there are changes that introduce errors, the bot will highlight them replying to the pull request.

When the default branch (e.g. `master`) receives an update, a workflow automatically publishes the API reference documentation site to GitHub Pages.

See `.github/workflows` to customize the available workflows. If you don't plan to use GitHub to host your spec or prefer to keep docs private, delete the `.github` folder.

## Contributing

Contributions are welcome and appreciated! 
If you want to enhance the specification, please read [CONTRIBUTING.md](CONTRIBUTING.md) file first.

## License

Copyright (c) 2019-present David Garcia ([@dgarcia360](https://davidgarcia.dev)), @lasconic. Licensed under the [MIT License](LICENSE.md).



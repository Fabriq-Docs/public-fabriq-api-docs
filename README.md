# Fabriq OpenAPI Definition

## How to use this repository

Editing this repository will update the official API documentation of the Fabriq platform that is used by case teams & client pitches. Make your edits, create a PR, and distribution assets will be automatically validated and created for you. We recommend you run `npm test` locally to be sure before pushing..

## Working on your OpenAPI Definition

### Install

1. Install [Node JS](https://nodejs.org/).
2. Clone this repo and run `npm install` in the repo root.

### Usage

#### `npm start`
Starts the reference docs preview server.

#### `npm test`
Validates the definition.

#### `npm run build`
Bundles the yaml definition.

#### `npm run prepare`
Creates a json definition in the docs folder based on the yaml definition.

#### `npm run preview`
Creates a preview server based on the yaml definition.


## Contribution Guide

The `.redocly.yaml` controls settings for various
tools including the lint tool and the reference
docs engine.  Open it to find examples and
[read the docs](https://redocly.com/docs/cli/configuration/)
for more information.


### Schemas

#### Adding Schemas

1. Navigate to the `openapi/components/schemas` folder.
2. Add a file named as you wish to name the schema.
3. Define the schema.
4. Refer to the schema using the `$ref`.

The value of the `$ref` is the path to the other schema definition.

You may use `$ref`s to compose schema from other existing schema to avoid duplication.

You will use `$ref`s to reference schema from your path definitions.

#### Editing Schemas

1. Navigate to the `openapi/components/schemas` folder.
2. Open the file you wish to edit.
3. Edit.

### Paths

#### Adding a Path

1. Navigate to the `openapi/paths` folder.
2. Add a new YAML file named like your URL endpoint except replacing `/` with `_` (or whichever character you prefer) and putting path parameters into curly braces like `{example}`.
3. Add the path and a ref to it inside of your `openapi.yaml` file inside of the `openapi` folder.

### Code samples

Automated code sample generations is enabled in the Redocly configuration file. Add manual code samples by the following process:

1. Navigate to the `openapi/code_samples` folder.
2. Navigate to the `<language>` (e.g. PHP) sub-folder.
3. Navigate to the `path` folder, and add ref to the code sample.

You can add languages by adding new folders at the appropriate path level.

More details inside the `code_samples` folder README.

### Updating Documentation

When you create a PR, GitHub Actions will automatically run the build & prepare steps to ensure a valid API definition can be created, producing the relevant artefacts.

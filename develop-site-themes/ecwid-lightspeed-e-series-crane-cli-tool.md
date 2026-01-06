# Ecwid (Lightspeed E-Series) Crane CLI tool

**Crane CLI** is a simple tool that provides CLI and IDE features for developing and deploying themes to Ecwid. With Crane, you can:

* Install all pre-required packages automatically
* Initialize theme templates
* Build and deploy themes and sections

### CLI commands

* `init` command initializes the project in your local environment and downloads code examples. It requires two arguments: `type` and `name`.

The `type` argument is one of the `--app`, `--section`, or `--template`.

Code example:

```bash
npx @lightspeed/crane@latest init --app _name_ 'change _name_ with your name for app/section/theme'
```

* `build` command compiles the project in your local environment. It doesn’t apply any changes to the project version deployed to Ecwid and should always be used in combination with the `deploy` command.
* `deploy` command sends the current build from your local environment to Ecwid.

Code example:

```bash
npx @lightspeed/crane@latest build
npx @lightspeed/crane@latest deploy
```

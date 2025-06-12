# Ecwid (Lightspeed E-Series) Crane CLI tool

Instant Site templates are built locally and then deployed to Ecwid. Therefore developers don’t need to worry about the hosting, but they need the tool specified for building templates. Ecwid offers such a tool called **Crane**.

Crane includes CLI (command line interface) and IDE features that help with creating and deploying templates and their components for Ecwid Instant Site:

* Install all pre-required packages automatically
* Initialize a new template using our example as a starting point
* Build and deploy templates and sections from the command line

### CLI commands

You can initialize, build, and deploy templates with the command line. Find a detailed guide for their usage in the [**Quickstart**](quickstart-guide-to-a-working-site-template.md).

`init` command initializes the project in your local environment and downloads code examples. It requires two arguments: `type` and `name`.

The `type` argument is one of the `-- app`, `--section`, or `--template`.

Code example:

```
npx @lightspeed/crane@latest init --app <name>
```

`build` command creates a new build in your local environment. It doesn’t apply any changes to the project version deployed to Ecwid and should always be used in combination with the `deploy` command.

Code example:

```
npx @lightspeed/crane@latest build
```

`deploy` command sends the current build from your local environment to Ecwid.

Code example:

```
npx @lightspeed/crane@latest deploy
```

# Quickstart guide to a working Site template

In the following guide, you’ll start by signing up with Ecwid and will end up with a fully working Site template code deployed to your test store.

You need a good knowledge of **Typescript** and its **Vue** framework to build templates. Site templates are built locally and then deployed to the Ecwid environment. After deploying, you can find and install your template in the website Editor. To apply any deployed changes, you need to reinstall the template.

### Step 1. Sign up with Ecwid

You need a store on any paid plan to start working with IS templates. [Sign up with Ecwid](https://my.ecwid.com/)

We will provide you with a free test store with API access if you:

* Work on a Site customization for one of our clients
* Want to develop a public section or template for our App Market

[Email us](mailto:ec.apps@lightspeedhq.com) to get a test store.

If you already have a working store, you can safely build templates in a local environment and check them with website Editor without applying any changes. Preview mode in the Editor allows it.

### Step 2. Set up an application

Working with Site templates requires authorization and access to Ecwid API. We have a platform called **application** where you can configure permissions called access scopes and authorize different APIs. A private application that gives access to your store API only is called a **custom application**.

Get up a custom app right from your Ecwid admin on the [app dashboard](https://my.ecwid.com/#develop-apps).

### Step 3. Get access scope

With the app, you can access store data with API. However, you need to request additional permissions to build Site templates: `add_custom_blocks` and `add_custom_templates`.

[Email us](mailto:ec.apps@lightspeedhq.com) with your application name or _client\_id_ and required access scopes, so we can update the app for you.

### Step 4. Install Node.js and npm

Use CLI (Command Line Interface) to deploy the template code to Ecwid. If your CLI doesn't yet support `npm`/`npx` commands, install the required package from the Node.js official website.

Please make sure that your local node version matches the minimum version required by the `crane` tool. Check the node and npm version by running the following commands:

```sh
node -v
npm -v
```

{% hint style="success" %}
We recommend using **Node.js LTS version 22** to ensure stability and avoid compatibility issues.
{% endhint %}

**Crane** is a CLI tool for developing Site templates. Learn more about the Crane tool

With Crane, you can get a template code working locally and control its deployment with CLI. Use the following commands to set up a project folder, install all dependencies, and get the example template code.

Create a project folder and go into it:

```sh
mkdir {proj_folder}
cd ~/{proj_folder} 
```

Install all required modules to the project folder:

```sh
npm install vite
npm install vue
npm install @lightspeed/crane@latest
npm install @lightspeed/eslint-config-crane@latest
```

Initialize a new app inside the project folder and go into its folder:

```sh
npx @lightspeed/crane@latest init --app my-app
cd my-app
```

Now, inside the app folder, you need to init an example template:

```sh
npx @lightspeed/crane@latest init --template example-template
```

Initializing the app automatically inits an example section inside its folder. However, you can add more sections at any time with the following code:

```sh
npx @lightspeed/crane@latest init --section my-section
```

After that, go into the example section folder and install additional dependencies for its example code:

```sh
npm install -D sass
```

Now you have a project folder with all the required files and modules to start template development.

### Step 6. Set up a project in IDE

We recommend using the free [**VS Code**](https://code.visualstudio.com/download) application with **Vue** and **TypeScript** extensions. Open the project folder there and check the file structure inside. [**Learn more about the structure**](https://api-docs.ecwid.com/docs/how-instant-site-templates-work)

First, you need to set up the crane.config.json file, it will connect the templates you build locally with the application on our side. Open it and copy the client\_id and client\_secret from your custom application to the file. Find these values at the bottom of the [**Ecwid admin > #develop-apps > Details**](https://my.ecwid.com/#develop-apps) page.

After the changes, your file should look like this:

```json
{
    "app_client_id": "custom-app-1003-1",
    "app_secret_key": "HHLmjxjjQrRpDPrC5Uzx2BooUQeeesEmr"
}
```

### Step 7. Deploy example template to Ecwid

From this point, you can start developing custom templates. To start, deploy the example template to Ecwid as it is.

To do so, make sure your application is installed in the Ecwid admin. Go to [**Ecwid admin > My apps**](https://my.ecwid.com/#my_apps) and check if your custom app is listed there. After that, run the build and deploy commands in CLI.

Go to the app folder inside the project:

```sh
$ cd ~/{proj_folder}/my-app
```

Build templates on your local machine:

```sh
$ npx @lightspeed/crane@latest build
```

Deploy built templates to Ecwid:

```sh
$ npx @lightspeed/crane@latest deploy
```

You should see build logs and a deploy success message in CLI. [Email us](mailto:ec.apps@lightspeedhq.com) with details about your application and store if you have any errors in this step.

Now you can find your custom template in the website Editor in your Ecwid admin. Go to **Settings > Templates** in the top left Editor menu.

### Next steps

Learn more about all the files in the project folder and building public templates:

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th data-hidden></th></tr></thead><tbody><tr><td><a href="build-site-templates-project-structure/">Learn the structure of your project</a></td><td></td></tr><tr><td><a href="broken-reference">Publish your templates</a></td><td></td></tr></tbody></table>


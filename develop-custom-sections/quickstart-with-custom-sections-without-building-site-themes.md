# Quickstart with custom sections without building Site themes

**Custom section** is a building block of the website page created by you or your developer. Sections are not limited in their content and therefore can cover any functionality. You can develop and publish sections without building fully functional themes as long as each of your sections has a completed style and functionality.

Sections are based on **Typescript** language and its **Vue** framework. You need proper knowledge of TypeScript to uncover the full potential of the feature.

Sections are built locally and then deployed to the Ecwid environment. After deploying, your custom sections will become available in the website editor. To apply any changes deployed to the existing section, remove and then reinstall the section in the editor.

### Step 1. Sign up with Ecwid

You need a store on any paid plan to start working with sections. [**Sign up with Ecwid**](https://my.ecwid.com/)

We will provide you with a free test store with API access if you:

* Work on a Site customization for one of our clients.
* Want to develop a public section for Ecwid.

[**Email us**](mailto:ec.apps@lightspeedhq.com) to get a test store.

To customize your working store, build sections in a local environment and test them inside the website Editor without applying any changes. Preview mode in the editor allows it.

### Step 2. Set up an application

Working with Site sections requires authorization and access to Ecwid API. We have a platform called **application** where you can configure permissions called access scopes and authorize different APIs. A private application that gives access to your store API only is called a **custom application**.

Set up a custom application for your Ecwid store right from the admin, it only takes a few seconds: [**#develop-apps**](https://my.ecwid.com/#develop-apps)

### Step 3. Get access scope

With the app, you can access store data with API. However, you need to request additional permission to build sections: `add_custom_blocks`.

[**Email us**](mailto:ec.apps@lightspeedhq.com) with your application name or _client\_id_ and required access scope, so we can update the app for you.

### Step 4. Install Node.js and npm package

CLI (Command Line Interface) is required to deploy sections to Ecwid. Make sure that your local node version matches the minimum version required by the `crane` tool. Find instructions on installing node and npm on the [**Node.js official website**](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm).

{% hint style="success" %}
We recommend using **Node.js LTS version 22** to ensure stability and avoid compatibility issues.
{% endhint %}

### Step 5. Start a local project with the Crane tool

**Crane** is a CLI tool for developing Site sections. [**Learn more about the Crane tool**](../develop-site-themes/ecwid-lightspeed-e-series-crane-cli-tool.md)

With Crane, you can get a section code working locally and control its deployment with CLI. Use the following commands to set up a project folder, install all dependencies, and get the example section code.

Create a project folder:

```sh
mkdir {proj_folder}
cd ~/{proj_folder} 
```

Install all required modules:

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

Initializing the app automatically inits an example section inside its folder. However, you can add more sections at any time with the following code:

```sh
npx @lightspeed/crane@latest init --section my-section
```

After that, go into the example section folder and install additional dependencies for its example code:

```sh
cd example-section
npm install -D sass
```

Now you have a project folder with all the required files and modules to start section development.

### Step 6. Set up a project in IDE

We recommend using the free [**VS Code**](https://code.visualstudio.com/download) application with **Vue** and **TypeScript** extensions. Open the project folder there and check the file structure inside. [**Learn more about the structure**](../develop-site-themes/build-site-themes-project-structure/)

First, you need to set up the `crane.config.json` file, it will connect the sections you build locally with the application on Ecwid side. Open the file and copy the `client_id` and `client_secret` from your custom application to the file. Find these values at the bottom of the [**Ecwid admin > #develop-apps > Details**](https://my.ecwid.com/#develop-apps) page.

After the changes, your file should look like this:

```json
{
    "app_client_id": "custom-app-1003-1",
    "app_secret_key": "HHLmjx1NQropDPrC5Uzx2BMoUQo4esEmr"
}
```

### Step 7. Deploy example section to Ecwid

From this point, you can start developing custom sections. To start, deploy your example section to Ecwid as it is.

To do so, make sure your application is installed in the Ecwid admin. Go to [**Ecwid admin > My apps**](https://my.ecwid.com/#my_apps) and check if your custom app is listed there. After that, run the build and deploy commands in CLI.

Code example:

```sh
'Go to section folder inside the project'
$ cd ~/{proj_folder}/example-section

'Build section on your local machine'
$ npx @lightspeed/crane@latest build

'Deploy built section to Ecwid'
$ npx @lightspeed/crane@latest deploy
```

You should see a success message in CLI. [**Email us**](mailto:ec.apps@lightspeedhq.com) with details about your application and store if you have any errors in this step.

After that, check the version in the `package.json` file. You should see something like this:

```json
{
  "name": "example-section",
  "private": true,
  "version": "0.0.2",
  ...
}
```

Version value starts with `0.0.1` and iterates automatically with each successful deployment. The value from the `package.json` file is the next deployment version. We recommend not editing it manually.

Now you can find your custom sections in the website editor in your Ecwid admin. Go to the editor and click the **+ Add section** button in the side menu.

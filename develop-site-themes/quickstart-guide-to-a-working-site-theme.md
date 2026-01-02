# Quickstart guide to a working Site theme

In the following guide, you’ll start by signing up with Ecwid and will end up with a fully working Site theme code deployed to your test store.

You need a good knowledge of **Typescript** and its **Vue** framework to build themes. Site themes are built locally and then deployed to the Ecwid environment. After deploying, you can find and install your theme in the website Editor. To apply any deployed changes, you need to reinstall the theme app.

### Step 1. Sign up with Ecwid

To work with themes, you need a store and API access.

Start your journey by submitting a new dev form from the following link: [https://portal.ecwid.com/en-us/app-market-request](https://portal.ecwid.com/en-us/app-market-request).

Specify that you are working on a theme, leave some contact details, and share some of your existing projects/apps here. Our App team will review the form shortly and contact you by email to give a **free test store with API access**.&#x20;

Feel free to [email us](mailto:ec.apps@lightspeedhq.com) anytime.

### Step 2. Set up an application

Working with Site themes requires authorization and access to Ecwid API. We have a platform called **application** where you can configure permissions called access scopes and authorize different APIs. A private application that gives access to your store API only is called a **custom application**.

Get up a custom app right from your Ecwid admin on the [app dashboard](https://my.ecwid.com/#develop-apps).

### Step 3. Get access scope

With the app, you can access store data with API. However, you need to request additional permissions to build Site themes: `add_custom_blocks` and `add_custom_templates`.

[Email us](mailto:ec.apps@lightspeedhq.com) with your application name or _client\_id_ and required access scopes, so we can update the app for you.

### Step 4. Initialize project files

Use CLI (Command Line Interface) to deploy the theme code to Ecwid. If your CLI doesn't yet support `npm`/`npx` commands, install the required package from the Node.js official website.

Please make sure that your local node version matches the minimum version required by the `crane` tool. Check the node and npm version by running the following commands:

```sh
node -v
npm -v
```

{% hint style="success" %}
We recommend using **Node.js LTS version 22+** to ensure stability and avoid compatibility issues.
{% endhint %}

**Crane** is a CLI tool for developing Site themes. Learn more about the Crane tool

With Crane, you can run themes locally and control their deployment with CLI. Use the following commands to start your project:

* Create a project folder, go into it, and install dependencies:

```sh
mkdir my-theme-project // create the project
cd my-theme-project // go inside the project
npm install vite vue sass @lightspeed/crane@latest @lightspeed/eslint-config-crane@latest
```

* Initialize a new app inside the project folder:

```sh
npx @lightspeed/crane@latest init --app my-app
```

* Go to the app folder, initialize the theme template code:

```sh
cd my-app // go inside the app
npx @lightspeed/crane@latest init --template example-template // name it however you want
```

* Initialize the example section code:

```sh
npx @lightspeed/crane@latest init --section my-section
```

Now you have a project folder with all the required files and modules to start theme development.

### Step 5. Set up a project in IDE

We recommend using the free [**VS Code**](https://code.visualstudio.com/download) application with **Vue** and **TypeScript** extensions. Open the project folder there and check the file structure inside. [**Learn more about the structure**](https://api-docs.ecwid.com/docs/how-instant-site-templates-work)

First, you need to set up the crane.config.json file, it will connect the themes you build locally with the application on our side. Open it and copy the client\_id and client\_secret from your custom application to the file. Find these values at the bottom of the [**Ecwid admin > #develop-apps > Details**](https://my.ecwid.com/#develop-apps) page.

After the changes, your file should look like this:

```json
{
    "app_client_id": "custom-app-1003-1",
    "app_secret_key": "HHLmjxjjQrRpDPrC5Uzx2BooUQeeesEmr"
}
```

### Step 6. Deploy theme template to Ecwid

{% hint style="info" %}
Before deploying, make sure your application is installed in the Ecwid admin. Go to [**Ecwid admin > My apps**](https://my.ecwid.com/#my_apps) and check if your custom app is listed there.
{% endhint %}

Once you are ready to check how your code works in the store, use the following commands:

```sh
cd ~/{proj_folder}/my-app  //make sure you run commands from your app folder 

npx @lightspeed/crane@latest preview  //preview

npx @lightspeed/crane@latest build  //compile locally

npx @lightspeed/crane@latest deploy  //upload section code to Ecwid
```

You should see a success message in CLI. [**Email us**](mailto:ec.apps@lightspeedhq.com) with details about your application and store if you have any errors in this step.

Now you can find your custom theme in the website Editor in your Ecwid admin. Go to **Settings > Themes** in the top left Editor menu.

### Next steps

Learn more about project structure and launching themes:

{% content-ref url="build-site-themes-project-structure/" %}
[build-site-themes-project-structure](build-site-themes-project-structure/)
{% endcontent-ref %}

{% content-ref url="/broken/pages/2v05Nufe5t3VYzcP8NqB" %}
[Broken link](/broken/pages/2v05Nufe5t3VYzcP8NqB)
{% endcontent-ref %}

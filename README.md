## What is Strapi?

Strapi is the leading open-source headless CMS offering [features](https://strapi.io/features), like customizable APIs, role-based permissions, multilingual support, etc. It simplifies content management and integrates effortlessly with modern [frontend frameworks](https://strapi.io/blog/comprehensive-review-of-top-javascript-frontend-frameworks).

Explore the [Strapi documentation](https://docs.strapi.io/) for more details.

## What is React.js?

[React](https://react.dev/) is a JavaScript library for building user interfaces, especially dynamic and interactive web applications. React lets you build user interfaces out of individual pieces called components.

Visit the [React.js documentation](https://react.dev/learn) for more.

## Strapi 5 Highlights

The out-of-the-box Strapi features allow you to get up and running in no time:

1. **Single types**: Create one-off pages that have a unique content structure.
2. **Draft and Publish**: Reduce the risk of publishing errors and streamline collaboration.
3. **100% TypeScript Support**: Enjoy type safety & easy maintainability
4. **Customizable API**: With Strapi, you can just hop in your code editor and edit the code to fit your API to your needs.
5. **Integrations**: Strapi supports integrations with Cloudinary, SendGrid, Algolia, and others.
6. **Editor interface**: The editor allows you to pull in dynamic blocks of content.
7. **Authentication**: Secure and authorize access to your API with JWT or providers.
8. **RBAC**: Help maximize operational efficiency, reduce dev team support work, and safeguard against unauthorized access or configuration modifications.
9. **i18n**: Manage content in multiple languages. Easily query the different locales through the API.
10. **Plugins**: Customize and extend Strapi using plugins.

Learn more about [Strapi 5 feature](https://strapi.io/five).

<cta title="See Strapi in action with an interactive demo" text="Explore Strapi in an instant, hands-on demo set up just for you." buttontext="Access Live Demo!" buttonlink="https://strapi.io/demo"></cta>

## Setup Strapi 5 Headless CMS

We are going to start by setting up our [Strapi 5](https://strapi.io/five) project with the following command:

> 🖐️ Note: make sure that you have created a new directory for your project.

You can find the full documentation for Strapi 5 [here](https://docs.strapi.io/dev-docs/intro).

### Install Strapi

```bash
npx create-strapi-app@latest server
```

You will be asked to choose if you would like to use Strapi Cloud we will choose to skip for now.

```bash
 Strapi   v5.6.0 🚀 Let's create your new project


We can't find any auth credentials in your Strapi config.

Create a free account on Strapi Cloud and benefit from:

- ✦ Blazing-fast ✦ deployment for your projects
- ✦ Exclusive ✦ access to resources to make your project successful
- An ✦ Awesome ✦ community and full enjoyment of Strapi's ecosystem

Start your 14-day free trial now!


? Please log in or sign up.
  Login/Sign up
❯ Skip
```

After that, you will be asked how you would like to set up your project. We will choose the following options:

```bash
? Do you want to use the default database (sqlite) ? Yes
? Start with an example structure & data? Yes <-- make sure you say yes
? Start with Typescript? Yes
? Install dependencies with npm? Yes
? Initialize a git repository? Yes
```

Once everything is set up and all the dependencies are installed, you can start your Strapi server with the following command:

```bash
cd server
npm run develop
```

You will be greeted with the **Admin Create Account** screen.

![003-strapi-5.png](https://delicate-dawn-ac25646e6d.media.strapiapp.com/003_strapi_5_0ec1eaaa6a.png)

Go ahead and create your first Strapi user. All of this is local so you can use whatever you want.

Once you have created your user, you will be redirected to the **Strapi Dashboard** screen.

![004-strapi-5.png](https://delicate-dawn-ac25646e6d.media.strapiapp.com/004_strapi_5_87bc6d8f39.png)

### Publish Article Entries

Since we created our app with the example data, you should be able to navigate to your **Article** collection and see the data that was created for us.

![005-strapi-5.png](https://delicate-dawn-ac25646e6d.media.strapiapp.com/005_strapi_5_dc3a4a7540.png)

Now, let's make sure that all of the data is **published**. If not, you can select all items via the checkbox and then click the **Publish** button.

![Strapi Articles Published](https://delicate-dawn-ac25646e6d.media.strapiapp.com/006_strapi_5_9c6055ac59.png)

### Enable API Access

Once all your articles are published, we will expose our Strapi API for the **Articles Collection**. This can be done in **_Settings -> Users & Permissions plugin -> Roles -> Public -> Article_**.

You should have `find` and `findOne` selected. If not, go ahead and select them.

![007-strapi-5.png](https://delicate-dawn-ac25646e6d.media.strapiapp.com/007_strapi_5_edd775db5f.png)

### Test API

Now, if we make a `GET` request to `http://localhost:1337/api/articles`, we should see the following data for our articles.

![008-strapi-5.png](https://delicate-dawn-ac25646e6d.media.strapiapp.com/008_strapi_5_66883c2963.png)

> 🖐️ Note: The article covers (images) are not returned. This is because the REST API by default does not populate any relations, media fields, components, or dynamic zones.. Learn more about [REST API: Population & Field Selection](https://docs.strapi.io/dev-docs/api/rest/populate-select).

So, let's get the article covers by using the `populate=*` parameter: `http://localhost:1337/api/articles?populate=*`

![vuejs strapi integration - api request.png](https://delicate-dawn-ac25646e6d.media.strapiapp.com/vuejs_strapi_integration_api_request_c748d16c83.png)

Nice, now that we have our Strapi 5 server setup, we can start to setup our React.js application.

## Getting Started with React

In order to get started with React, you are recommended to start with a framework.

- **Next.js**: Visit the [Next.js and Strapi integration page](https://strapi.io/integrations/nextjs-cms).
- **React Router 7 (Remix)**: Visit the [React Router 7 and Strapi integration page](https://strapi.io/integrations/react-router-7).
- **Using Vite**: Continue below 👇 to use [Vite](https://vite.dev/) build tool.

### Scaffolding a React App using Vite

Scaffold a React app using the command below. The command below will scaffold a React application using the TypeScript template.

Use `react` if you prefer plain JavaScript; otherwise, use `react-ts`.

Learn more [here](https://vite.dev/guide/)

```bash
npm create vite@latest my-react-app -- --template react-ts
```

### Install and Run Scaffolded React App

After running the command above, you will get the following response:

```bash
cd my-react-app
npm install
npm run dev
```

The command above will CD into your React application, install required dependencies and start your React applicaction on a Vite development server.

Your application should be available in the URL `http://localhost:5173/` as shown below:

![Create a React app with Vite.png](https://delicate-dawn-ac25646e6d.media.strapiapp.com/Create_a_React_app_with_Vite_661a3b2917.png)

## Add Tailwind CSS To React.js Project

We will install [Tailwind CSS](https://tailwindcss.com/) as a PostCSS plugin.

### Install Tailwind

Run the command below in your React project folder, in this case `my-react-app`. The command below will install `tailwindcss`, `@tailwindcss/postcss`, and `postcss` via npm.

```bash
npm install tailwindcss @tailwindcss/postcss postcss
```

### Add Tailwind CSS to your PostCSS configuration

Create a configuration file called `postcss.config.cjs` at the root of your project and add the following code:

```javascript
// Path: ./postcss.config.cjs

export default {
  plugins: {
    "@tailwindcss/postcss": {},
  },
};
```

### Import Tailwind CSS

Remove all the codes present inside your CSS file `./src/index.css` file and import Tailwind CSS.

```css
/* Path: ./src/index.css */

@import "tailwindcss";
```

### Restart your React Application

Make sure you are in your React application folder `my-react-app`. Stop your React app and restart it using the command below:

```bash
npm run dev
```

## Use an HTTP Client For Requests

Many HTTP clients are available, but on this integration page, we'll use [Axios](https://github.com/axios/axios) and [Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API).

### Using Axios

Install Axios by running any of the commands below:

```bash
# npm
npm i axios

# yarn
yarn add axios
```

### Using fetch

No installation needed

## Fetch Contents from Strapi

Execute a `GET` request on the **Article** collection type in order to fetch all your articles.

Be sure that you activated the `find` permission for the `Article` collection type.

> 🖐️ NOTE: We want to also fetch **covers (images)** of articles, so we have to use the `populate` parameter as seen below.

### Using Axios

```javascript
import axios;

// fetch articles along with their covers
const response = await axios.get("http://localhost:1337/api/articles?populate=*");
console.log(response.data.data);
```

### Using Fetch

```javascript
const response = await fetch("http://localhost:1337/api/articles?populate=*");
const data = await response.json();
console.log(data.data);
```

## Project Example

In this project example, you will fetch data from Strapi and display them in your React.js application.

Head over to your React.js entry file `./src/App.tsx` to proceed. Ensure you remove all code snippet inside it.

### Create a new React Component

Create a new component called **App**.

```javascript
export default function App() {
  return <div className=" text-3xl text-red">App</div>;
}
```

### Step 2: Import React Hooks

Import the React hooks `useEffect` and `useState` for side effects and state management, respectively.

```javascript
// Import React hooks
import { useEffect, useState } from "react";
```

### Step 3: Create Data Type and Constant

Create an interface called `Article`, which represents the data structure of the articles we will fetch from Strapi. Also, create a Strapi URL constant.

```javascript
// Create Article Interface
export interface Article {
  id: string;
  title: string;
  content: string;
  cover: any;
  publishedAt: Date;
}

// Define Strapi URL
const STRAPI_URL = "http://localhost:1337";
```

### Step 3: Define `articles` State Variable

Inside the **App** component, create a state variable `articles` to hold articles data fetched from Strapi.

```javascript
// Define articles state
const [articles, setArticles] = useState<Article[]>([]);
```

### Step 4: Create a Function to Fetch Articles

Create an asynchronous function that fetches the articles from the Strapi API. The data fetched is passed to `setArticles` to update the articles state.

```javascript
// fetch articles
const getArticles = async () => {
  const response = await fetch(`${STRAPI_URL}/api/articles?populate=*`);
  const data = await response.json();
  setArticles(data.data);
};
```

### Step 5: Create a Function to Format Dates

Create a helper function to format the `publishedAt` date of the article into a human-readable format `(MM/DD/YYYY)`.

```javascript
// Format date
const formatDate = (date: Date) => {
  const options: Intl.DateTimeFormatOptions = {
    year: "numeric",
    month: "2-digit",
    day: "2-digit",
  };
  return new Date(date).toLocaleDateString("en-US", options);
};
```

### Step 6: Fetch Articles on Component Mount

Use the `useEffect` hook to run the `getArticles` function when the component mounts.

```javascript
useEffect(() => {
  getArticles();
}, []);
```

### Step 7: Render and Display Articles

Render and display the fetched articles from Strapi.

```javascript
return (
  <div className="p-6">
    <h1 className="text-4xl font-bold mb-8">React.js and Strapi Integration</h1>
    <div>
      <h2 className="text-2xl font-semibold mb-6">Articles</h2>
      <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        {articles.map((article) => (
          <article
            key={article.id}
            className="bg-white shadow-md rounded-lg overflow-hidden"
          >
            <img
              className="w-full h-48 object-cover"
              src={STRAPI_URL + article.cover.url}
              alt={article.title}
              width={180}
              height={38}
            />
            <div className="p-4">
              <h3 className="text-lg font-bold mb-2">{article.title}</h3>
              <p className="text-gray-600 mb-4">{article.content}</p>
              <p className="text-sm text-gray-500">
                Published: {formatDate(article.publishedAt)}
              </p>
            </div>
          </article>
        ))}
      </div>
    </div>
  </div>
);
```

Now, this is what your React.js project should look like:

![ReactJs and Strapi Integration-min.png](https://delicate-dawn-ac25646e6d.media.strapiapp.com/React_Js_and_Strapi_Integration_min_58e79013db.png)

Awesome, congratulations!

## Github Project Repo

You can find the complete code for this project in the following [Github repo](https://github.com/Theodore-Kelechukwu-Onyejiaku/react-and-strapi-integration).

## Strapi Open Office Hours

If you have any questions about Strapi 5 or just would like to stop by and say hi, you can join us at **Strapi's Discord Open Office Hours** Monday through Friday at 12:30 pm - 1:30 pm CST: [Strapi Discord Open Office Hours](https://discord.com/invite/strapi)

For more details, visit the [Strapi documentation](https://strapi.io/documentation) and [React.js documentation](https://react.dev/learn).

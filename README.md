# WordPress + React Starter Kit

Postlight's Headless WordPress + React Starter Kit is an automated toolset that will spin up two things:

1. A WordPress backend that serves its data via the [WP REST API](https://developer.wordpress.org/rest-api/).
2. A server-side rendered React frontend using Next.js.

**What's inside:**

* Installer script which bootstraps a clean, default core WordPress installation plus all the plugins you need to set up custom post types and custom fields and expose them in the WP REST API (Advanced Custom Fields Pro, Custom Post Type UI, and ACF to WP API).
* All the starter theme code, fixes, and settings you need for building and running headless WordPress, including pretty permalinks, CORS Allow headers, and useful logging functions for easy debugging.
* A mechanism for easily importing data from an existing WordPress installation anywhere on the web using WP Migrate DB Pro and its accompanying plugins (license required).
* A Docker container and scripts to manage it, for easily running the frontend React app locally or deploying it to any hosting provider with Docker support.

Let's get started.

## WordPress Backend

The following setup will get WordPress running locally on your machine, along with the WordPress plugins you'll need to create and serve custom data via the WP REST API.

_Note: This environment has only been tested under OS X. It requires [Homebrew](https://brew.sh/) and [Yarn](https://yarnpkg.com/en/)._

To install and start WordPress, run the following command:

```zsh
> yarn install && yarn start
```

When that completes successfully, the WordPress REST API will be available at [http://localhost:8080](http://localhost:8080).

### Import Data (Optional)

To import data and media from a live WordPress install locally, use Migrate DB Pro. In the `robo.yml` file, set the plugin license and source install. Then, run `robo wordpress:import` to pull in the data.

### Extend the WordPress API

At this point you can start setting up custom fields, and if necessary, creating [custom REST API endpoints](https://developer.wordpress.org/rest-api/extending-the-rest-api/adding-custom-endpoints/) in the Postlight Headless WordPress Starter theme. When you do, be sure to [use WordPress coding standards](https://github.com/postlight/headless-wp-starter/blob/master/wordpress/wp-content/themes/postlight-headless-wp/README.md).

* The backend is running at [http://localhost:8080](http://localhost:8080)
* WordPress admin is at [http://localhost:8080/wp-admin/](http://localhost:8080/wp-admin/)  nedstark / winteriscoming
* Primary theme code is located in `wordpress/wp-content/themes/postlight-headless-wp`

## React Frontend

To spin up the frontend client app, run the following commands:

```zsh
> cd frontend && yarn install && yarn run dev
```

The Next.js app will be running on [http://localhost:3000](http://localhost:3000).

### Docker

This project uses a Docker container, which can be run locally or deployed to a hosting provider with Docker support like AWS Elastic Beanstalk.

Once you have [Docker](https://www.docker.com/) installed on your computer, you can run the container locally using this command:

```zsh
# Build and run the container
> yarn run deploy
```

---

Made with ❤️ by [Postlight](https://postlight.com). Happy coding!

# Getting Started

## Installation

You'll need to install the skeleton and the library.

Start by installing [the Yarn package manager](https://yarnpkg.com/) ([NPM](https://www.npmjs.com/) is also supported) and
the [Create React App](https://facebook.github.io/create-react-app/) tool.

Then, create a new React application for your admin:

    $ create-react-app my-admin

Now, go to the newly created `my-admin` directory:

    $ cd my-admin

Finally, install the `@api-platform/admin` library:

    $ yarn add @api-platform/admin

## Creating the Admin

Edit the `src/App.js` file the following way:

```javascript
import React from 'react';
import { HydraAdmin } from '@api-platform/admin';

export default () => <HydraAdmin entrypoint="https://demo.api-platform.com"/>; // Replace with your own API entrypoint
```

Be sure to make your API send proper [CORS HTTP headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) to allow
the admin's domain to access it.
To do so, update the value of the `CORS_ALLOW_ORIGIN` parameter in `api/.env` (it will be set to `^https?://localhost:?[0-9]*$`
by default).

If you're not using the API Platform distribution, you will need to adjust the NelmioCorsBundle configuration to expose the `Link` HTTP header and to send proper CORS headers on the route under which the API will be served (`/api` by default).
Here is a sample configuration (if you use the API Platform distribution, you can skip this step):

```yaml
# config/packages/nelmio-cors.yaml

nelmio_cors:
    paths:
        '^/api/':
            origin_regex: true
            allow_origin: ['^http://localhost:[0-9]+'] # You probably want to change this regex to match your real domain
            allow_methods: ['GET', 'OPTIONS', 'POST', 'PUT', 'PATCH', 'DELETE']
            allow_headers: ['Content-Type', 'Authorization']
            expose_headers: ['Link']
            max_age: 3600
```

Clear the cache to apply this change:

    $ docker-compose exec php bin/console cache:clear --env=prod

Your new administration interface is ready! Type `yarn start` to try it!

Note: if you don't want to hardcode the API URL, you can [use an environment variable](https://facebook.github.io/create-react-app/docs/adding-custom-environment-variables).

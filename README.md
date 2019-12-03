# Node SSR for Sitecore Content Delivery

#1. LayoutService API should be returning output if you make the following request to your Sitecore instance. `http://sitecore-host/sitecore/api/layout/render/jss?item=/&sc_apikey={YOUR_API_KEY}`

#2.  Build your JS app bundle with `jss build` and change SitecoreLayoutService Host in scconfig.json file with node proxy url(http://localhost:3000).


#3. Copy Build Artifact into Node proxy root folder as per sitecore dist folder in CD server. (dist/jss-app-name).

#4. Create Enviornment variables.


#Environment Variables

The following environment variables can be set to configure the proxy instead of modifying `config.js`, for environments where this is more desirable like containers:

| Parameter                              | Description                                                                                                                                |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `SITECORE_JSS_APP_NAME`                | The JSS app's name. Used in dictionary service URL, and the default value of `SITECORE_JSS_SERVER_BUNDLE` if it's not set.                 |
| `SITECORE_JSS_SERVER_BUNDLE`           | Path to the JSS app's `server.bundle.js` file.                                                                                             |
| `SITECORE_API_HOST`                    | Sitecore instance host name. Should be HTTPS in production.                                                                                |
| `SITECORE_API_KEY`                     | The Sitecore SSC API key your app uses.                                                                                                    |
| `SITECORE_ENABLE_DEBUG`                | Optional. Writes verbose request info to stdout for debugging. Defaults to `false`.                                                        |

#4. Build & run

#5.  Run `npm install`

#6.  Run `npm run start`

You should be able to see the following message:
`server listening on port 3000!` and see all the communication between this server and your Sitecore CD instance in the console.

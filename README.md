**Deprecated: this repository is no longer the recommended way of deploying Node-RED to IBM Cloud. It will not be receiving any new fixes or updates.**


Please refer to [this IBM Developer tutorial](https://developer.ibm.com/tutorials/how-to-create-a-node-red-starter-application/) for how to create a new Node-RED Starter Application in IBM Cloud.

***


### Node-RED on IBM Cloud

This repository is an example Node-RED application that can be deployed into
IBM Cloud with only a couple clicks. Try it out for yourself right now by clicking:

[Deploy to IBM Cloud](https://bluemix.net/deploy?repository=https://github.com/IBMDeveloperUK/node-red-bluemix-starter.git)

### How does this work?

When you click the button, you are taken to IBM Cloud where you get a pick a name
for your application at which point the platform takes over, grabs the code from
this repository and gets it deployed.

It will automatically create an instance of the Cloudant service and bind it to
your app. This is where your Node-RED instance will store its data.

When you first access the application, you'll be asked to set some security options
to ensure your flow editor remains secure from unauthorised access.

It includes a set of default flows that are automatically deployed the first time
Node-RED runs.

### Customising Node-RED

This repository is here to be cloned, modified and re-used to allow anyone create
their own Node-RED based application that can be quickly deployed to IBM Cloud.

The default flows are stored in the `defaults` directory in the file called `flow.json`.
When the application is first started, this flow is copied to the attached Cloudant
instance. When a change is deployed from the editor, the version in cloudant will
be updated - not this file.

The web content you get when you go to the application's URL is stored under the
`public` directory.

Additional nodes can be added to the `package.json` file and all other Node-RED
configuration settings can be set in `bluemix-settings.js`.

If you do clone this repository, make sure you update this `README.md` file to point
the `Deploy to IBM Cloud` button at your repository.

If you want to change the name of the Cloudant instance that gets created, the memory
allocated to the application or other deploy-time options, have a look in `manifest.yml`.

### Environment Variables

The following environment variables can be used to configure the application:

 - `NODE_RED_STORAGE_NAME` - the Cloudant service name as exposed in `VCAP_SERVICES`
 - `NODE_RED_STORAGE_DB_NAME` - the name of the database to use on Cloudant
 - `NODE_RED_STORAGE_APP_NAME` - the prefix used in document names, allowing multiple instances
    to share the same database.
 - `NODE_RED_USERNAME`, `NODE_RED_PASSWORD` - if set, used to secure the editor
 - `NODE_RED_GUEST_ACCESS` - if the editor is secured, this will allow anonymous,
    read-only access
 - `NODE_RED_USE_APPMETRICS` - enables the appmetrics dashboard

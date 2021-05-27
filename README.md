# test-submodules-backend-nodejs

This is the Node.js backend part of an experimental Autodesk Forge sample app
that is split across multiple GitHub repositories.

## Prerequisites

- [Autodesk Forge app](https://forge.autodesk.com/en/docs/oauth/v2/tutorials/create-app)
- [Node.js](https://nodejs.org) (LTS version)
- [Git](https://git-scm.com)

## Getting started

- Clone this repository _with submodules_:
    ```
    git clone --recurse-submodules https://github.com/petrbroz/test-submodules-backend-nodejs
    cd test-submodules-backend-nodejs
    ```

- Install Node.js dependencies: `npm install`

- Make a copy the _.env\_template_ file in the root folder, call the new file _.env_,
and add your application's client ID and client secret to it:

    | Bash (macOS/Linux) | Command Prompt (Windows) |
    |--------------------|--------------------------|
    |`export FORGE_CLIENT_ID=your-client-id`<br>`export FORGE_CLIENT_SECRET=your-client-secret`|`set FORGE_CLIENT_ID=your-client-id`<br>`set FORGE_CLIENT_SECRET=your-client-secret`|

- Run the server: `npm start`

### Visual Studio Code

If you're using [Visual Studio Code](https://code.visualstudio.com), make a copy the _.env\_template_ file
in the root folder, name it _.env_, and add your Forge client ID and client secret to it.
Now, you can run and debug your application from the editor using _Run_ > _Start Debugging_ or by pressing `f5`.

### Heroku Deployment

Heroku does [support git submodules](https://devcenter.heroku.com/articles/git-submodules)
when using the standard `git push heroku <branch>` deployment, meaning that if you have
the [Heroku CLI tool](https://devcenter.heroku.com/articles/heroku-cli) installed, you can simply do:

```bash
heroku login
heroku git:remote -a name-of-your-heroku-app
heroku config:set FORGE_CLIENT_ID=your-client-id
heroku config:set FORGE_CLIENT_SECRET=your-client-secret
git push heroku master
```

> Note that other deployment options (for example, linking your Heroku app directly to a GitHub repo)
> will not work. Heroku cannot resolve the git submodules in those cases, so the deployed application
> would have no frontend assets in the _public_ subfolder. To work around that limitation, you can
> remove the submodule while keeping the files, as explained [here](https://stackoverflow.com/questions/26752481/remove-git-submodule-but-keep-files).

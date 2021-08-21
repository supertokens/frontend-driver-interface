We use [swaggerhub](https://app.swaggerhub.com/apis/supertokens/FDI) to host the API spec.

### Overview
- The api spec is written in a `.yaml` file
- When releasing a new FDI version, add the spec to swaggerhub from this repo

### Branching
- Each version has its own branch
- When making changes, create a sub-branch of the appropriate version. For example if the changes are meant to reflect in version `1.8.2` you would create a branch from `1.8` (Your final Pull Request should also target `1.8` as the base branch)
- Changes are not made to the `master` branch directly
- The master branch will be synchronised with the latest spec when a new version is release

### Making changes
When making changes to the `api_spec.yaml` file
- 1) Go to [the swagger editor](https://editor.swagger.io/)
- 2) Copy / paste the contents of the `.yaml` file into the editor, and then you should see the API docs on the right of the screen.
- 3) Make changes to the online editor and then copy / paste the content back into the `.yaml` file
- 4) Issue a PR to the appropriate branch (refer to the branching section above)
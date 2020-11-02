# discovery-sprint-guide
Playbook microsite for running discovery sprints


## Deploying a staging site to cloud.gov
> prerequisites: Cloud Foundry cli ([docs](https://docs.cloudfoundry.org/cf-cli/install-go-cli.html)) and [cloud.gov access](https://cloud.gov/docs/getting-started/accounts/)

Run these commands from the project's root directory.

1. Build the site: `JEKYLL_ENV=staging bundle exec jekyll build`
The `JEKYLL_ENV=staging` will cause a `<meta name="robots" content="noindex" />` to be added to the head and a timestamp to the bottom of the page.
1. (optional) Create a `Staticfile.auth`: `htpasswd -c Staticfile.auth <username>`
This will create a file (`Staticfile.auth`) with the basic authentication that will be applied to the deployed site.
If no basic authentication is desired, make sure `Staticfile.auth` is not present before the Deploy step.
1. Login to cloud.gov: `cf login -a api.fr.cloud.gov --sso`
1. Deploy: `cf push`


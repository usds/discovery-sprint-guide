<!-- Using 18F's as a starting point to ours; they've done a great job with their documentation, paving the way for others to follow. -->

# Discovery Sprint Guide
Playbook microsite for running discovery sprints

## Table of contents
1. [Sprint Guide](https://github.com/usds/discovery-sprint-guide/blob/main/index.md)
   1. [Preparing for a sprint](https://github.com/usds/discovery-sprint-guide/blob/main/_pages/preparing.md)
   2. [Conducting the sprint](https://github.com/usds/discovery-sprint-guide/blob/main/_pages/conducting.md)
   3. [Delivering the sprint findings](https://github.com/usds/discovery-sprint-guide/blob/main/_pages/delivering.md)
   4. [Wrapping up the sprint](https://github.com/usds/discovery-sprint-guide/blob/main/_pages/wrapping-up.md)
   5. [Running remote sprints](https://github.com/usds/discovery-sprint-guide/blob/main/_pages/remote.md)
   6. [How sprints fail](https://github.com/usds/discovery-sprint-guide/blob/main/_pages/failure.md)
   7. [Glossary and other resources](https://github.com/usds/discovery-sprint-guide/blob/main/_pages/glossary.md)
2. [Interview Guide](https://github.com/usds/discovery-sprint-guide/blob/main/_pages/interview.md)
3. [Writing Guide](https://github.com/usds/discovery-sprint-guide/blob/main/_pages/writing.md)
4. [Case Studies](https://github.com/usds/discovery-sprint-guide/blob/main/_pages/cases.md)

## Development

### Deploying a staging site to cloud.gov
> prerequisites: Cloud Foundry cli ([docs](https://docs.cloudfoundry.org/cf-cli/install-go-cli.html)) and [cloud.gov access](https://cloud.gov/docs/getting-started/accounts/)

Run these commands from the project's root directory.

1. Build the site: `JEKYLL_ENV=staging bundle exec jekyll build`   
The `JEKYLL_ENV=staging` will cause the index.html to have a `<meta name="robots" content="noindex" />` in the head and a timestamp at the bottom.
1. (optional) Create a login for the deployed site: `htpasswd -c Staticfile.auth <username>`   
This will create a file (`Staticfile.auth`) with the basic authentication that will be applied to the deployed site.
If no basic authentication is desired, make sure `Staticfile.auth` is not present before the Deploy step.
1. Login to cloud.gov: `cf login -a api.fr.cloud.gov --sso`
1. Deploy: `cf push`

## Contributors / Acknowledgments
The first version of this public guide was authored by Jenn Noinaj and Kat Jurick and is based on a previously written guide internal to USDS, written in collaboration with GSA by co-editors Kara DeFrias and Kathy Pham with contributions from Eric Benson, Matt Collier, Evan Cook, Lisa Gelobter, Ginny Hunt, Brian Lefler, Jeff Maher, Erie Meyer, David Nesting, Chuck Rossi, Kim Rachmeler, Mollie Ruskin, Jess Teal, Albert Wong, and Charles Worthington.

We would like to thank the following folks for their feedback, edits and support: Kathy Pham, Mark Lerner, David Nesting, Chris Given, Hank Knaack, Shannon Sartin, Eddie Hartwig, Jeff Barrett, Shelly Smith, Drew Gardner and Lisa Chung from USDS, as well as Melissa Braxton and Julie Strothman from GSA for their timely advice. Thank you!


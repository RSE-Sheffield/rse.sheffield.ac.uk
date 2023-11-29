# rse.sheffield.ac.uk

GH pages repositories can only serve content to a single subdomain.

This repository enables the RSE website [RSE-Sheffield/RSE-Sheffield.github.io](https://github.com/RSE-Sheffield/RSE-Sheffield.github.io) to be served at both [rse.shef.ac.uk](https://rse.shef.ac.uk) **and** [rse.sheffield.ac.uk](https://rse.sheffield.ac.uk).

The CI workflow `.github/workflows/mirror.yaml` clones [RSE-Sheffield/RSE-Sheffield.github.io](https://github.com/RSE-Sheffield/RSE-Sheffield.github.io), builds the gh-pages gem and and deploys the website to github pages, in this case pointed at `rse.sheffield.ac.uk`, while the website repository deploys to `rse.shef.ac.uk`.

Deployment is triggered by a workflow_dispatch event from the `publish.yaml` workflow in [RSE-Sheffield/RSE-Sheffield.github.io](https://github.com/RSE-Sheffield/RSE-Sheffield.github.io), when a valid PAT exists.
It can also be triggered by pushes to `master` on this repository, or by an authorised user manually triggering the workflow via a `workflow_dispatch`.

## GitHub settings

The following settings must be set on the repository

+ Enable Github pages, with `GitHub Actions` as the source.
+ Set the `custom domain` to `rse.sheffield.ac.uk`
+ Wait up to 24 hours, then enable `Enforce HTTPS`

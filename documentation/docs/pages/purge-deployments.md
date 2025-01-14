# Purge Pages Deployments

**Required API Permissions**:

- _Account:Cloudflare Pages:Edit_

The purpose of this program is to offer a quick way to bulk remove all Cloudflare Pages deployments for a project.
If you want to remove deployments for a specific branch, check out the [prune deployments](prune-deployments.md) command.

## Running

You need to pass the following flags to run this program:

- `--api-token`: Your API token with the required permissions.
- `--account-id`: Your account ID where the pages project is located.
- `--project-name`: The name of the pages project.

Optional flags:

- `--dry-run`: If you want to see what would be deleted without actually deleting anything.
- `--delete-project`: If you want to delete the Pages project after deleting all deployments. It will delete the project even if there are deployments left.
- `--lots-of-deployments`: If you have more than 20,000 deployments, this will slow down the rate of listing deployments.

Example: 
```shell
cloudflare-utils --api-token <API Token with Pages:Edit> --account-id <account ID> purge-deployments --project-name <project name>
```

???+ warning

    I have only tested this with a project with 20,000 deployments. While doing so, it was able to delete all deployments even though there were some errors.
    It will take a while to run with a lot of deployments so be patient.
    
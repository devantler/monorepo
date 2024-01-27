# [monorepo-name]

Describe the monorepo here...

## Getting Started

This is a monorepo and it relies on Git submodules to include code from other repositories in the department. Therefore, after cloning the repo, you need to run the following command:

```bash
git submodule update --init --recursive
```

Alternatively you can clone the monorepo with the `--recurse-submodules` flag:

```bash
git clone --recurse-submodules git@github.com:energinet-digitalisering/[department-name].git
```

Make sure that all submodules are checked out on the correct branch the first time you clone the monorepo. Otherwise, you might risk loosing changes as the submodule will be in a detached head state.

> [!NOTE]
> Submodules are configured to clone with SSH, so it requires adding your public SSH key to DevOps and GitHub, respectively. You will not be able to clone the submodules with HTTPS. This decision was made, as HTTPS will require authentication on every request, where as SSH can do this automatically when the public key is shared.

### Adding a submodule

```sh
git submodule add -b <branch> <ssh-url> <path>
```

### Updating a submodule

Dependabot will create PRs for submodule updates daily. If you want to update a submodule manually, you just need to commit the change to the submodule and push it to the remote.

If the submodule has a nested submodule, you must update the nested submodule first, then commit and push the change to the remote. After that you can update the parent submodule.

## Overview

<!-- readme-tree start -->
```
.
├── .github
│   └── workflows
└── .vscode

3 directories
```
<!-- readme-tree end -->

## Contribution

To contribute to the monorepo issues and pull requests should be created in the respective repository where the change is being made. If the change is cross-cutting, then issues and pull requests should be created for each change required in the respective repositories.

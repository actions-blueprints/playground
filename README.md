# GitHub Actions Blueprints

## One worlflow out of N versions is automatically triggered
Using `.github/ci-config.yml` to configure a centrally managed, mandatory CI workflow. The config file allows the project to select a flavor of the workflow, but it needs to be one of the several centrally managed ones.
The workflow is automatically called, there is no option to embed it in the project's workflow.

Exemple of a `.github/ci-config.yml` file:

```yaml
central-ci:
  flavour: vanilla
```

![image](https://github.com/user-attachments/assets/67e6f3f3-80ad-4c0a-9ea1-55a44cecfbf0)

The manadatory workflow's entry point lives in `central-cy.yml` in `actions-blueprints/central-worflows` and is made mandatory thanks to a branch ruleset defined at the organisation level. 

![image](https://github.com/user-attachments/assets/716ff7db-4cd5-411c-988f-d01f704419b7)

## A workflow has to be called by a local workflow

The ruleset requires a reusable workflow to be called by a local workflow. The reusable workflow is defined in the central repository and is called by the local workflow in the project repository.

![image](https://github.com/user-attachments/assets/427c7627-dff3-42f1-ab75-9dd13218daa8)

```yaml
jobs:
  build:
    name: Central CI Build
    uses: actions-blueprints/central-workflows/.github/workflows/reusable-strawberry.yml@main
```

![image](https://github.com/user-attachments/assets/edd29fc0-81cd-4b07-a370-7cff50ad544a)

no config

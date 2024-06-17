# actions playground

Using `.github/ci-config.yml` to configure a centrally managed, mandatory CI workflow. The config file allows the project to select a flavor of the workflow, but it needs to be one of the several centrally managed ones.

Exemple of a `.github/ci-config.yml` file:

```yaml
central-ci:
  flavour: vanilla
```



Place a screenshot of the Actions tab
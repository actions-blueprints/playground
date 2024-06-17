# actions playground

Using `.github/ci-config.yml` to configure a centrally managed, mandatory CI workflow. The config file allows the project to select a flavor of the workflow, but it needs to be one of the several centrally managed ones.

Exemple of a `.github/ci-config.yml` file:

```yaml
central-ci:
  flavour: vanilla
```

![image](https://github.com/user-attachments/assets/67e6f3f3-80ad-4c0a-9ea1-55a44cecfbf0)
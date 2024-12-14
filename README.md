# pyphd


# Development

For development, I use a few GitHub actions to automate a few things. Here follows short description of each of these workflows:
- Reusable worflows
  * ~test-install.yml~
    - test install on various Python versions (by default 3.10-3.12)
    - ruff linting checks (stop build if error occurs)
    - unit tests with pytest
    - upload test results (for prosperity)
  * ~build-package.yml~
    - build package for Python version 3.x
    - upload package dist artifacts (by name)
  * ~github-release.yml~
    - download package dist artifact (by name)
    - sign package dist with Sigstore
    - create and upload GitHub release  
- Workflows with various triggers:
  * ~on_branches.yml~
    - triggers on commit to any branch (except ~main~)
    - runs ~test-install~ and ~build-package~

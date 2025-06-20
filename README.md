<p align="center">
  <img src="https://www.snaplogic.com/wp-content/uploads/2024/11/Agent-Creator-product-logo.webp" alt="SnapLogic Logo" width="676" style="vertical-align:middle;margin:10px 10px">
</p>

<p align="center">The <a href="https://snaplogic.github.io/agentcreator-docs">AgentCreator Experimental (Beta)</a> provides a path of Beta features developed by the <a href="https://www.snaplogic.com/products/agent-creator">SnapLogic AgentCreator</a> team for customers to get a preview of new functionality.</p>

# Running Locally

### Prerequisites

You're going to need:

 - **Linux or macOS** — Windows may work, but is unsupported.
 - **Python 3**

### Getting Set Up

1. Fork this repository on Github. (SnapLogic employees can skip this step.)
2. Clone *your forked repository* (not our original one) to your hard drive with `git clone https://github.com/YOURUSERNAME/agentcreator-docs.git`
3. `cd agentcreator-docs`
4. Create a virtual environment and install the requirements as required
5. `pip install -r requirements.txt`

```shell
# with python (and a virtual environment with mkdocs and all requirements installed) you can serve the contents from the root folder by running
mkdocs serve
```

You can now see the docs at http://localhost:8080 and they live-update based on changes made

### Deploying
If you need to manually deploy the docs, you can (with the same setup to see above) simply run the following.
```shell
# with python (and virtual environment with mkdocs and all requirements installed) you can deploy the contents from the root folder by running
mkdocs gh-deploy
```
A GitHub action will automatically deploy this to the repo already, so there shouldn't be a need to deploy manually once the items are merged to the `main` branch.
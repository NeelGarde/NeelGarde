https://neelgarde.github.io/NeelGarde
## Tips if the template does not initially publish/update correctly:
If, after checking these [settings](https://embedded-systems-design.github.io/fork-report-website/#settings-to-check/), you often find that renaming the workflow file initiates builds (for whatever reason).

Either on your computer or on the GitHub website,
1. Navigate to the files of your repository in the .github/workflows/.
1. Rename **pages.yml** to something else (**main.yml** worked for me).
1 Stage, commit, and push your files.
1. Check the "actions" tab (found in your repository's main GitHub page) to see that your commit is triggering the **"mkdocs-build"** action.
A video detailing the steps to check your build process can be viewed [here.](https://www.youtube.com/watch?v=8EgFkG2HHxM/) 


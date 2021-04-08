# Mini_man_pages
*Simplified man pages, stripped of bells and whistles*

---

Please [use Pull Requests](https://opensource.com/article/19/7/create-pull-request-github) to make changes:

* Fork this repository to your own account
* Clone your fork locally
  ```bash
  cd ~/your/chosen/parent/directory # <= use your own directory path
  git clone git@github.com:<your_username>/Mini_man_pages.git
  ```
  (Note: replace `your_username` with your own GitHub username.

* `cd` into the local directory:
  ```bash
  cd Mini_man_pages
  ```
* Create a new branch
  ```bash
  git checkout -b changes # << you can use your own branch name, if you wish
  ```
* Create a remote named "upstream" which references this repository:
  ```
  git remote add upstream git@github.com:FbW-E04-1/Mini_man_pages.git
  ```
* Make your changes in your new branch
* Commit your changes and push them to your fork:
  ```bash
  git add .
  git commit -m "<Description of your changes>"
  git push origin changes
  ```
* Visit your repository in your browser. You should now see a Compare & Pull Request button. Click on that and type a message explaining the changes that you propose.
* Click on Create Pull Request
---
After a collaborator has reviewed your proposed changes, they can merge them to the `main` branch of this repository. To see the updated version of the upstream repository in your local repository you will need to [pull the upstream changes](https://bioconductor.org/developers/how-to/git/pull-upstream-changes/):

```bash
git checkout main       # make sure you are on the main branch
git fetch upstream      # fetch the updated content
git merge upstream/main # merge the update into the main branch of your fork, locally
git push origin main    # push the updates to your online repository

git checkout changes    ### make sure that you are on your custom branch ###
git merge main/changes  # Now you are ready to make more changes
```

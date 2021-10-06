# Acquia CMS
This is sample repository having acquia_cms starter code to deploy on Acquia environment.

# Steps to Deploy code
1. [Login](https://cloud.acquia.com/) into your Acquia Cloud account.
2. Navigate to your **Organization** -> **Application**.
3. Click on the **Actions** button appearing at the top right side and then click on **View Git Information** as shown below.
![Git Information](https://i.imgur.com/jU4oR8N.png)
4. Copy that git repo url and update [blt/bly.yml](https://github.com/vishalkhode1/acquia-cms/blob/main/blt/blt.yml) file. Ex:
```
git:
  default_branch: master
  remotes:
    cloud: '<add_your_repo_url_here>'
```
5. Run the following commands to deploy code to Acquia:
```
git add blt/bly.yml
git commit -m "CHANGEME-2: BLT file updated."
composer install
blt artifact:build
blt artifact:deploy --commit-msg "BLT-000: Deploying code to develop branch." --branch "develop-build" --no-interaction
```
6. Now in Acquia cloud, navigage to **Organization** -> **Application** -> **Environment** where you need to deploy code. Ex:
![Switch Branch](https://i.imgur.com/RNuY5c4.png)
7. Now filter branch with name `develop-build` and click **Continue** button.

## Deploy a static website with Heroku

Heroku makes deployment easy by not letting you worry too much about what's going on on the server. With a couple of commands you can put your project online. Heroku enables you to deploy all kinds of projects, for example with NodeJs, React and MongoDB. The websites we made so far do not include these technologies. They consist out of plain HTML, CSS and javascript instead. Another term for such websites is "static websites". (In case you do want deploy a NodeJs project, you've to use another 'buildpack')

Heroku depends on git. First you've to commit your project on your machine as you would do normally. Afterwards you let Heroku create a domain and a seperate Heroku git repository using a couple of commands we'll demonstrate. Finally you push your code to the Heroku repository and Heroku takes it from there!

### Create an account and install Heroku
Before we can get started you've to [create a Heroku account](https://signup.heroku.com/login?redirect-url=https%3A%2F%2Fid.heroku.com%2Foauth%2Fauthorize%3Fclient_id%3D1e7d4c52-6008-4a73-b132-09abb5d04859%26response_type%3Dcode%26scope%3Dglobal%252Cplatform%26state%3DSFMyNTY.g3QAAAACZAAEZGF0YW0AAAAxaHR0cHM6Ly9kYXNoYm9hcmQuaGVyb2t1LmNvbS9hdXRoL2hlcm9rdS9jYWxsYmFja2QABnNpZ25lZG4GAFfaM_NmAQ.zbhKmh0-YC0M_rzmlb4lN8z4DAJ_E7t57PGgD4oXwVM). You also have to [install Heroku.](https://devcenter.heroku.com/articles/heroku-cli#download-and-install).

### Create an account and install Heroku
Before we can get started you've to [create a Heroku account](https://signup.heroku.com/login?redirect-url=https%3A%2F%2Fid.heroku.com%2Foauth%2Fauthorize%3Fclient_id%3D1e7d4c52-6008-4a73-b132-09abb5d04859%26response_type%3Dcode%26scope%3Dglobal%252Cplatform%26state%3DSFMyNTY.g3QAAAACZAAEZGF0YW0AAAAxaHR0cHM6Ly9kYXNoYm9hcmQuaGVyb2t1LmNvbS9hdXRoL2hlcm9rdS9jYWxsYmFja2QABnNpZ25lZG4GAFfaM_NmAQ.zbhKmh0-YC0M_rzmlb4lN8z4DAJ_E7t57PGgD4oXwVM) and [install.](https://devcenter.heroku.com/articles/heroku-cli#download-and-install) it on your computer.

### Step 1
Did you install Heroku and create an account? Sweeeet, now we can get started. This type of project (static website) requires you to create a `static.json` file in the root directory of your project. In this file you can configure a lot of things, but for now we're only going to let Heroku know, that the root directory is in fact the root directory:
```
{
    "root": "./"
}
```
You do not really have to understand why you have to state the obvious. Just make sure you put this json file in the root directory of your project and you call it `static.json`.

### Step 2
First of all, create your local git repository and commit your project. This shouldn't look unfamiliar:

```
 git init
 git add *
 git commit -m "very nice, I like"
```
### Step 3
Now the Heroku magic can begin
```
heroku login
heroku create nameOfApp -buildpack https://github.com/heroku/heroku-buildpack-static.git
```
Heroku should output two links. The first one is your domain where your app is hosted. The second one is the Heroku git repository where you have to push your code to. This is the final step.

### Final step

```
git push theHerokuGitRepositoryFromStep3 master
```
Now you can go to the domain of Step 3. In case you lost the link, you can look it up on the Heroku platform.

Hail to the deployed website! :metal:
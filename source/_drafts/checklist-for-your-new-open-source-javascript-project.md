title: Checklist for your new open-source JavaScript Project
tags:
  - open-source
  - javascript

---

![Open-source JavaScript](http://i.imgur.com/fIeyz2I.png)

In this post, I'll synthesize the main lessons passed by [Kent C. Dodds](https://twitter.com/kentcdodds) in his series "How to Write an Open Source JavaScript Library". Check his course on [egghead.io](https://egghead.io/series/how-to-write-an-open-source-javascript-library). 

After watching that (**excellent**) course, you can use this checklist to quickly refresh your mind and remember each step that you need to do in order to create your next open-source project.

## Checklist

- **Prefer to write a micro-library**. Benefits:
  - More easy to reason about
  - More easy to test
  - More easy to reuse

- **Create a repository for your libray**:
  - Go to your git repository hosting service (here we'll use [GitHub](https://github.com/))
  - Create a new repository
  - Create a README file
  - Clone your repository to your local machine
    ```shell
    git clone git@github.com:YOUR_USER_NAME/YOUR_REPOSITORY_NAME
    ```

- **Ensure that you have [Node.js](https://nodejs.org) installed**.

- **Set NPM properties**:
  ```shell
  npm set init-author-name 'Your name'
  npm set init-author-email 'Your email'
  npm set init-author-url 'http://yourdomain.com'
  npm set init-license 'MIT'
  ```

- **Save modules with an exactly version**:
  ```shell
  npm set save-exact true
  ```

- **Login with your NPM account on terminal**:
  ```shell
  npm adduser
  Username: YOUR_USER_NAME
  Password: YOUR_PASSWORD
  Email: YOUR_EMAIL@domain.com
  ```
  
- **Create a `package.json`**:
  ```shell
  npm init
  ```

- **Create the main file**:
  - Create the `src/index.js` file that will expose all the module's functionalities.
  ```js
  module.exports = {
    funcOne: funcOne,
    funcTwo: funcTwo
  };
  ```

- **PROTIPs**:
  - Install and save modules: `npm i -S module-name` is equal to `npm install --save module-name`
  - Install and save dependency modules: `npm i -D module-name` is equal to `npm install --save-dev module-name`

- **Add a .gitignore file**

- **Push your changes to GitHub**

- **Publish to NPM**: `npm publish`

- **Releasing a version to GitHub**
  ```sh
  git tag 1.0.0
  git push --tags
  ```
  - Go to *releases* on GitHub
  - Draft a new release

- **Releasing a new version to NPM**:
  - Based on the type of change that you did in your code, you should bump the version of your module.
  - Use [Semantic Versioning](http://semver.org/) to bump the version correctly
  - Commit the code `git add` & `git commit`
  - Add a new tag `git tag 1.1.0`
  - Push to GH (GitHub) `git push`
  - Push the tags `git push --tags`
  - Republish to NPM `npm publish`
  - See if all is okay `npm info <your-module-name>`

- **Publishing a beta version**:
  - Do some stuff in your code
  - Bump the version with the sufix `-beta.0`. **Ex**: `1.3.1-beta.3`
  - Commit the code `git add` & `git commit`
  - Add a new tag `git tag 1.1.0`
  - Push to GH (GitHub) `git push`
  - Push the tags `git push --tags`
  - Publish to NPM with **--tag beta** . **Ex**: `npm publish --tag beta`
  - See if all is okay. `npm info <your-module-name>`
  - How to install a beta version: `npm install <module-name>@beta` (latest beta) or `npm install <module-name>@1.3.1-beta.3` (specific version)

- **Setting up Unit Testing with Mocha and Chai**:
  - Install mocha and chai `npm i -D mocha chai`
  - Create your test file `src/index.test.js` or `src/index.spec.js`
  - Update package.json `"test": "mocha src/index.test.js -w"`
  - Run `npm test`

- **Automating Releases with semantic-release**:
  - Install semantic-release `npm i -g semantic-release-cli`
  - Setup semantic-release `semantic-release-cli setup`
  - Setup your CI configuration file to run the tests before run semantic-release.
    - Ex: `.travis.yml`
    ```
    # some stuff here

    before_script:
      - npm prune
    script:
      - npm run test
    after_success:
      - npm run semantic-release
    ```
   
- **Writing conventional commits with commitizen**:
  - [Angular git commit guidelines](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#commit) 
  - `npm i -D commitizen cz-conventional-changelog`
    - **commitizen**: allows to write commit messages
    - **cz-conventional-changelog**: Ask questions to generate the commit
  - Add commitizen into npm scripts: 
    ```json
    "script": {
      "commit": "git-cz"
    }
    ```
  - Configure **commitizen** to use **cz-conventional-changelog**. In `package.json`, add the following property:
    ```json
    "czConfig": {
      "path": "node_modules/cz-conventional-changelog"
    }
    ```
  - **ps**: I got a problem with the version 1.1.1 and 1.1.0 of the cz-conventional-changelog, [and other people too](https://github.com/commitizen/cz-conventional-changelog/issues/6). To fix it, I installed the version **1.0.1**, and worked properly.
    ```sh
    npm install cz-conventional-changelog@1.0.1 -D
    ```
  - Using commitizen:
    - Add your changes `git add`
    - `npm run commit`
      - Choose the type of changes that you did. **Ex**: *chore*
      - Choose the scope of the change. **Ex**: *releasing*
      - Add a description. **Ex**: *Add travis config, conventional commit and semantic-release*
      - Add a longer description
      - List break changes or issues closed by this change. **Ex**: *closes #1*
  - See if everything is ok `git log`
    
    

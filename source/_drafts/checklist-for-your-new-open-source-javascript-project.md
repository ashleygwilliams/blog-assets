title: Checklist for your new open-source JavaScript Project
tags:
  - open-source
  - javascript

---

![Open-source JavaScript](http://i.imgur.com/fIeyz2I.png)

In this post, I'll synthesize the main lessons really well passed by [Kent C. Dodds](https://twitter.com/kentcdodds) in his series "How to Write an Open Source JavaScript Library". Check his course on egghead.io [here](https://egghead.io/series/how-to-write-an-open-source-javascript-library). 

After watching that (**excellent**) course, you can use this checklist to quickly refresh your mind and remember of each step you need to do in order to create your next open-source project.

## Checklist

1. **Prefer to write a micro-library**. Benefits:
  - More easy to reason about
  - More easy to test
  - More easy to reuse

1. **Create a repository for your libray**:
  - Go to your git repository hosting service (here we'll use [GitHub](https://github.com/))
  - Create a new repository
  - Create a README file
  - Clone your repository to your local machine
    ```shell
    git clone git@github.com:YOUR_USER_NAME/YOUR_REPOSITORY_NAME
    ```

1. **Ensure that you have [Node.js](https://nodejs.org) installed**.

1. **Set NPM properties**:
  ```shell
  npm set init-author-name 'Your name'
  npm set init-author-email 'Your email'
  npm set init-author-url 'http://yourdomain.com'
  npm set init-license 'MIT'
  ```

1. **Save modules with an exactly version**:
  ```shell
  npm set save-exact true
  ```

1. **Login with your NPM account on terminal**:
  ```shell
  npm adduser
  Username: YOUR_USER_NAME
  Password: YOUR_PASSWORD
  Email: YOUR_EMAIL@domain.com
  ```
  
1. **Create a `package.json`**:
  ```shell
  npm init
  ```

1. Video 4

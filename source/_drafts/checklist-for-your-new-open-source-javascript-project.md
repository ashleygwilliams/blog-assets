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

1. Create a repository for your libray:
  - Go to your git repository hosting service (here we'll use [GitHub](https://github.com/))
  - Create a new repository
  - Create a README file
  - Clone your repository to your local machine
    ```shell
    git clone git@github.com:YOUR_USER_NAME/YOUR_REPOSITORY_NAME
    ```

1. Ensure that you have node.js installed

1. Set NPM properties:
  ```shell
  npm set init-author-name 'Your name'
  npm set init-author-email 'Your email'
  npm set init-author-url 'http://yourdomain.com'
  npm set init-license 'MIT'
  ```

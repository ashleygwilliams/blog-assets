title: Getting Started with Ember 2.0
date: 2015-08-16 15:57:35
tags:
    ember
---

![Getting Started with Ember 2.0](http://i.imgur.com/cduds4J.jpg)

In this *checklist-like* article, we will create a simple blog application with Ember 2.0 and Firebase! 

Here we'll focus exclusively on the **how** to create an Ember 2.0 application.

> This article was inspired by [this](https://medium.com/@jamesfuthey/8ef1f378ee4) one. Many thanks for [James Futhey](https://medium.com/@jamesfuthey).
>
> Read the original article to understand the **Whys**.

### You can see the live application [here](https://ember-2-blog.firebaseapp.com/), and the source [here](https://github.com/ericdouglas/ember-simple-blog).

1. First you need to install [Ember-CLI](http://www.ember-cli.com/), that is the command-line interface for building Ember applications.
```
npm install -g ember-cli
```

1. (Optional) Put an alias in your .bashrc:
```
alias e='ember'
```

1. Create a new project with ember-cli: 
```
e new simple-blog
```

1. Upgrade Ember and Ember Data:
```
bower install --save ember#2.0.0
bower install --save ember-data#2.0.0-beta.1
```

1. Let's see if our upgrade was well succeed. Type on terminal:
```
e s 
```

  **ps**: This is an alias to `ember serve`

  Now go to `localhost:4200` to see your Welcome message :)

  See what changed in your application [here](https://github.com/ericdouglas/ember-simple-blog/commit/66f4beffb80caa3556ea75934abc7051094e1800).

1. Change the structure of your application layout at `app/templates/application.hbs`:
```
<header>
  <h1>EmberBlog</h1>

  <p>
    Simple blog application written with Ember 2.0 and Firebase
  </p>
</header>

{{outlet}}
```

  See what changed [here](https://github.com/ericdouglas/ember-simple-blog/commit/8a58597da5217b2ce57f430f7b37fd81e31137f4)

1. Create a Index route
```
e g route index
```

1. Add some code in `app/templates/index.hbs` to verify if everything is working correctly:
```
<h2>Index Page</h2>
```

  Go to `localhost:4200` to see if `Index Page` is beign displayed.

  See what changed [here](https://github.com/ericdouglas/ember-simple-blog/commit/8853729867f7a79ac570513edbbf86d95460d170).

1. Install the Firebase addon:
```
e install emberfire
```

1. Create a new app on your [Firebase](https://www.firebase.com) dashboard. 

1. To connect Firebase to our application, you should edit the file `config/environment.js` and add on line 8 the name of your Firebase app created in the previously step. Your `environment.js` file will looks like it:
```
module.exports = function(environment) {
  var ENV = {
    modulePrefix: 'ember-simple-blog',
    environment: environment,
    contentSecurityPolicy: { 'connect-src': "'self' https://auth.firebase.com wss://*.firebaseio.com" },
    firebase: 'https://YOUR-APP-NAME.firebaseio.com/',
    baseURL: '/',
    locationType: 'auto',
    EmberENV: {
      FEATURES: {
        // Here you can enable experimental features on an ember canary build
        // e.g. 'with-controller': true
      }
    },

    APP: {
      // Here you can pass flags/options to your application instance
      // when it is created
    }
  };
```

  See what changed [here](https://github.com/ericdouglas/ember-simple-blog/commit/9b0f79eac227cd78d9e4e068bde0646e60f00929).

1. Create a Post model:
```
e g model post title:string author:string createdDate:date text:string
```

  See what changed [here](https://github.com/ericdouglas/ember-simple-blog/commit/1c4ff25fda8d3661660dac38eba0723864fc1518).

1. Edit your Post model to be able to load Ember Data pieces independently. Your `app/models/post.js` file should looks like this:
```
import DS from 'ember-data';

let {
  Model,
  attr
} = DS;

export default Model.extend({
  title: attr('string'),
  author: attr('string'),
  createdDate: attr('date'),
  text: attr('string')
});
```

  **ps**: Here we are using a new **ES2015** feature called [Destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) :D

  See what changed [here](https://github.com/ericdouglas/ember-simple-blog/commit/97be18a66bd2140f4d6ebe8c9d1f994ece7047ab).

1. Create a `create-new-post` component that will be responsible to add new posts to our app. Here we will use the *POD* structure.
```
e g component create-new-post --pod
```

1. Edit the file `app/components/create-new-post/template.hbs` to insert the necessary elements that we need to create a new post:
```
<h3>Create a new post</h3>

<form>
  <p>
    {{input value=post.title placeholder="Post title"}}
    {{input value=post.author placeholder="Author"}}
  </p>
  <p>
    {{textarea value=post.text placeholder="Content"}}
  </p>
  <p>
    <span {{action "createPost" post}} class="btn btn-submit">Publish</span>
  </p>
</form>
```

  > **Warning!** If you read the original article, you'll notice that the logic that I implemented to create the post is different. In our future articles all of it will be thoroughly explained.

1. Let's refactor our Index template and add our component in it. Your `app/templates/index.hbs` should look like this:
```
{{create-new-post}}
```

1. Now that we have our HTML structure, let's add some style to it. Open your `app/styles/app.css` file and add the following CSS:
```
* {
  font-family: 'Roboto', sans-serif;
  box-sizing: border-box;
}

body {
  width: 80%;
  margin: 1em auto;
}

.container {
  float: left;
  width: 60%;
}

aside {
  float: left;
  width: 20%;
}

header {
  background-color: #e74c3c;
  color: #fff;
  padding: 2em;
  margin-bottom: 1em;
}

.btn {
  padding: .5em 2em;
  border-radius: 3px;
}

.btn:active {
  position: relative;
  top: 1px;
}

.btn:hover {
  cursor: pointer;
}

.btn-submit {
  background-color: #c0392b;
  color: #fff;
}
```

1. To load the `Roboto` font you will need to do two things:
  - Add the `<link>` reference to that font in your `app/index.html`.
  ```
  <link href='http://fonts.googleapis.com/css?family=Roboto' rel='stylesheet' type='text/css'>
  ```

  - Allow that your application load that font from an external resource. To do it, edit your `config/environment.js` and add the `contentSecurityPolicy` section in your file. It will look like this:
  ```
  module.exports = function(environment) {
    var ENV = {
      modulePrefix: 'ember2-blog',
      environment: environment,
      contentSecurityPolicy: { 'connect-src': "'self' https://auth.firebase.com wss://*.firebaseio.com" },
      firebase: 'https://firember2-blog.firebaseio.com/',
      baseURL: '/',
      locationType: 'auto',
      EmberENV: {
        FEATURES: {
          // Here you can enable experimental features on an ember canary build
          // e.g. 'with-controller': true
        }
      },

    APP: {
      // Here you can pass flags/options to your application instance
      // when it is created
    },

    contentSecurityPolicy: {
      'font-src': "'self' data: fonts.gstatic.com",
      'style-src': "'self' 'unsafe-inline' fonts.googleapis.com"
    }
  };
  ```

  See what changed [here](https://github.com/ericdouglas/ember-simple-blog/pull/9).

1. Add an action to our `create-new-post` component. Your `app/components/create-new-post/component.js` should look like this:
```
import Ember from 'ember';

export default Ember.Component.extend({
  actions: {
    createPost(post) {
      this.sendAction('createPost', post);
      this.set('post', {});
    }
  }
});
```

1. Refactor our Index Route to handle the `createPost` method and effectively create a post. We will also add the logic necessary to return all posts that have been created. Edit the file `app/routes/index.js`
```
import Ember from 'ember';

export default Ember.Route.extend({
  model() {
    return {
      data: this.store.findAll('post'),
      post: {}
    }
  },

  actions: {
    createPost(info) {
      let newPost = this.store.createRecord('post', {
        title: info.title,
        text: info.text,
        author: info.author,
        createdDate: new Date()
      });

      newPost.save();
    }
  }
});
```

1. Passing data to our component in Index template. Edit the file `app/templates/index.hbs`:
```
{{create-new-post post=model.post createPost="createPost"}}
```

  Now if you submit your form and look in your Firebase dashboard, you will be able to see that your post was created! Amazing! ;D

  We did a lot of things, wow! See all the commits that was done [here](https://github.com/ericdouglas/ember-simple-blog/pull/6).

1. Now that we are able to create our post, we need to show it! Let's create a component for that purpose. Run the following command:
```
e g component blog-post
```

1. Add the structure to our blog-post component. The file `app/templates/components/blog-post.hbs` should look like this:
```
<article>
  <h2>{{post.title}}</h2>
  <p>{{post.text}}</p>
  <em>(Posted on {{post.createdDate}} by {{post.author}})</em>
</article>
```

1. Let's refactor the Index template to list all articles that you have in your Firebase database. The file `app/templates/index.hbs` should now look like this:
```
<div class="container">
  {{#each model.data as |post|}}
    {{blog-post post=post}}
  {{/each}}
</div>
<aside>
  {{#create-new-post post=model.post createPost="createPost"}}{{/create-new-post}}
</aside>
```

  **Awesome**!!! Now, if you followed all the steps correctly, you should be able to see all your posts and to create new ones too!

  See what changed [here](https://github.com/ericdouglas/ember-simple-blog/pull/8).

**We are almost done!** Our application is working correctly, and now we need to deploy it. Go to [this](https://medium.com/@jamesfuthey/8ef1f378ee4) article and follow the instructions in the section "**Deploying our Application**".

### And that's it!

I hope that you enjoy to build that simple but functional application with Ember 2.0!

Cheers! =)

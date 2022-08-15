# Component Creation

## Learning Goals

-

## Introduction

We're going to create components in the order of the hierarchy we defined
earlier, starting with the level 1 components.

## Level 1 Components:

The level 1 components are the container for the header and the container for
the main application panel. We can create them as follows:

```
ng generate component header-component
```

and

```
ng generate component application-component
```

> Remember that `ng generate component` can be shortened to `ng g c`, which is
> what we'll use from now on

Generating both components with the CLI now gives us the following folders and
files in our main app folder:

![Files for Level 1 Components](https://curriculum-content.s3.amazonaws.com/java-mod-8/ng-messaging-components-level-1.png)

We can now add these components to our `app.components.html` file with their
default selectors assigned by the CLI:

```html
<app-header-component></app-header-component>

<app-application-component></app-application-component>
```

This gives us the following view:

![The Level 1 components in the default view](https://curriculum-content.s3.amazonaws.com/java-mod-8/ng-messaging-level-1-comps-view.png)

Let's now apply our Bootstrap layout knowledge to make this view match our
target view a little better:

1. Inside `app.component.html`, we create two containers, one for the header and
   one for the application
2. Then we give each container the entire width of the view and put each
   component in its corresponding container

Our `app.component.html` file now looks like this:

```html
<div class="container">
  <div class="row">
    <div class="col-12 border p-3">
      <app-header-component></app-header-component>
    </div>
  </div>
</div>

<div class="container">
  <div class="row">
    <div class="col-12 border p-3">
      <app-application-component></app-application-component>
    </div>
  </div>
</div>
```

> As we start creating components at a lower level, note that the parent
> component, in this case our "app component" is the one that controls how the
> child components are laid out. The child components then control their own
> layout, including how their own children are laid out.

Here is what our application looks like now:

![The Level 1 components in their proper layout](https://curriculum-content.s3.amazonaws.com/java-mod-8/ng-messaging-level-1-comps-view-layout.png)

## Level 2 Components

Our level 2 components are:

1. The conversation control panel
2. The contact list
3. The conversation history

All 3 of these components are children of the application component, so let's
create them as follows:

```
ng g c application-component/conversation-control-component
```

and

```
ng g c application-component/contact-list-component
```

and

```
ng g c application-component/conversation-history-component
```

![Files for Level 2 Components](https://curriculum-content.s3.amazonaws.com/java-mod-8/ng-messaging-components-level-2.png)

We can now add these new components to the application component view in
`application-component.component.html`:

```html
<p>application-component works!</p>

<app-conversation-control-component></app-conversation-control-component>
<app-contact-list-component></app-contact-list-component>
<app-conversation-history-component></app-conversation-history-component>
```

> Go ahead and remove the "application-component works" text, which was just
> there for the initial validation

As we consider applying bootstrap layout to this component like we did the
previous component, you will notice that both the contact list and the
conversation history components are meant to occupy the same space. We will
learn how to deal with the navigation between components later - for now, let's
just put both those components on top of one another:

```html
<div class="container">
  <div class="row">
    <div class="col-12 border p-3">
      <app-conversation-control-component></app-conversation-control-component>
    </div>
  </div>
</div>

<div class="container">
  <div class="row">
    <div class="col-12 border p-3">
      <app-conversation-history-component></app-conversation-history-component>
    </div>
  </div>
</div>

<div class="container">
  <div class="row">
    <div class="col-12 border p-3">
      <app-contact-list-component></app-contact-list-component>
    </div>
  </div>
</div>
```

Here is our updated UI:

![The Level 2 components in their proper layout](https://curriculum-content.s3.amazonaws.com/java-mod-8/ng-messaging-level-2-comps-view-layout.png)

## Level 3 and Level 4 Components

Now that we've done level 1 and level 2 components, let's do level 3 and 4 at
the same time. The components are:

1. Level 3:
   1. Inside the conversation history panel:
      1. The conversation thread panel
      2. The new message panel
   2. Inside the contact list panel:
      1. Each contact in the contact list
2. Level 4:
   1. Inside the conversation thread panel:
      1. Each message from a sender other than the current user
      2. Each message from the current user

We create those components inside their parent components, as follows:

```
ng g c application-component/conversation-history-component/conversation-thread-component
```

and

```
ng g c application-component/conversation-history-component/send-message-component
```

and

```
ng g c application-component/contact-list-component/contact-component
```

and

```
ng g c application-component/conversation-history-component/conversation-thread-component/sender-message-component
```

and

```
ng g c application-component/conversation-history-component/conversation-thread-component/user-message-component
```

You should now have a file structure with all the levels of components reflected
and with a hierarchy that matches the hierarchy in the last diagram above:

![Files for Level 3 and Level 4 Components](https://curriculum-content.s3.amazonaws.com/java-mod-8/ng-message-components-level-3-and-4.png)

# ![React Router - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to explain what React Router is and why it is useful

## Description

Single Page Applications have many advantages over older multi-page server-side-rendered applications from the perspective of user experience.  There are some drawbacks, though.  Because everything is experienced in a single page with a single URL, some basic uses of the browser won't initially work.  Here are some examples:

- You can't bookmark anything because there is only one URL.  You could bookmark the root of the app, but you'd need to repeat a set of steps each time you wanted to go to a certain location
- Similarly, you can't send URL's to other people.  Just like with bookmarks, if there's only one URL, you'd have to include instructions on how get from the home page of the app to a specific location along with the URL itself
- `<a>` tags, the basic building block of the web, don't work anymore.  Again, if there's only one URL for the app, you can't link between specific sub sections of an application.

React itself doesn't do anything to help with this, but fortunately a third party package called React Router allows Single Page Applications to mimic the feel of multi-page applications by allowing develoeprs to generate URLs and links for different aspects of their SPA's.  You'll have all the advantages of a Single Page Application without the drawbacks!
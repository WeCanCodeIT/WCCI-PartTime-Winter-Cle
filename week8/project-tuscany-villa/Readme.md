# Tuscany Villa
## Due:Monday March 27 at 5:30pm
### [Submission Link](https://goo.gl/forms/3BQOC4eRJurdMGtp1)

## Overview
Given some mockups from a designer create a close approximation of a website. Utilize HTML, CSS, and Bootstrap to replicate the responsive site.

## Skills Required
- HTML
- CSS
- Bootstrap

## Tasks
- [ ] Elements
  - [ ] Header
    - Make sure the title is centered
  - [ ] Navbar
    - Include 3 "links".  These don't have to be live links but they must appear to be actual links. 
  - [ ] Large box
    - Photo background
    - Text centered in the box with a translucent background
  - [ ] Map box
    - Map background
    - Text centered in the box with a white background
  - [ ] Small boxes (12)
    - [ ] White text boxes (4)
      - White background with text
    - [ ] Photo background (3: Weddings, Friends, Family)
      - Photo background
      - Text centered in the box with a translucent background
    - [ ] Photo background (3: Sample Villas)
      - Photo background
      - Text centered and placed at bottom of the box
      - Multiple color backgrounds for text
      - Include accomodation details about the villa
    - [ ] Misc (2: Reviews, Seen On)
      - Review box: Color background with "Ratings" text
      - Seen On: image
  - [ ] Footer
    - [ ] Company info text
    - [ ] Social media icons (Look up Glyphicons)
- [ ] Is the site responsive?
  - [ ] Use existing bootstrap classes to develop the mobile version first
  - [ ] Address `xs`, `sm`, `md`, and `lg` sizes as shown in the mockups


## Details
You are working as a front-end developer at a marketing agency. The design team has created a new layout for a client's web site. Their previous website was done several years back, and was not responsive. Not only do they want an attractive site featuring homes, but they want to ensure it is usable on all screen sizes.

Below, find the mockups from the design team. They have given us a good amount to work with.

To get the colors right, either choose an online color picker, or download a program (like Gimp) that allows you to choose colors from a picture and tells you their hex values.

The designers didn't specify fonts for us, but want us to get as close as we can to their design images. They want to use free fonts, so you thought you could help the team save money by using Google Fonts.

https://www.google.com/fonts

You are pretty sure these can be included on web pages pretty easily. Also, they are open source / free to use, plus since many sites use Google fonts, some users may already have these cached on their computers, making the page ultimately faster to load than if using a completely custom font.

![animated version](responsiveanim.gif)

![responsive screenshot](responsive1.png)

![multiple layout sizes](responsive2.jpg)


## Stretch Tasks
Once you've got the basic layout implemented and responsive, it's time to add some pizzazz. Experiment using different CSS techniques to accentuate boxes when the mouse is over them, and/or look into using transitions to make them smoothly animated!

- [ ] Explore using `:hover` and CSS transitions to make the site more dynamic
- [ ] After you have finished the homepage you can try expanding your design and creating other pages linked from the homepage
- [ ] Experiment using additional Bootstrap components that we haven't explored in class

## Hints
Work Priority: Structure, Responsive, Styling!!

Start with the **structure**. Before getting too caught up in getting everything pixel perfect, look at how the layout is going to fit into Bootstrap's grid system, and determine what class(es) you need to use to get it there for the different screen sizes. Finally, create your own custon CSS to try to match the styling of the mockups.

Use [semantic elements](http://www.w3schools.com/html/html5_semantic_elements.asp) where appropriate

Check out the [Bootstrap components](http://getbootstrap.com/components/) list for ideas of things to simply drop into your HTML, along with the [Bootstrap CSS](http://getbootstrap.com/css/) for some more examples of how to use the grid system.

Remember to use the bootstrap class ```img-responsive``` on your ```<img/>``` elements if you would like them to be responsive.
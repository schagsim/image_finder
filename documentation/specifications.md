# Image Finder User Study Specifications

## Completion requirements

Prepare a web service where users undergo a test where they are sequentially presented images and are asked to find that images in galleries of images.
There are two main goals of this project

1) Learn about user-experience and user interaction with software so the users stay engaged while visiting the web
2) Provide a platform which collects data from the study so it can be used for some scientific conclusions

The test will measure certain properties, amongst them

* time to answer
* correctness of the answer
* amount of scrolling through the gallery
* which type of gallery display is better
* which type of gallery sorter is better
* etc.

The solver needs investigate how to provide the best possible user experience so the users are engaged by the user study and do not leave in the middle of the tests.

The solver needs to prepare different types of sorting of the images in the gallery.
The examples of these diffrerent sorters are sorting by

* color histograms of the images
* google label relevancy
* semantic vectors obtained by analyzing the images by a neural network

The solver should use a very simple machine-learning mechanism which dynamically changes the test according to the user input.
This will only affect a few parameters (number of images presented in the gallery, width of the gallery, etc.).
The machine-learning used should be as simple as possible so we can explain the decisions of this mechanism to the user when displaying a new gallery.

## Example of the typical use-case

1) User enters the Image Finder User Study
2) The user is presented info about the nature of the study and by pressing "Start", the user will be then taken into the test
3) The user is presented an image and is asked to remember the image
4) In the next page, a gallery of images is displayed and the user is asked to find the presented image
5) The user searches and either clicks the image in the gallery or provides an info it is not present
6) Repeat 3) to 5) for N times
7) Present the results of the test for the last sequence (comparison with other people, correctness, etc)
8) Ask the user to continue to the next sequence of images and inform them how the parameters of the test are going to change and why
9) Go to 3) and repeat

There might be some nuances in this typical use-case, however, the idea will remain the same.

## Added value

We need to obtain a certain amount of relevant data from the users navigating through the user study.

For that, we need the web application to be very interactive so the users stay and finish the tests we give them.

This will be achieved by

* dynamically changing the parameters of the output displayed to the user
* manually (admin-side) changing the parameters of the web application to test theories
* changing the parameters of the test by learning from the user and either
  * setting the displayed test to help the user be faster
  * setting the displayed test to make the life harder for the user
* informing users why they are receiving the specific output
* displaying the results of the tests and comparing them to other users

The idea is that by using a simple machine learning principles, this web can show how such an addition can improve the web-user interaction by providing this simple info to the user why the software makes these decisions based on the user behavior.

A very important aspect of this user experience will be providing information as to why we are displaying a specific output.
This will probably be the most tricky part since if we use machine-learning in some parts of the tests, it might be difficult to know why the ML blackbox decided to change the parameters the way it did.

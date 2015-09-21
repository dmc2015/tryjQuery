Buzz Words
Ajax traversal manipulation
Event handling
Document Object Model - a tree like structure created by browsers so we can quickly find HTML Elements using javascript. Inside the DOM, HTML elements become nodes which have relationships with one another.

Facts
It is best to require jQuery before the end of the closing body tag

Ways in which you can use jQuery?

find elements in the html document
change html content
listen to what the user does and react
animating content on the page
talking over the network to fetch new content without re-rendering the entire page

Why we use jQuery and not Javascript to interact with the DOM?
Browsers treat the DOM differently, have a slightly differently DOM interface.  jQuery allows  us to interact with the DOM in a standard fashion that is not browser based.

Examples of jQuery?

Find
jQuery(“h1”); or $(“h1”);

jquery.(“h1”) .text();
(gets the inner text of the h1)

Change

jquery.(“h1”) .text(“Where will you got");
(sets the inner text of the h1)

How do we instantiate jQuery?

jquery(document)

or

$(jquery)

How do we select all of one element of with jQuery?

$(“li");
(selects all of the li’s on the page)

$(“li”).text(“Orlando");
(changes all of the li’s on the page)

How do we select specific id’s or classes to avoid situations where you would select all elements?

$(‘#container’).text(’new container data’);
(this will change text in the element with a id of container)

$(‘.classContainer’).text(’new container data’);
(this will change the text in the class classContainer)

Chapter 2

Descendant Selector - allows you to select all children of a element

$(“.destination li”);
(this will select all li’s that are descendant of the destination class)

$('#destination ul li');
(this will select all li’s that are descendant of the destination id and ul element)

Child Selector - allows you to select only direct children of a element

$(‘#destination > li’);
(this will select li’s that are direct children of the destination id)

 Select Multiple Elements with Jquery
$(‘.promo, #france’);
(This will select the class promo and the id france)

Select first element of a selection
$(‘#destination li:first’);
(This selector will select the first li of the destination id with a pseudo-class)

Common Examples of this:
$(‘#destination li:first’);
$(‘#destination li:last’);
$(‘#destination li:odd’);
$(‘#destination li:even’);

Traversing
Traversing can be a faster way of navigating through elements on the DOM with filters/methods.

$(‘#destination’).find(‘li’);

find requires a argument of a element

When you traverse the selection has two parts, the ‘selection’ (#destination)
&
The traversal .find(‘li’);

This takes more code but programmatically it is executed faster

Examples of Traversal

$(‘li’).first();
$(‘li’).last();
$(‘li’).middle();
$(‘li’).odd();
$(‘li’).even();

Walking the DOM - a way of getting to a middle element, navigating through the DOM using traversal

$(‘li’).first().next();
(selects the first list item and then the next one)

Walking the dom involves method chaining, combining multiple methods for DOM navigation

$(‘li’).first().next().prev();
(selects the first list item, then the next and then the previous. essentially selecting the first element)

 $("li").first();
(selects the first li)

Walking the DOM - Traverse UP selecting the parent of an element

$(‘li’).first().parent();
(selects the first element and then the parent of that element)

 $(".featured").parent();
(selects the parent of the featured class)

Walking the DOM - Traverse Down selecting the child of an element

$(‘#destination’).children(‘li’);
(children, unlike find, does not select all of the li’s. find would of selected all li’s that are children of #destination. Selects direct children of #destination)

$(‘#destination’).find(‘li’);
(selects all of the li child elements of #destination)

Chapter 3

Appending the DOM

var price = $(‘<p>From $399.99</p>’);
(creates a variable that is capable of being inserted into the DOM with jQuery)

4 ways to append DOM

.append(<element> or variable) - places the node as the last child of the selected element
.before(<element> or variable) - places the node before the selected element

.after(<element> or variable) - places the node after the selected element

.prepend(<element> or variable) - places the node as the first child of the selected element

$(‘.vacation’).append(price);

Removing the Node
$(‘button’).remove();

4 Other Methods That Append with Different Syntax

.appendTo(<element> or variable) - price.appendTo($(‘.vacation'));

.prependTo(<element> or variable) - price.prependTo($(‘.vacation’));

.insertBefore(<element> or variable) - price.insertBefore($(‘.vacation’));

.insertAfter(<element> or variable) - price.insertAfter($(‘.vacation’));

Activate a Function on Click

$(document).ready(function()  {
  $('.book').on('click', function() {
    'code'
  });
});

Applying a Function to the Particular Element that is Clicked when there are Several of the Same Element

$(document).ready(function() {
     $(‘button’).on(‘click’, function() {
          var price = $(‘<p>From $399.99</p>’);
          $(‘.vacation’).append(price);
          $(this).remove();
     });
} );

$(this).remove();

Benefits and Negatives of Using jQuery?

It is possible that jQuery/javascript will finish loading prior to the javascript finishing loading the DOM. In this case the jquery/js will not have a DOM to run against and there will be no effect. This is remedied by putting the jQuery/js in a  ‘document.read’ function.

jQuery(document).ready(function() {
‘code'
});

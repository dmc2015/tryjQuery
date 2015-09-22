Making a Button Slide in DOM

Watch for the click event
Find the Ticket
Show the Ticket

Watch for the click event
$(‘.confirmation’).on(‘click’, ‘button', function() {
$(this).closetst
});

Find the Ticket
$(‘.confirmation’).on(‘click’, ‘button', function() {
$(this).closest(‘.confirmation’).find(‘.ticket')
});

Show the Ticket
.slideDown() - shows info
.slideUp() - hides info
.slideToggle() - goes back and forth between two states
(eliminates the need for both slideDown and slideUp usually)

$(‘.confirmation’).on(‘click’, ‘button', function() {
$(this).closest(‘.confirmation’).find(‘.ticket’).slideDown();
});

Debugging JS

var liItems = $(‘li’).length;
alert(liItems);

alert($(‘button’).length);

make sure that the function is wrapped in a ready function
or it the expression may be run prior to the DOM finishing
loading.

$(document).ready(function() {
alert($(‘img’).length);
});

jQuery Events
Mouse Events

- click
- dblclick
- focusin
- focusout
- mousedown
- mouseup
- mouseout
- mousemove
- mouseover
- mouseleave
- mouseenter - when the mouse is first positioned over the element

Keyboard Events

- keypress - combination of keyup and keydown
- keydown - when a users starts pressing a key
- keyup - when the user stops pressing a key

Form Events

- blur
- select
- focus
- change
- submit

Keeping Event Handling Dry with Functions

function showTicket() {
$(this).closest(‘.confirmation’).find(‘.ticket’).slideDown();
}

$(document).ready(function() {
$(‘.confirmation’).on(‘click’, ‘button’, showTicket);
$(‘.confirmation’).on(‘mouseover’, ‘h3’, showTicket);

});

Fun with Toggles
Toggles on and off a label, if you remove the mouse leave
it only toggles on entering.
$(document).ready(function() {

  $('#tour').on('click', 'button', function() {
    $('.photos').slideToggle();
  });

  $('.photos').on('mouseenter', 'li', function() {
    $(this).find('span').slideToggle();
  });

  $('.photos').on('mouseleave', 'li', function(){
    $(this).find('span').slideToggle();
  });

});

(the third argument of a on method is a function, even if it
is just a function name. Notice that the function does not have
parenthesis behind it, if it did it would execute immediately.)

jQuery Helper Methods for User Input
.val()
(gets the value)

.val('123')
(sets the value)

var quantity = +$(this).val();
(when getting a value you will usually want to turn it into a number otherwise it will be a string. when setting a value for the dom it can be a number or string value)

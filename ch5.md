Taming CSS

jQuery Object Methods for CSS

.css(attribute, value) - set the attribute and value

.css(attr) - get the value based on the attribute

.css(object) - send a object

Three Ways of Setting CSS Values

This sets the Border and Background Color but there are more efficient ways to do this

$(document).ready(function() {
     $(‘#vacations’).on(‘click’, ‘.vacation’, function() {
          $(this).css(‘background-color’, ‘#252b30’);
          $(this).css(‘border’, ‘1px solid #967’);
     });
});

CSS Methods Can Also Be Chained
$(this).css(‘background-color’, ‘#252b30’)
          .css(‘border’, ‘1px solid #967’);

This CSS Method Uses a Object and is More Efficient
$(this).css({‘background-color’: ‘#252b30’,
                    ‘border’: ‘1px solid #967'});

CSS Method jQuery
.show() - display is changed to block
.hide() - display is changed to hide
.toggleClass - allows you to toggle a css class on and off with a click event

Mouse Enter and Mouse Leave Example

$(document).ready(function() {
  $('.tour').on('mouseenter', function() {
    $(this).addClass('highlight');
    $(this).find('.photos').show();
  });

  $('.tour').on('mouseleave', function() {
    $(this).removeClass('highlight');
  });
});

jQuery Animate
Allows us to animate, slow transition elements on the page into a new position that would otherwise pop into place with the css method.

$(document).ready(function() {
     $(‘.vacation’).on(‘click’, function() {
          $(this).animate({’top’ : ‘-10px’});
     });
});

Animating a object up and then down if it was already animated up

$(document).ready(function() {
     $(‘#vacations).on(‘click’, ‘.vacation’, function() {
     $(this).toggleClass(‘highlighted’);

     if($(this).hasClass(‘highlighted')){
          $(this).animate({’top’ : ‘10px’});
     }
     else{
          $(this).animate({’top’ : ‘0px’}, 400); //the second argument of animate specifies the speed 400:normal 200:fast 600:slow
     }
     });
});

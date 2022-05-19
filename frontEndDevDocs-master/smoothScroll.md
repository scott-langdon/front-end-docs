# Smooth Scroll Code


```javascript
<script type="text/javascript">
$(document).ready(function(){
    // Add smooth scrolling to all links
    $("#button_that_does_the_smooth_scroll_element").on('click', function(event) {
        $('html, body').animate({
            scrollTop: $('#anchored_tag').offset().top
        }, 800)
    });
});
</script>
```

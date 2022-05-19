# Cookie Code
## Cookie Timer

```javascript
<script src="js/jquery.cookie.js"></script>
<script>
    $(document).ready(function() {
        if(!$.cookie('videoNext')){
            setTimeout(function(){
                $.cookie('videoNext', '1', {expires:7, path:'/'});
            }, 10000);
            // Price Button Timer: 20min
            delay = 60000 * 1200;
            setTimeout(function(){
                $(".buyNowButton").css("display", "block");

            }, delay);
        } else {
            $(".buyNowButton").css("display", "block");

        }
    })
</script>
```

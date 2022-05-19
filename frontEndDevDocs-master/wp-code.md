### JQuery for adding 1-Step Checkout
```javascript
jQuery(".addToCart3").attr("href", jQuery(this).find(".productLink").html() + '&bn=1&clear=1');
```
#### Example to get &mob=1 to work 

```javascript 
jQuery(document).ready(
	function(){jQuery(".product").click(function(){
		if(jQuery(document).width() < 768){
			if(!jQuery(this).hasClass('active')){
				jQuery(".product").removeClass('active');jQuery(this).addClass('active');
			}
			if(jQuery(this).hasClass("oneBtl")){
				jQuery(".oneBtl").addClass("active");
				jQuery(".cta").attr("href",jQuery(this).find(".productLink").html()  + '&mob=1&bn=1&clear=1')
			}
			if(jQuery(this).hasClass("threeBtl")){
				jQuery(".threeBtl").addClass("active");
				jQuery(".cta").attr("href",jQuery(this).find(".productLink").html() + '&mob=1&bn=1&clear=1');
			}
			if(jQuery(this).hasClass("sixBtl")){
				jQuery(".sixBtl").addClass("active");
				jQuery(".cta").attr("href",jQuery(this).find(".productLink").html() + '&mob=1&bn=1&clear=1');
			}
		} else {
			if(!jQuery(this).hasClass('active')){
				jQuery(".product").removeClass('active');jQuery(this).addClass('active');
			}
			if(jQuery(this).hasClass("oneBtl")){
				jQuery(".oneBtl").addClass("active");
				jQuery(".cta").attr("href",jQuery(this).find(".productLink").html()  + '&bn=1&clear=1')
			}
			if(jQuery(this).hasClass("threeBtl")){
				jQuery(".threeBtl").addClass("active");
				jQuery(".cta").attr("href",jQuery(this).find(".productLink").html() + '&bn=1&clear=1');
			}
			if(jQuery(this).hasClass("sixBtl")){
				jQuery(".sixBtl").addClass("active");
				jQuery(".cta").attr("href",jQuery(this).find(".productLink").html() + '&bn=1&clear=1');
			}
		}
	});
})
```

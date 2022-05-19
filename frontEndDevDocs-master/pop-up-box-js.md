

```php
    <?php
        $file="MGI5purchases.csv";
        $csv= file_get_contents($file);
		$array = array_map("str_getcsv", explode("\n", $csv));
		$purchasesJSON = json_encode($array);
    ?>
	<div class="popup-box">
	    <ul id="purchase-box"></ul>
    </div>
	<script>
		var purchases = <?php echo $purchasesJSON; ?>;
		console.log(purchases);
		function iterate(purchases) {
			for (var i = 0; i < purchases.length; i++) {
				var ul = document.getElementById("purchase-box")
				var li = document.createElement("li");
				li.appendChild(document.createTextNode(purchases[i][0] + " in " + purchases[i][1] + " bought " + purchases[i][2] + " bottle of " + "Bio Complete 3"));
				ul.appendChild(li);
			}
		}
		iterate(purchases);
	</script>
<script>
        var item = $('#purchase-box li');
		item.hide();
		
		function recentlyBought() {
			counter = 0;
			var box = document.getElementById('purchase-box');
			var boxLength = box.children.length;
			
			function recentlyBoughtItemShow(num) {
				$(box.children[num]).show().delay(9000).fadeOut();	
			}
			function animatedPopUp() {
				$('.popup-box')
					.animate({
						bottom: -200,
					}, 10, function() {
						recentlyBoughtItemShow(counter);
						counter++;
						if (counter >= boxLength) {
							counter = 0;
						}
					})
					.animate({
						bottom: 50,
					}, 1000)
					.animate({
						bottom: 50,
					}, 2000)
					.animate({
						bottom: -200,
					}, 1000, function() {
						var delay_time = (Math.floor((Math.random() * ((12 - 5) + 1) + 5)) * 1000);
						setTimeout(function() {
							animatedPopUp()
						}, delay_time)
					})
			}
			animatedPopUp();
		}
		setTimeout(function() {
			recentlyBought()
		}, 4000);
		</script>
```

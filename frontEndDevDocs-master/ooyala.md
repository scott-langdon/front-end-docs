# Ooyala CODE

#### Links & Scripts
```html
<script src="//player.ooyala.com/static/v4/stable/4.24.9/core.min.js"></script>
<script src="//player.ooyala.com/static/v4/stable/4.24.9/video-plugin/main_html5.min.js"></script>
<script src="//player.ooyala.com/static/v4/stable/4.24.9/skin-plugin/html5-skin.min.js"></script>
<link rel="stylesheet" href="//player.ooyala.com/static/v4/stable/4.24.9/skin-plugin/html5-skin.min.css" />
```

#### Basic Version
```javascript
var playerParam = {
	autoplay: true,
	pcode: "xvYWgyOgX8LlAER8dMPTua1yO938",
	playerBrandingId: "38dd44cdbeca4132a08badd1e565fab6",
	skin: {
		config: '../otc_m.json'
	},
};
OO.ready(function() {
	window.pp = OO.Player.create("ooyalaplayer", "g5aHc3ZjE69Y_EVJfMWzsMYPgiCGe3kD", playerParam);
});
```
#### Dynamic Button Pop
```javascript
<script>
    var playerParam = {
        autoplay: true,
        pcode: "xvYWgyOgX8LlAER8dMPTua1yO938",
        playerBrandingId: "38dd44cdbeca4132a08badd1e565fab6",
        skin: {
            config: '../otc_m.json'
        },
    };
    var mplayer, mesb, dur, title;
    OO.ready(function() {
        var lastTriggerPos;
        mplayer = OO.Player.create('ooyalaplayer', 'g5aHc3ZjE69Y_EVJfMWzsMYPgiCGe3kD', playerParam);
        mplayer.mb.subscribe(OO.EVENTS.PLAYBACK_READY, 'g5aHc3ZjE69Y_EVJfMWzsMYPgiCGe3kD', function(eventName) {
            title = mplayer.getCurrentItemTitle();
            var vData = mplayer.getItem();
            dur = parseInt(vData.time);
        });
        window.setInterval(function(){
            mplayer.mb.subscribe(OO.EVENTS.PLAYHEAD_TIME_CHANGED, 'g5aHc3ZjE69Y_EVJfMWzsMYPgiCGe3kD', function(eventName) {
                phPos = parseInt(mplayer.getPlayheadTime());
                // phPos is the time in seconds - Price Button Timer: 12:07
                if(phPos > 727) {
                    $('.buyNowButton').css('display', 'block');
                }
            })
        }, 2000);
    });

</script>
```

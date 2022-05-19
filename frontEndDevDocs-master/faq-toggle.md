# FAQ Toggle

```html
<style>
.faq {
    background: white;
}
.faq_container {
    width: 100%;
    margin: 0 auto;
    margin-bottom: 11px;
    padding: 40px 18px;
}
.questionDiv p {
    float: left; 
    width: 80%; 
    color: #3C60AA; 
    font-family: "Graphik-Bold", serif;
}
.questionDiv img {float: right; width: 41px;}
.answer {color: #4A4A4A; display: none;}
.transition { 
    transform: rotate(180deg);
    transition-timing-function: ease-in; 
}
</style>
<script>
    $(".question").click(function(){
        $(this).find(".questionDiv img").toggleClass("transition");
        $(this).find(".answer").slideToggle( 1200, function() {
            $(this).find(".answer").toggleClass("show-reviews");
        });
    });
</script>
<body>
    <div class="faq">
        <div class="faq_container">
            <p>
                <b>Frequently Asked Questions</b>
            </p>
            <div class="question">
                <div class="questionDiv">
                    <p>What makes Beverly Hills MD Thick + Full Brow Enhancing Serum different from other brow enhancing products?</p>
                    <img src="images/faq-static@2x.png" alt="">
                    <div class="clear"></div>
                </div>
                <div class="answer">
                    <p>Two big reasons. First, most other "brow enhancing" products are are hugely watered-down. Some companies do what we call "fairy dusting" — adding a microscopic amount of active ingredients, so they can produce a cheap (and often ineffective) product but still advertise the ingredients.</p>
                    <p>Second, some other formulas contain PROSTAGLANDINS — ingredients that help re-grow hair by manipulating your body's hormones. This can result in darkening skin, rashes and irritation, and even changing eye color. That's why Thick + Full Brow Enhancing Serum contains absolutely zero prostaglandins — and only uses ingredients that work WITH your body's natural chemistry, never against it.</p>
                </div>
            </div>
            <hr>
            <div class="question">
                <div class="questionDiv">
                    <p>What makes Beverly Hills MD Thick + Full Brow Enhancing Serum different from other brow enhancing products?</p>
                    <img src="images/faq-static@2x.png" alt="">
                    <div class="clear"></div>
                </div>
                <div class="answer">
                    <p>Two big reasons. First, most other "brow enhancing" products are are hugely watered-down. Some companies do what we call "fairy dusting" — adding a microscopic amount of active ingredients, so they can produce a cheap (and often ineffective) product but still advertise the ingredients.</p>
                    <p>Second, some other formulas contain PROSTAGLANDINS — ingredients that help re-grow hair by manipulating your body's hormones. This can result in darkening skin, rashes and irritation, and even changing eye color. That's why Thick + Full Brow Enhancing Serum contains absolutely zero prostaglandins — and only uses ingredients that work WITH your body's natural chemistry, never against it.</p>
                </div>
            </div>
        </div>
    </div>
</body>
```

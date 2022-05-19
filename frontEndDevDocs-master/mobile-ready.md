```php
<?php
    $tablet_browser = 0;
    $mobile_browser = 0;
    $httpUserAgent = empty($_SERVER['HTTP_USER_AGENT']) ? "" : $_SERVER['HTTP_USER_AGENT'];

    if (preg_match('/(tablet|ipad|playbook)|(android(?!.*(mobi|opera mini)))/i', strtolower($httpUserAgent))) {
        $tablet_browser++;
    }

    if (preg_match('/(up.browser|up.link|mmp|symbian|smartphone|midp|wap|phone|android|iemobile)/i', strtolower($httpUserAgent))) {
        $mobile_browser++;
    }

    if ((strpos(strtolower($_SERVER['HTTP_ACCEPT']),'application/vnd.wap.xhtml+xml') > 0) or ((isset($_SERVER['HTTP_X_WAP_PROFILE']) or isset($_SERVER['HTTP_PROFILE'])))) {
        $mobile_browser++;
    }

    $mobile_ua = strtolower(substr($httpUserAgent, 0, 4));
    $mobile_agents = array(
        'w3c ','acs-','alav','alca','amoi','audi','avan','benq','bird','blac',
        'blaz','brew','cell','cldc','cmd-','dang','doco','eric','hipt','inno',
        'ipaq','java','jigs','kddi','keji','leno','lg-c','lg-d','lg-g','lge-',
        'maui','maxo','midp','mits','mmef','mobi','mot-','moto','mwbp','nec-',
        'newt','noki','palm','pana','pant','phil','play','port','prox',
        'qwap','sage','sams','sany','sch-','sec-','send','seri','sgh-','shar',
        'sie-','siem','smal','smar','sony','sph-','symb','t-mo','teli','tim-',
        'tosh','tsm-','upg1','upsi','vk-v','voda','wap-','wapa','wapi','wapp',
        'wapr','webc','winw','winw','xda ','xda-');

    if (in_array($mobile_ua,$mobile_agents)) {
        $mobile_browser++;
    }

    if (strpos(strtolower($httpUserAgent),'opera mini') > 0) {
        $mobile_browser++;
        //Check for tablets on opera mini alternative headers
        $stock_ua = strtolower(isset($_SERVER['HTTP_X_OPERAMINI_PHONE_UA'])?$_SERVER['HTTP_X_OPERAMINI_PHONE_UA']:(isset($_SERVER['HTTP_DEVICE_STOCK_UA'])?$_SERVER['HTTP_DEVICE_STOCK_UA']:''));
        if (preg_match('/(tablet|ipad|playbook)|(android(?!.*mobile))/i', $stock_ua)) {
            $tablet_browser++;
        }
    } else if ($mobile_browser > 0) {
    // do something for mobile devices
    } else {
    // do something for desktop
        header("Location: propowerplus_nov.php");
    }
?>
<!DOCTYPE html>
<html>
<head>
    <title></title>
	<meta charset="utf-8">
	<meta name="description" content="">
	<meta name="viewport" content="width=device-width, initial-scale=1">
    <style type="text/css">
        /* Font Family */
        @font-face {
            font-family: "Proxima Nova";
            src: url('../fonts/proximanova-reg-webfont.ttf'),
                 url('../fonts/proximanova-reg-webfont.woff'),
                 url('../fonts/proximanova-reg-webfont.eot');
        }

        @font-face {
            font-family: "Proxima Nova Bold";
            src: url('../fonts/ProximaNova-Bold.otf');
        }

        @font-face {
            font-family: "Proxima Nova Light";
            src: url('../fonts/proximanova-light-webfont.ttf'),
                 url('../fonts/proximanova-light-webfont.woff'),
                 url('../fonts/proximanova-light-webfont.eot');
        }
        /* Mobile Styling */
        *{text-decoration: none; max-width: 100%;}
        html,body{margin: 0; padding: 0; box-sizing: border-box;background-color: #f4f4f4;}
        body{font-family: "Proxima Nova", sans-serif;}
        img{border: none;}
        .clear{clear: both}
        .bold{font-weight: bold;}
        .italic{font-style: italic;}
        .underline{text-decoration: underline;}
        .center{text-align: center;}
        .left{text-align: left;}
        .container{width: 90%; margin: 0 auto;}
        .caption{font-size: smaller;}
        .greenDivider{width: 70px; border: 2px solid #b8d436; margin-bottom: 20px;}

        /* Page Styling */
        .header {background: #FFFFFF; padding: 30px 0px;}
        .header_logo {width: 30%}
        .package h1 {text-align: center; font-size: 23px; color: #475F72;}
    </style>
</head>
<body>
    <header class="header">
        <div class="container">
            <img src="images/DR.MARTYLOGO.png" class="header_logo">
        </div>
    </header>
    <div class="package">

    </div>
</body>
</html>
```

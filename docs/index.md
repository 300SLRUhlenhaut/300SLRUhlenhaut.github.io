<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">
		<script
			id="sap-ui-bootstrap"
			src="/resources/sap-ui-core.js"
			data-sap-ui-theme="sap_bluecrystal"
			data-sap-ui-modules="sap.m.library"
			data-sap-ui-compatVersion="edge"
			data-sap-ui-preload="async" >
		</script>
		<script>
			sap.ui.getCore().attachInit(function () {
				new sap.m.Text({
					text : "OpenUI5 is loaded successfully!"
				}).placeAt("content");
			});
		</script>
    <title>CityExplore Homepage</title>

    <style>
        * {
            margin: 0px;
            padding: 0px;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            background-color: whitesmoke;
        }

        .n {
            height: 75px;
            width: 100%;
            top: 0px;
            position: fixed;
            z-index: 9999;
            background-color: rgb(255, 255, 255);
        }

        .top {
            position: absolute;
            height: 60px;
            width: 100%;
        }

        .logo {
            background-image: url(icons/cityexplorelogo.png);
            background-size: contain;
            height: 65px;
            width: 158px;
            position: absolute;
            margin-left: 40px;
            margin-top: -10px;
        }

        .S {
            display: inline-block;
            position: absolute;
            top: 28px;
            left: 720px;
        }

        .parent {
            position: relative;
        }

        .search {
            width: 200px;
            height: 29px;
            border-top-left-radius: 8px;
            border-bottom-left-radius: 8px;
            outline: none;
            border-left: #3a3a3a 1px solid;
            border-top: #3a3a3a 1px solid;
            border-bottom: #3a3a3a 1px solid;
            padding-left: 20px;
            position: absolute;
        }

        .sousuo {
            float: left;
            margin-left: 930px;
            margin-top: 28px;
            width: 30px;
            height: 29px;
            border-top-right-radius: 8px;
            border-bottom-right-radius: 8px;
            background-color: #000000;
            background-image: url(icons/ss.svg);
            background-position: center;
            background-repeat: no-repeat;
            border-right: #3a3a3a 1px solid;
            border-top: #3a3a3a 1px solid;
            border-bottom: #3a3a3a 1px solid;
            outline: none;
            padding-left: 20px;
            position: absolute;
            font-size: 20px;
        }

        .xtxx {
            background-color: rgba(231, 231, 231, 0);
            width: 40px;
            height: 40px;
            position: absolute;
            right: 200px;
            top: 22px;
            border-radius: 30px;
            background-color: rgb(255, 255, 255);
            background-image: url(icons/xtxx.svg);
            background-position: center;
            background-repeat: no-repeat;
        }

        .sixin {
            background-color: rgba(231, 231, 231, 0);
            width: 40px;
            height: 40px;
            position: absolute;
            right: 135px;
            top: 22px;
            border-radius: 30px;
            background-color: rgb(255, 255, 255);
            background-image: url(icons/sixin\ \(1\).svg);
            background-position: center;
            background-repeat: no-repeat;
        }

        .denglu {
            background-color: rgba(231, 231, 231, 0);
            width: 40px;
            height: 40px;
            position: absolute;
            right: 65px;
            top: 22px;
            border-radius: 30px;
            background-color: rgb(241, 241, 241);
            background-image: url(images/tou.jpg);
            background-position: center;
            background-repeat: no-repeat;
        }

        .denglu ul {
            display: none;
            position: absolute;
            left: -40px;
            top: 35px;
        }

        .denglu ul li {
            list-style-type: none;
            background-color: #fff;
            width: 120px;
            text-align: center;
        }

        .denglu ul li a {
            display: block;
            text-decoration: none;
            font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
            color: rgb(0, 0, 0);
            padding: 13px 10px;
        }

        .denglu:hover>ul {
            display: block;
        }

        .denglu ul li:hover {
            background-color: rgb(255, 178, 106);
        }

        .denglu ul li a:hover {
            color: white;
        }

        .sanjiao {
            width: 0;
            height: 0;
            overflow: hidden;
            font-size: 0;
            /*是因为, 虽然宽高度为0, 但在IE6下会具有默认的 */
            line-height: 0;
            /* 字体大小和行高, 导致盒子呈现被撑开的长矩形 */
            border-width: 10px;
            border-style: dashed dashed solid dashed;
            /*IE6下, 设置余下三条边的border-style为dashed,即可达到透明的效果*/
            border-color: transparent transparent rgb(216, 216, 216) transparent;
            position: absolute;
            left: 50px;
            top: 5px;
        }

        nav {
            text-align: center;
            text-decoration: none;
            font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
            font-weight: lighter;
            position: absolute;
            width: 900px;
            top: 15px;
            left: -15px;
            padding: 0px;
        }

        nav ul {
            display: inline-table;
            position: relative;
        }

        nav ul li {
            float: left;
            list-style-type: none;
            width: 120px;
        }

        nav ul li a {
            font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
            font-weight: lighter;
            display: block;
            padding: 18px 10px;
            text-decoration: none;
            font-weight: bolder;
            color: rgb(0, 0, 0);
        }

        nav ul ul {
            display: none;
            background: #ffffff;
            position: absolute;
            top: 100%;
            padding: 0;
        }

        nav ul ul li {
            width: 170px;
            position: relative;
            float: none;
            font-size: 15px;
        }

        nav ul ul li a {
            font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
            font-weight: lighter;
            padding: 13px 10px;
            color: rgb(0, 0, 0);
        }

        nav ul li:hover>ul {
            display: block;
        }

        nav>ul>li:hover {
            background-color: #fff;
            border-top: rgb(255, 178, 106) 3px solid;
        }

        nav ul ul li:hover {
            background-color: rgb(255, 178, 106);
        }

        nav ul ul li a:hover {
            color: white;
        }

        .datu {
            height: 540px;
            margin: auto;
            background-image: url(Home_images/yellow\ train.jpeg);
            background-position: center;
            background-repeat: no-repeat;
        }

        header {
            font-size: 35px;
            text-align: center;
            color: rgb(255, 255, 255);
            padding-top: 230px;
            text-shadow: rgb(0, 0, 0) 3px 2px 25px;
        }

        .login {
            background-color: #6cd0e2;
            height: 24px;
            width: 130px;
            margin: auto;
            margin-top: 60px;
            text-align: center;
            padding: 15px;
            border-radius: 35px;
        }

        /* 城市介绍 */
        .container1 {
            background-color: whitesmoke;
            width: 1000px;
            height: 500px;
            margin: auto;
            margin-top: 50px;
            margin-bottom: 30px;
            background-position: center;
        }

        .container1 h1 {
            font-size: 30px;
            text-align: center;
        }

        .b1 {
            height: 350px;
            width: 270px;
            border-radius: 7px;
            background-color: rgb(255, 255, 255);
            background-image: url(Home_images/地理.jpeg);
            margin-left: 47.5px;
            margin-top: 35px;
            float: left;
            transition: All 0.2s ease-in-out;
        }

        .b2 {
            height: 350px;
            width: 270px;
            border-radius: 7px;
            background-color: rgb(255, 255, 255);
            background-image: url(Home_images/历史.jpg);
            margin-left: 47.5px;
            margin-top: 35px;
            float: left;
            transition: All 0.2s ease-in-out;
        }

        .b3 {
            height: 350px;
            width: 270px;
            border-radius: 7px;
            background-color: rgb(255, 255, 255);
            background-image: url(Home_images/文化.jpeg);
            margin-left: 47.5px;
            margin-top: 35px;
            float: left;
            transition: All 0.2s ease-in-out;
        }

        .c {
            height: 350px;
            width: 270px;
            background-color: rgba(223, 223, 223, 0.116);
            position: absolute;
            margin-top: 0px;
            color: white;
            font-size: 28px;
            text-align: center;
            text-shadow: rgb(0, 0, 0) 2px 2px 20px;
            border-radius: 7px;
        }

        .findm {
            position: absolute;
            margin-top: 410px;
            margin-left: 470px;

        }

        .c p {
            margin-top: 150px;
        }

        .b1:hover {
            transform: translate(0, -5px);
            -webkit-box-shadow: #ccc 0px 10px 10px;
            -moz-box-shadow: #ccc 0px 10px 10px;
            box-shadow: #ccc 0px 10px 10px;
        }

        .b2:hover {
            transform: translate(0, -5px);
            -webkit-box-shadow: #ccc 0px 10px 10px;
            -moz-box-shadow: #ccc 0px 10px 10px;
            box-shadow: #ccc 0px 10px 10px;
        }

        .b3:hover {
            transform: translate(0, -5px);
            -webkit-box-shadow: #ccc 0px 10px 10px;
            -moz-box-shadow: #ccc 0px 10px 10px;
            box-shadow: #ccc 0px 10px 10px;
        }

        .container1 h6 {
            text-align: center;
        }

        .container1 h6 a {
            color: rgb(83, 83, 83);
            text-decoration: none;
        }

        /* 可去地方 */
        .container2 {
            background-image: url(Home_images/车流.jpeg);
            width: 1000px;
            height: 500px;
            margin: auto;
            border-top-left-radius: 5px;
            border-top-right-radius: 5px;
        }

        .where {
            width: 1000px;
            height: 500px;
            border-top-left-radius: 5px;
            border-top-right-radius: 5px;
            background-color: rgba(221, 221, 221, 0.233);
        }

        .container2 p {
            color: white;
            position: absolute;
            margin-top: 220px;
            margin-left: 260px;
            font-size: 50px;
            font-weight: bolder;
            text-shadow: black 5px 5px 30px;
        }

        .box {
            height: 450px;
            width: 320px;
            background-color: #6cd0e2;
            position: absolute;
            margin-top: 50px;
            margin-left: 100px;
        }

        .container22 {
            background-color: rgb(29, 29, 29);
            width: 1000px;
            height: 300px;
            margin: auto;
            border-bottom-left-radius: 5px;
            border-bottom-right-radius: 5px;
        }

        .f {
            position: absolute;
            margin-top: 270px;
            margin-left: 470px;
        }

        .f a {
            text-decoration: none;
            color: white;
        }

        .container22 ul {
            height: 200px;
            width: 200px;
            background-color: rgb(255, 255, 255);
            margin-left: 40px;
            margin-top: 40px;
            border-radius: 5px;
            float: left
        }

        .u1 {
            background-image: url(Home_images/historical\ gallery0084_small.jpg);
            background-size: 200px 200px;
            border-radius: 5px;
        }

        .u2 {
            background-image: url(Home_images/太平山.JPEG);
            background-size: 200px 200px;
            border-radius: 5px;
        }

        .u3 {
            background-image: url(Home_images/购物.jpg);
            background-size: 200px 200px;
            border-radius: 5px;
        }

        .u4 {
            background-image: url(Home_images/夜生活.jpeg);
            background-size: 200px 200px;
            border-radius: 5px;
        }

        .xianshi {
            width: 200px;
            height: 200px;
            background-color: rgba(36, 34, 34, 0.555);
            display: none;
        }

        .u1:hover>.xianshi {
            display: block;
        }

        .u2:hover>.xianshi {
            display: block;
        }

        .u3:hover>.xianshi {
            display: block;
        }

        .u4:hover>.xianshi {
            display: block;
        }

        .container22 p {
            text-align: center;
            color: white;
            padding-top: 90px;
            font-size: 15px;
            font-weight: bolder;

        }

        /* 近期活动 */
        .container3 {
            background-color: whitesmoke;
            width: 1000px;
            height: 410px;
            margin: auto;
            margin-top: 50px;
        }

        .container3 h1 {
            text-align: center;
            margin-bottom: 10px;
        }

        .container3 ul {
            height: 320px;
            width: 255px;
            background-color: rgb(255, 255, 255);
            margin-left: 58.75px;
            margin-top: 10px;
            float: left;
            border-radius: 5px;
        }

        .container3 img {
            border-top-left-radius: 5px;
            border-top-right-radius: 5px;
        }

        .more {
            width: 250px;
            height: 30px;
            position: absolute;
            margin-left: 380px;
            margin-top: 350px;
            background-color: whitesmoke;
            text-align: center;
        }

        .container3 h6 a {
            text-decoration: none;
            color: rgb(83, 83, 83);
        }

        .container3 ul img {
            height: 200px;
            width: 255px;
        }

        .hdmc {
            padding-left: 10px;
            padding-top: 10px;
            font-weight: bolder;
            color: black;
        }

        .jieshao {
            padding: 10px;
            font-size: 5px;
            color: black;
        }

        /* 服务提供 */
        .container4 {
            width: 1000px;
            height: 300px;
            margin: auto;
            margin-top: 25px;
            margin-bottom: 50px;
        }

        .container4 h1 {
            text-align: center;
            margin-bottom: 10px;
        }

        .container4 ul {
            height: 250px;
            width: 290px;
            background-color: rgb(255, 255, 255);
            margin-left: 35px;
            margin-top: 10px;
            float: left;
            border-radius: 5px;
        }

        .container4 img {
            position: absolute;
            margin-top: 30px;
            margin-left: 75px;
        }

        .j {
            position: absolute;
            margin-top: 200px;
            margin-left: 110px;
            font-weight: bolder;
            color: black;
        }

        /* 页脚 */
        .footer {
            width: 100%;
            height: 200px;
            margin: auto;
            background-color: rgb(0, 0, 0);
        }

        .wenzi {
            width: 1000px;
            height: 200px;
            margin: 0 auto;
            background-color: rgb(0, 0, 0);
        }

        .wenzi ul {
            width: 150px;
            height: 120px;
            background-color: rgb(0, 0, 0);
            position: relative;
            float: left;
            margin-left: 20px;
            margin-top: 30px;
        }

        .wenzi p {
            font-weight: bolder;
            color: white;
            margin-left: 5px;
            margin-bottom: 5px;
        }

        .wenzi ul li {
            list-style-type: none;
            padding: 3px 5px;
            font-size: 10px;
        }

        .wenzi a {
            text-decoration: none;
            color: white;
        }

        .wenzi li a:hover {
            color: rgb(255, 178, 106);
        }

        .follow {
            width: 200px;
            height: 120px;
            position: absolute;
            margin-top: 30px;
            right: 200px;
            background-color: rgb(0, 0, 0);
        }

        .follow li {
            list-style-type: none;
            font-weight: bolder;
            padding: 3px 5px;
        }

        .copyright {
            position: absolute;
            margin-top: 160px;
            margin-left: 380px;
            background-color: rgb(0, 0, 0);
            font-weight: lighter;
        }
    </style>

</head>

<body>
    <!-- 导航栏 -->
    <div class="n">
        <nav>
            <a href="Home.html">
                <div class="logo">
                </div>
            </a>
            <ul>
                <li><a href="Home.html">Home</a></li>
                <li><a href="#">Guidance</a>
                    <ul>
                        <li><a
                                href="02 Guidance/City Introdctions/City_Introduction_Homepage/City_Introduction_Homepage.html">City
                                Introductions</a></li>
                        <li><a href="02 Guidance/Places To Go/PlacesToGo.html">Places To Go</a></li>
                        <li><a href="02 Guidance/Recent Activities/Recent Activities.html">Recent Activities</a></li>
                    </ul>
                </li>

                <li><a href="#">Community</a>
                    <ul>
                        <li><a href="03 Community/Community.html">Square</a></li>
                        <li><a href="03 Community/Groups.html">Groups</a></li>
                    </ul>
                </li>

                <li><a href="#">Services</a>
                    <ul>
                        <li><a href="04 Services/Ticket Booking/Ticket Booking Homepage.html">Tickets Booking</a></li>
                        <li><a href="04 Services/Coupon/Coupon.html">Coupons</a></li>
                        <li><a href="04 Services/Car Rental/Car Rental Homepage.html">Car Rental</a></li>
                    </ul>
                </li>
            </ul>
        </nav>

        <!-- 搜索栏 -->
        <div class="S">
            <form class="parent">
                <input type="text" class="search" placeholder="search">
            </form>
        </div>
        <div class="sousuo">
        </div>

        <!-- 系统通知/私聊/头像 -->
        <div class="xtxx"></div>
        <div class="sixin"></div>
        <div class="denglu">
            <ul>
                <li style="display: block; padding-top: 5px; 
                height: 20px; margin-bottom: 0px; background-color: transparent">
                    <div class="sanjiao"></div>
                </li>
                <li><a href="05 Mine/My Page.html">My page</a></li>
                <li><a href="05 Mine/My Page.html">Write</a></li>
                <li><a href="05 Mine/My Page.html">Set</a></li>
                <li><a href="01 LoginReg/Log In.html">Log out</a></li>
                </li>
            </ul>
        </div>
    </div>

    <!-- 大图 -->
    <div class="datu">

        <header>
            <h2>Begin Your Exploration </h3>
                <h6>City Explore will be your best guide</h6>
        </header>

        <div class="login">
            <a href="01 LoginReg/Log In.html" style="text-decoration: none;">
                <p style="color: white; font-weight: bolder;">Log In</p>
            </a>
        </div>

    </div>

    <!-- 城市介绍 -->
    <div class="container1">

        <div>
            <h1>Getting to know Hong Kong</h1>
        </div>

        <div class="b1">
            <a href="02 Guidance/City Introdctions/City_Introduction_Subpage/About Hong Kong.html">
                <div class="c">
                    <p>Geography</p>
                </div>
            </a>
        </div>
        <div class="b2">
            <a href="02 Guidance/City Introdctions/City_Introduction_Subpage/About Hong Kong.html">
                <div class="c">
                    <p>History</p>
                </div>
            </a>
        </div>

        <div class="b3">
            <a href="02 Guidance/City Introdctions/City_Introduction_Subpage/About Hong Kong.html">
                <div class="c">
                    <p> Cultral</p>
                </div>
            </a>
        </div>

        <div class="findm">
            <h6>
                <a href="02 Guidance/City Introdctions/City_Introduction_Homepage/City_Introduction_Homepage.html">Find
                    More</a>
            </h6>
        </div>

    </div>

    <!-- 可去地方-->
    <div class="container2">
        <div class="where">
            <p>Where shall we go ?</p>
        </div>

    </div>
    <div class="container22">
        <a href="02 Guidance/Places To Go/culturalObserver.html">
            <ul class="u1">
                <div class="xianshi">
                    <p>Cultral Oberver</p>
                </div>
            </ul>
        </a>

        <a href="02 Guidance/Places To Go/outdoorEnthusiast.html">
            <ul class="u2">
                <div class="xianshi">
                    <p>Outdoor Enthusiast</p>
                </div>
            </ul>
        </a>

        <a href="02 Guidance/Places To Go/shoppingMecca.html">
            <ul class="u3">
                <div class="xianshi">
                    <p>Shopping Mecca</p>
                </div>
            </ul>
        </a>

        <a href="02 Guidance/Places To Go/nightlifeCapital.html">
            <ul class="u4">
                <div class="xianshi">
                    <p>Shopping Mecca</p>
                </div>
            </ul>
        </a>

        <div class="f">
            <h6><a href="Guidance/PlacesToGo/">Find More</a></h6>
        </div>
    </div>

    <!-- 近期活动 -->
    <div class="container3">
        <h1>Recent Activities</h1>

        <a href="04 Services/Ticket Booking/Ticket Booking Information.html">
            <ul><img src="Home_images/p1.jpg">
                <div class="hdmc">"Romeo + Juliet"-- Hong Kong Ballet</div>
                <div class="jieshao">18 ‑ 20 Nov. (everyday) 7:30pm (2.5 hrs)
                    Grand Theatre, Hong Kong Cultural Centre</div>
            </ul>
        </a>


        <a href="04 Services/Ticket Booking/Ticket Booking Information.html">
            <ul><img src="Home_images/p2.jpg">
                <div class="hdmc">'Open book meow'-- puppet theater</div>
                <div class="jieshao">18 Nov. ‑ 3 Nov. (every Fri, Sat) 7:45pm (2 hrs)
                    Cultural Activities Hall, Tsuen Wan Town Hall</div>
            </ul>
        </a>

        <a href="04 Services/Ticket Booking/Ticket Booking Information.html">
            <ul><img src="Home_images/p3.jpg">
                <div class="hdmc">"Edge point"-- Eastern Dance Troupe</div>
                <div class="jieshao">15 - 23 Dec. (every Fri, Sat) 7:45pm (2hr)
                    Cultural Activities Hall, Ngau Chi Wan Centre</div>
            </ul>
        </a>


        <div class="more">
            <h6><a href="02 Guidance/Recent Activities/Recent Activities.html">Find More</a></h6>
        </div>


    </div>

    <!-- 服务提供 -->
    <div class="container4">
        <h1>Our Services</h1>
        <a href="04 Services/Ticket Booking/Ticket Booking Homepage.html">
            <ul><img src="icons/订票1.svg">
                <div class="j">Booking</div>
            </ul>
        </a>

        <a href="04 Services/Coupon/Coupon.html">
            <ul><img src="icons/优惠券领取.svg">
                <div class="j">Cunpons</div>
            </ul>
        </a>

        <a href="04 Services/Car Rental/Car Rental Homepage.html">
            <ul><img src="icons/租车.svg">
                <div class="j">Car Rental</div>
            </ul>
        </a>

    </div>

    <!-- 页脚 -->
    <div class="footer">

        <div class="wenzi">

            <ul>
                <p style="font-weight: bolder;"><a href="">About Web</a></p>
                <li><a href="">Legal Statement</a></li>
                <li><a href="">Privacy Policy</a></li>
                <li><a href="">Cookie Policy</a></li>
            </ul>

            <ul>
                <p><a href="">About Us</a> </p>
                <li><a href="">History</a> </li>
                <li><a href="">Partners</a> </li>
                <li><a href="">Certifications</a> </li>
            </ul>

            <ul>
                <p><a href="">Contact</a> </p>
                <li><a href="">Coperation</a></li>
                <li><a href="">Join us</a> </li>
                <li><a href="">Inform</a> </li>
            </ul>

            <ul>
                <p style="font-weight: bolder;"><a href="">More</a> </p>
                <li><a href="">FQA</a> </li>
                <li><a href="">Subscribe</a> </li>
            </ul>

            <div class="follow">
                <p style="font-weight: bolder;">Follow Us</p>
                <img src="icons/微信-白48.svg" height="40px" width="40px">&nbsp;
                <img src="icons/instagram-白48.svg" height="40px" width="40px">&nbsp;
                <img src="icons/推特-白48.svg" height="40px" width="40px">&nbsp;
                <img src="icons/facebook-白48.svg" height="40px" width="40px">&nbsp;

            </div>

            <div class="copyright">
                <p>Copyright &copy; CityExplorer.ltd</p>
            </div>
        </div>

    </div>

</body>

</html>

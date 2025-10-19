<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Apple Restoran Website</title>
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/7.0.0/css/all.min.css">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.7/dist/css/bootstrap.min.css" rel="stylesheet">
    <link href="https://getbootstrap.com/docs/5.3/assets/css/docs.css" rel="stylesheet">
</head>

<body>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            overflow-x: hidden;
        }


        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 20px;
            background-color: #f8f9fa;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            flex-wrap: wrap;
        }

        .img i {
            font-size: 40px;
            color: #e07f08;
            transition: all 0.3s ease;
            display: inline-block;
        }

        .img i:hover {
            transform: scale(1.1);
        }


        .menu {
            display: flex;
            list-style: none;
            gap: 15px;
            margin: 0;

            padding: 0;
        }

        .menu a {
            text-decoration: none;
            color: black;
            font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
            font-size: 25px;
            position: relative;
            display: inline-block;
            padding: 10px 15px;
        }

        .menu a:hover {
            color: #FF9500;
            transition: color 0.3s ease;
        }

        .menu a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: #f18901;
            transition: width 0.5s ease;
        }

        .menu a:hover::after {
            width: 100%;
        }

        /* İkonlar ve Arama/Sepet Stilleri */
        .icon {
            display: flex;
            align-items: center;
            gap: 20px;
            /* İkonlar arası boşluk */
        }

        .search-container {
            position: relative;
            display: inline-block;

        }

        #searchIcon {
            cursor: pointer;
            font-size: 1.7rem;
            color: black;
            padding-right: 0;
            /* Fazla padding'i kaldır */
        }

        .search-box {

            position: absolute;
            top: 75px;
            right: 0;
            opacity: 0;
            transition: all 0.4s ease-out;
            z-index: 1000;
            padding: 10px;
            background-color: #f8f9fa;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            white-space: nowrap;

        }

        .search-box.active {
            opacity: 1;
        }

        .search-box input {
            height: 40px;

            width: 250px;
            padding: 8px 10px;
            border: 1px solid #ccc;
            border-radius: 10px;
            outline-color: #e07f08;
        }

        .cart-container {
            position: relative;
            display: inline-block;
        }

        .cart-icon {
            width: 150px;
            /* Daha makul bir genişlik */
            padding: 10px 15px;
            background: #b36e00;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.3s;
            white-space: nowrap;
        }

        .cart-icon:hover {
            background: #d49a26;
        }

        .cart-dropdown {
            position: absolute;
            top: 100%;
            right: 0;
            /* Sağa hizala */
            width: 280px;
            /* Dropdown genişliğini ayarla */
            background: white;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
            border-radius: 4px;
            overflow: hidden;
            max-height: 0;
            transition: max-height 0.5s ease-in-out, opacity 0.3s ease;
            opacity: 0;
            z-index: 1000;
            padding: 10px;
        }

        .cart-dropdown.active {
            max-height: 600px;
            opacity: 1;
        }

        /* Dropdown içindeki ürünler */
        .card-items a {
            display: flex;
            align-items: center;
            margin-bottom: 10px;
            padding: 5px;
            border-bottom: 1px solid #eee;
            transition: all 0.2s ease;
            text-decoration: none;
            color: black;
            gap: 10px;
        }

        .card-items a:hover {
            background-color: #f9f9f9;
        }

        .card-items .iconimg {
            width: 60px;
            /* Küçük resim boyutu */
            height: 40px;
            object-fit: cover;
        }

        .card-items b {
            display: flex;
            justify-content: space-between;
            flex-grow: 1;
        }

        .checkout-btn {
            cursor: pointer;
            width: 100%;
            padding: 10px;
            margin-top: 15px;
            background: #b36e00;
            color: white;
            border: 1px solid;
            border-radius: 4px;
            transition: all 0.3s;
            font-size: 19px;
        }

        /* Hero Alanı (Content) Stilleri */
        .content {
            font-size: 30px;
            padding-top: 250px;
            padding-left: 40px;
            color: #f8f9fa;
            background-repeat: no-repeat;
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url("img folder/burgerbc.jpg");
            background-size: center;
            background-position: center;
            height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            text-align: left;
        }

        .content h1 {
            font-size: 3em;
            margin-bottom: 15px;
        }

        .content h6 {
            font-size: 1.2em;
            margin-left: 2%;
            margin-bottom: 5px;
        }

        .content .button {
            margin-top: 30px;
            margin-left: 2%;
            /* Hizalama için düzeltildi */
            font-size: 20px;
            border: 1px solid;
            border-radius: 5px;
            font-family: Verdana, Geneva, Tahoma, sans-serif;
            cursor: pointer;
            background-color: black;
            color: white;
            padding: 10px 20px;
            white-space: nowrap;
            transition: all 0.3s ease;
            display: inline-block;
        }

        .content .button:hover {
            transform: scale(1.05);
            background-color: #FF9500;
        }

        /* Menü Başlığı */
        .menu1 {
            background-color: rgb(249, 135, 53);
            padding: 20px 0;
            text-align: center;
        }

        .menu1 .menuh1 {
            font-size: 40px;
            color: white;
            margin: 0;
        }

        /* Ürün Kartları (Footer Alanı) Stilleri */
        .footer {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            padding: 50px 20px;
            background-color: rgb(249, 135, 53);
            gap: 30px;
            /* Kartlar arası boşluk */
        }

        .card {
            width: 300px;
            /* Bootstrap'in 20rem'ini piksele çevirip düzenledik */
            text-decoration: none;
            transition: all 0.4s ease;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            overflow: hidden;
            background-color: white;
            margin: 0;
            /* Dışarıdaki marginleri temizle */
        }

        .card .cards {
            display: block;
            text-decoration: none;
            color: black;
            height: 100%;
            /* Tüm kart içeriğini kapsamasını sağla */
        }

        .card:hover {
            transform: translateY(-8px) scale(1.03);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        .card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            padding: 20px;
        }

        .card .card-img-top1 {
            height: 250px;
        }

        .card .card-img-top2 {
            height: 200px;
        }

        .card-img-top3 {
            height: 200px;
        }

        .card-img-top4 {
            height: 250px;
        }

        .card-body {
            padding: 15px;
            text-align: center;
        }

        .card h5 {
            font-size: 1.25rem;
            margin-bottom: 5px;
        }

        .card del {
            color: #888;
            margin-right: 10px;
        }

        .card h4 {
            color: #ff0000fe;
            font-size: 1.75rem;
            margin-top: 5px;
            margin-bottom: 15px;
        }

        .card button {
            width: 90%;
            margin: 0 auto 15px;
            display: block;
            padding: 12px 24px;
            background: #834600;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .card button:hover {
            background: #ff0000fe;
        }

        /* END Alanı (Tanıtım Kartları) Stilleri */
        .end {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            background-color: rgb(249, 135, 53);
            padding-bottom: 50px;
            gap: 20px;
        }

        .cartt,
        .cartt2,
        .cartt3 {
            max-width: 400px;
            /* Genişliği ayarla */
            height: auto;
            /* Yüksekliği içeriğe bırak */
            border-radius: 20px;
            background-color: white;
            margin-top: 20px;
            /* Boşluk bırak */
            padding: 20px;
            text-align: center;
            transition: transform 0.3s ease;
        }

        .cartt:hover,
        .cartt2:hover,
        .cartt3:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .end p {
            font-size: 14px;
            color: #888;
            margin: 0;
        }

        .end h1 {
            font-size: 2.5rem;
            margin: 5px 0 15px;
        }

        .cartt .burger,
        .cartt2 .burger,
        .cartt3 .burger {
            width: 100%;
            height: auto;
            max-height: 250px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 15px;
        }

        .strong {
            font-size: 26px;
            color: #b36e00;
        }

        .fa-cart-plus {
            font-size: 40px;
            color: #b36e00;
            margin-left: 30px;
            /* Yan yana hizalama için düzeltildi */
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .fa-cart-plus:hover {
            color: #ff0000fe;
        }

        /* Contact Alanı Stilleri */
        .contact2 {
            background-color: rgb(249, 135, 53);
            padding: 50px 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .input-container {
            position: relative;
            background-color: #e0cfc7;
            width: 800px;
            height: auto;
            /* Yüksekliği içeriğe bırak */
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            margin: 0;
            /* Merkezi konumlandırma için margin'i temizle */
        }

        .input-container h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            text-align: center;
        }

        .input-form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .user-icon {
            position: relative;
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .input-name,
        .input-email,
        .input-number {
            padding-left: 50px;
            /* İkona yer bırak */
            display: block;
            width: 100%;
            height: 50px;
            border-radius: 8px;
            border: 1px solid #ccc;
            outline: none;
            transition: border-color 0.3s;
        }

        .input-name:focus,
        .input-email:focus,
        .input-number:focus {
            border-color: #ff9800;
        }

        /* İkonların konumlandırılması */
        .fa-user-tie,
        .fa-envelope-circle-check,
        .fa-phone-volume {
            position: absolute;
            left: 15px;
            font-size: 1.2rem;
            color: #b36e00;
            z-index: 10;
        }

        .fa-user-tie {
            top: 18px;
        }

        .fa-envelope-circle-check {
            top: 83px;
        }

        .fa-phone-volume {
            top: 148px;
        }

        /* Submit Button */
        .submit {
            background: linear-gradient(135deg, #ff9800, #ff5722);
            color: #fff;
            padding: 12px 24px;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
            align-self: center;
            /* Butonu ortala */
            margin-top: 10px;
            width: 50%;
            /* Butonun genişliğini ayarla */
            max-width: 200px;
        }

        /* --- MEDIA QUERIES (Duyarlı Tasarım) --- */

        @media (max-width: 1200px) {
            .content {
                padding-top: 200px;
                font-size: 26px;
            }

            .input-container {
                width: 700px;
            }
        }

        @media (max-width: 992px) {
            .menu a {
                font-size: 22px;
                padding: 8px 12px;
            }

            .cart-icon {
                width: 130px;
                font-size: 14px;
            }

            .content h1 {
                font-size: 2.5em;
            }

            .content h6 {
                font-size: 1em;
            }

            .input-container {
                width: 90%;
            }
        }

        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                padding: 15px;
            }

            .img {
                margin-bottom: 10px;
            }

            .menu {
                margin-top: 10px;
                flex-wrap: wrap;
                justify-content: center;
                gap: 5px;
            }

            .menu a {
                font-size: 18px;
                padding: 5px 8px;
            }

            .icon {
                margin-top: 10px;
                width: 100%;
                justify-content: space-around;
                gap: 10px;
            }

            #searchIcon {
                font-size: 1.5rem;
                padding-right: 0;
            }

            .search-box {
                right: 70%;
                transform: translateX(50%);
                top: 100%;

            }

            .search-box input {
                width: 300px;
            }

            .cart-container {
                order: 3;
                /* Sepet butonunu sona taşı */
            }

            .cart-icon {
                width: 100%;
                max-width: 200px;
            }

            .cart-dropdown {
                right: 50%;
                transform: translateX(50%);
            }

            .content {
                padding-top: 150px;
                padding-left: 15px;
                align-items: center;
                text-align: center;
                font-size: 18px;
            }

            .content h6 {
                margin-left: 0;
                text-align: center;
            }

            .content .button {
                margin-left: 0;
            }

            .cartt,
            .cartt2,
            .cartt3 {
                max-width: 90%;
            }

            .submit {
                width: 70%;
            }

            /* İkon konumlarını düzelt */
            .fa-user-tie,
            .fa-envelope-circle-check,
            .fa-phone-volume {
                left: 23px;
            }

        }

        @media (max-width: 576px) {
            .content {
                padding-top: 100px;
                font-size: 16px;
            }

            .content h1 {
                font-size: 2em;
            }

            .menu {
                flex-direction: column;
                gap: 5px;
            }

            .search-box input {
                width: 250px;
            }

            .card {
                width: 90%;
                /* Küçük ekranlarda tam genişlik */
            }

            .cartt,
            .cartt2,
            .cartt3 {
                max-width: 95%;
            }

            .end h1 {
                font-size: 2rem;
            }

            .strong {
                font-size: 22px;
            }

            .fa-cart-plus {
                font-size: 30px;
                margin-left: 20px;
            }

            .submit {
                width: 80%;
            }

            /* İkon konumlarını düzelt */
            .fa-user-tie {
                top: 14px;
                left: 15px;
            }

            .fa-envelope-circle-check {
                top: 75px;
                left: 15px;
            }

            .fa-phone-volume {
                top: 135px;
                left: 15px;
            }

            .input-name,
            .input-email,
            .input-number {
                padding-left: 45px;
                height: 45px;
            }
        }
    </style>

    <div class="navbar">
        <div class="img">
            <a href="#">
                <i class="fa-brands fa-apple"></i>
            </a>
        </div>
        <ul class="menu">
            <a href="#">
                <li class="menu-items">Home</li>
            </a>
            <a href="#">
                <li class="menu-items">Menu</li>
            </a>
            <a href="#">
                <li class="menu-items">Blogs</li>
            </a>
            <a href="#">
                <li class="menu-items">About us</li>
            </a>
            <a href="#">
                <li class="menu-items">Contact</li>
            </a>
        </ul>
        <div class="icon">
            <div class="search-container"><a href="#" id="searchIcon"> <span><i
                            class="fa-solid fa-magnifying-glass"></i> </span></a></div>
            <div class="search-box" id="searchBox">
                <input type="text" placeholder="Search here:">
            </div>
            <div class="cart-container">

                <button class="cart-icon" onclick="toggleCartMenu()">
                    Shopping Cart
                </button>

                <div class="cart-dropdown" id="cartDropDown">
                    <div class="cart-content">

                        <div class="card-items">

                            <a href="" class="menuitems"><b><img src="img folder/gamburger.jpg" class="iconimg" alt="">
                                    Item
                                    1/
                                    <i class="pizza">$6.00</i>
                                </b></a>
                            <a href="" class="menuitems2"><b><img src="img folder/gamburger2.jpg" class="iconimg"
                                        alt="">
                                    Item 2/
                                    <i class="pizza">$8.00</i>
                                </b></a>
                            <a href="" class="menuitems3"><b><img src="img folder/sandwitch.jpg" class="iconimg" alt="">
                                    Item 3/
                                    <i class="pizza">$11.00</i>
                                </b></a>
                            <a href="" class="menuitems4"><b><img src="img folder/kartoffree2.jpg" class="iconimg"
                                        alt="">
                                    Item 4/
                                    <i class="pizza">$9.00</i>
                                </b></a>
                            <a href="" class="menuitems5"><b><img src="img folder/pizza2.jpg" class="iconimg" alt="">
                                    Item 5/
                                    <i class="pizza">$8.50</i>
                                </b></a>


                        </div>
                        <button class="checkout-btn">
                            Checkout now
                        </button>
                    </div>
                </div>
            </div>

        </div>


    </div>


    <div class="content">
        <h1>Welcome to Apple Restoran</h1>

        <h6 class="h4">"Thank you for dining with us. </h6>
        <h6>where every meal is crafted with passion and served with warmth.</h6>
        <h6> We look forward to welcoming you back soon!"</h6>
        <button class="button">Order now</button>
    </div>
    <div class="menu1">
        <h1 class="menuh1">Menu</h1>
    </div>
    <div class="footer">

        <br>
        <div class="card" style="width: 20rem;"><a href="#" class="cards">
                <img src="img folder/gamburger.jpg" class="card-img-top1  " alt="5 Middle Burgers">
                <div class="card-body ">
                    <h5>5 Middle Burgers</h5>
                    <del>$110</del>
                    <h4>$92</h4>
                </div>
                <button>Add Cart</button>
            </a>
        </div>

        <div class="card" style="width: 20rem;"> <a href="#" class="cards">
                <img src="img folder/gamburger2.jpg" class="card-img-top2  " alt="5 Mini Burgers">
                <div class="card-body ">
                    <div class="price2">
                        <h5>5 Mini Burgers</h5>
                        <del>$95</del>
                        <h4>$71</h4>
                    </div>
                </div>
                <button>Add Cart</button>
            </a>
        </div>
        <div class="card" style="width: 20rem;"> <a href="#" class="cards">
                <img src="img folder/sandwitch.jpg" class="card-img-top3 " alt="5 Mini Sandwichs">
                <div class="card-body ">
                    <div class="price3">
                        <h5>5 Mini Sandwichs</h5>
                        <del>$100</del>
                        <h4>$85</h4>
                    </div>

                </div>
                <button>Add Cart</button>
            </a>
        </div>
        <div class="card  d-flex flex-column" style="width: 20rem;"> <a href="#" class="cards">
                <img src="img folder/gamburger2.jpg" class="card-img-top4  " alt="6 Big Burgers">
                <div class="card-body ">
                    <h5>6 Big Burgers</h5>
                    <del>$130</del>
                    <h4>$100</h4>

                </div>
                <button>Add Cart</button>
            </a>
        </div>

    </div>

    <div class="end">
        <div class="cartt">
            <p>BIG Burger</p>
            <h1>Beef Burger</h1>
            <img src="img folder/gamburger4.jpg" alt="Beef Burger" class="burger">

            <strong class="strong">$17</strong>
            <i class="fa-solid fa-cart-plus"></i>
        </div>
        <div class="cartt2">
            <p>BIG Burger</p>
            <h1>Mutton Burger</h1>
            <img src="img folder/gamburger2.jpg" alt="Mutton Burger" class="burger">

            <strong class="strong">$10</strong>
            <i class="fa-solid fa-cart-plus"></i>
        </div>
        <div class="cartt3">
            <p>BIG Burger</p>
            <h1>Chicken Burger</h1>
            <img src="img folder/chickenburger.jpg" alt="Chicken Burger" class="burger">
            <strong class="strong">$14</strong>
            <i class="fa-solid fa-cart-plus"></i>
        </div>
        <div class="contact">
        </div>
    </div>
    <div class="contact2">
        <div class="input-container">
            <h2>Get in Touch</h2>
            <form action="submit" class="input-form">
                <div class="user-icon">
                    <i class="fa-solid fa-user-tie"></i>
                    <input type="text" id="name" name="name" placeholder="Your Name" class="input-name">
                    <i class="fa-solid fa-envelope-circle-check"></i>
                    <input type="email" placeholder="Email" class="input-email">
                    <i class="fa-solid fa-phone-volume"></i>
                    <input type="number" class="input-number" placeholder="Phone Number">
                </div>


                <button class="submit">Submit</button>
            </form>

        </div>
    </div>




    <script defer src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.7/dist/js/bootstrap.bundle.min.js">
    </script>
    <script> document.addEventListener("DOMContentLoaded", () => {
            const searchIcon = document.getElementById("searchIcon");
            const searchBox = document.getElementById("searchBox");

            // Icona kliklə aç/gizlət
            searchIcon.addEventListener("click", (e) => {
                e.preventDefault();
                e.stopPropagation();
                searchBox.classList.toggle("active");

                if (searchBox.classList.contains("active")) {
                    searchBox.querySelector("input").focus();
                }
            });

            // Başqa yerə klik ediləndə bağla
            document.addEventListener("click", (e) => {
                // Arama kutusunu, ikonunu ve input alanını kontrol et
                const isClickInsideSearch = searchBox.contains(e.target) || e.target.closest('#searchIcon');
                if (!isClickInsideSearch && searchBox.classList.contains("active")) {
                    searchBox.classList.remove("active");
                }
            });
        });


        function toggleCartMenu() {
            const dropdown = document.getElementById("cartDropDown");
            dropdown.classList.toggle("active");

            // Kliklənmə zamanı menyunu bağlamaq
            document.addEventListener("click", function (event) {
                // Sepet konteynerini (butonu ve dropdown'u içerir) kontrol et
                const isClickInsideCart = event.target.closest(".cart-container");
                if (!isClickInsideCart && dropdown.classList.contains("active")) {
                    dropdown.classList.remove("active");
                }
            });
        }</script>
</body>

</html>

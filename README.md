# Apple-Restaurant
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
<style> * {
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
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            flex-wrap: wrap;
        }
        
        .content {
            font-size: 30px;
            padding-top: 250px;
            padding-left: 40px;
            color: #f8f9fa;
            background: linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.3)), url("img folder/background..jpg");
            background-size: cover;
            background-position: center;
            height: 100vh;
        }
        
        .content .h4 {
            margin-left: 2%;
        }
        
        .content .button {
            margin-top: 15px;
            margin-left: 10%;
            font-size: 20px;
            border: 1px solid;
            border-radius: 5px;
            font-family: Verdana, Geneva, Tahoma, sans-serif;
            cursor: pointer;
            background-color: black;
            color: white;
            padding: 6px;
            white-space: nowrap;
            transition: all 0.3s ease;
            display: inline-block;
        }
        
        .content .button:hover {
            transform: scale(1.1)
        }
        
        .menu {
            display: flex;
            list-style: none;
            gap: 15px;
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
        
        .menu-items {
            margin-left: 20px;
            font-size: 24px;
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
        
        .icon {
            display: flex;
        }
        
        .icon a span {
            justify-content: flex-end;
            font-size: 25px;
            margin-left: 10px;
            color: #FF9500;
            transition: all 0.3s ease;
            display: inline-block;
        }
        
        .icon a span:hover {
            transform: scale(1.4);
        }
        
        .img i {
            font-size: 40px;
            color: #e07f08;
            font-size: 40px;
            transition: all 0.3s ease;
            display: inline-block;
        }
        
        .img i:hover {
            transform: scale(1.4);
        }
        
        .search-container {
            position: relative;
            display: inline-block;
        }
        
        .fa-magnifying-glass {
            font-size: 1.7rem;
            cursor: pointer;
            padding-top: 10px;
            padding-right: 80px;
        }
        
        .search-box {
            height: 100px;
            position: absolute;
            top: 90px;
            right: 160px;
            opacity: 0;
            transition: all 0.4s ease-out;
        }
        
        .search-box.active {
            border-bottom-color: #007bff;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            opacity: 1;
            gap: 10px;
        }
        
        #searchIcon {
            cursor: pointer;
            font-size: 1.5rem;
            padding-top: 10px;
            padding-left: 30px;
        }
        
        .search-box input {
            height: 40px;
            width: 400px;
            padding: 8px 10px;
            border: 1px solid #ccc;
            border-radius: 10px;
            outline: #e07f08;
        }
        
        .cart-container {
            position: relative;
            display: inline-block;
        }
        
        .cart-icon {
            width: 250px;
            margin-right: 5px;
            padding: 10px 60px;
            background: #b36e00;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            transition: all 0.9s;
        }
        
        .cart-icon:hover {
            background: #d49a26;
        }
        
        .cart-dropdown {
            position: absolute;
            top: 100%;
            left: 0;
            width: 250px;
            background: white;
            box-shadow: 0 8px 16px rgba(0,0,0,0.2);
            border-radius: 4px;
            overflow: hidden;
            max-height: 0;
            transition: max-height 1s ease-out, opacity 0.3s ease;
            opacity: 0;
        }
        
        .cart-dropdown.active {
            max-height: 600px;
            opacity: 1;
        }
        
        .menuitems {
            text-decoration: none;
            color: black;
            width: 400px;
        }
        
        .menuitems .iconimg {
            width: 120px;
            height: 80px;
            margin-left: 5px;
        }
        
        .menuitems2 {
            text-decoration: none;
            color: black;
            width: 400px;
        }
        
        .menuitems2 .iconimg {
            margin-bottom: 7px;
            width: 130px;
            height: 70px;
            margin-left: 5px;
        }
        
        .menuitems3 {
            text-decoration: none;
            color: black;
            width: 400px;
        }
        
        .menuitems3 .iconimg {
            width: 130px;
            height: 90px;
            margin-right: 10px;
        }
        
        .menuitems4 {
            text-decoration: none;
            color: black;
            width: 400px;
        }
        
        .menuitems4 .iconimg {
            width: 140px;
            height: 70px;
        }
        
        .menuitems5 {
            text-decoration: none;
            color: black;
            width: 400px;
        }
        
        .menuitems5 .iconimg {
            width: 140px;
            height: 70px;
        }
        
        b .iconimg {
            vertical-align: middle;
        }
        
        .card-items img {
            padding-right: 20px;
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
            transition: all 0.9s;
            font-size: 19px;
        }
        
        .checkout-btn:hover {
            background: #d49a26;
        }
        
        .card-items a {
            display: inline-block;
            transition: all 0.4s ease;
            transform: translateZ(0);
        }
        
        .card-items a:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        
        .footer {
            display: flex;
            height: 1500px;
            width: 100%;
            clear: both;
            background-color: rgb(249, 135, 53);
            flex-wrap: wrap;
            justify-content: center;
        }
        
        .menu1 {
            height: 20px;
        }
        
        .menu1 .menuh1 {
            font-size: 40px;
            color: white;
            padding-top: 20px;
            padding-left: 45%;
            background-color: rgb(249, 135, 53);
        }
        
        .card {
            left: 75px;
            margin-top: 100px;
            margin-left: 15px;
            text-decoration: none;
            transition: all 0.4s ease;
            transform: translateZ(0);
            max-height: 500px;
        }
        
        .card .cards {
            text-decoration: none;
            color: black;
        }
        
        .card button {
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
            box-shadow: 0 4px 8px rgb(198, 122, 0);
        }
        
        .card .card-img-top1 {
            height: 250px;
            margin-top: 20px;
        }
        
        .card .card-img-top2 {
            height: 200px;
            margin-top: 20px;
        }
        
        .card-img-top3 {
            padding-top: 20px;
            height: 200px;
        }
        
        .card-img-top4 {
            height: 250px;
            padding-top: 3px;
        }
        
        .card-body .price2 {
            margin-top: 45px;
        }
        
        .card-body .price3 {
            margin-top: 60px;
        }
        
        .card:hover {
            transform: translateY(-8px) scale(1.05);
        }
        
        .end {
            display: flex;
            background-color: rgb(249, 135, 53);
            flex-wrap: wrap;
            justify-content: center;
        }
        
        .cartt {
            max-width: 450px;
            height: 550px;
            margin-top: -750px;
            margin-left: 110px;
            border-radius: 20px;
            background-color: white;
        }
        
        .cartt2 {
            max-width: 450px;
            height: 550px;
            margin-top: -750px;
            margin-left: 20px;
            border-radius: 20px;
            background-color: white;
        }
        
        .cartt3 {
            max-width: 450px;
            height: 550px;
            margin-top: -750px;
            margin-left: 20px;
            border-radius: 20px;
            background-color: white;
        }
        
        .cartt .burger {
            width: 550px;
            max-width: 100%;
        }
        
        .cartt2 .burger {
            width: 550px;
            max-width: 100%;
        }
        
        .cartt3 .burger {
            width: 550px;
            max-width: 100%;
        }
        
        .end p {
            font-size: 14px;
            padding-left: 45%;
            padding-top: 15px
        }
        
        .strong {
            font-size: 26px;
            margin-left: 10px;
        }
        
        .fa-cart-plus {
            margin-left: 310px;
            font-size: 40px;
            color: #b36e00;
        }
        
        .contact {
            transform: translateX();
            margin-top: -110px;
            margin-right: 5px;
        }
        
        .contact h1 {
            margin-left: -500%;
            font-size: 40px;
            color: white;
            background-color: rgb(249, 135, 53);
        }
        
        .contact2 {
            background-color: rgb(249, 135, 53);
            height: 500px;
        }
        
        .input-container {
            position: relative;
            background-color: #e0cfc7;
            margin-left: 350px;
            width: 800px;
            height: 350px;
            border-radius: 12px;
        }
        
        .input-container h2 {
            margin-top: 0;
            margin-left: 38%;
        }
        
        .input-name {
            padding-left: 30px;
            display: block;
            width: 600px;
            height: 40px;
            margin-left: 12%;
            margin-top: 40px;
            border-radius: 8px;
            border: 0px;
        }
        
        .input-email {
            padding-left: 30px;
            display: block;
            width: 600px;
            height: 40px;
            margin-left: 12%;
            margin-top: 40px;
            border-radius: 8px;
            border: 0px;
        }
        
        .input-number {
            padding-left: 30px;
            display: block;
            width: 600px;
            height: 40px;
            margin-left: 12%;
            margin-top: 40px;
            border: 0px;
            border-radius: 8px;
        }
        
        .submit {
            margin-top: 15px;
            margin-left: 45%
        }
        
        .user-icon {
            position: relative;
            margin-bottom: 20px;
        }
        
        .user-icon .fa-user-tie {
            position: absolute;
            margin-top: 13px;
            margin-left: 100px
        }
        
        .user-icon .fa-envelope-circle-check {
            position: absolute;
            margin-top: 55px;
            margin-left: 100px;
        }
        
        .user-icon .fa-phone-volume {
            position: absolute;
            margin-top: 55px;
            margin-left: 100px;
        }
        
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
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
            margin-top: 6px;
        }
        
        .submit:hover {
            background: linear-gradient(135deg, #ffb74d, #ff7043);
            transform: translateY(-3px);
            box-shadow: 0 6px 14px rgba(0,0,0,0.4);
        }
        
        .submit:active {
            transform: translateY(0);
            box-shadow: 0 2px 6px rgba(0,0,0,0.2);
        }
        
        .input-container {
            height: 400px;
        }
        
        /* Responsive dizayn üçün media sorğuları */
        @media (max-width: 1200px) {
            .content {
                padding-top: 200px;
                font-size: 26px;
            }
            
            .input-container {
                margin-left: 200px;
                width: 700px;
            }
        }
        
        @media (max-width: 900px) {
            .navbar {
                flex-direction: column;
                padding: 15px;
            }
            
            .menu {
                margin-top: 15px;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .content {
                padding-top: 150px;
                padding-left: 20px;
                font-size: 22px;
                text-align: center;
            }
            
            .content .button {
                margin-left: 0;
            }
            
            .footer {
                height: auto;
                padding-bottom: 50px;
            }
            
            .card {
                margin: 30px auto;
                left: 0;
            }
            
            .end {
                flex-direction: column;
                align-items: center;
            }
            
            .cartt, .cartt2, .cartt3 {
                margin: 20px 0;
                max-width: 90%;
            }
            
            .input-container {
                margin: 0 auto;
                width: 90%;
            }
            
            .input-name, .input-email, .input-number {
                width: 90%;
                margin-left: 5%;
            }
            
            .input-container h2 {
                margin-left: 0;
                text-align: center;
            }
            
            .submit {
                margin-left: 40%;
            }
        }
        
        @media (max-width: 768px) {
            .menu {
                flex-direction: column;
                align-items: center;
                gap: 10px;
            }
            
            .menu a {
                font-size: 20px;
                padding: 5px 10px;
            }
            
            .content {
                padding-top: 120px;
                font-size: 18px;
            }
            
            .content .button {
                font-size: 16px;
                padding: 8px 16px;
            }
            
            .search-box input {
                width: 300px;
            }
            
            .cart-icon {
                width: 200px;
                padding: 10px 30px;
            }
            
            .menu1 .menuh1 {
                padding-left: 0;
                text-align: center;
            }
            
            .user-icon .fa-user-tie,
            .user-icon .fa-envelope-circle-check,
            .user-icon .fa-phone-volume {
                margin-left: 30px;
            }
            
            .contact h1 {
                margin-left: 0;
                text-align: center;
            }
        }
        
        @media (max-width: 576px) {
            .content {
                padding-top: 100px;
                font-size: 16px;
            }
            
            .img i {
                font-size: 30px;
            }
            
            .icon a span {
                font-size: 20px;
            }
            
            .search-box input {
                width: 250px;
                right: 0;
            }
            
            .cart-icon {
                width: 150px;
                padding: 8px 15px;
                font-size: 14px;
            }
            
            .card {
                width: 90% !important;
                margin-left: 0;
            }
            
            .input-container {
                height: auto;
                padding: 20px 0;
            }
            
            .input-name, .input-email, .input-number {
                width: 85%;
            }
            
            .submit {
                margin-left: 35%;
                padding: 10px 20px;
            }
            
            .fa-cart-plus {
                margin-left: 200px;
            }
            
            .end p {
                padding-left: 35%;
            }
        }
        
        @media (max-width: 400px) {
            .content {
                padding-top: 80px;
                font-size: 14px;
            }
            
            .content .button {
                font-size: 14px;
            }
            
            .search-box input {
                width: 200px;
            }
            
            .menu a {
                font-size: 18px;
            }
            
            .card {
                width: 100% !important;
            }
            
            .input-container {
                
                width: 95%;
                margin-left: 2.5%;
            }
            
            .input-name, .input-email, .input-number {
                width: 95%;
                margin-left: 2.5%;
            }
            
            .submit {
                margin-left: 30%;
            }
            
            .fa-cart-plus {
                margin-left: 150px;
                font-size: 30px;
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
  <a href="#"> <li class="menu-items">Home</li> </a>
    <a href="#"><li class="menu-items">Menu</li> </a> 
     <a href="#"><li class="menu-items">Blogs</li></a>  
     <a href="#"><li class="menu-items">About us</li> </a> 
     <a href="#"><li class="menu-items">Contact</li> </a> 
        </ul> 
 <div class="icon">
    
            
            <div class="search-container"><a href="#" id="searchIcon"> <span><i class="fa-solid fa-magnifying-glass"></i> </span></a></div>
           <div class="search-box" id="searchBox">
            <input type="text" placeholder="Search here:">
           </div>
           <div class="cart-container">
             
               <button class="cart-icon" onclick="toggleCartMenu()">
                Shopping Card
                </button>
 
             <div class="cart-dropdown" id="cartDropDown">
             <div class="cart-content">
                
                <div class="card-items">
                    
                    <a href="" class="menuitems"><b><img src="img folder/menu.png" class="iconimg" alt=""> Item 1/ 
                           <i class="pizza">$6.00</i>
                    </b></a>
                     <a href="" class="menuitems2"><b><img src="img folder/menu2.png" class="iconimg" alt=""> Item 2/ 
                           <i class="pizza">$8.00</i>
                    </b></a>
                     <a href="" class="menuitems3"><b><img src="img folder/menu3.png" class="iconimg" alt=""> Item 3/ 
                           <i class="pizza">$11.00</i>
                    </b></a>
                     <a href="" class="menuitems4"><b><img src="img folder/menu4.png" class="iconimg" alt=""> Item 4/ 
                           <i class="pizza">$9.00</i>
                    </b></a>
                     <a href="" class="menuitems5"><b><img src="img folder/menu5.png" class="iconimg" alt=""> Item 5/ 
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
  <img src="img folder/menu.png" class="card-img-top1  " alt="...">
  <div class="card-body ">
      <h5>5 Middle Burgers</h5>
    <del>$110</del>
    <h4>$92</h4>
  </div>
  <button>Add Cart</button></a>
</div>

     <div class="card" style="width: 20rem;"> <a href="#" class="cards">
  <img src="img folder/menu2.png" class="card-img-top2  " alt="...">
  <div class="card-body ">
    <div class="price2">
   <h5>5 Mini Burgers</h5>
    <del>$95</del>
    <h4>$71</h4>
    </div>
  </div>
   <button>Add Cart</button></a>
</div> 
   <div class="card" style="width: 20rem;">   <a href="#" class="cards">
  <img src="img folder/menu5.png" class="card-img-top3 " alt="...">
  <div class="card-body ">
    <div class="price3">
    <h5>5 Mini Sandwichs</h5>
    <del>$100</del>
    <h4>$85</h4>
    </div>
    
  </div>
   <button>Add Cart</button></a>
</div>
    <div class="card  d-flex flex-column" style="width: 20rem;"> <a href="#" class="cards">
  <img src="img folder/menu.png" class="card-img-top4  " alt="...">
  <div class="card-body ">
    <h5>6 Big Burgers</h5>
     <del>$130</del>
    <h4>$100</h4>
     
  </div>
  <button>Add Cart</button></a>
</div> 

</div>

<div class="end">
<div class="cartt">
    <p>BIG Burger</p>
    <h1>Beef Burger</h1>
    <img src="img folder/menu.png" alt="" class="burger">
    
     <strong class="strong">$17</strong>
     <i class="fa-solid fa-cart-plus"></i>
  </div>
  <div class="cartt2">
    <p>BIG Burger</p>
    <h1>Mutton Burger</h1>
    <img src="img folder/menu.png" alt="" class="burger">
   
     <strong class="strong">$10</strong>
      <i class="fa-solid fa-cart-plus"></i>
  </div>
   <div class="cartt3">
    <p>BIG Burger</p>
    <h1>Chicken Burger</h1>
    <img src="img folder/menu.png" alt="" class="burger">
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
            <input type="text"id="name" name="name" placeholder="Your Name" class="input-name">
            <i class="fa-solid fa-envelope-circle-check"></i>
             <input type="email"placeholder="Email" class="input-email">
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
    if (!searchBox.contains(e.target) && e.target !== searchIcon) {
      searchBox.classList.remove("active");
    }
  });
});


function toggleCartMenu() {
  const dropdown = document.getElementById("cartDropDown");
  dropdown.classList.toggle("active");
  
  // Kliklənmə zamanı menyunu bağlamaq
  document.addEventListener("click", function(event) {
    if (!event.target.closest(".cart-container")) {
      dropdown.classList.remove("active");
    }
  });
}</script>
</body>
</html>

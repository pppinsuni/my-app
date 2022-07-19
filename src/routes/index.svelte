<script>
// import { Scroll, Nav } from "@src/components/button";

</script>
<!-- import { scroll } from "@src/components/button";
import { nav } from "@src/components/button"; -->


<style>
  *{
    padding:0;
    margin:0;
    box-sizing: border-box;
}
body{
    color:black;
    font-family: 'M PLUS 1', sans-serif;
}
/* html{
    scroll-behavior: smooth;
} */
.desktop{
    display:none;
}
@media (min-width: 768px) {
    .desktop{
        display: initial;
    }
}
header{
    display:grid;
    grid-template-columns: auto 1fr auto;
    padding : 5px 20px;
    position: fixed;
    top:0;
    z-index: 2;
    width:100%;
}
a.logo{
    height:12px;
    width:100px;
    color:inherit;
}
header a{
    color:inherit;
}
header nav a{
    text-decoration:none;
    padding: 1px 10px;
}
header nav.center{
    text-align: center;
}
header nav.right{
    text-align: right;
}
section{
    height:100vh;
    background-size: cover;
    background-position: center center;
}
section .content{
    opacity:0;
    position:fixed;
    width: 100%;
    top:0;
    transition: opacity .3s ease;
    height:100vh;
    padding-top:15vh;
    padding-bottom:15vh;
    text-align:center;
    display:grid;
    grid-template-rows: min-content auto min-content;
}
section.active .content{
    opacity:1;
}
section h1 {
    font-size:3rem;
}
section a {
    color:inherit;
}
section .buttons a {
    display:block;
    background-color: #eee;
    color:inherit;
    padding:12px 50px;
    border-radius: 25px;
    text-decoration: none;
    text-transform: uppercase;
    font-size: 12px;
    font-weight: 500;
}
section .buttons a:first-child {
    background-color: #444;
    color:#fff;
}
section .buttons {
    display: grid;
    row-gap: 20px;
    margin:0 40px;
}
@media (min-width: 768px){
    section .buttons{
        max-width: 648;
        margin: 0 auto;
        grid-template-columns: 1fr 1fr;
        column-gap:20px;
    }
}

aside{
    position:fixed;
    transition:right .4s ease;
    right:-320px;
    width:320px;
    background-color: #fff;
    padding:80px 40px;
    z-index:4;
    height:100vh;
}
aside.active{
    right:0;
}
aside a{
    display:block;
    color:inherit;
    text-decoration: none;
    padding: 12px 0;
    font-size:14px;
    font-weight: 500;
}
aside button.close{
    font-size:24px;
    border:0;
    background-color: transparent;
    position:absolute;
    top:10px;
    right:10px;
    padding:10px;
    font-family: sans-serif;
    font-weight:100;
    cursor:pointer;
}
.backdrop {
    display: none;
    position: fixed;
    z-index: 3;
    inset: 0;
    background-color: rgba(0,0,0,0);
    transition: background-color .4s ease;
    backdrop-filter: blur(5px);
}
.backdrop.active {
    display: block;
    background-color: rgba(0,0,0,.35);
}  
</style>


<head> 
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=M+PLUS+1&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <a href=" " class="logo">
      <svg class="tds-icon tds-icon-logo-wordmark tds-site-logo-icon" viewBox="0 0 342 35" xmlns="http://www.w3.org/2000/svg"><path d="M0 .1a9.7 9.7 0 007 7h11l.5.1v27.6h6.8V7.3L26 7h11a9.8 9.8 0 007-7H0zm238.6 0h-6.8v34.8H263a9.7 9.7 0 006-6.8h-30.3V0zm-52.3 6.8c3.6-1 6.6-3.8 7.4-6.9l-38.1.1v20.6h31.1v7.2h-24.4a13.6 13.6 0 00-8.7 7h39.9v-21h-31.2v-7h24zm116.2 28h6.7v-14h24.6v14h6.7v-21h-38zM85.3 7h26a9.6 9.6 0 007.1-7H78.3a9.6 9.6 0 007 7zm0 13.8h26a9.6 9.6 0 007.1-7H78.3a9.6 9.6 0 007 7zm0 14.1h26a9.6 9.6 0 007.1-7H78.3a9.6 9.6 0 007 7zM308.5 7h26a9.6 9.6 0 007-7h-40a9.6 9.6 0 007 7z" fill="currentColor"></path></svg>
    </a>
    <nav class="center desktop">
      <a href=" ">Model S
      <a href=" ">Model 3</a>
      <a href=" ">Model X</a>
      <a href=" ">Model Y</a>
      <a href=" ">Cybertruck</a>
      <a href=" ">Powerwall</a>
    </nav>
    <nav class="right desktop">
      <a href=" " class="desktop">Shop</a>
      <a href=" " class="desktop">Account</a>
      <a href=" " id="menuBtn">Menu</a>
    </nav>
  </header>
  <div class="backdrop"></div>
  <aside>
    <button class="close">&times;</button>
    <a href=" ">신규 인벤토리</a>
    <a href=" ">인증중고 인벤토리</a>
    <a href=" ">보상 판매</a>
    <a href=" ">Roadster</a>
    <a href=" ">충전</a>
    <a href=" ">상업용 에너지</a>
    <a href=" ">공익사업</a>
    <a href=" ">에너지</a>
    <a href=" ">법인 판매</a>
    <a href=" ">Tesla 찾기</a>
    <a href=" ">이벤트</a>
    <a href=" ">지원</a>
    <a href=" ">투자자 정보</a>
  </aside>

  <section style="background-image: url('@src/components/images/tesla/model-s.jpg')" class="active">
    <div class="content">
      <h1>Model S</h1>
      <p>
        Order Online for 
        <a href=" ">Touchless Delivery</a>
      </p>
      <div class="buttons">
        <a href=" ">custom order</a>
        <a href=" ">existing inventory</a>
      </div>
    </div>
  </section>
  <section style="background-image: url('../components/images/tesla/model-3.jpg')" >
    <div class="content">
      <h1>Model S</h1>
      <p>
        Order Online for 
        <a href=" ">Touchless Delivery</a>
      </p>
      <div class="buttons">
        <a href=" ">custom order</a>
        <a href=" ">existing inventory</a>
      </div>
    </div>
  </section>
  <section style="background-image: url('../components/images/tesla/model-x.jpg')" >
    <div class="content">
      <h1>Model X</h1>
      <p>
        Order Online for 
        <a href=" ">Touchless Delivery</a>
      </p>
      <div class="buttons">
        <a href=" ">custom order</a>
        <a href=" ">existing inventory</a>
      </div>
    </div>
  </section>
  <section style="background-image: url('../components/images/tesla/model-y.jpg')"></section>
  <section style="background-image: url('../components/images/tesla/solarpanels.jpg')"></section>
  <section style="background-image: url('../components/images/tesla/roof.jpg')"></section>
  <section style="background-image: url('@src/components/images/tesla/roof.jpg')"></section>
  <script src="@src/components/buttons/nav.js"></script>
  <script src="@src/components/buttons/scroll.js"></script>
</body>
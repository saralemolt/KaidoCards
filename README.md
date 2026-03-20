<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>KaidoCards</title>
<style>
body{font-family: 'Comic Sans MS', cursive; margin:0; background:#f5efe6; color:#2c2c2c}
header{background:#2f2a4a; color:white; padding:20px; text-align:center}
nav{display:flex; justify-content:center; gap:20px; background:#4b4570; padding:10px}
nav a{color:white; text-decoration:none; font-weight:bold}
section{padding:40px}
.card{background:white; padding:20px; border-radius:10px; margin:10px; box-shadow:0 4px 10px rgba(0,0,0,0.1)}
button{background:#6b63a8; border:none; color:white; padding:10px 15px; border-radius:8px; cursor:pointer}
button:hover{background:#524a8a}
#cart{position:fixed; right:0; top:0; background:white; width:250px; height:100%; box-shadow:-3px 0 10px rgba(0,0,0,0.2); padding:20px; overflow:auto}
footer{background:#2f2a4a; color:white; text-align:center; padding:15px}
</style>
</head>
<body>

<header>
<h1>KaidoCards</h1>
<p>Een kaartspel door studenten, voor studenten</p>
</header>

<nav>
<a href="#home">Home</a>
<a href="#spel">Het Spel</a>
<a href="#bestellen">Bestellen</a>
<a href="#about">Over Ons</a>
<a href="#contact">Contact</a>
</nav>

<section id="home">
<h2>Welkom!</h2>
<p>Verwacht magie, chaos, strategie en een beetje humor.</p>
</section>

<section id="spel">
<h2>Hoe werkt het spel?</h2>
<p>Spelregels:</p>
Wat zit er in het spel 40: Vraagkaarten 12: Speciale kaarten Totaal 52 kaarten 
<div class="card">
<h3>Doel van het spel</h3>
<p> </p>
</div>

<div class="card">
<h3>Kaarttypes</h3>
<ul>
<li>⚔️ Aanval kaarten</li>
<li>🛡️ Verdediging kaarten</li>
<li>✨ Mythische kaarten</li>
<li>😈 Chaos kaarten</li>
</ul>
</div>

<div class="card">
<h3>Speelduur</h3>
<p>Ongeveer 20-40 minuten per spel.</p>
</div>
</section>

<section id="bestellen">
<h2>Bestel het Spel</h2>
<div class="card">
<h3>Starter Deck</h3>
<p>Prijs: €15</p>
<button onclick="addToCart('Starter Deck',15)">Toevoegen aan winkelwagen</button>
</div>

<div class="card">
<h3>Deluxe Deck</h3>
<p>Prijs: €25</p>
<button onclick="addToCart('Deluxe Deck',25)">Toevoegen aan winkelwagen</button>
</div>
</section>

<section id="about">
<h2>Over Ons</h2>
<p>Wij zijn een groep studenten die een kaartspel wilden maken dat leuk, grappig en een beetje chaotisch is. Ons doel is om een spel te maken dat studenten samenbrengt tijdens studie pauzes, feestjes of gewoon voor de lol.</p>
</section>

<section id="contact">
<h2>Contact</h2>
<p>Heb je vragen of ideeën? Stuur ons een bericht!</p>

<form>
<label>Naam:</label><br>
<input type="text"><br><br>

<label>Email:</label><br>
<input type="email"><br><br>

<label>Bericht:</label><br>
<textarea></textarea><br><br>

<button type="submit">Versturen</button>
</form>
</section>

<div id="cart">
<h2>🛒 Winkelwagen</h2>
<ul id="cartItems"></ul>
<p><strong>Totaal: €<span id="total">0</span></strong></p>
<button onclick="checkout()">Bestellen</button>
</div>

<footer>
<p>© 2026 Studenten Kaartspel</p>
</footer>

<script>
let cart=[];

function addToCart(name,price){
cart.push({name,price});
updateCart();
}

function updateCart(){
const cartList=document.getElementById('cartItems');
const totalEl=document.getElementById('total');
cartList.innerHTML='';
let total=0;

cart.forEach(item=>{
let li=document.createElement('li');
li.textContent=item.name+' - €'+item.price;
cartList.appendChild(li);

 total+=item.price;
});

totalEl.textContent=total;
}

function checkout(){
if(cart.length===0){
alert('Je winkelwagen is leeg!');
}else{
alert('Bedankt voor je bestelling! (Dit is een demo checkout)');
cart=[];
updateCart();
}
}
</script>

</body>
</html>

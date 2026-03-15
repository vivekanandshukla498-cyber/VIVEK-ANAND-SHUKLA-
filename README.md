<section id="register" class="py-20 text-center bg-slate-100">

<h2 class="text-3xl font-bold mb-8">
Register to Access Ideas
</h2>

<div class="max-w-md mx-auto space-y-4">

<input id="name" placeholder="Full Name" class="border p-3 w-full">

<input id="age" placeholder="Age" class="border p-3 w-full">

<input id="phone" placeholder="Phone Number" class="border p-3 w-full">

<input id="email" placeholder="Email" class="border p-3 w-full">

<input id="password" type="password" placeholder="Password" class="border p-3 w-full">

<button onclick="registerUser()"
class="bg-blue-600 text-white px-6 py-2 rounded">

Register
</button>

<p id="registerStatus"></p>

</div>

</section><script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-auth.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore.js"></script>
<script>

function registerUser(){

let email=document.getElementById("email").value
let password=document.getElementById("password").value

auth.createUserWithEmailAndPassword(email,password)

.then(userCredential=>{

let user=userCredential.user

user.sendEmailVerification()

document.getElementById("registerStatus").innerText=
"Verification email sent. Please verify."

})

.catch(error=>{
document.getElementById("registerStatus").innerText=error.message
})

}

</script>
async function askAI(){

let question=document.getElementById("question").value

let response=await fetch("/api/ai",{

method:"POST",

body:JSON.stringify({question})

})

let data=await response.json()

document.getElementById("response").innerText=data.answer

}
<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Vivek Anand Shukla | AI Innovation Platform</title>

<script src="https://cdn.tailwindcss.com"></script>

<link rel="stylesheet"
href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"/>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

</head>

<body class="bg-slate-50 text-gray-800">

<!-- NAVBAR -->

<header class="bg-black text-white p-4 sticky top-0">

<div class="max-w-6xl mx-auto flex justify-between">

<h1 class="font-bold text-xl">
Vivek Anand Shukla
</h1>

<nav class="space-x-4 text-sm">

<a href="#about">About</a>
<a href="#projects">Projects</a>
<a href="#cosmos">Cosmos</a>
<a href="#map">Map</a>
<a href="#ai">AI</a>
<a href="#register">Register</a>
<a href="#ideas">Ideas</a>
<a href="#contact">Contact</a>

</nav>

</div>

</header>

<!-- HERO -->

<section class="bg-blue-600 text-white text-center py-24">

<h2 class="text-4xl font-bold mb-4">

AI • Startup Innovation • Space Research

</h2>

<p>

Technology platform by Vivek Anand Shukla

</p>

</section>

<!-- ABOUT -->

<section id="about" class="py-20 text-center">

<img src="yourphoto.jpg"
class="w-40 rounded-full mx-auto shadow mb-6">

<h3 class="text-3xl font-bold">
About Me
</h3>

<p class="max-w-2xl mx-auto mt-4">

Researching artificial intelligence,
transport systems and universe science.

</p>

</section>

<!-- PROJECTS -->

<section id="projects" class="py-20 bg-white text-center">

<h3 class="text-3xl font-bold mb-10">
Projects
</h3>

<div class="grid md:grid-cols-3 gap-6 max-w-5xl mx-auto">

<div class="shadow p-6 rounded">
AI Research
</div>

<div class="shadow p-6 rounded">
Transport Innovation
</div>

<div class="shadow p-6 rounded">
Startup Ideas
</div>

</div>

</section>

<!-- MAP -->

<section id="map" class="py-20 text-center">

<h3 class="text-3xl font-bold mb-10">
Global Network
</h3>

<div id="worldMap" style="height:400px;max-width:900px;margin:auto"></div>

</section>

<script>

var map=L.map('worldMap').setView([20,0],2)

L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png')
.addTo(map)

L.marker([28.4595,77.0266])
.addTo(map)
.bindPopup("Gurgaon - India")

</script>

<!-- COSMOS -->

<section id="cosmos" class="py-20 bg-black text-white text-center">

<h3 class="text-3xl font-bold mb-10">
Cosmos Explorer
</h3>

<div id="planet" style="height:300px"></div>

</section>

<script>

const scene=new THREE.Scene()

const camera=new THREE.PerspectiveCamera(75,1,0.1,1000)

const renderer=new THREE.WebGLRenderer()

renderer.setSize(300,300)

document.getElementById("planet").appendChild(renderer.domElement)

const geometry=new THREE.SphereGeometry(2,32,32)

const material=new THREE.MeshBasicMaterial({color:0x3399ff})

const planet=new THREE.Mesh(geometry,material)

scene.add(planet)

camera.position.z=5

function animate(){

requestAnimationFrame(animate)

planet.rotation.y+=0.01

renderer.render(scene,camera)

}

animate()

</script>

<!-- AI ASSISTANT -->

<section id="ai" class="py-20 text-center">

<h3 class="text-3xl font-bold mb-6">
AI Assistant
</h3>

<input id="question"
class="border p-3 rounded"
placeholder="Ask any question">

<button onclick="askAI()"
class="bg-blue-600 text-white px-4 py-2 rounded">

Ask AI

</button>

<p id="answer" class="mt-4"></p>

</section>

<script>

function askAI(){

let q=document.getElementById("question").value

document.getElementById("answer").innerText =
"AI answer will appear here after API connection."

}

</script>

<!-- REGISTER -->

<section id="register" class="py-20 bg-slate-100 text-center">

<h3 class="text-3xl font-bold mb-8">
Register
</h3>

<div class="max-w-md mx-auto space-y-3">

<input placeholder="Full Name" class="border p-3 w-full">
<input placeholder="Age" class="border p-3 w-full">
<input placeholder="Phone Number" class="border p-3 w-full">
<input placeholder="Email" class="border p-3 w-full">
<input placeholder="Password" type="password"
class="border p-3 w-full">

<button class="bg-green-600 text-white px-6 py-2 rounded">
Create Account
</button>

</div>

</section>

<!-- IDEAS -->

<section id="ideas" class="py-20 text-center">

<h3 class="text-3xl font-bold mb-8">
Startup Ideas Platform
</h3>

<p>

Members will access innovation ideas after verification.

</p>

</section>

<!-- VISITOR COUNTER -->

<section class="text-center py-10">

<p id="visits"></p>

</section>

<script>

let v=localStorage.getItem("visits")

if(!v){v=1}else{v++}

localStorage.setItem("visits",v)

document.getElementById("visits").innerText="Visitors: "+v

</script>

<!-- CONTACT -->

<section id="contact" class="py-20 text-center">

<h3 class="text-3xl font-bold mb-6">
Contact
</h3>

<p>
vivekanandshukla498@gmail.com
</p>

</section>

<footer class="text-center py-10">

<a href="https://www.linkedin.com/in/vivek-anand-shukla-0a55a7377">LinkedIn</a> |
<a href="https://www.instagram.com/iamvvk.18">Instagram</a> |
<a href="https://www.facebook.com/share/1AeZmAq7Jd/">Facebook</a> |
<a href="https://x.com/VivekSh09712505">X</a> |
<a href="https://youtube.com/@vivekanandshukla4168">YouTube</a>

</footer>

</body>
</html>
<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">

<title>Vivek Anand Shukla | AI & Startup Platform</title>

<meta name="description"
content="Official website of Vivek Anand Shukla – AI research, transport innovation and startup ideas.">

<script src="https://cdn.tailwindcss.com"></script>

<link rel="stylesheet"
href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"/>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<script src="//unpkg.com/three"></script>
<script src="//unpkg.com/globe.gl"></script>

</head>

<body class="bg-slate-50 text-slate-800">

<!-- NAVBAR -->

<header class="bg-white shadow sticky top-0">

<div class="max-w-6xl mx-auto flex justify-between p-4">

<h1 class="font-bold text-xl">
Vivek Anand Shukla
</h1>

<nav class="space-x-4 text-sm">

<a href="#about">About</a>
<a href="#projects">Projects</a>
<a href="#maps">Maps</a>
<a href="#ai">AI</a>
<a href="#blog">Blog</a>
<a href="#pricing">Plans</a>
<a href="#login">Login</a>
<a href="#contact">Contact</a>

</nav>

</div>

</header>


<!-- HERO -->

<section class="bg-blue-600 text-white text-center py-24">

<h2 class="text-4xl font-bold mb-4">

AI • Logistics • Business Innovation

</h2>

<p>

Technology platform by Vivek Anand Shukla

</p>

</section>


<!-- ABOUT -->

<section id="about" class="py-20 text-center">

<img src="yourphoto.jpg"
class="w-40 rounded-full mx-auto shadow mb-6">

<h3 class="text-3xl font-bold">
About Me
</h3>

<p class="max-w-2xl mx-auto mt-4">

I explore artificial intelligence, transport logistics,
and startup innovation.

</p>

</section>


<!-- PROJECTS -->

<section id="projects" class="py-20 bg-white text-center">

<h3 class="text-3xl font-bold mb-10">
Projects
</h3>

<div class="grid md:grid-cols-3 gap-6 max-w-5xl mx-auto">

<div class="shadow p-6 rounded">
<h4>AI Research</h4>
<p>Artificial intelligence applications.</p>
</div>

<div class="shadow p-6 rounded">
<h4>Transport Innovation</h4>
<p>Smart logistics systems.</p>
</div>

<div class="shadow p-6 rounded">
<h4>Startup Ideas</h4>
<p>Digital entrepreneurship concepts.</p>
</div>

</div>

</section>


<!-- MAPS -->

<section id="maps" class="py-20 text-center">

<h3 class="text-3xl font-bold mb-10">
Global Network
</h3>

<div class="grid md:grid-cols-3 gap-8 max-w-6xl mx-auto">

<div>
<h4>3D Earth</h4>
<div id="globe" style="height:300px"></div>
</div>

<div>
<h4>World Map</h4>
<div id="worldMap" style="height:300px"></div>
</div>

<div>
<h4>India Map</h4>
<div id="indiaMap" style="height:300px"></div>
</div>

</div>

</section>


<script>

const globe = Globe()(document.getElementById('globe'))
.globeImageUrl('//unpkg.com/three-globe/example/img/earth-blue-marble.jpg')

var worldMap=L.map('worldMap').setView([20,0],2)

L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png')
.addTo(worldMap)

L.marker([28.6139,77.2090])
.addTo(worldMap)
.bindPopup("India")

var indiaMap=L.map('indiaMap').setView([22.97,78.65],5)

L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png')
.addTo(indiaMap)

L.marker([28.4595,77.0266])
.addTo(indiaMap)
.bindPopup("Gurgaon")

</script>


<!-- AI -->

<section id="ai" class="py-20 bg-slate-100 text-center">

<h3 class="text-3xl font-bold mb-6">

AI Assistant

</h3>

<input
id="question"
class="border p-3 rounded"
placeholder="Ask anything">

<button
onclick="askAI()"
class="bg-blue-600 text-white px-4 py-2 rounded">

Ask

</button>

<p id="response" class="mt-4"></p>

</section>


<script>

function askAI(){

document.getElementById("response").innerText =
"AI responses will appear here after API connection."

}

</script>


<!-- BLOG -->

<section id="blog" class="py-20 text-center">

<h3 class="text-3xl font-bold mb-10">
Blog
</h3>

<p>

Articles about AI, logistics and startups.

</p>

</section>


<!-- PRICING -->

<section id="pricing" class="py-20 text-center">

<h3 class="text-3xl font-bold mb-10">

Membership Plans

</h3>

<div class="grid md:grid-cols-3 gap-6 max-w-5xl mx-auto">

<div class="shadow p-6">
<h4>Free Trial</h4>
<p>7 Days Free</p>
</div>

<div class="shadow p-6">
<h4>Monthly</h4>
<p>₹499</p>
</div>

<div class="shadow p-6">
<h4>Annual</h4>
<p>₹3999</p>
</div>

</div>

</section>


<!-- LOGIN -->

<section id="login" class="py-20 text-center bg-slate-100">

<h3 class="text-3xl font-bold mb-6">
Member Login
</h3>

<input placeholder="Email" class="border p-3 m-2">
<input placeholder="Password" class="border p-3 m-2">

<br>

<button class="bg-blue-600 text-white px-4 py-2 rounded">
Login
</button>

</section>


<!-- VISITOR COUNTER -->

<section class="text-center py-10">

<p id="visits"></p>

</section>


<script>

let v=localStorage.getItem("visits")

if(!v){v=1}else{v++}

localStorage.setItem("visits",v)

document.getElementById("visits").innerText="Visitors: "+v

</script>


<!-- CONTACT -->

<section id="contact" class="py-20 text-center">

<h3 class="text-3xl font-bold mb-6">
Contact
</h3>

<p>
vivekanandshukla498@gmail.com
</p>

</section>


<!-- SOCIAL -->

<footer class="text-center py-10">

<a href="https://www.linkedin.com/in/vivek-anand-shukla-0a55a7377">LinkedIn</a> |
<a href="https://www.instagram.com/iamvvk.18">Instagram</a> |
<a href="https://www.facebook.com/share/1AeZmAq7Jd/">Facebook</a> |
<a href="https://x.com/VivekSh09712505">X</a> |
<a href="https://youtube.com/@vivekanandshukla4168">YouTube</a>

</footer>

</body>
</html>
<section id="cosmos" class="py-24 bg-black text-white text-center">

<h2 class="text-4xl font-bold mb-10">
Cosmos & Universe Exploration
</h2>

<p class="max-w-3xl mx-auto mb-12">
Explore planets, galaxies, and the mysteries of space through 3D simulations.
</p>

<div class="grid md:grid-cols-3 gap-10 max-w-6xl mx-auto">

<div>
<h3 class="text-xl mb-4">Earth</h3>
<div id="earth3d" style="height:300px"></div>
</div>

<div>
<h3 class="text-xl mb-4">Mars</h3>
<div id="mars3d" style="height:300px"></div>
</div>

<div>
<h3 class="text-xl mb-4">Saturn</h3>
<div id="saturn3d" style="height:300px"></div>
</div>

</div>

</section>
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

<script>

function createPlanet(container, textureURL){

const scene = new THREE.Scene()

const camera = new THREE.PerspectiveCamera(75,1,0.1,1000)

const renderer = new THREE.WebGLRenderer()

renderer.setSize(300,300)

document.getElementById(container).appendChild(renderer.domElement)

const geometry = new THREE.SphereGeometry(2,32,32)

const texture = new THREE.TextureLoader().load(textureURL)

const material = new THREE.MeshBasicMaterial({map:texture})

const planet = new THREE.Mesh(geometry,material)

scene.add(planet)

camera.position.z = 5

function animate(){

requestAnimationFrame(animate)

planet.rotation.y += 0.003

renderer.render(scene,camera)

}

animate()

}

createPlanet("earth3d","https://threejs.org/examples/textures/earth_atmos_2048.jpg")

createPlanet("mars3d","https://threejs.org/examples/textures/mars_1k_color.jpg")

createPlanet("saturn3d","https://threejs.org/examples/textures/planets/saturn.jpg")

</script>
<section id="cosmos" class="py-24 bg-black text-white text-center">

<h2 class="text-4xl font-bold mb-10">
Cosmos Explorer
</h2>

<p class="max-w-3xl mx-auto mb-12">
Explore the planets of our solar system in 3D.
</p>

<div class="grid md:grid-cols-4 gap-8 max-w-6xl mx-auto">

<div>
<h3>Mercury</h3>
<div id="mercury"></div>
</div>

<div>
<h3>Venus</h3>
<div id="venus"></div>
</div>

<div>
<h3>Earth</h3>
<div id="earth"></div>
</div>

<div>
<h3>Mars</h3>
<div id="mars"></div>
</div>

<div>
<h3>Jupiter</h3>
<div id="jupiter"></div>
</div>

<div>
<h3>Saturn</h3>
<div id="saturn"></div>
</div>

<div>
<h3>Uranus</h
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

<script>

function createPlanet(id,color){

const scene=new THREE.Scene()

const camera=new THREE.PerspectiveCamera(75,1,0.1,1000)

const renderer=new THREE.WebGLRenderer()

renderer.setSize(200,200)

document.getElementById(id).appendChild(renderer.domElement)

const geometry=new THREE.SphereGeometry(2,32,32)

const material=new THREE.MeshBasicMaterial({color:color})

const planet=new THREE.Mesh(geometry,material)

scene.add(planet)

camera.position.z=5

function animate(){

requestAnimationFrame(animate)

planet.rotation.y+=0.01

renderer.render(scene,camera)

}

animate()

}

createPlanet("mercury",0xaaaaaa)
createPlanet("venus",0xffcc88)
createPlanet("earth",0x3399ff)
createPlanet("mars",0xff5533)
createPlanet("jupiter",0xffaa66)
createPlanet("saturn",0xffddaa)
createPlanet("uranus",0x66ffff)
createPlanet("neptune",0x3366ff)

</script>
<section id="universe" class="py-24 bg-black text-white text-center">

<h2 class="text-4xl font-bold mb-10">
Universe Explorer
</h2>

<p class="max-w-3xl mx-auto mb-12">
Discover planets, galaxies, black holes and cosmic mysteries.
</p>

<div class="grid md:grid-cols-3 gap-10 max-w-6xl mx-auto">

<div class="p-6 bg-gray-900 rounded">
<h3 class="text-xl mb-3">Galaxies</h3>
<p>
Billions of galaxies exist in the universe.
Each contains millions or billions of stars.
</p>
</div>

<div class="p-6 bg-gray-900 rounded">
<h3 class="text-xl mb-3">Black Holes</h3>
<p>
Extremely dense objects whose gravity is so strong
that even light cannot escape.
</p>
</div>

<div class="p-6 bg-gray-900 rounded">
<h3 class="text-xl mb-3">Dark Matter</h3>
<p>
Invisible matter believed to make up most of
the mass in the universe.
</p>
</div>

</div>

</section>
<script>

const canvas=document.createElement("canvas")

document.body.appendChild(canvas)

canvas.style.position="fixed"
canvas.style.top="0"
canvas.style.left="0"
canvas.style.zIndex="-1"

const ctx=canvas.getContext("2d")

canvas.width=window.innerWidth
canvas.height=window.innerHeight

let stars=[]

for(let i=0;i<200;i++){

stars.push({
x:Math.random()*canvas.width,
y:Math.random()*canvas.height,
size:Math.random()*2
})

}

function draw(){

ctx.fillStyle="black"
ctx.fillRect(0,0,canvas.width,canvas.height)

ctx.fillStyle="white"

stars.forEach(s=>{
ctx.fillRect(s.x,s.y,s.size,s.size)
})

requestAnimationFrame(draw)

}

draw()

</script>

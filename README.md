<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Vivek Anand Shukla | AI Research & Innovation</title>

<meta name="description" content="Official website of Vivek Anand Shukla — AI research, transport innovation, startups and technology ideas.">

<script src="https://cdn.tailwindcss.com"></script>

<link
rel="stylesheet"
href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
/>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

</head>

<body class="bg-slate-50 text-slate-800">


<!-- NAVBAR -->

<header class="bg-white shadow sticky top-0">

<div class="max-w-6xl mx-auto flex justify-between p-4">

<h1 class="font-bold text-xl">Vivek Anand Shukla</h1>

<nav class="space-x-4">

<a href="#about">About</a>
<a href="#projects">Projects</a>
<a href="#transport">Transport</a>
<a href="#map">World Map</a>
<a href="#ai">AI</a>
<a href="#contact">Contact</a>

</nav>

</div>

</header>


<!-- HERO -->

<section class="py-24 text-center bg-blue-600 text-white">

<h2 class="text-4xl font-bold mb-4">

AI • Transport • Business Innovation

</h2>

<p class="max-w-xl mx-auto">

The personal innovation platform of Vivek Anand Shukla exploring artificial intelligence, logistics and entrepreneurship.

</p>

</section>


<!-- ABOUT -->

<section id="about" class="py-20 text-center">

<img src="yourphoto.jpg" class="w-40 rounded-full mx-auto shadow mb-6">

<h3 class="text-3xl font-bold mb-6">About Me</h3>

<p class="max-w-2xl mx-auto">

I am Vivek Anand Shukla working in operations and CRM and previously as a problem solver at Amazon.
My interests include artificial intelligence, logistics systems, transport management and digital entrepreneurship.

</p>

</section>


<!-- PROJECTS -->

<section id="projects" class="py-20 bg-white">

<h3 class="text-3xl font-bold text-center mb-10">Projects</h3>

<div class="grid md:grid-cols-3 gap-6 max-w-5xl mx-auto">

<div class="shadow p-6 rounded">
<h4 class="font-semibold">AI Research</h4>
<p>Exploring AI applications for modern businesses.</p>
</div>

<div class="shadow p-6 rounded">
<h4 class="font-semibold">CRM Optimization</h4>
<p>Improving customer engagement systems.</p>
</div>

<div class="shadow p-6 rounded">
<h4 class="font-semibold">Digital Startup Ideas</h4>
<p>Researching scalable internet businesses.</p>
</div>

</div>

</section>


<!-- TRANSPORT -->

<section id="transport" class="py-20 text-center">

<h3 class="text-3xl font-bold mb-10">Transport & Logistics Innovation</h3>

<div class="grid md:grid-cols-3 gap-6 max-w-5xl mx-auto">

<div class="shadow p-6 rounded">
<h4>Fleet Management</h4>
<p>Improving vehicle efficiency using analytics.</p>
</div>

<div class="shadow p-6 rounded">
<h4>Route Optimization</h4>
<p>AI systems optimizing delivery routes.</p>
</div>

<div class="shadow p-6 rounded">
<h4>Supply Chain</h4>
<p>Research on global logistics networks.</p>
</div>

</div>

</section>


<!-- WORLD MAP -->

<section id="map" class="py-20 text-center bg-white">

<h3 class="text-3xl font-bold mb-8">Global Innovation Vision</h3>

<div id="worldMap" style="height:400px; max-width:900px; margin:auto;"></div>

</section>


<script>

var map = L.map('worldMap').setView([20,0],2)

L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png').addTo(map)

L.marker([28.6139,77.2090]).addTo(map)
.bindPopup("India - Innovation Base")

</script>


<!-- BUSINESS IDEAS -->

<section class="py-20 text-center">

<h3 class="text-3xl font-bold mb-8">Startup Ideas</h3>

<ul class="space-y-3 max-w-xl mx-auto">

<li>AI logistics platform</li>
<li>Automation tools for businesses</li>
<li>AI customer service assistant</li>

</ul>

</section>


<!-- AI ASSISTANT -->

<section id="ai" class="py-20 bg-slate-100 text-center">

<h3 class="text-3xl font-bold mb-6">AI Assistant</h3>

<input
id="question"
class="border p-3 rounded w-72"
placeholder="Ask anything..."
>

<button
onclick="askAI()"
class="bg-blue-600 text-white px-5 py-3 rounded ml-2"
>
Ask AI
</button>

<button
onclick="startVoice()"
class="bg-green-600 text-white px-4 py-3 rounded ml-2"
>
🎤 Speak
</button>

<p id="aiResponse" class="mt-6"></p>

</section>


<script>

async function askAI(){

const q=document.getElementById("question").value

document.getElementById("aiResponse").innerText="Thinking..."

const r=await fetch("https://api.openai.com/v1/chat/completions",{

method:"POST",

headers:{
"Content-Type":"application/json",
"Authorization":"Bearer YOUR_OPENAI_API_KEY"
},

body:JSON.stringify({

model:"gpt-4o-mini",

messages:[
{role:"system",content:"You are an AI assistant helping visitors on Vivek Anand Shukla's website."},
{role:"user",content:q}
]

})

})

const data=await r.json()

document.getElementById("aiResponse").innerText=
data.choices[0].message.content

}



function startVoice(){

const rec = new webkitSpeechRecognition()

rec.start()

rec.onresult=function(e){

document.getElementById("question").value =
e.results[0][0].transcript

askAI()

}

}

</script>


<!-- CONTACT -->

<section id="contact" class="py-20 text-center">

<h3 class="text-3xl font-bold mb-6">Contact</h3>

<p>Email: vivekanandshukla498@gmail.com</p>

<a
href="mailto:vivekanandshukla498@gmail.com"
class="bg-blue-600 text-white px-6 py-3 rounded mt-4 inline-block"
>
Send Email
</a>

</section>


<!-- SOCIAL -->

<footer class="text-center py-10 bg-white">

<div class="space-x-6">

<a href="https://www.linkedin.com/in/vivek-anand-shukla-0a55a7377">LinkedIn</a>
<a href="https://www.instagram.com/iamvvk.18">Instagram</a>
<a href="https://www.facebook.com/share/1AeZmAq7Jd/">Facebook</a>
<a href="https://x.com/VivekSh09712505">X</a>
<a href="https://youtube.com/@vivekanandshukla4168">YouTube</a>

</div>

<p class="mt-6 text-sm">© 2026 Vivek Anand Shukla</p>

</footer>

</body>
</html>

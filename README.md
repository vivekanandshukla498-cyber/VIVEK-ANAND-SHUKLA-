<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">

<title>Vivek Anand Shukla | AI Innovation & Research</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap" rel="stylesheet">

<style>

body{
font-family:Poppins;
margin:0;
background:#f5f7fb;
color:#222;
}

header{
background:#0f172a;
color:white;
display:flex;
justify-content:space-between;
padding:18px 40px;
}

header a{
color:white;
margin-left:20px;
text-decoration:none;
font-size:14px;
}

.hero{
background:linear-gradient(135deg,#2563eb,#06b6d4);
color:white;
padding:120px 20px;
text-align:center;
}

.hero h1{
font-size:42px;
}

.section{
padding:70px 20px;
max-width:1100px;
margin:auto;
}

.grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
gap:30px;
}

.card{
background:white;
padding:30px;
border-radius:12px;
box-shadow:0 8px 25px rgba(0,0,0,0.08);
}

.ai-box{
background:white;
padding:30px;
border-radius:12px;
box-shadow:0 5px 20px rgba(0,0,0,0.1);
text-align:center;
}

.ai-box input{
width:70%;
padding:12px;
margin-right:10px;
}

button{
padding:12px 18px;
background:#2563eb;
color:white;
border:none;
border-radius:6px;
}

footer{
background:#0f172a;
color:white;
text-align:center;
padding:40px;
}

</style>

</head>

<body>

<header>

<div><b>Vivek Anand Shukla</b></div>

<nav>
<a href="#about">About</a>
<a href="#projects">Projects</a>
<a href="#transport">Transport</a>
<a href="#blog">Blog</a>
<a href="#ai">AI</a>
<a href="#contact">Contact</a>
</nav>

</header>

<section class="hero">

<h1>AI Innovation • Research • Startup Ideas</h1>

<p>Personal technology platform by Vivek Anand Shukla</p>

</section>

<section id="about" class="section">

<h2>About</h2>

<p>

Focused on artificial intelligence innovation, logistics and
transport systems, research projects and startup development.

</p>

</section>

<section id="projects" class="section">

<h2>Projects</h2>

<div class="grid">

<div class="card">
<h3>AI Research</h3>
<p>Exploring machine learning and future AI technologies.</p>
</div>

<div class="card">
<h3>Innovation Projects</h3>
<p>Building new digital and startup ideas.</p>
</div>

<div class="card">
<h3>Technology Experiments</h3>
<p>Working on practical research implementations.</p>
</div>

</div>

</section>

<section id="transport" class="section">

<h2>Transport & Logistics Ideas</h2>

<div class="grid">

<div class="card">
<h3>Smart Logistics</h3>
<p>AI-powered delivery and warehouse systems.</p>
</div>

<div class="card">
<h3>Route Optimization</h3>
<p>Improving transportation efficiency using data.</p>
</div>

<div class="card">
<h3>Future Mobility</h3>
<p>Research on advanced transport technologies.</p>
</div>

</div>

</section>

<section id="blog" class="section">

<h2>Blog</h2>

<div class="grid">

<div class="card">
<h3>AI Future</h3>
<p>Thoughts on artificial intelligence and society.</p>
</div>

<div class="card">
<h3>Startup Ideas</h3>
<p>Business innovation concepts and opportunities.</p>
</div>

<div class="card">
<h3>Science & Space</h3>
<p>Research on universe and technology.</p>
</div>

</div>

</section>

<section id="ai" class="section">

<h2>AI Assistant</h2>

<div class="ai-box">

<input id="question" placeholder="Ask a question">

<button onclick="askAI()">Search</button>

<p id="answer"></p>

</div>

</section>

<script>

function askAI(){

let q=document.getElementById("question").value

document.getElementById("answer").innerText =
"AI response will appear here after connecting API."

}

</script>

<section id="contact" class="section">

<h2>Contact</h2>

<p>Email: vivekanandshukla498@gmail.com</p>

<p>

<a href="https://www.linkedin.com/in/vivek-anand-shukla-0a55a7377">LinkedIn</a> |
<a href="https://www.instagram.com/iamvvk.18">Instagram</a> |
<a href="https://x.com/VivekSh09712505">X</a> |
<a href="https://youtube.com/@vivekanandshukla4168">YouTube</a>

</p>

</section>

<footer>

<p>© 2026 Vivek Anand Shukla</p>

</footer>

</body>
</html>

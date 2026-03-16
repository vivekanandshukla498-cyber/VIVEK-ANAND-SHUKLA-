<title>Vivek Anand Shukla | AI Innovation</title>

<meta name="viewport" content="width=device-width,initial-scale=1">

<link rel="stylesheet" href="style.css">

</head>

<body>

<header>

<h1>Vivek Anand Shukla</h1>

<nav>

<a href="index.html">Home</a>
<a href="pages/blog.html">Blog</a>
<a href="pages/projects.html">Projects</a>
<a href="pages/transport.html">Transport</a>
<a href="pages/ai.html">AI Assistant</a>
<a href="pages/contact.html">Contact</a>

</nav>

</header>

<section class="hero">

<h2>AI Innovation • Research • Startup Ideas</h2>

<p>

Technology platform for research, transport innovation,
and artificial intelligence.

</p>

</section>

<section class="about">

<h2>About Me</h2>

<p>

I work on AI innovation, research, transport systems
and future technology.

</p>

</section>

<section class="features">

<div class="card">
<h3>AI Research</h3>
<p>Artificial intelligence innovation platform.</p>
</div>

<div class="card">
<h3>Projects</h3>
<p>Research and technology projects.</p>
</div>

<div class="card">
<h3>Transport Innovation</h3>
<p>Logistics and transport management ideas.</p>
</div>

<div class="card">
<h3>Blog</h3>
<p>Articles on science, startups and technology.</p>
</div>

</section>

<footer>

<p>

Contact: vivekanandshukla498@gmail.com

</p>

</footer>

</body>
</html>
body{

font-family:Arial;
margin:0;
background:#f4f6f9;

}

header{

background:#111;
color:white;
padding:20px;
display:flex;
justify-content:space-between;

}

nav a{

color:white;
margin:10px;
text-decoration:none;

}

.hero{

background:linear-gradient(120deg,#007cf0,#00dfd8);
color:white;
padding:120px;
text-align:center;

}

.features{

display:grid;
grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
gap:20px;
padding:60px;

}

.card{

background:white;
padding:20px;
border-radius:10px;
box-shadow:0 5px 15px rgba(0,0,0,0.1);

}
<h2>AI Assistant</h2>

<input id="question" placeholder="Ask anything">

<button onclick="askAI()">Ask AI</button>

<p id="answer"></p>

<script>

async function askAI(){

let q=document.getElementById("question").value

let response=await fetch("http://localhost:3000/ai",{

method:"POST",

headers:{
"Content-Type":"application/json"
},

body:JSON.stringify({question:q})

})

let data=await response.json()

document.getElementById("answer").innerText=data.answer

}

</script>
const express=require("express")

const fetch=require("node-fetch")

const app=express()

app.use(express.json())

app.post("/ai",async(req,res)=>{

let question=req.body.question

let response=await fetch(
"https://api.openai.com/v1/chat/completions",
{

method:"POST",

headers:{
"Content-Type":"application/json",
"Authorization":"Bearer YOUR_API_KEY"
},

body:JSON.stringify({

model:"gpt-4o-mini",

messages:[
{role:"user",content:question}
]

})

})

let data=await response.json()

res.json({

answer:data.choices[0].message.content

})

})

app.listen(3000)

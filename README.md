	<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Vinoth Tamilarasu Portfolio</title>
  <style>
	* {
  	margin: 0;
  	padding: 0;
  	box-sizing: border-box;
	}
	html {
  	scroll-behavior: smooth;
	}
	body {
  	font-family: 'Segoe UI', sans-serif;
  	background: #f5f7fa;
  	color: #2b2525;
	}
	header {
  	background: linear-gradient(135deg, #1e3c72, #2a5298);
  	color: white;
  	text-align: center;
  	padding: 3rem 1rem 5rem;
  	position: relative;
	}
	.profile-picture {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  object-fit: cover;
  border: 4px solid #fff;
  position: relative;
  margin-top: -80px;
  margin-bottom: 1rem;
}
	.tabs {
  	display: flex;
  	flex-wrap: wrap;
  	justify-content: center;
  	background: white;
  	box-shadow: 0 2px 4px rgba(0,0,0,0.1);
	}
	.tabs button {
  	padding: 0.8rem 1.5rem;
  	background: #ffffff;
  	border: 2px solid #2a5298;
  	border-radius: 8px;
  	margin: 0.5rem;
  	cursor: pointer;
  	font-size: 16px;
  	font-weight: 500;
  	color: #2a5298;
  	transition: all 0.3s ease;
	}
	.tabs button:hover,
	.tabs button.active {
  	background: #135ee0;
  	color: #fff;
  	border-color: #1752b9;
	}
	section {
  	max-width: 900px;
  	margin: auto;
  	background: white;
  	padding: 2rem;
  	margin-top: 2rem;
  	border-radius: 12px;
  	box-shadow: 0 0 10px rgba(0,0,0,0.05);
  	display: none;
  	opacity: 0;
  	transform: translateY(30px);
  	transition: all 0.5s ease;
	}
	section.active {
  	display: block;
  	opacity: 1;
  	transform: translateY(0);
	}
	h2 {
  	color: #2a5298;
  	margin-bottom: 1rem;
	}
	ul li {
  	margin-bottom: 0.5rem;
	}
	.download-button {
  	display: inline-block;
  	background: #2a5298;
  	color: white;
  	padding: 0.5rem 1rem;
  	border-radius: 20px;
  	text-decoration: none;
  	margin-top: 1rem;
	}
	.download-button:hover {
  	background: #1e3c72;
	}
	footer {
  	text-align: center;
  	padding: 1.5rem;
  	background: #2a5298;
  	color: white;
  	margin-top: 3rem;
	}
	.modal {
  	display: none;
  	position: fixed;
  	top: 0; left: 0;
  	width: 100%; height: 100%;
  	background: rgba(0,0,0,0.5);
  	justify-content: center;
  	align-items: center;
	}
	.modal-content {
  	background: white;
  	padding: 2rem;
  	border-radius: 10px;
  	width: 300px;
  	text-align: center;
  	animation: fadeIn 0.3s ease-in-out;
	}
	.modal-content input {
  	width: 100%;
  	padding: 10px;
  	margin-top: 10px;
  	font-size: 16px;
  	border-radius: 6px;
	}
	.modal-content button {
  	background: #2a5298;
  	color: white;
  	border: none;
  	padding: 10px 20px;
  	margin-top: 1rem;
  	border-radius: 6px;
  	cursor: pointer;
	}
	.modal-content .error {
  	color: red;
  	font-size: 14px;
  	margin-top: 10px;
	}
	@keyframes fadeIn {
  	from { opacity: 0; transform: scale(0.95); }
  	to { opacity: 1; transform: scale(1); }
	}
	@media (max-width: 600px) {
  	.tabs button {
    	flex: 1 0 100%;
    	padding: 0.75rem;
    	font-size: 15px;
  	}
  	.profile-picture {
    	position: static;
    	margin-bottom: 1rem;
  	}
  	header {
    	padding-bottom: 2rem;
  	}
	}
	.dark-mode {
  	background-color: #121212;
  	color: #f5f5f5;
	}
	.dark-mode section {
  	background-color: #1e1e1e;
  	color: #f5f5f5;
	}
	.dark-mode header {
  	background: linear-gradient(135deg, #000000, #2a2a2a);
	}
	.dark-mode .tabs button {
  	background-color: #2a2a2a;
  	color: #f5f5f5;
  	border-color: #555;
	}
	.dark-mode .tabs button.active,
	.dark-mode .tabs button:hover {
  	background-color: #444;
  	color: #fff;
	}
	.dark-toggle {
  	position: absolute;
  	top: 1rem;
  	right: 1rem;
  	background: #fff;
  	border: none;
  	padding: 0.5rem 1rem;
  	font-weight: bold;
  	cursor: pointer;
  	border-radius: 5px;
  	color: #2a5298;
	}
  </style>
</head>
<body>
<header style="display: flex; flex-direction: row; align-items: center; justify-content: space-between; padding: 2rem">
  <button class="dark-toggle" onclick="toggleDarkMode()">Toggle Dark Mode</button>
  <img src="./my photos.jpg" alt="Profile Picture" class="profile-picture" id="profileImage" style="margin: 0 1rem 0 0; align-self: flex-start;">
  <div style="text-align: left;">
	<h1>VinothTamilarasu</h1>
    
  </div>
  <p>Student<br>Kaamadhenu Arts and Science College</p>
  <input type="file" id="fileInput" accept="image/*" style="display:none">
  <button onclick="showModal()">Change Profile</button>
</header>

<div class="tabs">
  <button class="tab-btn active" data-tab="about">About</button>
  <button class="tab-btn" data-tab="certificates">Certificates</button>
  <button class="tab-btn" data-tab="experience">Experience</button>
  <button class="tab-btn" data-tab="education">Education</button>
  <button class="tab-btn" data-tab="skills">Skills</button>
  <button class="tab-btn" data-tab="projects">Projects</button>
  <button class="tab-btn" data-tab="resume">Resume</button>
  <button class="tab-btn" data-tab="contact">Contact</button>
</div>

<section id="about" class="active">
  <h2>About Me</h2>
  <p>I'm a <b>Student</b> in the Department of computer science at KASC specializes in software development and data structures.<br>I has over 2 years of student experience and believes in creating a dynamic learning environment that encourages problem-solving and hands-on coding practice.</p>
</section>

<section id="education">
  <h2>Education</h2>
  <p>computer science in Bharathiyar University <br>MCA in Anna University<br>B.Ed in TTEducation University</p>
</section>

<section id="skills">
  <h2>Skills</h2>
  <ul>
	<li>C,C++,Java</li>
	<li>Internet of Things</li>
	<li>SQL-RDBMS</li>
	<li>Python</li>
	<li>DSA</li>
	<li>Blockchain</li>
	<li>JavaScript</li>
  </ul>
</section>

<section id="projects">
  <h2>Projects</h2>
  <ul>
	<li>Automobile Finance Application</li>
	<li>Smart Campus</li>
	<li>Mini Project - Library Management</li>
  </ul>
</section>

<section id="resume">
  <h2>Resume</h2>
  <a href="./Name list for IBM SkillsBuild.pdf" target="_blank" class="download-button">Download CV</a>
</section>

<section id="contact">
  <h2>Contact</h2>
  <p>Email: <a href="vinoth.cs24@kascsathy.ac.in">vinoth.cs24@kascsathy.ac.in</a></p>
  <p>Phone: +91-8438984975</p>
  <p>Location: Avinashi, Tiruppur District, India</p>
  <div style="margin-top: 1rem;">
	<a href="https://linkedin.com/in/Vinoth T" target="_blank">LinkedIn</a> |
	<a href="https://github.com/Vinoth T" target="_blank">GitHub</a> |
	<a href="https://instagram.com/xo_toxic_mt15" target="_blank">Instagram</a>
  </div>
</section>

<section id="certificates">
  <h2>Certificates</h2>
  <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
	<div style="text-align: center;">
    	<img src="./certif.PNG" alt="MS-356" style="max-width: 200px; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);">
    	<p>Web Developmen - Fron End : IBM</p>
	</div>
	<div style="text-align: center;">
    	<img src="./Capture.PNG" alt="life of JavaScrip – IBM" style="max-width: 200px; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);">
    	<p>Web Developmen - Fron End : IBM</p>
	</div>
	<div style="text-align: center;">
    	<img src="./certificate.PNG" alt="Comple course : IBM" style="max-width: 200px; border-radius: 8px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);">
    	<p>Web Developmen - Fron End : IBM</p>
	</div>
  </div>
</section>

<section id="experience">
  <h2>Experience</h2>
  <ul>
	<li><b>Assistant Student</b>KASC - Sathy (2023 - Present)<br>Department of CA and IT</li>
	<li><b>Faculty</b> – CCI Computer Center (2003 - 2007)<br>Handled Ms-Office, Java, C,C++, Oracle, VB</li>
	<li><b>Assistant student</b> MPNMJ Engg. College (2011 - 2013)<br>Department of MCA </li>
	<li><b>Computer Student</b> VVMHSS (2016 - 2023)<br>Worked on Under Bharathidhasan University</li>
  </ul>
</section>

<footer>
  <p>&copy; 2025 Mr. T VINOTH : All rights reserved.</p>
</footer>

<div class="modal" id="passwordModal">
  <div class="modal-content">
	<h3>Enter Password</h3>
	<input type="password" id="passwordInput" placeholder="Password">
	<div class="error" id="errorMsg"></div>
	<button onclick="checkPassword()">Submit</button>
  </div>
</div>

<script>
  const fileInput = document.getElementById('fileInput');
  const profileImage = document.getElementById('profileImage');
  const modal = document.getElementById('passwordModal');
  const passwordInput = document.getElementById('passwordInput');
  const errorMsg = document.getElementById('errorMsg');
  const correctPassword = "1234";

  const savedImage = localStorage.getItem("profileImage");
  if (savedImage) {
	profileImage.src = savedImage;
  }

  function showModal() {
	modal.style.display = 'flex';
	passwordInput.value = '';
	errorMsg.textContent = '';
	passwordInput.focus();
  }

  function checkPassword() {
	if (passwordInput.value === correctPassword) {
  	modal.style.display = 'none';
  	fileInput.click();
	} else {
  	errorMsg.textContent = "Incorrect password!";
	}
  }

  fileInput.addEventListener('change', function () {
	const file = this.files[0];
	if (file && file.type.startsWith('image/')) {
  	const reader = new FileReader();
  	reader.onload = function (e) {
    	profileImage.src = e.target.result;
    	localStorage.setItem("profileImage", e.target.result);
  	};
  	reader.readAsDataURL(file);
	} else {
  	alert("Please select a valid image file.");
	}
  });

  window.onclick = function(e) {
	if (e.target === modal) modal.style.display = "none";
  };

  const tabButtons = document.querySelectorAll('.tab-btn');
  const tabSections = document.querySelectorAll('section');

  tabButtons.forEach(btn => {
	btn.addEventListener('click', () => {
  	document.querySelector('.tab-btn.active').classList.remove('active');
  	btn.classList.add('active');
  	tabSections.forEach(section => section.classList.remove('active'));
  	document.getElementById(btn.getAttribute('data-tab')).classList.add('active');
	});
  });

  function toggleDarkMode() {
	document.body.classList.toggle('dark-mode');
  }
</script>
</body>
</html>footer {
  	text-align: center;
  	padding: 1.5rem;
  	background: #2a5298;
  	color: white;
  	margin-top: 3rem;
	}
	.modal {
  	display: none;
  	position: fixed;
  	top: 0; left: 0;
  	width: 100%; height: 100%;
  	background: rgba(0,0,0,0.5);
  	justify-content: center;
  	align-items: center;
	}
	.modal-content {
  	background: white;
  	padding: 2rem;
  	border-radius: 10px;
  	width: 300px;
  	text-align: center;
  	animation: fadeIn 0.3s ease-in-out;
	}
	.modal-content input {
  	width: 100%;
  	padding: 10px;
  	margin-top: 10px;
  	font-size: 16px;
  	border-radius: 6px;
	}
	.modal-content button {
  	background: #2a5298;
  	color: white;
  	border: none;
  	padding: 10px 20px;
  	margin-top: 1rem;
  	border-radius: 6px;
  	cursor: pointer;
	}
	.modal-content .error {
  	color: red;
  	font-size: 14px;
  	margin-top: 10px;
	}
	@keyframes fadeIn {
  	from { opacity: 0; transform: scale(0.95); }
  	to { opacity: 1; transform: scale(1); }
	}
	@media (max-width: 600px) {
  	.tabs button {
    	flex: 1 0 100%;
    	padding: 0.75rem;
    	font-size: 15px;
  	}
  	.profile-picture {
    	position: static;
    	margin-bottom: 1rem;
  	}
  	header {
    	padding-bottom: 2rem;
  	}
	}
	.dark-mode {
  	background-color: #121212;
  	color: #f5f5f5;
	}
	.dark-mode section {
  	background-color: #1e1e1e;
  	color: #f5f5f5;
	}
	.dark-mode header {
  	background: linear-gradient(135deg, #000000, #2a2a2a);
	}
	.dark-mode .tabs button {
  	background-color: #2a2a2a;
  	color: #f5f5f5;
  	border-color: #555;
	}
	.dark-mode .tabs button.active,
	.dark-mode .tabs button:hover {
  	background-color: #444;
  	color: #fff;
	}
	.dark-toggle {
  	position: absolute;
  	top: 1rem;
  	right: 1rem;
  	background: #fff;
  	border: none;
  	padding: 0.5rem 1rem;
  	font-weight: bold;
  	cursor: pointer;
  	border-radius: 5px;
  	color: #2a5298;
	}
  	<h3>Enter Password</h3>
	<input type="password" id="passwordInput" placeholder="Password">
	<div class="error" id="errorMsg"></div>
	<button onclick="checkPassword()">Submit</button>
  

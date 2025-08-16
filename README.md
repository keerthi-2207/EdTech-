<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EdTech - Login & Signup Animation</title>
<style>
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background-color: black;
        color: white;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
    }

    .container {
        text-align: center;
    }

    h1 {
        font-size: 40px;
        margin-bottom: 10px;
        animation: glow 1.5s infinite alternate;
    }

    h2 {
        font-size: 28px;
        margin-bottom: 20px;
        color: #00ccff;
    }

    @keyframes glow {
        from { text-shadow: 0 0 5px #00aaff, 0 0 10px #00aaff; }
        to { text-shadow: 0 0 15px #00ccff, 0 0 25px #00ccff; }
    }

    .form-box {
        background-color: black;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 15px rgba(0,0,0,0.6);
        width: 300px;
        margin: auto;
        animation: fadeIn 1s ease;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(20px); }
        to { opacity: 1; transform: translateY(0); }
    }

    input {
        width: 90%;
        padding: 10px;
        margin: 10px 0;
        border: none;
        border-radius: 5px;
        background-color: #001f3f;
        color: white;
        font-size: 16px;
    }

    button {
        width: 95%;
        padding: 10px;
        background-color: #004080;
        border: none;
        border-radius: 5px;
        color: white;
        font-size: 18px;
        cursor: pointer;
        margin-top: 10px;
        transition: background-color 0.3s;
    }

    button:hover {
        background-color: #0066cc;
    }

    .switch-text {
        margin-top: 15px;
        font-size: 14px;
    }

    .switch-link {
        color: #00ccff;
        cursor: pointer;
        text-decoration: underline;
    }
</style>
</head>
<body>

<div class="container">
    <h1>EdTech</h1>
    <h2 id="formHeading">LOGIN</h2>

    <div id="loginBox" class="form-box">
        <input type="text" placeholder="Username" required>
        <input type="password" placeholder="Password" required>
        <button>Login</button>
        <div class="switch-text">
            Do you want to switch to <span class="switch-link" onclick="showSignup()">Signup?</span>
        </div>
    </div>

    <div id="signupBox" class="form-box" style="display:none;">
        <input type="text" placeholder="Full Name" required>
        <input type="email" placeholder="Email" required>
        <input type="password" placeholder="Password" required>
        <input type="password" placeholder="Confirm Password" required>
        <button>Sign Up</button>
        <div class="switch-text">
            Do you want to switch to <span class="switch-link" onclick="showLogin()">Login?</span>
        </div>
    </div>
</div>

<script>
    function showSignup() {
        document.getElementById("loginBox").style.display = "none";
        document.getElementById("signupBox").style.display = "block";
        document.getElementById("formHeading").textContent = "SIGNUP";
    }

    function showLogin() {
        document.getElementById("signupBox").style.display = "none";
        document.getElementById("loginBox").style.display = "block";
        document.getElementById("formHeading").textContent = "LOGIN";
    }

    setTimeout(showSignup, 30000); // Auto switch after 30s
</script>

</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>EdTech App</title>
  <style>
    @font-face {
      font-family: "EngraversGothicBT";
      src: local("Engravers Gothic BT"),
           url("https://fonts.cdnfonts.com/s/14763/EngraversGothic.woff") format("woff");
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: "EngraversGothicBT", sans-serif;
      background: linear-gradient(135deg, #ffd1dc, #fdfd96, #b5ead7, #c7ceea, #ffecb3, #ff9a9e);
      background-attachment: fixed;
      background-size: cover;
      min-height: 100vh;
    }

    h1, h2, h3 {
      text-align: center;
      margin: 15px 10px;
      font-weight: bold;
      background: linear-gradient(90deg, #ff9a9e, #fad0c4, #fbc2eb, #a1c4fd, #fdfd96, #b5ead7);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .search-bar {
      display: flex;
      justify-content: center;
      margin: 10px 0 20px 0;
    }
    .search-bar input {
      padding: 8px 12px;
      width: 70%;
      border-radius: 20px;
      border: 2px solid #ff9a9e;
      outline: none;
      font-size: 16px;
    }

    /* Rainbow pastel bordered square box */
    .square-box {
      width: 150px;
      height: 100px;
      border: 3px solid transparent;
      border-image: linear-gradient(45deg, #ff9a9e, #fdfd96, #b5ead7, #c7ceea);
      border-image-slice: 1;
      background: #fff9;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 10px;
      text-align: center;
      border-radius: 10px;
      cursor: pointer;
    }

    .box-row {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
    }

    /* Open-top 3-sided box */
    .open-box {
      width: 150px;
      height: 100px;
      border-left: 3px solid #ff9a9e;
      border-right: 3px solid #b5ead7;
      border-bottom: 3px solid #c7ceea;
      background: #fff9;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 10px;
      font-weight: bold;
      cursor: pointer;
    }

    /* Oval shapes */
    .oval-container {
      display: flex;
      justify-content: space-around;
      margin: 30px 15px;
    }

    .oval {
      width: 160px;
      height: 70px;
      border-radius: 40px;
      border: 3px solid transparent;
      border-image: linear-gradient(90deg, #ff9a9e, #fdfd96, #c7ceea);
      border-image-slice: 1;
      display: flex;
      justify-content: center;
      align-items: center;
      font-weight: bold;
      background: #fff9;
      cursor: pointer;
    }

    /* Bottom navigation */
    .bottom-nav {
      display: flex;
      justify-content: space-around;
      align-items: center;
      padding: 10px 0;
      background: #fff9;
      border-top: 2px solid #ccc;
      position: fixed;
      bottom: 0;
      width: 100%;
    }
    .bottom-nav div {
      text-align: center;
      cursor: pointer;
      font-size: 14px;
    }

    /* Categories Page */
    #categories-page {
      display: none;
      padding-bottom: 80px;
    }

    .categories-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 15px;
      justify-items: center;
      margin: 20px;
    }

    .categories-grid.second-row {
      grid-template-columns: repeat(3, 1fr);
    }

    .category-box {
      width: 120px;
      height: 90px;
      border: 3px solid transparent;
      border-image: linear-gradient(45deg, #ff9a9e, #b5ead7, #c7ceea);
      border-image-slice: 1;
      background: #fff9;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 5px;
      border-radius: 8px;
      cursor: pointer;
      text-align: center;
    }
  </style>
</head>
<body>

  <!-- HOME PAGE -->
  <div id="home-page">
    <h1>What will you learn today?</h1>

    <!-- Search bar -->
    <div class="search-bar">
      🔍 <input type="text" placeholder="Search for anything...">
    </div>

    <!-- Learning dashboard -->
    <h2>LEARNING DASHBOARD</h2>
    <div class="box-row">
      <div class="square-box">Soft Skills</div>
      <div class="square-box">Creative</div>
      <div class="square-box">Learning Techniques</div>
    </div>

    <!-- What's new -->
    <h2>See What's New</h2>
    <div class="box-row">
      <div class="open-box">Subscription Plans</div>
      <div class="open-box">Freemium Model</div>
      <div class="open-box">Offers</div>
    </div>

    <!-- Certificates + Leaderboard -->
    <div class="oval-container">
      <div class="oval">Certificates Gained</div>
      <div class="oval">Leaderboard</div>
    </div>
  </div>

  <!-- CATEGORIES PAGE -->
  <div id="categories-page">
    <h2>Categories</h2>
    <div class="categories-grid">
      <div class="category-box">Future Scope</div>
      <div class="category-box">Monetization</div>
      <div class="category-box">Educator Side</div>
      <div class="category-box">Achievements</div>
    </div>
    <div class="categories-grid second-row">
      <div class="category-box">Community</div>
      <div class="category-box">Learning Modes</div>
      <div class="category-box">Security & Compliance</div>
    </div>
  </div>

  <!-- Bottom Navigation -->
  <div class="bottom-nav">
    <div onclick="showPage('home')">🏠<br>Home</div>
    <div>📝<br>Tests</div>
    <div>👤<br>Profile</div>
    <div onclick="showPage('categories')">📂<br>Categories</div>
    <div>👑<br>Pro</div>
  </div>

  <script>
    function showPage(page) {
      document.getElementById("home-page").style.display = (page === 'home') ? 'block' : 'none';
      document.getElementById("categories-page").style.display = (page === 'categories') ? 'block' : 'none';
    }
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Monetization Mind Map</title>
  <style>
    body {
      background-color: black;
      font-family: Arial, sans-serif;
      color: skyblue;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 50px 20px;
    }

    .box {
      border: 2px solid skyblue;
      border-radius: 10px;
      padding: 20px;
      margin: 20px;
      max-width: 700px;
      width: 100%;
      text-align: center;
      cursor: pointer;
      transition: transform 0.3s, background 0.3s;
    }

    .box:hover {
      transform: scale(1.03);
      background-color: rgba(135, 206, 235, 0.1);
    }

    .title-box {
      font-size: 32px;
      font-weight: bold;
      border: 3px solid skyblue;
      background-color: rgba(135, 206, 235, 0.1);
    }

    .content {
      display: none;
      color: #ccc;
      font-size: 16px;
      margin-top: 10px;
      text-align: left;
    }

    .box.active .content {
      display: block;
      animation: fadeIn 1s ease-in;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
  </style>
</head>
<body>

  <div class="box title-box" id="titleBox">
    Monetization
  </div>

  <div class="box" id="monetization1" onclick="toggleContent(this)">
    <h2>1. Freemium Model</h2>
    <div class="content">
      <p>This model offers basic features and content for free, while advanced features, premium content, or an ad-free experience are available through a paid subscription.</p>
    </div>
  </div>

  <div class="box" id="monetization2" onclick="toggleContent(this)">
    <h2>2. Course Purchase</h2>
    <div class="content">
      <p>To effectively sell courses, the app must optimize the purchase process for a seamless user experience. This includes streamlined payment options, intuitive design, and compelling course offerings.</p>
    </div>
  </div>

  <div class="box" id="monetization3" onclick="toggleContent(this)">
    <h2>3. Corporate Licensing</h2>
    <div class="content">
      <p>EdTech apps can license their technology, content, or platforms to businesses and institutions. This includes access to digital textbooks, training modules, or proprietary tools, generating revenue through licensing fees.</p>
    </div>
  </div>

  <script>
    function toggleContent(element) {
      element.classList.toggle("active");
    }

    const monetizationNodes = ["monetization1", "monetization2", "monetization3"];
    monetizationNodes.forEach((id, index) => {
      setTimeout(() => {
        document.getElementById(id).style.display = "block";
      }, 5000 * (index + 1)); // +1 to delay after title
    });

    window.onload = () => {
      monetizationNodes.forEach(id => {
        document.getElementById(id).style.display = "none";
      });
    };
  </script>

</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Community - EdTech</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: black;
      color: white;
      font-family: Arial, sans-serif;
      overflow-x: hidden;
    }

    .container {
      width: 100%;
      padding: 50px 20px;
      box-sizing: border-box;
    }

    /* Heading */
    .heading {
      width: 100%;
      max-width: 800px;
      margin: 0 auto 40px auto;
      padding: 20px;
      background: linear-gradient(135deg, #00c6ff, #0072ff);
      border-radius: 15px;
      text-align: center;
      font-size: 24px;
      font-weight: bold;
      color: white;
      box-shadow: 0 0 25px #00c6ff;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0% {
        box-shadow: 0 0 10px #00c6ff;
      }
      50% {
        box-shadow: 0 0 30px #00c6ff, 0 0 60px #00c6ff;
      }
      100% {
        box-shadow: 0 0 10px #00c6ff;
      }
    }

    /* Clickable cards */
    a.node {
      display: block;
      max-width: 800px;
      margin: 30px auto;
      padding: 20px;
      border-left: 4px solid skyblue;
      background-color: rgba(255, 255, 255, 0.05);
      border-radius: 10px;
      opacity: 0;
      transform: translateY(20px);
      color: skyblue;
      font-size: 14px;
      text-decoration: none;
      animation: fadeIn 2s ease forwards;
      transition: background-color 0.3s ease, border-color 0.3s ease;
      cursor: pointer;
    }

    a.node:hover {
      background-color: rgba(0, 198, 255, 0.15);
      border-left-color: #00e0ff;
      color: #00e0ff;
    }

    a.node h3 {
      margin-top: 0;
      color: skyblue;
      font-size: 20px;
      transition: color 0.3s ease;
    }

    a.node:hover h3 {
      color: #00e0ff;
    }

    @keyframes fadeIn {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Animation delays */
    .node1 { animation-delay: 5s; }
    .node2 { animation-delay: 10s; }
    .node3 { animation-delay: 15s; }

  </style>
</head>
<body>
  <div class="container">

    <!-- Community Heading -->
    <div class="heading">Community</div>

    <!-- Node 1: Discussion Forum -->
    <a href="#" class="node node1">
      <h3>1. Discussion Forum</h3>
      <p>Our discussion forum provides a platform for learners to engage with peers and instructors. By sharing thoughts and ideas, users gain new perspectives and insights. The forum fosters a sense of community, enabling learners to support and motivate each other. Through discussions, users clarify doubts and deepen their understanding.</p>
    </a>

    <!-- Node 2: Peer Review -->
    <a href="#" class="node node2">
      <h3>2. Peer Review</h3>
      <p>Our peer review feature enables learners to evaluate and provide feedback on each other's work. By reviewing peers' submissions, users develop critical thinking and analytical skills. Peer review promotes collaboration and knowledge sharing, helping learners improve their own work. Through constructive feedback, users refine their skills and build confidence.</p>
    </a>

    <!-- Node 3: Mentor Interaction -->
    <a href="#" class="node node3">
      <h3>3. Mentor Interaction</h3>
      <p>Our mentor interaction feature connects learners with experienced instructors and industry experts. By seeking guidance and feedback, users gain valuable insights and practical advice. Mentors provide personalized support, helping learners overcome challenges and achieve their goals. Through mentor interaction, users receive tailored guidance and motivation.</p>
    </a>

  </div>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Future Scope Mind Map</title>
  <style>
    body {
      background-color: black;
      font-family: Arial, sans-serif;
      color: skyblue;
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 50px 20px;
    }

    .box {
      border: 2px solid skyblue;
      border-radius: 10px;
      padding: 20px;
      margin: 20px;
      max-width: 700px;
      width: 100%;
      text-align: center;
      cursor: pointer;
      transition: transform 0.3s, background 0.3s;
    }

    .box:hover {
      transform: scale(1.03);
      background-color: rgba(135, 206, 235, 0.1);
    }

    .title-box {
      font-size: 32px;
      font-weight: bold;
      border: 3px solid skyblue;
      background-color: rgba(135, 206, 235, 0.1);
    }

    .content {
      display: none;
      color: #ccc;
      font-size: 16px;
      margin-top: 10px;
      text-align: left;
    }

    .box.active .content {
      display: block;
      animation: fadeIn 1s ease-in;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
  </style>
</head>
<body>

  <div class="box title-box" id="titleBox">
    Future Scope
  </div>

  <div class="box" id="node1" onclick="toggleContent(this)">
    <h2>1. AR/VR Learning</h2>
    <div class="content">
      <p>Our app leverages AR and VR to create immersive and interactive learning experiences. Students can explore virtual simulations and 3D models, making complex concepts more tangible and engaging. This enhances student engagement, promotes deeper comprehension, and improves learning outcomes.</p>
    </div>
  </div>

  <div class="box" id="node2" onclick="toggleContent(this)">
    <h2>2. AI Tutors</h2>
    <div class="content">
      <p>AI-powered tutors within our app provide personalized learning paths tailored to each student's needs and pace. They offer real-time feedback and support, addressing individual strengths and weaknesses. Available 24/7, these tutors empower students to learn at their convenience and receive instant assistance.</p>
    </div>
  </div>

  <div class="box" id="node3" onclick="toggleContent(this)">
    <h2>3. Skill Certification</h2>
    <div class="content">
      <p>We offer industry-recognized skill certifications that validate students' proficiency and expertise in specific domains. These certifications enhance employability, open doors to career advancement, and lead to potentially higher earning potential.</p>
    </div>
  </div>

  <div class="box" id="node4" onclick="toggleContent(this)">
    <h2>4. Job Placement Assistance</h2>
    <div class="content">
      <p>Our app provides comprehensive job placement assistance, helping students transition from learning to employment. This includes career counseling, resume building, interview preparation, and connecting students with relevant job opportunities.</p>
    </div>
  </div>

  <script>
    function toggleContent(element) {
      element.classList.toggle("active");
    }

    const nodes = ["node1", "node2", "node3", "node4"];
    nodes.forEach((id, index) => {
      setTimeout(() => {
        document.getElementById(id).style.display = "block";
      }, 5000 * (index + 1));  // +1 to start after title
    });

    window.onload = () => {
      nodes.forEach(id => {
        document.getElementById(id).style.display = "none";
      });
    };
  </script>

</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>EdTech Achievements Mindmap</title>
  <style>
    body {
      margin: 0;
      background-color: black;
      height: 100vh;
      overflow: hidden;
      font-family: Arial, sans-serif;
      color: white;
    }

    .container {
      position: relative;
      width: 100%;
      height: 100%;
    }

    .center {
      position: absolute;
      top: 10%;
      right: 5%;
      width: 180px;
      height: 180px;
      background: linear-gradient(135deg, #00c6ff, #0072ff);
      border-radius: 20px;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      color: white;
      font-size: 18px;
      font-weight: bold;
      box-shadow: 0 0 25px #00c6ff;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0% {
        box-shadow: 0 0 10px #00c6ff;
      }
      50% {
        box-shadow: 0 0 30px #00c6ff, 0 0 60px #00c6ff;
      }
      100% {
        box-shadow: 0 0 10px #00c6ff;
      }
    }

    .node {
      position: absolute;
      width: 320px;
      background-color: rgba(255, 255, 255, 0.05);
      border-left: 3px solid skyblue;
      padding: 15px 20px;
      border-radius: 10px;
      opacity: 0;
      color: skyblue;
      font-size: 14px;
      animation: fadeIn 2s ease forwards;
    }

    .node h3 {
      margin: 0 0 10px;
      font-size: 18px;
      color: skyblue;
    }

    @keyframes fadeIn {
      to {
        opacity: 1;
      }
    }

    .node1 {
      top: 35%;
      left: 10%;
      animation-delay: 5s;
    }

    .node2 {
      top: 60%;
      left: 10%;
      animation-delay: 10s;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="center">
      Achievements
    </div>

    <div class="node node1">
      <h3>1. Badges and Certificates</h3>
      <p>Our EdTech app rewards learners with badges and certificates for completing courses and achieving milestones. These visual symbols of accomplishment motivate users to continue learning. Badges and certificates can be showcased on social media or resumes, providing a sense of pride and recognition. By earning badges and certificates, learners feel a sense of achievement.</p>
    </div>

    <div class="node node2">
      <h3>2. Leaderboard</h3>
      <p>Our leaderboard ranks learners based on their progress, points, and achievements. By fostering a sense of friendly competition, we encourage users to strive for excellence. The leaderboard provides a clear picture of individual progress, motivating learners to climb the ranks. As learners compete with peers, they stay engaged and motivated to learn.</p>
    </div>
  </div>
</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Learning Modes - EdTech</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: black;
      color: white;
      font-family: Arial, sans-serif;
      overflow-x: hidden;
    }

    .container {
      width: 100%;
      padding: 50px 20px;
      box-sizing: border-box;
    }

    /* Learning Modes Heading */
    .heading {
      width: 100%;
      max-width: 800px;
      margin: 0 auto 40px auto;
      padding: 20px;
      background: linear-gradient(135deg, #00c6ff, #0072ff);
      border-radius: 15px;
      text-align: center;
      font-size: 24px;
      font-weight: bold;
      color: white;
      box-shadow: 0 0 25px #00c6ff;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0% {
        box-shadow: 0 0 10px #00c6ff;
      }
      50% {
        box-shadow: 0 0 30px #00c6ff, 0 0 60px #00c6ff;
      }
      100% {
        box-shadow: 0 0 10px #00c6ff;
      }
    }

    /* Clickable Cards */
    a.node {
      display: block;
      max-width: 800px;
      margin: 30px auto;
      padding: 20px;
      border-left: 4px solid skyblue;
      background-color: rgba(255, 255, 255, 0.05);
      border-radius: 10px;
      opacity: 0;
      transform: translateY(20px);
      color: skyblue;
      font-size: 14px;
      text-decoration: none;
      animation: fadeIn 2s ease forwards;
      transition: background-color 0.3s ease, border-color 0.3s ease;
      cursor: pointer;
    }

    a.node:hover {
      background-color: rgba(0, 198, 255, 0.15);
      border-left-color: #00e0ff;
      color: #00e0ff;
    }

    a.node h3 {
      margin-top: 0;
      color: skyblue;
      font-size: 20px;
      transition: color 0.3s ease;
    }

    a.node:hover h3 {
      color: #00e0ff;
    }

    @keyframes fadeIn {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Animation delays for sequential reveal */
    .node1 { animation-delay: 5s; }
    .node2 { animation-delay: 10s; }
    .node3 { animation-delay: 15s; }
    .node4 { animation-delay: 20s; }

  </style>
</head>
<body>
  <div class="container">
    <!-- Main Heading -->
    <div class="heading">Learning Modes</div>

    <!-- Video Lessons -->
    <a href="#" class="node node1">
      <h3>1. Video Lessons</h3>
      <p>Our EdTech app offers high-quality video lessons that cater to diverse learning styles. These engaging videos provide in-depth explanations and examples, making complex concepts easy to understand. With video lessons, learners can pause, rewind, and re-watch content at their own pace. This flexible approach enables effective learning and retention.</p>
    </a>

    <!-- Interactive Quizzes -->
    <a href="#" class="node node2">
      <h3>2. Interactive Quizzes</h3>
      <p>Our interactive quizzes assess learners' understanding and knowledge retention. By providing immediate feedback and explanations, we help users identify areas for improvement. These quizzes are designed to be engaging and fun, making learning an enjoyable experience. With interactive quizzes, learners can track their progress and build confidence.</p>
    </a>

    <!-- Case Studies -->
    <a href="#" class="node node3">
      <h3>3. Case Studies</h3>
      <p>Our case studies provide real-world examples and scenarios, enabling learners to apply theoretical knowledge. By analyzing case studies, users develop critical thinking and problem-solving skills. These practical examples help learners connect concepts to real-world applications. With case studies, users gain valuable insights and perspectives.</p>
    </a>

    <!-- Gamified Challenges -->
    <a href="#" class="node node4">
      <h3>4. Gamified Challenges</h3>
      <p>Our gamified challenges make learning fun and competitive. By incorporating game-like elements, we motivate learners to engage with content and achieve their goals. These challenges provide a sense of accomplishment and recognition, encouraging users to continue learning. With gamified challenges, learners develop a growth mindset and enjoy the learning process.</p>
    </a>
  </div>
</body>
</html>



<!DOCTYPE html>
<html>
<head>
  <title>College Connect App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f5f5f5;
    }
    header {
      background-color: #4CAF50;
      color: white;
      padding: 15px;
      text-align: center;
      font-size: 24px;
    }
    .container {
      display: flex;
      margin: 20px;
    }
    .sidebar, .feed, .profile {
      background-color: white;
      padding: 15px;
      margin-right: 20px;
      border-radius: 10px;
      flex: 1;
    }
    .feed-post {
      border-bottom: 1px solid #ddd;
      margin-bottom: 10px;
      padding-bottom: 10px;
    }
    .chat-box {
      margin-top: 10px;
    }
    input, textarea {
      width: 100%;
      padding: 8px;
      margin: 5px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      padding: 8px 12px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #45a049;
    }
  </style>
</head>
<body>
  <header>College Connect</header>
  
  <div class="container">
    <!-- Sidebar for Nearby Users -->
    <div class="sidebar">
      <h3>Nearby Students</h3>
      <ul id="nearbyUsers">
        <!-- Mock users -->
        <li>Jane, 19, Coding Skills</li>
        <li>Alex, 20, Marketing Skills</li>
        <li>Sam, 18, Graphic Design</li>
      </ul>
    </div>

    <!-- Feed -->
    <div class="feed">
      <h3>Feed</h3>
      <div id="feedPosts">
        <div class="feed-post">
          <strong>Jane:</strong> Looking for a study buddy for math.
        </div>
        <div class="feed-post">
          <strong>Alex:</strong> Offering help with resume building!
        </div>
      </div>
      <textarea id="newPost" placeholder="Share a post..."></textarea>
      <button onclick="addPost()">Post</button>
    </div>

    <!-- Profile -->
    <div class="profile">
      <h3>Your Profile</h3>
      <input type="text" id="name" placeholder="Your Name">
      <input type="number" id="age" placeholder="Your Age">
      <input type="text" id="state" placeholder="Your State">
      <input type="text" id="skills" placeholder="Skills (comma separated)">
      <input type="text" id="jobs" placeholder="Job Interests (comma separated)">
      <button onclick="saveProfile()">Save Profile</button>

      <div class="chat-box">
        <h4>Chat (Example)</h4>
        <textarea id="chatInput" placeholder="Type a message..."></textarea>
        <button onclick="sendMessage()">Send</button>
        <div id="chatMessages"></div>
      </div>
    </div>
  </div>

  <script>
    function addPost() {
      const postText = document.getElementById('newPost').value;
      if(postText.trim() !== '') {
        const feed = document.getElementById('feedPosts');
        const newPost = document.createElement('div');
        newPost.className = 'feed-post';
        newPost.innerHTML = '<strong>You:</strong> ' + postText;
        feed.prepend(newPost);
        document.getElementById('newPost').value = '';
      }
    }

    function saveProfile() {
      const name = document.getElementById('name').value;
      const age = document.getElementById('age').value;
      const state = document.getElementById('state').value;
      const skills = document.getElementById('skills').value;
      const jobs = document.getElementById('jobs').value;

      alert(`Profile Saved!\nName: ${name}\nAge: ${age}\nState: ${state}\nSkills: ${skills}\nJob Interests: ${jobs}`);
    }

    function sendMessage() {
      const chatInput = document.getElementById('chatInput').value;
      if(chatInput.trim() !== '') {
        const chatMessages = document.getElementById('chatMessages');
        const newMessage = document.createElement('div');
        newMessage.textContent = "You: " + chatInput;
        chatMessages.appendChild(newMessage);
        document.getElementById('chatInput').value = '';
      }
    }
  </script>
</body>
</html>

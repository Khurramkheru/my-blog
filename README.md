# my-blogmy-blog/
│
├── index.html
├── styles.css
└── script.js
<!doctype html>
<html lang="bn">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>আমার ব্লগ</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header>
    <h1>🖋️ আমার ব্লগ</h1>
    <p>ভাবনা, গল্প আর অভিজ্ঞতার ছোট্ট ডায়েরি</p>
  </header>

  <main>
    <section id="posts" class="post-list">
      <!-- পোস্টগুলো এখানে JS দিয়ে যোগ হবে -->
    </section>

    <section class="add-post">
      <h2>✍️ নতুন পোস্ট যোগ করুন</h2>
      <input type="text" id="titleInput" placeholder="পোস্টের শিরোনাম" />
      <textarea id="contentInput" placeholder="পোস্টের বিষয়বস্তু..."></textarea>
      <button id="addPostBtn">পোস্ট প্রকাশ করুন</button>
    </section>
  </main>

  <footer>
    <p>&copy; 2025 — আমার ব্লগ | তৈরি করেছেন <strong>আপনার নাম</strong></p>
  </footer>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: "Noto Sans Bengali", sans-serif;
  margin: 0;
  background: #f9f9f9;
  color: #333;
}

header {
  text-align: center;
  background: linear-gradient(90deg, #0077b6, #00b4d8);
  color: white;
  padding: 30px 10px;
}

h1 {
  margin-bottom: 10px;
}

main {
  max-width: 700px;
  margin: 30px auto;
  padding: 0 15px;
}

.post {
  background: white;
  margin-bottom: 20px;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.post h2 {
  margin-top: 0;
}

.add-post {
  background: #ffffff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.add-post input,
.add-post textarea {
  width: 100%;
  margin-bottom: 10px;
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ddd;
  font-family: inherit;
}

.add-post button {
  background: #0077b6;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  font-size: 1rem;
}

.add-post button:hover {
  background: #023e8a;
}

footer {
  text-align: center;
  padding: 15px;
  margin-top: 30px;
  font-size: 0.9em;
  color: #555;
}
const postsContainer = document.getElementById("posts");
const addPostBtn = document.getElementById("addPostBtn");

addPostBtn.addEventListener("click", () => {
  const title = document.getElementById("titleInput").value.trim();
  const content = document.getElementById("contentInput").value.trim();

  if (!title || !content) {
    alert("দয়া করে শিরোনাম ও বিষয়বস্তু লিখুন!");
    return;
  }

  const post = document.createElement("div");
  post.classList.add("post");
  post.innerHTML = `
    <h2>${title}</h2>
    <p>${content}</p>
    <small>প্রকাশের সময়: ${new Date().toLocaleString("bn-BD")}</small>
  `;
  postsContainer.prepend(post);

  // ইনপুট ফাঁকা করুন
  document.getElementById("titleInput").value = "";
  document.getElementById("contentInput").value = "";
});

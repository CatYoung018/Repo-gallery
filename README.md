# 📂 GitHub Repo Gallery

A dynamic web application that fetches and displays GitHub repositories in an interactive gallery format. Search through repositories, view detailed information, and explore projects with a clean, user-friendly interface.

![CSS](https://img.shields.io/badge/CSS-43.4%25-blue)
![JavaScript](https://img.shields.io/badge/JavaScript-38.9%25-yellow)
![HTML](https://img.shields.io/badge/HTML-17.7%25-orange)
![GitHub API](https://img.shields.io/badge/API-GitHub-181717?logo=github)

## 📸 Preview

![GitHub Repo Gallery](https://github.com/user-attachments/assets/09731278-7f53-4f73-b006-41c4b77bead5)

*Browse and explore GitHub repositories with an interactive gallery interface*

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [How It Works](#how-it-works)
- [Getting Started](#getting-started)
- [API Integration](#api-integration)
- [Project Structure](#project-structure)
- [Learning Outcomes](#learning-outcomes)
- [Future Enhancements](#future-enhancements)

---

## 🎯 About

**GitHub Repo Gallery** is an interactive web application that connects to the GitHub API to dynamically fetch and display repository information. Users can browse through repositories, search for specific projects, and view detailed information about each repository—all in a visually appealing gallery layout.

This project demonstrates proficiency in working with RESTful APIs, asynchronous JavaScript, and creating dynamic, data-driven web applications.

---

## ✨ Features

### 🔍 **Repository Search & Display**
- Fetch repositories from any GitHub user
- Display repository information in an organized gallery
- View key details: name, description, language, and more

### 📊 **Repository Information**
- **Repository Name** - Clear identification
- **Description** - Project summaries
- **Primary Language** - Technology used
- **Last Updated** - Recency information
- **Direct Links** - Quick access to GitHub repos

### 🎨 **User Interface**
- Clean, modern design
- Responsive layout for all devices
- Interactive hover effects
- Easy-to-navigate gallery view

### 🔗 **GitHub API Integration**
- Real-time data fetching
- Asynchronous operations
- Error handling for API requests
- Dynamic content rendering

---

## 🛠️ Technologies Used

### Frontend
- **HTML5** - Semantic structure
- **CSS3** - Styling and responsive design
- **JavaScript (ES6+)** - Dynamic functionality and API calls

### API & Data
- **GitHub REST API** - Repository data source
- **Fetch API** - Asynchronous HTTP requests
- **JSON** - Data format and parsing

### Key JavaScript Concepts
- Async/Await functions
- Promise handling
- DOM manipulation
- Event listeners
- Template literals
- Array methods (map, filter, forEach)

---

## 🔧 How It Works

### Data Flow

1. **User Input/Page Load**
   ```
   User visits site → JavaScript initializes → 
   Fetch request sent to GitHub API
   ```

2. **API Request**
   ```
   GitHub API receives request → 
   Returns JSON data → JavaScript processes response
   ```

3. **Display Repositories**
   ```
   Loop through repository data → 
   Create HTML elements dynamically → 
   Display in gallery format
   ```

4. **Search Functionality**
   ```
   User types in search → Filter repositories → 
   Update display with matching results
   ```

### GitHub API Endpoints Used

```javascript
// Fetch user repositories
GET https://api.github.com/users/{username}/repos

// Repository details include:
// - name, description, language
// - html_url, updated_at
// - and more...
```

---

## 🚀 Getting Started

### View Online

If deployed, you can view the live application here:
**[Live Demo Link]** *(Add your deployment link)*

### Run Locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/CatYoung018/Repo-gallery.git
   cd Repo-gallery
   ```

2. **Open in browser**
   - Simply open `index.html` in your web browser
   - Or use a local server:
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js http-server
   npx http-server
   ```

3. **View the application**
   - Navigate to `http://localhost:8000` (or the appropriate port)
   - Start exploring GitHub repositories!

**Prerequisites:**
- Modern web browser (Chrome, Firefox, Edge, Safari)
- Internet connection (for GitHub API access)

---

## 🔌 API Integration

### GitHub API Implementation

This project uses the GitHub REST API v3 to fetch repository data:

**Key Features:**
- No authentication required for public repositories
- Rate limit: 60 requests per hour for unauthenticated requests
- Returns comprehensive repository information
- Real-time data updates

**API Request Example:**
```javascript
async function getRepos(username) {
  const response = await fetch(`https://api.github.com/users/${username}/repos`);
  const data = await response.json();
  return data;
}
```

**Error Handling:**
- Checks for successful API responses
- Handles rate limiting
- Displays user-friendly error messages
- Graceful fallbacks for missing data

---

## 📁 Project Structure

```
Repo-gallery/
├── index.html           # Main HTML file
├── css/
│   └── style.css       # Styling and layout
├── js/
│   └── script.js       # JavaScript functionality and API calls
└── .gitignore          # Git ignore rules
```

---

## 📚 Learning Outcomes

This project demonstrates proficiency in:

- **API Integration** - Working with RESTful APIs
- **Asynchronous JavaScript** - Fetch API, async/await, Promises
- **Dynamic DOM Manipulation** - Creating elements programmatically
- **Error Handling** - Managing API errors and edge cases
- **JSON Data Parsing** - Working with structured data
- **ES6+ Features** - Modern JavaScript syntax
- **Responsive Design** - Mobile-friendly layouts
- **Event Handling** - User interactions
- **Array Methods** - Data manipulation and filtering

---

## 🎨 Code Highlights

### Fetching Repository Data
```javascript
// Async function to get repositories from GitHub
async function fetchRepositories(username) {
  try {
    const response = await fetch(`https://api.github.com/users/${username}/repos`);
    const repos = await response.json();
    displayRepos(repos);
  } catch (error) {
    console.error('Error fetching repos:', error);
  }
}
```

### Dynamic HTML Generation
```javascript
// Create repository cards dynamically
function displayRepos(repos) {
  repos.forEach(repo => {
    const repoCard = `
      <div class="repo-card">
        <h3>${repo.name}</h3>
        <p>${repo.description || 'No description available'}</p>
        <span class="language">${repo.language}</span>
        <a href="${repo.html_url}" target="_blank">View on GitHub</a>
      </div>
    `;
    container.innerHTML += repoCard;
  });
}
```

---

## 🔮 Future Enhancements

Potential improvements for future versions:

- [ ] Add filtering by programming language
- [ ] Sort repositories (stars, forks, recent)
- [ ] Display repository statistics (stars, forks, watchers)
- [ ] Add pagination for users with many repos
- [ ] Include search by topic/tags
- [ ] Show contributor information
- [ ] Add dark mode toggle
- [ ] Display repository README previews
- [ ] Save favorite repositories to LocalStorage
- [ ] Compare multiple repositories

---

## 🤝 Contributing

Contributions are welcome! If you'd like to improve the Repo Gallery:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

This project is open source and available for educational purposes.

---

## 🙏 Acknowledgments

- **Skillcrush** - Built as part of their front-end development program, which provided the skills and guidance to create this project including API integration best practices
- **GitHub REST API** - For providing access to repository data

---

## 📧 Contact

**Cat Young**  
- GitHub: [@CatYoung018](https://github.com/CatYoung018)
- LinkedIn: [Catrillia Young](https://www.linkedin.com/in/catrillia-young18/)
- Portfolio: [catyoung018.github.io/Cat-Young-Dev](https://catyoung018.github.io/Cat-Young-Dev/)

---

<div align="center">

**📂 Explore repositories in style! 🚀**

⭐ Star this repo if you find it helpful!

</div>

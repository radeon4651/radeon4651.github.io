# 🌟 Personal Portfolio Website

A professional, responsive portfolio website that automatically imports and displays your projects from a structured folder system. Built with vanilla HTML, CSS, and JavaScript for optimal performance and GitHub Pages compatibility.

## ✨ Features

### 🎨 **Professional Design**
- Modern, clean interface with smooth animations
- Responsive design (mobile, tablet, desktop)
- Accessible (WCAG 2.1 compliant)
- Professional color scheme and typography

### 📁 **Automatic Project Import**
- **Smart Scanning**: Automatically scans `projects/` folder structure
- **Description Import**: Reads `Description.txt` files from each project
- **Image Import**: Loads numbered images (1.jpg, 2.png, etc.) in order
- **Technology Detection**: Auto-detects technologies from descriptions and folder names
- **Validation**: Comprehensive validation with error reporting

### 🚀 **Performance & Compatibility**
- **GitHub Pages Ready**: No build process required
- **Fast Loading**: Optimized for 3-second load times
- **Progressive Enhancement**: Works without JavaScript
- **Cross-Browser**: Supports all modern browsers
- **Mobile-First**: Optimized for mobile devices

### ♿ **Accessibility Excellence**
- Semantic HTML structure
- ARIA labels and screen reader support
- Keyboard navigation
- Color contrast compliance
- Touch-friendly interface (44px minimum targets)

## 🚀 Quick Start

### 1. **Setup Your Projects**
```bash
# Create project folders
mkdir -p projects/my-awesome-app
mkdir -p projects/web-dashboard
mkdir -p projects/mobile-app

# Add descriptions
echo "A modern web application built with React and Node.js..." > projects/my-awesome-app/Description.txt

# Add images (optional)
cp screenshot1.png projects/my-awesome-app/1.png
cp screenshot2.jpg projects/my-awesome-app/2.jpg
```

### 2. **Import Projects**
```bash
# Scan and import all projects
python3 scan-projects.py
```

### 3. **Launch Website**
```bash
# Start development server
python3 serve.py

# Or use simple Python server
python3 -m http.server 8000
```

### 4. **View Your Portfolio**
Open `http://localhost:8000` in your browser!

## 📁 Project Structure

```
portfolio/
├── index.html              # Main portfolio page
├── projects.json           # Generated project data
├── serve.py               # Development server
├── scan-projects.py       # Project scanner
├── PROJECT-SETUP-GUIDE.md # Detailed setup guide
├── test-projects.html     # Project loading test page
└── projects/              # Your project folders
    ├── project-1/
    │   ├── Description.txt # Project description
    │   ├── 1.jpg          # First screenshot
    │   └── 2.png          # Second screenshot
    ├── project-2/
    │   ├── Description.txt
    │   └── 1.gif
    └── project-3/
        └── Description.txt
```

## 🔧 Project Requirements

### **Description Files**
- **File**: `Description.txt` in each project folder
- **Length**: 20-300 characters
- **Content**: Clear project description mentioning technologies used

### **Images (Optional)**
- **Naming**: Numerical order (1.jpg, 2.png, 3.gif, etc.)
- **Formats**: .jpg, .jpeg, .png, .gif, .webp, .svg
- **Auto-sizing**: Automatically resized to fit containers

### **Technology Detection**
Automatically detects from descriptions and folder names:
- **Frontend**: HTML5, CSS3, JavaScript, React, Vue.js, Angular
- **Backend**: Node.js, Express, Python, Django, Flask, PHP
- **Databases**: MongoDB, MySQL, PostgreSQL, Firebase
- **Tools**: Git, Docker, AWS, Bootstrap, Tailwind CSS

## 🎯 Example Project Setup

```bash
# Create a new project
mkdir -p projects/weather-dashboard

# Add description
cat > projects/weather-dashboard/Description.txt << EOF
A real-time weather dashboard built with React and OpenWeather API. Features location-based forecasts, interactive maps, and responsive design. Uses Redux for state management and Chart.js for data visualization.
EOF

# Add screenshots
cp ~/Desktop/weather-home.png projects/weather-dashboard/1.png
cp ~/Desktop/weather-map.jpg projects/weather-dashboard/2.jpg

# Import the project
python3 scan-projects.py

# Result: Weather Dashboard project appears on your portfolio!
```

## 🛠️ Development Tools

### **Project Scanner** (`scan-projects.py`)
- Scans all project folders
- Extracts descriptions and images
- Detects technologies automatically
- Validates project data
- Generates `projects.json`

### **Development Server** (`serve.py`)
- Enhanced Python HTTP server
- Automatic browser opening
- Security headers
- Clean logging
- Port auto-detection

### **Test Page** (`test-projects.html`)
- Tests project loading functionality
- Displays all imported project data
- Useful for debugging

## 📊 Project Validation

The scanner validates each project:

### ✅ **Complete Projects**
- Description: 20-300 characters ✓
- Technologies: At least one detected ✓
- Valid data structure ✓

### ⚠️ **Projects with Warnings**
- Valid but could be improved
- Missing images or links
- Recommendations provided

### ❌ **Incomplete Projects**
- Missing or invalid description
- No technologies detected
- Shows error indicators

## 🎨 Customization

### **Update Links**
Edit `scan-projects.py` to customize demo and source links:
```python
def generate_demo_link(self, project_name: str) -> str:
    return f"https://your-domain.com/{project_name}"

def generate_source_link(self, project_name: str) -> str:
    return f"https://github.com/your-username/{project_name}"
```

### **Add Technologies**
Add custom technology detection:
```python
tech_keywords = {
    'your-framework': 'Your Framework',
    'custom-tool': 'Custom Tool',
    # ... existing keywords
}
```

### **Styling**
Customize colors and fonts in `index.html`:
```css
:root {
    --primary-color: #your-color;
    --secondary-color: #your-secondary;
    /* ... other variables */
}
```

## 🚀 GitHub Pages Deployment

### **Automatic Deployment**
1. Push all files to your GitHub repository
2. Go to Settings → Pages
3. Select "Deploy from a branch" → "main" → "/ (root)"
4. Your portfolio will be live at `https://username.github.io/repository-name`

### **Custom Domain (Optional)**
1. Add `CNAME` file with your domain
2. Configure DNS with your domain provider
3. Enable "Enforce HTTPS" in GitHub Pages settings

## 🧪 Testing

### **Local Testing**
```bash
# Test project loading
open http://localhost:8000/test-projects.html

# Test main portfolio
open http://localhost:8000

# Validate projects.json
cat projects.json | python3 -m json.tool
```

### **Cross-Browser Testing**
- Chrome, Firefox, Safari, Edge
- Mobile browsers (iOS Safari, Chrome Mobile)
- Test responsive breakpoints

### **Accessibility Testing**
- Keyboard navigation (Tab, Enter, Arrow keys)
- Screen reader compatibility
- Color contrast validation

## 📈 Performance

### **Load Time Requirements**
- **Broadband (≥5 Mbps)**: ≤3 seconds ✓
- **Mobile 3G**: ≤5 seconds ✓
- **Graceful degradation**: Works on slow connections ✓

### **Optimization Features**
- Lazy loading images
- Efficient CSS and JavaScript
- Minimal external dependencies
- Progressive enhancement

## 🐛 Troubleshooting

### **Common Issues**

**"No projects found"**
- Ensure `projects/` folder exists
- Check for `Description.txt` files in subfolders

**"Description too short"**
- Descriptions must be 20+ characters
- Add more project details

**"Images not loading"**
- Use numerical names (1.jpg, 2.png)
- Check supported formats
- Verify file paths

**"Technologies not detected"**
- Mention specific technologies in descriptions
- Use recognizable names (React, Node.js, Python)

### **Debug Commands**
```bash
# Verbose project scanning
python3 scan-projects.py

# Check server logs
# (server shows request logs in terminal)

# Validate JSON structure
python3 -c "import json; print(json.load(open('projects.json')))"
```

## 📚 Documentation

- **[PROJECT-SETUP-GUIDE.md](PROJECT-SETUP-GUIDE.md)**: Detailed project setup instructions
- **[test-projects.html](test-projects.html)**: Project loading test page
- **Console logs**: Check browser console for debugging info

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🎉 You're Ready!

Your professional portfolio website is now set up with automatic project import! 

**Next Steps:**
1. Add your real projects to the `projects/` folder
2. Run `python3 scan-projects.py` to import them
3. Customize the About and Contact sections in `index.html`
4. Deploy to GitHub Pages
5. Share your amazing portfolio with the world! 🌍

**Need Help?** Check the troubleshooting section or open an issue in the repository.

**Happy Coding!** 🚀
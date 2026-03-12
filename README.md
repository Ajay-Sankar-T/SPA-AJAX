# ⚡ Single Page Application (SPA)

**AJAX + XMLHttpRequest** frontend consuming **JSON API** (Project #4). **NO PAGE RELOADS**.

## 🎯 Project Requirements
- **Single HTML file**
- **AJAX / XMLHttpRequest**
- **JSON API integration**
- **Dynamic DOM updates**
- **First Assessment - 25 marks**

## 🎭 SPA Architecture

```
index.html ──User Input──> XMLHttpRequest
     │
     ↓ GET ../api-search/api.php?q=term
     │
JSON ──> parse() ──> Build HTML ──> document.getElementById('results').innerHTML
```

## 🔄 Core JavaScript Flow

```javascript
// 1. Create XHR
const xhr = new XMLHttpRequest();
xhr.open('GET', `../api-search/api.php?q=${query}`, true);

// 2. Handle response  
xhr.onreadystatechange = () => {
    if (xhr.readyState === 4 && xhr.status === 200) {
        const data = JSON.parse(xhr.responseText);
        // 3. Dynamic DOM update
        results.innerHTML = buildStudentCards(data.results);
    }
};
xhr.send();
```

## ✨ Features Demonstrated
- ✅ **XMLHttpRequest** (not fetch)
- ✅ **JSON parsing**
- ✅ **Asynchronous** (no blocking)
- ✅ **DOM manipulation**
- ✅ **Loading states**
- ✅ **Error handling**
- 🎨 **Card animations** (CSS hover)

## 📡 API Dependency
```
Consumes: ../api-search/api.php?q=term
Expects: {status, count, results[]}
```

## 🚀 Zero Setup
```
1. htdocs/spa-app/index.html
2. api-search project running (same XAMPP)
3. http://localhost/spa-app/
```

## 🧪 User Experience Tests

| Action | Expected | Tech Used |
|--------|----------|-----------|
| Page load | Auto "ME" search | `window.onload` |
| Type+Enter | Instant results | `keypress` event |
| Search button | Loading → Cards | XHR + DOM |
| Empty search | "No results" | Conditional render |
| API down | Graceful error | `xhr.status` check |

## 🎨 Visual Features
```
✅ Responsive cards (Bootstrap 5)
✅ Hover animations (CSS transform)
✅ Loading spinners
✅ Gradient background
✅ Mobile optimized
✅ Real-time status
```

## 🔍 Single File Magic
```
1 File: 138 lines
- HTML structure
- CSS styling  
- XMLHttpRequest logic
- DOM manipulation
- Error handling
- Responsive design
```

## 🛤️ Integration Chain
```
Project #1 (DB) → #3 (Search) → #4 (JSON API) → #5 (SPA Frontend)
```

## 📊 Live Demo
```
http://localhost/spa-app/
Type: "BCA", "23BCA", "ME", Enter
Watch: NO PAGE RELOAD! ✨
```

**First Assessment Project #5**  
**Status: 25/25 marks** ✅  
**Complete 5/5 project suite**  
**Built: March 13, 2026**  
**Author: Ajay Sankar T**
```

# My LLM-Style Bio

A minimal static web app that displays your bio as if it were typed by ChatGPT.  
It types text character-by-character (with bursts and pauses for realism), supports **Markdown** formatting, and can load bios from local `.md` files. 

> ⚡️ This whole repo has been **vibe-coded** — meant to be hacked on, adapted, and shared.

---

Features:
- 🖋️ Realistic typing effect with variable speed  
- 🔗 Markdown support (links, code, lists, etc.)  
- • List items show their bullets **as soon as they start typing**  
- 🔄 Regenerate button with refresh icon to reload a random bio  
- 📂 Bios stored as individual Markdown files, listed in `bios/manifest.json`  
- 📎 Source button linking to this repo  

---

## Project Structure

/index.html          # Main app

/bios/manifest.json  # List of bio Markdown files

/bios/bio1.md        # Example bio

/bios/bio2.md

…

/README.md           # This file

## How It Works

1. **HTML & CSS**  
   - `index.html` creates a ChatGPT-like UI with header, chat bubble area, and footer buttons.  
   - Styling mimics a minimal chat window.

2. **Markdown Bios**  
   - Each bio lives in its own `.md` file under `/bios/`.  
   - `manifest.json` is just an array of file paths, e.g.:
     ```json
     [
       "bios/bio1.md",
       "bios/bio2.md",
       "bios/bio3.md"
     ]
     ```

3. **Typing Effect**  
   - When the page loads, JavaScript:
     - Picks a random `.md` file from the manifest  
     - Fetches and sanitizes the Markdown  
     - Builds the final HTML once  
     - Reveals it character-by-character, simulating typing  

4. **Buttons**  
   - **Regenerate**: reloads a new random bio  
   - **Source**: links to the GitHub repo (replace with your own)

---

## How To Run

You need to serve it via HTTP (because browsers block `fetch` for local `file://` URLs).

### Option 1: Python

```bash
python3 -m http.server 8000
```

Then open: [http://localhost:8000](http://localhost:8000)

### Option 2: Node.js
  
```
npx serve
```


---

## **Adapting It**

1. In index.html, change the chat header:
	```html
	<div class="chat-header">Your Name</div>
	```
   and
   ```html
   <title>Your Name</title>
   ```
2. Write your own bios in Markdown (/bios/bioX.md).
3. Update bios/manifest.json with your files.

---

## **License**

MIT — free to use, modify, and share.

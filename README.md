# Gemini HTML → TXT / MD (PowerShell)

Two small PowerShell scripts to archive locally saved **Google Gemini** chats.

- **GeminiSavedHtmlToTxt.ps1** – export assistant replies to numbered `.txt` files.
- **GeminiHtmlSaveToMD_OverPandoc.ps1** – convert assistant replies to numbered `.md` files via **Pandoc** (GitHub-Flavored Markdown).

---

## 1) GeminiSavedHtmlToTxt.ps1

### What it does
Parses a locally saved Google Gemini chat **HTML** file and exports the **assistant’s replies** as individual, plain-text files (`.txt`).  
Each reply becomes `001.txt`, `002.txt`, … in the output folder.

### Why it’s useful
- Creates a clean, offline archive of your Gemini conversations.
- Plain text is easy to search, diff, and feed into other tools.
- Keeps each reply separate—ideal for datasets or notes.

### How it works (high level)
1. Loads the HTML from disk.  
2. Locates the assistant message blocks.  
3. Extracts their textual content.  
4. Writes numbered `.txt` files to the chosen output directory.

### Requirements
- Windows with PowerShell.
- A locally saved Gemini chat page (HTML).

### Output
A folder (e.g., `C:\temp\output`) containing `001.txt`, `002.txt`, … each with one assistant reply.

---

## 2) GeminiHtmlSaveToMD_OverPandoc.ps1

### What it does
Converts a locally saved Google Gemini chat **HTML** into **Markdown** (`.md`) using **Pandoc**.  
Exports each assistant reply as its own Markdown file (GitHub-Flavored Markdown).

### Why it’s useful
- Produces clean, portable Markdown for docs, wikis, and repos.
- Preserves basic formatting better than raw text.
- Works smoothly with static site generators and code review workflows.

### How it works (high level)
1. Verifies **Pandoc** is installed and on `PATH`.  
2. Loads the HTML and identifies assistant reply blocks.  
3. Streams each block through Pandoc (`-f html -t gfm`) to produce `.md`.  
4. Saves numbered Markdown files to the output directory.

### Requirements
- Windows with PowerShell.
- **Pandoc** installed (and on `PATH`).
- A locally saved Gemini chat page (HTML).

### Output
A folder (e.g., `C:\temp\output`) containing `001.md`, `002.md`, … each with one assistant reply in GFM.

---

## Usage

### 1) GeminiSavedHtmlToTxt.ps1 (manual edit)

1. Open the script and edit these lines to your paths:
   ```powershell
   $htmlFilePath = "C:\temp\Google Gemini.html"
   $outputDir    = "C:\temp\output"


---

## Notes (both scripts)

* Update your input HTML path and output directory as needed.
* Works fully **offline** on local files—no credentials required.
* Files are zero-padded to keep ordering.

---

## License

MIT License
Copyright (c) 2025 Selahattin Erkoc

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

---

## Legal

“Pandoc” is a separate tool by John MacFarlane and contributors.
“Google” and “Gemini” are trademarks of Google LLC.
“Microsoft” and “Windows” are trademarks of Microsoft Corporation.
All other names are trademarks of their respective owners. Use here is for identification only; no endorsement implied.


# GeminiSavedHtmlToTxt.ps1

**What it does**
Parses a locally saved **Google Gemini chat HTML** file and exports the **assistant’s replies** as individual, plain-text files (`.txt`). Each response becomes `001.txt`, `002.txt`, … in an output folder.

**Why it’s useful**

* Creates a clean, offline archive of your Gemini conversations.
* Plain text is easy to search, diff, or feed into other tools.
* Keeps each reply separate, which is ideal for dataset building or notes.

**How it works (high level)**

* Loads the HTML from disk.
* Locates the message/reply blocks in the page.
* Extracts their textual content.
* Writes them as numbered `.txt` files to the chosen output directory.

**Requirements**

* Windows with PowerShell.
* A locally saved Gemini chat page (HTML).

**Output**
A folder (e.g., `C:\temp\output`) containing `001.txt`, `002.txt`, … each holding one assistant response.

---

# GeminiHtmlSaveToMD_OverPandoc.ps1

**What it does**
Converts a locally saved **Google Gemini chat HTML** into **Markdown** (`.md`) using **Pandoc**. Exports each assistant reply as its own Markdown file (GitHub-Flavored Markdown).

**Why it’s useful**

* Produces clean, portable Markdown for documentation, wikis, or Git repos.
* Preserves basic formatting better than raw text.
* Plays nicely with static site generators and code review workflows.

**How it works (high level)**

* Verifies that **Pandoc** is installed and available on `PATH`.
* Loads the HTML, identifies the assistant reply blocks.
* Streams each reply through Pandoc (`-f html -t gfm`) to generate `.md`.
* Saves numbered Markdown files into the output directory.

**Requirements**

* Windows with PowerShell.
* **Pandoc** installed (and on `PATH`).
* A locally saved Gemini chat page (HTML).

**Output**
A folder (e.g., `C:\temp\output`) containing `001.md`, `002.md`, … each holding one assistant response in GFM.

---

## Notes for both scripts

* Update the `$htmlFilePath` and `$outputDir` variables to match your environment.
* Both scripts work offline on local files—no credentials required.
* Ideal for backing up, cleaning, and reusing Gemini content across tooling.

---

## MIT License

### Copyright (c) 2025 Selahattin Erkoc

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


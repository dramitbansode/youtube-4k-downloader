# youtube-4k-downloader
Extract YouTube links from Word files and download in 4K/8K quality
# 🎬 YouTube 4K/8K Bulk Downloader

Extract YouTube links from a Word document (.docx) and download them in the highest available quality.

## 📁 Files in This Repository

| File | Description | ffmpeg Required |
|------|-------------|-----------------|
| `downloader_4k.py` | Downloads up to 4K/8K by merging separate video/audio streams | ✅ Yes |
| `downloader_simple.py` | Downloads up to 720p using built-in progressive streams | ❌ No |
| `README.md` | This guide | - |

---

## 🚀 Quick Start (New Machine)

### Step 1: Download Files from GitHub

1. Go to your repository on GitHub
2. Click the **green "Code" button**
3. Select **"Download ZIP"**
4. Extract the ZIP to your desired folder

**Or use git (if installed):**
```bash
git clone https://github.com/YOUR_USERNAME/youtube-4k-downloader.git
cd youtube-4k-downloader


Step 2: Install Python
Download from python.org
Important: Check "Add Python to PATH" during installation
Step 3: Install Required Libraries
Open terminal (Command Prompt/PowerShell) in the project folder:
bash
pip install python-docx pytubefix
Step 4: Install ffmpeg (For 4K Version Only)
Skip this if using downloader_simple.py
Windows:
Download: https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-essentials.zip
Extract to your project folder
Find the bin folder inside (may be nested: ffmpeg-x.x.x-essentials_build/ffmpeg-x.x.x-essentials_build/bin/)
Update FFMPEG_PATH in downloader_4k.py line 25:
FFMPEG_PATH = r"D:\your\path\to\ffmpeg\bin\ffmpeg.exe"

Mac:
brew install ffmpeg

Linux:
sudo apt install ffmpeg


Step 5: Prepare Your Word File
Create a new Word document
Name it: videos.docx
Paste YouTube links inside (as text or clickable hyperlinks)
Save in the same folder as the script
Example content:
https://www.youtube.com/watch?v=dQw4w9WgXcQ
https://youtu.be/anotherVideoID

Step 6: Run the Script
For 4K/8K quality (requires ffmpeg):
Bash
python downloader_4k.py

For simple 720p (no ffmpeg needed):
Bash
python downloader_simple.py

📊 Quality Comparison
| Feature         | `downloader_4k.py`         | `downloader_simple.py` |
| --------------- | -------------------------- | ---------------------- |
| Max Resolution  | 4K / 8K                    | 720p                   |
| Audio Quality   | Best (original)            | Good (compressed)      |
| File Size       | Large (1-5 GB)             | Medium (100-500 MB)    |
| Requires ffmpeg | ✅ Yes                      | ❌ No                   |
| Download Speed  | Slower (2 streams + merge) | Faster (single stream) |
| Use Case        | Archiving, editing         | Quick viewing, sharing |



🔧 How the 4K Version Works
┌─────────────────┐     ┌──────────────────┐     ┌─────────────┐
│  Read Word File │────▶│ Extract YouTube  │────▶│  For Each   │
│   (videos.docx) │     │      Links       │     │    Link     │
└─────────────────┘     └──────────────────┘     └──────┬──────┘
                                                        │
                              ┌───────────────────────┼───────────────────────┐
                              ▼                       ▼                       ▼
                        ┌──────────┐            ┌──────────┐            ┌──────────┐
                        │ Download │            │ Download │            │  Merge   │
                        │  Video   │            │  Audio   │            │  with    │
                        │ (4K/8K)  │            │ (Best)   │            │  ffmpeg  │
                        │ No Audio │            │ No Video │            │ -c copy  │
                        └──────────┘            └──────────┘            └──────────┘
                                                                              │
                                                                              ▼
                                                                       ┌──────────┐
                                                                       │ Final    │
                                                                       │ .mp4     │
                                                                       │ (4K/8K)  │
                                                                       └──────────┘


🛠️ Troubleshooting
| Problem                 | Cause                       | Solution                                         |
| ----------------------- | --------------------------- | ------------------------------------------------ |
| `ffmpeg not found`      | Wrong path or not installed | Check path in code, reinstall ffmpeg             |
| `ModuleNotFoundError`   | Libraries not installed     | Run `pip install python-docx pytubefix`          |
| `File not found`        | Wrong folder or filename    | Ensure `videos.docx` is in same folder as script |
| `No links found`        | Links not recognized        | Check URL format, try plain text links           |
| Very slow download      | Large 4K file               | Normal - 4K videos are 2-5 GB each               |
| Merge fails             | ffmpeg error                | Check ffmpeg path, ensure temp files deleted     |
| `python not recognized` | Python not in PATH          | Reinstall Python with "Add to PATH" checked      |


💡 Pro Tips
Start with simple version to test your setup, then switch to 4K
Check disk space before downloading - 4K videos are huge
Use a fast internet connection - 4K downloads can take 30+ minutes
Keep ffmpeg in your project folder for easy path management
Use private repos if your video links are sensitive


📦 Requirements Summary
| Requirement | 4K Version | Simple Version |
| ----------- | ---------- | -------------- |
| Python 3.7+ | ✅          | ✅              |
| python-docx | ✅          | ✅              |
| pytubefix   | ✅          | ✅              |
| ffmpeg      | ✅          | ❌              |
| Disk space  | 5-20 GB    | 1-5 GB         |


📝 Changelog
| Date       | Change                                      |
| ---------- | ------------------------------------------- |
| 2026-07-03 | Initial release with 4K and simple versions |


📄 License
Personal use only. Respect YouTube's Terms of Service.

Created: 2026-07-03
Repository: https://github.com/YOUR_USERNAME/youtube-4k-downloader



4. Scroll down, commit message: `Update README with complete guide`
5. Click **Commit changes**

---

### Step 6: Create a `.gitignore` File (Optional but Recommended)

1. **Add file** → **Create new file**
2. Name: `.gitignore`
3. Paste:



Ignore downloaded videos
downloads/
*.mp4


Ignore temp files
temp_*

Ignore Python cache
pycache/
*.pyc

Ignore Word files (keep links private)
videos.docx
4. Commit message: `Add .gitignore`
5. Click **Commit new file**

---

## How to Use on a New Machine (After Saving on GitHub)

| Step | Action |
|------|--------|
| 1 | Go to `github.com/YOUR_USERNAME/youtube-4k-downloader` |
| 2 | Click **Code** → **Download ZIP** |
| 3 | Extract ZIP to new machine |
| 4 | Follow README.md instructions |
| 5 | Install Python, libraries, ffmpeg |
| 6 | Create `videos.docx` with your links |
| 7 | Run `python downloader_4k.py` |

---

## Your Repository Structure Will Look Like

youtube-4k-downloader/
├── .gitignore              # Ignore downloads & temp files
├── README.md               # Complete guide (this file)
├── downloader_4k.py        # 4K/8K version (needs ffmpeg)
└── downloader_simple.py    # 720p version (no ffmpeg)


---

## Quick Reference: Download Single File from GitHub

If you only need one file (not the whole repo):

1. Open the file in GitHub
2. Click **Raw** button (top right)
3. Press **Ctrl + S** to save
4. Or right-click → **Save As**

---

**Your GitHub repo is now ready!** You can access it from any machine, read the guide, and download the files you need. Want me to add anything else?

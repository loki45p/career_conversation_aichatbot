---
title: career_conversation
app_file: app.py
sdk: gradio
sdk_version: 5.49.1
---
# Career Conversation AI Chatbot 🤖
 
A career coaching chatbot built with Gradio and OpenAI, deployed on Hugging Face Spaces.
 
---
 
## 🚀 Live Demo
[https://huggingface.co/spaces/laxman45p/career_conversation](https://huggingface.co/spaces/laxman45p/career_conversation)
 
---
 
## 🛠️ Tech Stack
- **UI:** Gradio
- **AI:** OpenAI API
- **PDF Parsing:** pypdf
- **Notifications:** Pushover
- **Hosting:** Hugging Face Spaces
 
---
 
## 📁 Project Structure
```
career_conversation_aichatbot/
├── app.py               # Main application
├── me/
│   ├── linkedin.pdf     # Your LinkedIn profile export
│   └── summary.txt      # Your personal summary
├── requirements.txt     # Python dependencies
└── README.md            # This file
```
 
---
 
## 📦 requirements.txt
```txt
gradio
openai>=1.0.0
pypdf
python-dotenv
requests
```
 
---
 
## 🔑 Getting Your API Keys
 
### OpenAI API Key
1. Go to [platform.openai.com](https://platform.openai.com)
2. Settings → API Keys → **Create new secret key**
 
### Pushover Credentials
1. Go to [pushover.net](https://pushover.net) and sign up
2. On the home screen, click **"Create an Application/API Token"**, give it a name (e.g. `Agents`) and click **Create Application**
3. **PUSHOVER_USER** → Top right of your Pushover home screen
4. **PUSHOVER_TOKEN** → Inside your new application page
5. Click **"Add Phone, Tablet or Desktop"** to install the app on your phone
 
---
 
## 🔐 Environment Variables
Add these to your `.env` file:
```env
OPENAI_API_KEY=sk-proj-...
PUSHOVER_USER=u...
PUSHOVER_TOKEN=a...
HF_TOKEN=hf_...
```
 
---
 
## 🤗 Deploy to Hugging Face Spaces
 
### Before You Start
- Update the files in the `me/` directory with **your own** LinkedIn PDF and `summary.txt`
- In `app.py`, change `self.name = "YOUR NAME"` to your own name

 
---
 
### Step 1 — Install uv
`uv` is a fast Python package and project manager. Install it once on your machine:
 
**Mac / Linux:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```
 
**Windows:**
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```
 
**Or via pip:**
```bash
pip install uv
```
 
Verify installation:
```bash
uv --version
```
 
---
 
### Step 2 — Create a Hugging Face Account
- Sign up at [huggingface.co](https://huggingface.co)
 
---
 
### Step 3 — Create a HuggingFace Access Token
1. Click your **Avatar** (top right) → **Access Tokens**
2. Click **"Create New Token"**
3. Give it **WRITE** permissions ⚠️ (Write is required!)
4. Copy the token and save it to your `.env` file:
   ```env
   HF_TOKEN=hf_xxxxxx
   ```
 
---
 
### Step 4 — Install HuggingFace CLI
```bash
uv tool install 'huggingface_hub[cli]'
```
 
---
 
### Step 5 — Login via CLI
```bash
hf auth login --token YOUR_TOKEN_HERE
# e.g. hf auth login --token hf_xxxxxx
```
 
Verify you're logged in:
```bash
hf auth whoami
```
 
---
 
### Step 6 — Deploy
From the `1_foundations` folder, run:
```bash
uv run gradio deploy
```
 
---
 
### Step 7 — Follow the Prompts
When prompted, enter the following:
 
| Prompt | Answer |
|---|---|
| Space name | `career_conversation` |
| App file | `app.py` |
| Hardware | `cpu-basic` |
| Supply secrets? | `Yes` |
| OPENAI_API_KEY | `sk-proj-...` |
| PUSHOVER_USER | `u...` |
| PUSHOVER_TOKEN | `a...` |
| GitHub Actions? | `No` |
 
> **Tip on entering secrets:** It will ask for the key name and value separately. Enter the name first (e.g. `OPENAI_API_KEY`), press Enter, then enter the value (e.g. `sk-proj-...`).
 
---
 
## 🔧 Updating Secrets After Deployment
If something goes wrong with secrets or you need to update them later:
1. Log in to [huggingface.co](https://huggingface.co)
2. Go to your **Avatar** → your profile
3. Click on your Space
4. Click the **Settings wheel** (top right)
5. Scroll down to **Variables and Secrets** section
 
---
 
## ♻️ Redeploying
If you need to completely redeploy from scratch:
1. Delete the `README.md` that was created in the `1_foundations` folder by the previous deploy
2. Run `uv run gradio deploy` again
3. It will ask you all the setup questions fresh
 
---
 
## 🗑️ Deleting Your Space
1. Log in to HuggingFace
2. Avatar → Profile → click your Space
3. Click the **Settings wheel** (top right)
4. Scroll to the **Delete** section at the bottom
5. Also delete the `README.md` created in the `1_foundations` folder
 
---
 
## 📚 Further Reading
- [Gradio Sharing Guide](https://www.gradio.app/guides/sharing-your-app#hosting-on-hf-spaces)
- [uv Documentation](https://docs.astral.sh/uv/)
- [HuggingFace Spaces Docs](https://huggingface.co/docs/hub/spaces)
 
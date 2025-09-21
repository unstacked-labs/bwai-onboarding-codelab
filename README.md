author: Unstacked Labs
summary: Complete setup guide for building modern AI applications with Google's cutting-edge technologies
id: docs
categories: AI,Development,Google Cloud,Genkit,Agent Development Kit
environments: Web
status: Published
feedback link: https://github.com/unstacked/unstacked-onboarding-workshop/issues
analytics account:

# Build with AI - Setup Guide

Welcome to **Build with AI** by Unstacked Labs! This setup guide will prepare
your development environment for building modern AI applications with Google's
cutting-edge technologies.

## 🚀 What You'll Build

Get ready to create incredible AI applications using three powerful Google AI technologies:

**🔥 Genkit (TypeScript)** - Build conversational AI chatbots, content generators, and intelligent workflows

- Example: AI-powered story writer that creates personalized narratives
- Example: Smart customer service bot with context awareness
- Example: Content summarizer for documents and articles

**🐍 Agent Development Kit (Python)** - Create sophisticated AI agents and automation systems

- Example: Intelligent data analysis agent that generates insights from spreadsheets
- Example: Multi-step research assistant that gathers and synthesizes information
- Example: Smart scheduling agent that coordinates meetings across timezones

**☁️ Google Cloud Vertex AI** - Deploy and scale your AI models in the cloud

- Example: Image recognition system for product categorization
- Example: Real-time sentiment analysis for social media monitoring
- Example: Predictive analytics dashboard for business intelligence

## 🎯 Ready to Start?

This guide focuses on **environment setup only**. The actual coding tutorials, step-by-step projects, and hands-on codelabs will be provided during the workshop sessions.

**Your goal**: Complete this setup to be ready for an incredible learning experience!

## 📅 Workshop Information

For detailed schedule information and registration, visit: **[Build with AI Workshop](https://unstacked.dev/build-with-ai/)**

## 💻 System Requirements

### Minimum Requirements

- **Operating System**: Windows 10+ (ends October 14, 2025), macOS 12+ (Monterey or later), or Ubuntu 20.04+ LTS (Ubuntu 18.04 ended standard support June 2023)
- **RAM**: 8GB minimum, 16GB recommended
- **Storage**: 10GB free space
- **Internet**: Stable broadband connection
- **Browser**: Chrome, Firefox, Safari, or Edge (latest versions)

### Supported Operating Systems

This workshop provides setup instructions for:

- 🪟 **Windows 10/11** (with WSL2 support)
- 🍎 **macOS** (Intel and Apple Silicon)
- 🐧 **Linux** (Ubuntu, Debian, CentOS, Fedora)

### 💡 Less Powerful Machine? No Problem!

**Don't have a powerful machine or facing installation issues?** We've got you covered with cloud-based alternatives:

- **🔥 Firebase Studio** - Cloud-based development environment with zero setup required

  - Perfect for Genkit development without local Node.js installation
  - Access from any device with a browser
  - Pre-configured templates ready to use

- **💻 GitHub Codespaces** - Full VS Code environment in the cloud

  - Works for all three platforms (Genkit, ADK, Vertex AI)
  - Free tier includes 60 hours per month
  - No local installation needed

- **💬 Discord Community** - Join our support server for:
  - Real-time help with setup issues
  - Community troubleshooting
  - Collaboration and project sharing
  - **[Join our Discord](https://discord.gg/unstacked)**

These alternatives ensure everyone can participate regardless of their hardware limitations!

## 🚀 Quick Start

1. Choose your operating system section below
2. Follow the setup instructions for each platform
3. Verify your installation with the provided tests
4. Join our community for support and discussions

---

## Genkit (TypeScript) Setup

**What is Genkit?** Google's AI application framework for TypeScript developers. Perfect for building conversational AI, content generators, and intelligent workflows.

**What you'll build:** AI-powered applications like chatbots, content creators, and smart automation tools.

### Prerequisites Checklist

Before starting, ensure you have:

- [ ] Administrator/sudo access on your machine
- [ ] A Google account for Firebase access
- [ ] A code editor (VS Code recommended)
- [ ] **Gemini API key** from [Google AI Studio](https://aistudio.google.com/apikey) (free with quota limits)

## Operating System Specific Setup

### 🪟 Windows Setup

#### Step 1: Install Node.js and npm

**Option A: Using Official Installer (Recommended)**

```bash
# Download and install from https://nodejs.org/
# Choose the LTS version (Long Term Support)
# This will include npm automatically
```

**Option B: Using Chocolatey**

```powershell
# First install Chocolatey if you haven't already
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

# Then install Node.js
choco install nodejs
```

**Option C: Using Winget**

```cmd
winget install OpenJS.NodeJS
```

#### Step 2: Setup WSL2 (Optional but Recommended)

```powershell
# Enable WSL and install Ubuntu
wsl --install
# Restart your computer when prompted
# Follow Linux setup instructions within WSL
```

#### Step 3: Verify Installation

```cmd
node --version
npm --version
# Should show version numbers (Node.js v20+ and npm 10+ recommended)
```

### 🍎 macOS Setup

#### Step 1: Install Homebrew (if not already installed)

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### Step 2: Install Node.js and npm

**Option A: Using Homebrew (Recommended)**

```bash
brew install node
```

**Option B: Using Official Installer**

```bash
# Download from https://nodejs.org/
# Choose the macOS installer for your chip (Intel or Apple Silicon)
```

**Option C: Using Node Version Manager (for multiple Node versions)**

```bash
# Install nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
# Restart terminal or run:
source ~/.bashrc
# Install latest LTS Node.js
nvm install --lts
nvm use --lts
```

#### Step 3: Verify Installation

```bash
node --version
npm --version
```

### 🐧 Linux Setup

#### Ubuntu/Debian

**Option A: Using Package Manager**

```bash
# Update package index
sudo apt update

# Install Node.js and npm
sudo apt install nodejs npm

# For latest version, use NodeSource repository
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

**Option B: Using Snap**

```bash
sudo snap install node --classic
```

#### CentOS/RHEL/Fedora

```bash
# For CentOS/RHEL
sudo yum install nodejs npm

# For Fedora
sudo dnf install nodejs npm

# Or use NodeSource for latest version
curl -fsSL https://rpm.nodesource.com/setup_lts.x | sudo bash -
sudo yum install nodejs
```

#### Arch Linux

```bash
sudo pacman -S nodejs npm
```

## Genkit Installation and Setup

### Prerequisites

Before you begin, ensure your environment meets these requirements:

- **Node.js v20 or later**
- **npm**

### Step 1: Install Genkit CLI

```bash
# Install Genkit CLI globally
npm install -g @genkit-ai/cli

# Verify installation
genkit --version
```

### Step 2: Set Up Your Project

Create a new Node.js project and configure TypeScript:

```bash
# Create a new directory for your project
mkdir my-genkit-app
cd my-genkit-app

# Initialize npm project
npm init -y

# Set up source directory
mkdir src
touch src/index.ts

# Install and configure TypeScript
npm install -D typescript tsx
npx tsc --init
```

### Step 3: Install Genkit Packages

```bash
# Install core Genkit packages
npm install genkit @genkit-ai/google-genai

# Optional: Install additional model providers
# npm install @genkit-ai/openai
# npm install @genkit-ai/anthropic
```

### Step 4: Configure Gemini API Key

**Get your free Gemini API key:**

1. Visit [Google AI Studio](https://aistudio.google.com/apikey)
2. Sign in with your Google account
3. Click "Create API Key"
4. Copy your API key (keep it secure!)

**Set as environment variable:**

```bash
# For current session
export GEMINI_API_KEY=<your-api-key>

# To make permanent, add to your shell profile:
# ~/.bashrc, ~/.zshrc, or ~/.bash_profile
echo 'export GEMINI_API_KEY=<your-api-key>' >> ~/.bashrc
```

### Step 5: Verify Your Setup

Test your Genkit installation:

```bash
# Verify Genkit CLI is working
genkit --version

# Create a simple test project
mkdir genkit-test && cd genkit-test
npm init -y
npm install genkit @genkit-ai/google-genai

# Start the Developer UI to confirm everything works
genkit start
```

You should see:

- Genkit CLI version displayed
- Developer UI opens at `http://localhost:4000`
- No installation errors

🎉 **Setup Complete!** Your Genkit environment is ready for the workshop.

### What's Next?

With Genkit set up, you'll be able to build:

- AI story generators and content creators
- Intelligent chatbots with memory
- Document analysis and summarization tools
- Multi-step AI workflows and automation

📚 **Resources for Reference:**

- [Official Genkit Documentation](https://genkit.dev/docs/get-started/)
- [Genkit Developer Tools Guide](https://genkit.dev/docs/devtools/)

---

## 🌟 Workshop Recommendation: Use Firebase Studio!

**Skip the local setup complexity!** For this workshop, we **highly recommend using Firebase Studio** instead of local development. It will save you time and let you focus on learning Genkit rather than troubleshooting environment issues.

**🚀 Quick Start**: [Create New Genkit Project](https://studio.firebase.google.com/new/genkit) (one-click setup!)

**👉 Or jump directly to the Firebase Studio section below for detailed instructions.**

---

## 🔥 Firebase Studio Integration (Highly Recommended!)

**Firebase Studio is the fastest and easiest way to get started with Genkit!** It's a cloud-based development environment that eliminates the need for complex local setup. We **strongly encourage** all workshop participants to use Firebase Studio for the best learning experience.

### ✨ Why Choose Firebase Studio?

- **Zero Setup Time** - No Node.js, npm, or local environment configuration needed
- **Pre-configured Templates** - Genkit projects ready to use in seconds
- **Cloud-based Development** - Access your projects from anywhere
- **Automatic Updates** - Always running the latest Genkit version
- **Built-in Collaboration** - Easy sharing and pair programming
- **No Installation Issues** - Bypass common local setup problems

### 🚀 Quick Start with Firebase Studio (Recommended Path)

**Option A: Create New Project from Template** ⭐ **Most Popular**

1. **Direct Link**: Visit **[Firebase Studio - New Genkit Project](https://studio.firebase.google.com/new/genkit)**
2. Sign in with your Google account
3. Your Genkit project will be automatically created and configured
4. **You're ready to code!** - Start building with Genkit immediately

**Alternative**: You can also visit **[Firebase Studio](https://firebase.studio/)** and manually select the Genkit template.

**Option B: Import Existing Genkit Project**

1. Go to **[Firebase Studio](https://firebase.studio/)**
2. Choose **"Import Project"**
3. Connect your GitHub repository or upload your project files
4. Firebase Studio automatically detects and configures your Genkit setup
5. Start developing immediately!

### 💡 Pro Tips for Firebase Studio

- **Save time** - Skip environment troubleshooting
- **Focus on learning Genkit** - Not on setup issues
- **Share projects easily** - Great for getting help and collaboration
- **Works on any device** - Tablets, Chromebooks, any laptop with a browser

### Step 5: Start Development Server

```bash
# Start Genkit development server
genkit start

# This will open:
# - Genkit Developer UI (usually http://localhost:4000)
# - Your application server
```

## Your First Genkit Flow

Create a simple AI flow to test your setup:

```typescript
// src/flows/hello.ts
import { defineFlow } from '@genkit-ai/flow';
import { gemini15Flash } from '@genkit-ai/googleai';

export const helloFlow = defineFlow(
  {
    name: 'helloFlow',
    inputSchema: z.object({
      name: z.string(),
    }),
    outputSchema: z.string(),
  },
  async (input) => {
    const response = await gemini15Flash.generate({
      prompt: `Say hello to ${input.name} in a creative way!`,
    });

    return response.text();
  },
);
```

## Testing Your Setup

### Step 1: Start the Genkit Developer UI

```bash
# Start the Genkit UI with your application
genkit start -- npx tsx --watch src/index.ts

# Or automatically open in browser
genkit start -o -- npx tsx --watch src/index.ts
```

### Step 2: Access Genkit UI

1. After running the command above, the Developer UI will automatically start
2. Open your browser to `http://localhost:4000` (or it opens automatically with `-o` flag)
3. You should see the Genkit Developer UI
4. Navigate to Flows and test your flows interactively

## Genkit Setup Verification

### Essential Genkit Checks

- [ ] Verify Node.js and npm are installed correctly
- [ ] Create and run a simple Genkit project
- [ ] Access Genkit UI successfully
- [ ] Test a simple flow with Gemini API

---

## Agent Development Kit (Python) Setup

**What is ADK?** Google's Agent Development Kit for Python - perfect for building sophisticated AI agents that can perform complex, multi-step tasks.

**What you'll build:** Intelligent agents that analyze data, conduct research, automate workflows, and make decisions based on complex reasoning.

### Prerequisites Checklist

- [ ] Python 3.9+ installed (Python 3.8 reached end of life in October 2024)
- [ ] Basic understanding of Python virtual environments
- [ ] Code editor with Python support

## Operating System Specific Python Setup

### 🪟 Windows Setup

#### Step 1: Install Python

**Option A: Microsoft Store (Recommended for Windows 11)**

```cmd
# Search for "Python" in Microsoft Store and install Python 3.9+
```

**Option B: Official Python Installer**

```cmd
# Download from https://python.org
# ⚠️ IMPORTANT: Check "Add Python to PATH" during installation
```

**Option C: Using Chocolatey**

```powershell
choco install python
```

**Option D: Using Winget**

```cmd
winget install Python.Python.3.12
```

#### Step 2: Verify Installation

```cmd
python --version
pip --version
# If "python" doesn't work, try "python3" or "py"
```

#### Step 3: Install Build Tools (if needed)

```cmd
# Some packages require compilation
# Install Microsoft C++ Build Tools
# Download from: https://visualstudio.microsoft.com/visual-cpp-build-tools/
```

### 🍎 macOS Setup

#### Step 1: Install Python

**Option A: Using Homebrew (Recommended)**

```bash
# Install Homebrew if you haven't already
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Python
brew install python@3.11
```

**Option B: Using pyenv (for multiple Python versions)**

```bash
# Install pyenv
brew install pyenv

# Add to your shell configuration (~/.zshrc or ~/.bash_profile)
echo 'export PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init -)"' >> ~/.zshrc
source ~/.zshrc

# Install Python
pyenv install 3.11.5
pyenv global 3.11.5
```

**Option C: Official Installer**

```bash
# Download from https://python.org
# Choose the macOS installer
```

#### Step 2: Install Xcode Command Line Tools

```bash
xcode-select --install
```

### 🐧 Linux Setup

#### Ubuntu/Debian

```bash
# Update package list
sudo apt update

# Install Python and pip
sudo apt install python3 python3-pip python3-venv

# Install build essentials
sudo apt install build-essential python3-dev

# Create symlink for python command (optional)
sudo ln -s /usr/bin/python3 /usr/bin/python
```

#### CentOS/RHEL/Fedora

```bash
# For CentOS/RHEL 8+
sudo dnf install python3 python3-pip

# For older versions
sudo yum install python3 python3-pip

# For Fedora
sudo dnf install python3 python3-pip python3-devel

# Install development tools
sudo dnf groupinstall "Development Tools"
```

#### Arch Linux

```bash
sudo pacman -S python python-pip
```

## Virtual Environment Setup

### Create Project Directory Structure

```bash
mkdir ai-agent-workspace
cd ai-agent-workspace
mkdir projects venvs
```

### Method 1: Using venv (Built-in)

```bash
# Create virtual environment
python -m venv venvs/adk-env

# Activate virtual environment
# On Windows:
venvs\adk-env\Scripts\activate
# On macOS/Linux:
source venvs/adk-env/bin/activate

# Verify activation (should show virtual env path)
which python
```

### Method 2: Using conda (Alternative)

```bash
# Install Miniconda first
# Download from: https://docs.conda.io/en/latest/miniconda.html

# Create environment
conda create -n adk-env python=3.11
conda activate adk-env
```

### Method 3: Using virtualenv

```bash
# Install virtualenv
pip install virtualenv

# Create environment
virtualenv venvs/adk-env

# Activate (same as venv method above)
```

## ADK Setup Verification

### Step 1: Install ADK Packages

```bash
# Make sure your virtual environment is activated
# Install Google's Agent Development Kit and related packages
pip install google-genai-agents google-cloud-aiplatform
pip install langchain openai anthropic
pip install jupyter streamlit  # For development and demos

# Verify installation
python -c "from google.genai import agents; print('ADK installed successfully!')"
```

### Step 2: Test Your Setup

```bash
# Quick installation test
python -c "
from google.genai import agents
print('✅ ADK is ready!')
"
```

🎉 **Setup Complete!** Your Python ADK environment is ready for the workshop.

### What's Next?

With ADK set up, you'll be able to build:

- **Multi-step research agents** that gather and synthesize information
- **Data analysis assistants** that process spreadsheets and generate insights
- **Task automation agents** that handle complex workflows
- **Conversational AI systems** with memory and context awareness

### Step 2: Project Structure

Your ADK project should look like this:

```
my-first-agent/
├── agents/
│   ├── __init__.py
│   └── base_agent.py
├── tools/
│   ├── __init__.py
│   └── basic_tools.py
├── config/
│   ├── settings.py
│   └── prompts.py
├── tests/
│   └── test_agents.py
├── requirements.txt
├── .env.example
└── main.py
```

### Step 3: Environment Configuration

```bash
# Copy environment template
cp .env.example .env

# Edit .env file with your API keys
# OPENAI_API_KEY=your_openai_key
# ANTHROPIC_API_KEY=your_anthropic_key
# GOOGLE_CLOUD_PROJECT=your_project_id
```

## Your First Agent

### Step 1: Create a Simple Agent

```python
# agents/hello_agent.py
from google.genai import agents
from typing import Dict, Any
from datetime import datetime

class HelloAgent:
    def __init__(self):
        self.name = "hello_agent"
        self.description = "A friendly agent that greets users"

    def greet_user(self, name: str) -> str:
        """Greet a user by name."""
        return f"Hello, {name}! How can I help you today?"

    def get_time(self) -> str:
        """Get the current time."""
        return datetime.now().strftime("%Y-%m-%d %H:%M:%S")

    async def process(self, message: str) -> str:
        # Simple processing logic
        if "time" in message.lower():
            return self.get_time()
        elif "hello" in message.lower():
            return self.greet_user("there")
        else:
            return "I can greet you or tell you the time. What would you like?"
```

### Step 2: Create Main Application

```python
# main.py
import asyncio
from agents.hello_agent import HelloAgent

async def main():
    agent = HelloAgent()

    print("Hello Agent is ready! Type 'quit' to exit.")

    while True:
        user_input = input("\nYou: ")

        if user_input.lower() == 'quit':
            break

        response = await agent.process(user_input)
        print(f"Agent: {response}")

if __name__ == "__main__":
    asyncio.run(main())
```

### Step 3: Test Your Agent

```bash
# Run your agent
python main.py

# Try these inputs:
# "Hello"
# "What time is it?"
# "quit"
```

## Development Tools Setup

### Step 1: Jupyter Notebook Integration

```bash
# Install Jupyter kernel for your virtual environment
pip install ipykernel
python -m ipykernel install --user --name=adk-env --display-name "ADK Environment"

# Start Jupyter
jupyter notebook
```

### Step 2: IDE Configuration

**For VS Code:**

```bash
# Install Python extension
# Select interpreter: Ctrl+Shift+P -> "Python: Select Interpreter"
# Choose your virtual environment interpreter
```

**For PyCharm:**

- Go to Settings > Project > Python Interpreter
- Click gear icon > Add > Existing environment
- Select your virtual environment's python executable

### Step 3: Code Quality Setup

```bash
# Create setup.cfg for code quality tools
cat > setup.cfg << EOF
[flake8]
max-line-length = 88
extend-ignore = E203, W503

[isort]
profile = black
multi_line_output = 3

[tool:pytest]
testpaths = tests
python_files = test_*.py
python_classes = Test*
python_functions = test_*
EOF
```

## ADK Setup Verification

### Essential ADK Checks

- [ ] Set up Python virtual environment
- [ ] Install ADK and dependencies
- [ ] Create and run the hello agent
- [ ] Test agent with basic tools

---

## Google Cloud Vertex AI Setup

**What is Vertex AI?** Google's enterprise-grade ML platform for deploying, managing, and scaling AI models in production.

**What you'll build:** Production-ready AI systems with model deployment, monitoring, and scaling capabilities.

### Prerequisites Checklist

- [ ] Google account (required for Google Cloud)
- [ ] Credit card for GCP billing (workshop credits will be provided)
- [ ] Basic understanding of cloud concepts

### Google Cloud Setup

1. **Create Account**: Visit [Google Cloud Console](https://console.cloud.google.com/) and sign in
2. **Create Project**: Click "New Project" and name it (e.g., "Vertex AI Workshop")
3. **Enable Billing**: Required for Vertex AI (workshop credits provided)
4. **Install CLI**: Install Google Cloud CLI for your OS
5. **Authenticate**: Run `gcloud init` and `gcloud auth application-default login`
6. **Enable APIs**: Enable Vertex AI, Storage, and Compute APIs
7. **Install SDK**: `pip install google-cloud-aiplatform`

### Quick Verification

Test your setup:

```bash
gcloud config list
gcloud services list --enabled
python -c "from google.cloud import aiplatform; print('✅ Vertex AI SDK installed')"
```

### What You'll Build

With Vertex AI set up, you'll be able to create production ML systems:

- **Custom Model Training**: Train and deploy your own ML models on real data
- **AutoML Solutions**: Use Google's automated machine learning for quick model development
- **MLOps Pipelines**: Automated training, deployment, and monitoring workflows
- **Model Endpoints**: Real-time prediction APIs with auto-scaling
- **Integration**: Connect Vertex AI with your Genkit and ADK applications for complete AI solutions

---

## Platform Integration Overview

Once all three platforms are set up, you can combine them to build complete AI applications. This is where everything comes together to create production-ready systems.

### Integration Possibilities

**Multi-Platform Architecture:**

- Connect Genkit frontend with ADK backend
- Add Vertex AI custom models to your agents
- Build real-time AI workflows

**Production Deployment:**

- Deploy complete AI applications
- Implement monitoring and scaling
- Create robust, scalable systems

### Project Examples

- **AI Customer Service**: Genkit chat UI → ADK conversation agent → Vertex AI models
- **Content Pipeline**: Automated content generation and analysis system
- **Smart Dashboard**: Real-time data analysis with AI insights

---

## Setup Completion Checklist

Before you can build integrated applications, ensure you have:

### Genkit Setup ✅

- [x] Node.js and TypeScript environment
- [x] Firebase project configured
- [x] Basic Genkit application running
- [x] Genkit CLI working properly

### ADK Setup ✅

- [x] Python virtual environment
- [x] Agent Development Kit installed
- [x] Simple agent created and tested
- [x] Required Python packages installed

### Vertex AI Setup ✅

- [x] Google Cloud project and billing
- [x] Vertex AI APIs enabled
- [x] CLI and SDK authentication working
- [x] Project permissions configured

### Integration Readiness ✅

- [x] All three platforms working independently
- [x] Basic understanding of each framework
- [x] Development environment fully configured

## Next Steps

**Congratulations!** You're now ready to start building production AI applications.

With your environment configured, you can:

- **Connect Everything**: Integrate Genkit, ADK, and Vertex AI into unified applications
- **Deploy at Scale**: Launch your AI systems to production environments
- **Monitor & Optimize**: Ensure your applications perform reliably in the real world

### Ready to Begin?

With your development environment fully configured, you're prepared to:

1. **Build Real Applications**: Create AI solutions using all three platforms
2. **Deploy to Production**: Launch your applications with confidence
3. **Join the Community**: Connect with other developers building the future of AI

---

## Troubleshooting Setup Issues

### Quick Fixes for Common Problems

**Genkit Issues:**

- Command not found? → `npm install -g @genkit-ai/cli`
- Firebase errors? → `firebase login` and `firebase use --add`
- TypeScript errors? → Ensure Node.js 18+ and `npm install`

**ADK Issues:**

- Import errors? → Activate virtual environment: `source venv/bin/activate`
- Package missing? → `pip install google-genai-agents`
- Python version? → Ensure Python 3.9+

**Vertex AI Issues:**

- Authentication errors? → `gcloud auth application-default login`
- API not enabled? → `gcloud services enable aiplatform.googleapis.com`
- Project issues? → Verify project ID and billing enabled

### Getting Help

- **💬 Discord Community**: **[Join our Discord server](https://discord.gg/unstacked)** for:
  - Real-time help with setup issues
  - Community troubleshooting and support
  - Project collaboration and code sharing
  - Direct access to instructors and mentors
- **📚 Office Hours**: Regular Q&A sessions with instructors
- **📖 Documentation**: Each platform's official docs for deep troubleshooting

---

**Congratulations!** You're ready to start building the future of AI applications!

With all three platforms properly configured, you now have the foundation to build sophisticated AI applications that leverage the best of Google's AI technologies.

## Continue Your Journey

1. **Start Building**: Use your configured environment to create amazing AI applications
2. **Join the Community**: Connect with other developers and continue learning
3. **Share Your Work**: Contribute back and help others in the community
4. **Keep Learning**: Explore advanced topics like MLOps, AI safety, and model optimization
5. **Get Certified**: Consider Google Cloud AI/ML certifications to validate your skills

Happy coding! 🚀

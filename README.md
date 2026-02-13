# Q&A Chatbot with Groq 🤖

A fast and intelligent Q&A chatbot powered by Groq's lightning-fast LLM inference and built with Streamlit.

## Features ✨

- **Multiple LLM Models**: Choose from various Groq models (Llama, Mixtral, Gemma)
- **Adjustable Parameters**: Control temperature and max tokens for customized responses
- **Chat History**: Keep track of your conversation
- **Clean UI**: Modern and intuitive interface
- **Fast Responses**: Powered by Groq's optimized inference engine

## Prerequisites 📋

- Python 3.8 or higher
- Groq API key (get one at [console.groq.com](https://console.groq.com))

## Installation 🚀

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd <your-repo-name>
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   ```bash
   # Copy the example env file
   cp .env.example .env
   
   # Edit .env and add your API keys
   # GROQ_API_KEY=your_actual_api_key_here
   ```

## Running Locally 💻

```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`

## Deployment Options 🌐

### Option 1: Streamlit Community Cloud (Recommended)

1. **Push your code to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin <your-github-repo-url>
   git push -u origin main
   ```

2. **Deploy on Streamlit Cloud**
   - Go to [share.streamlit.io](https://share.streamlit.io)
   - Click "New app"
   - Select your repository, branch, and main file (`app.py`)
   - Click "Advanced settings" and add your secrets:
     ```
     GROQ_API_KEY = "your_groq_api_key"
     LANGCHAIN_API_KEY = "your_langchain_key" (optional)
     ```
   - Click "Deploy"

### Option 2: Heroku

1. **Create a Procfile**
   ```bash
   web: streamlit run app.py --server.port=$PORT --server.address=0.0.0.0
   ```

2. **Create a setup.sh file**
   ```bash
   mkdir -p ~/.streamlit/
   echo "\
   [server]\n\
   headless = true\n\
   port = $PORT\n\
   enableCORS = false\n\
   \n\
   " > ~/.streamlit/config.toml
   ```

3. **Deploy to Heroku**
   ```bash
   heroku create your-app-name
   heroku config:set GROQ_API_KEY=your_groq_api_key
   git push heroku main
   ```

### Option 3: Docker

1. **Create a Dockerfile** (see Dockerfile in repo)

2. **Build and run**
   ```bash
   docker build -t groq-chatbot .
   docker run -p 8501:8501 -e GROQ_API_KEY=your_key groq-chatbot
   ```

## Configuration ⚙️

### Environment Variables

- `GROQ_API_KEY` (required): Your Groq API key
- `LANGCHAIN_API_KEY` (optional): For LangSmith tracing
- `LANGCHAIN_PROJECT` (optional): LangSmith project name

### Model Options

- **llama-3.3-70b-versatile**: Most capable, best for complex tasks
- **llama-3.1-70b-versatile**: Balanced performance and speed
- **llama-3.1-8b-instant**: Fast responses, good for simple queries
- **mixtral-8x7b-32768**: Large context window (32K tokens)
- **gemma2-9b-it**: Efficient and instruction-tuned

## Usage 📖

1. Select your preferred model from the sidebar
2. Adjust temperature and max tokens as needed
3. Type your question in the input field
4. Press "Send" or hit Enter
5. View the response and chat history

## Troubleshooting 🔧

### API Key Issues
- Make sure your API key is valid and active
- Check that the key is properly set in environment variables
- For Streamlit Cloud, verify secrets are configured correctly

### Import Errors
- Ensure all dependencies are installed: `pip install -r requirements.txt`
- Try upgrading pip: `pip install --upgrade pip`

### Slow Responses
- Try using a smaller model like `llama-3.1-8b-instant`
- Reduce the `max_tokens` parameter
- Check your internet connection

## Tech Stack 🛠️

- **Frontend**: Streamlit
- **LLM Framework**: LangChain
- **LLM Provider**: Groq
- **Language**: Python 3.8+

## Contributing 🤝

Contributions are welcome! Please feel free to submit a Pull Request.

## License 📄

This project is licensed under the MIT License.

## Support 💬

If you encounter any issues or have questions, please open an issue on GitHub.

---

**Made with ❤️ using Streamlit and Groq**

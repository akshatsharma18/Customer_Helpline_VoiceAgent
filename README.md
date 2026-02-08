# Akshat - Power Supply Support Assistant

An AI-powered voice/video agent built with LiveKit and Google's Gemini model. Akshat is a professional power supply support assistant designed to help customers with electricity-related issues.

## Features

- 🤖 **AI-Powered**: Uses Google's Gemini 2.5 Flash model for intelligent responses
- 🎤 **Voice Support**: Real-time audio processing with Silero text-to-speech
- 🔊 **Noise Cancellation**: Built-in background noise removal
- ⚡ **Professional Support**: Handles power supply, consumption, and load-related issues
- 💬 **Natural Conversations**: Context-aware, conversational assistant

## Prerequisites

- Python 3.12 or higher
- pip or uv package manager
- Google API key (free from [Google AI Studio](https://aistudio.google.com/app/apikeys))
- LiveKit Cloud account (free from [cloud.livekit.io](https://cloud.livekit.io))

## Installation

### 1. Create Virtual Environment

```bash
python -m venv venv
.\venv\Scripts\Activate  # Windows
# or
source venv/bin/activate  # macOS/Linux
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

Or use the faster `uv` installer:

```bash
uv pip install -r requirements.txt
```

### 3. Download Model Files

```bash
python agent.py download-files
```

This downloads required voice and AI models (~500MB).

### 4. Set Up Environment Variables

Create a `.env` file in the project root:

```env
GOOGLE_API_KEY=your_google_api_key_here
LIVEKIT_URL=wss://your-project.livekit.cloud
LIVEKIT_API_KEY=your_livekit_api_key
LIVEKIT_API_SECRET=your_livekit_api_secret
```

## Configuration

### Get API Keys

1. **Google API Key**:
   - Visit [Google AI Studio](https://aistudio.google.com/app/apikeys)
   - Create a new API key
   - Add to `.env`

2. **LiveKit Credentials**:
   - Sign up at [cloud.livekit.io](https://cloud.livekit.io) (free)
   - Create a project
   - Copy credentials to `.env`

## Usage

### Console Mode (Recommended for Testing)

Run the agent in your terminal:

```bash
python .\agent.py console
```

Then type your questions about power supply, electricity consumption, or any power-related concerns.

### Example Interactions

```
You: My power consumption is very high.
Simii: I understand your concern and I am now checking the possible causes of high power usage.

You: How do I reduce my electricity bill?
Simii: I will review your power usage patterns and suggest optimization strategies.
```

## Project Structure

```
.
├── agent.py              # Main agent code
├── prompts.py            # Agent instructions and personas
├── requirements.txt      # Python dependencies
├── pyproject.toml        # Project metadata
├── .env                  # Environment variables (not in Git)
└── README.md            # This file
```

## Customization

### Change Agent Behavior

Edit `prompts.py` to modify:
- Agent persona and tone
- Response guidelines
- Greeting messages
- Specific instructions

### Modify Model Settings

Edit `agent.py` to adjust:
- Model selection: `models/gemini-2.5-flash-native-audio-latest`
- Voice: `Aoede` (or other available voices)
- Temperature: `0.8` (0.0 = deterministic, 1.0 = creative)

## Troubleshooting

### Slow Responses

If the agent takes too long to respond:
1. Use the faster Gemini model (already configured)
2. Reduce response length in `prompts.py`
3. Check your internet connection

### Dependency Conflicts

If you encounter dependency issues:

```bash
uv pip install -r requirements.txt
```

The `uv` installer handles complex dependencies better than pip.

### Missing Environment Variables

Ensure all required keys are in `.env`:
- `GOOGLE_API_KEY`
- `LIVEKIT_URL`
- `LIVEKIT_API_KEY`
- `LIVEKIT_API_SECRET`

## Technologies Used

- **LiveKit Agents**: Real-time voice/video agent framework
- **Google Gemini**: Large language model
- **Silero**: Text-to-speech engine
- **Python 3.12+**: Programming language

## License

This project is provided as-is for educational and commercial use.

## Support

For issues or questions:
1. Check the troubleshooting section above
2. Review environment variables in `.env`
3. Ensure all dependencies are installed correctly

---

**Created with ❤️ for power supply support**

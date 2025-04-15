# Darwix: AI-Powered Blog Tools 🧠🎤

Darwix is a Django-based web application that provides two powerful AI-driven features for bloggers and content creators. The application integrates audio transcription with speaker diarization and generates AI-powered blog post title suggestions based on your content.

---

## 🚀 Features

1. Audio Transcription with Speaker Diarization** 🎤
- Transcribe audio files** into text.
- Speaker diarization**: Identify who spoke when in the audio.
- Multilingual support**: Thanks to OpenAI's Whisper and pyannote.audio.

 2. AI Blog Post Title Suggestions** 🧠
- Generate **3 AI-powered blog post title suggestions** based on your content.
- Uses the **BART model** for summarization to generate catchy and relevant titles.

---

🧑‍💻 Setup Instructions

1. Clone the Repository
Clone the repository to your local machine:
```bash
git clone https://github.com/shubham-899844/Darwix.git
cd Darwix
2. Create a Virtual Environment
Set up a virtual environment to isolate dependencies:

bash
Copy
Edit
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
3. Install Required Dependencies
Install the necessary packages using pip:

bash
Copy
Edit
pip install -r requirements.txt
4. Set Up the Database and Migrations
Make sure to apply migrations to set up the database:

bash
Copy
Edit
python manage.py migrate
5. Run the Development Server
Start the Django development server:

bash
Copy
Edit
python manage.py runserver
Open your browser and navigate to http://127.0.0.1:8000/ to see the app in action!

📡 API Endpoints
1. POST /api/suggest-titles/
Generate 3 AI-powered title suggestions based on the blog content you provide.

Request Body:

json
Copy
Edit
{
  "content": "In this article, we dive deep into the applications of AI and how it is revolutionizing industries worldwide."
}
Response:

json
Copy
Edit
{
  "suggested_titles": [
    "How AI is Revolutionizing Industries",
    "The Future of AI in Modern Industries",
    "AI: A Game Changer for the Future"
  ]
}
2. POST /api/transcribe-audio/
Transcribe audio files into text with speaker diarization.

Request Body (Multipart Form):

file: The audio file you wish to transcribe (e.g., audio.wav).

Response:

json
Copy
Edit
{
  "file": "audio.wav",
  "speaker_segments": [
    {
      "start": 0.0,
      "end": 15.0,
      "speaker": "Speaker 1",
      "transcription": "Hello, and welcome to the podcast."
    },
    {
      "start": 15.1,
      "end": 30.0,
      "speaker": "Speaker 2",
      "transcription": "Thanks for having me, it's great to be here!"
    }
  ]
}
🤖 Models Used
Whisper (OpenAI) for multilingual speech-to-text transcription.

pyannote.audio for speaker diarization (identifying speakers in the audio).

BART (facebook/bart-large-cnn) for AI-based blog title suggestions.

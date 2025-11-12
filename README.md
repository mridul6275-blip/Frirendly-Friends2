# Friendly Friends App

A social platform for sharing videos, blogs, messages, and creative content with AI-powered features.

## Features

- 🎥 **Video Sharing**: Upload and share videos with the community
- 📝 **Blog Creation**: Create and publish blog posts with images
- 💬 **Messaging**: Real-time messaging with file attachments
- 🎨 **Paint**: Collaborative drawing and painting
- ✅ **Todo Lists**: Personal task management
- 🤖 **AI Chat**: Chat with AI assistant powered by OpenAI
- 📄 **AI Docs**: AI-powered document creation
- 🎓 **AI Training**: Admin tools for training the AI (admin only)
- 📞 **Video Calls**: WebRTC-based video calling
- 👥 **Members**: View and manage community members

## Tech Stack

### Frontend
- React 18
- Vite
- React Router
- Axios
- Video.js (for video playback)

### Backend
- Python 3
- Flask
- SQLite
- OpenAI API integration
- WebRTC for video calls

## Installation

### Prerequisites
- Node.js (v18 or higher)
- Python 3.9+
- npm or yarn

### Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install Python dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
Create a `.env` file in the backend directory:
```
OPENAI_API_KEY=your_openai_api_key_here
FLASK_SECRET_KEY=your_secret_key_here
PORT=5002
```

4. Initialize the database:
```bash
python3 -c "from db import init_db; init_db()"
```

5. Start the backend server:
```bash
PORT=5002 python3 app.py
```

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

The app will be available at `http://localhost:5173`

## Project Structure

```
Friendly Friends App/
├── backend/
│   ├── app.py              # Flask application
│   ├── db.py               # Database operations
│   ├── requirements.txt    # Python dependencies
│   └── uploads/            # User uploaded files
├── frontend/
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── contexts/       # React contexts
│   │   └── services/       # API services
│   ├── package.json        # Node dependencies
│   └── vite.config.js      # Vite configuration
└── github/                 # GitHub configuration files
```

## Environment Variables

### Backend
- `OPENAI_API_KEY`: Your OpenAI API key for AI features
- `FLASK_SECRET_KEY`: Secret key for Flask sessions
- `PORT`: Port for the backend server (default: 5002)

## Usage

1. **Register/Login**: Create an account or login as a member or research viewer
2. **Upload Videos**: Share videos with the community
3. **Create Blogs**: Write and publish blog posts
4. **Chat**: Message other users and attach files
5. **AI Features**: Use AI chat, document creation, and more
6. **Video Calls**: Make video calls to other users

## Admin Features

Admin users have access to:
- User management
- AI training data management
- System administration

## Development

### Running Tests

Backend tests:
```bash
cd backend
pytest
```

Frontend tests:
```bash
cd frontend
npm test
```

### Building for Production

Frontend:
```bash
cd frontend
npm run build
```

The built files will be in `frontend/dist/`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

[Add your license here]

## Support

For issues and questions, please open an issue on GitHub.

## Acknowledgments

- OpenAI for AI capabilities
- React and Flask communities
- All contributors


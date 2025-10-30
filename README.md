# Audio Player Web Application

A modern, responsive web-based audio player built with Django that allows users to browse, organize, and play music through YouTube embeds. Users can create personal playlists, discover new tracks, and enjoy a seamless music listening experience with shuffle playback functionality.

## Features

### 🎵 Core Functionality
- **Song Library**: Browse a collection of songs with cover images, artist information, and genre details
- **YouTube Integration**: Play songs directly through embedded YouTube videos with autoplay support
- **Playlist Management**: Create, view, and manage personal playlists
- **Shuffle Playback**: Enjoy randomized playback within playlists
- **Responsive Design**: Optimized for desktop and mobile devices

### 👤 User Management
- **User Registration**: Create new accounts with secure password validation
- **User Authentication**: Login/logout functionality with session management
- **Personal Playlists**: Each user has their own private playlist collection

### 🎨 User Interface
- **Modern Design**: Dark theme with golden accents and smooth animations
- **Bootstrap Integration**: Responsive layout with mobile-friendly navigation
- **Interactive Elements**: Hover effects, transitions, and intuitive controls
- **Visual Feedback**: Loading states and user-friendly error handling

## Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- Git

### Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd Audio_player
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install django
   pip install pillow  # For image handling
   ```

4. **Apply database migrations:**
   ```bash
   python manage.py migrate
   ```

5. **Create a superuser (optional, for admin access):**
   ```bash
   python manage.py createsuperuser
   ```

6. **Run the development server:**
   ```bash
   python manage.py runserver
   ```

7. **Access the application:**
   Open your browser and navigate to `http://127.0.0.1:8000/`

## Usage

### For Regular Users
1. **Register/Login**: Create an account or log in to access playlist features
2. **Browse Songs**: View the song library on the homepage
3. **Play Music**: Click the play button on any song card to start playback
4. **Create Playlists**: Use the "Create Playlist" option to make new collections
5. **Add Songs**: Select songs from the library and add them to your playlists
6. **View Playlists**: Access your playlists through "My Playlists" in the navigation
7. **Shuffle Mode**: Enable shuffle in playlist view for randomized playback

### For Administrators
- Access the Django admin panel at `http://127.0.0.1:8000/admin/`
- Add new songs through the admin interface
- Manage user accounts and playlists

## Project Structure

```
Audio_player/
├── db.sqlite3                    # SQLite database
├── manage.py                     # Django management script
├── main/                         # Main application
│   ├── migrations/               # Database migrations
│   ├── templates/main/           # HTML templates
│   │   ├── base.html            # Base template with navigation
│   │   ├── index.html           # Homepage with song library
│   │   ├── login_user.html      # Login page
│   │   ├── register_user.html   # Registration page
│   │   ├── create_playlist.html # Playlist creation form
│   │   ├── view_playlist.html   # Individual playlist view
│   │   └── all_playlists.html   # User's playlist overview
│   ├── models.py                # Database models (Song, Playlist)
│   ├── views.py                 # View functions and logic
│   ├── urls.py                  # URL routing for main app
│   └── apps.py                  # App configuration
├── media/                       # User-uploaded media files
│   └── cover_image/             # Song cover images
├── mysite/                      # Django project settings
│   ├── settings.py             # Project configuration
│   ├── urls.py                 # Main URL routing
│   └── wsgi.py                 # WSGI configuration
└── README.md                   # This file
```

## Technologies Used

- **Backend**: Django 5.2.7 (Python web framework)
- **Database**: SQLite (development), easily configurable for PostgreSQL/MySQL
- **Frontend**: HTML5, CSS3, JavaScript
- **Styling**: Bootstrap 5.3.3, Custom CSS with animations
- **Media Handling**: Pillow (Python Imaging Library)
- **Authentication**: Django's built-in user authentication system
- **Deployment**: WSGI/ASGI ready for production deployment

## Models

### Song Model
- `title`: Song title (CharField)
- `artist`: Artist name (CharField)
- `genre`: Music genre (CharField)
- `audio_url`: YouTube URL (CharField)
- `duration`: Song duration (CharField)
- `cover_image`: Cover image (ImageField)

### Playlist Model
- `name`: Playlist name (CharField)
- `user`: Owner (ForeignKey to User)
- `song`: Songs in playlist (ManyToManyField to Song)

## API Endpoints

- `/` - Homepage with song library
- `/register_user/` - User registration
- `/login_user/` - User login
- `/logout_user/` - User logout
- `/create_playlist/` - Create new playlist
- `/view_playlist/<id>/` - View specific playlist
- `/all_playlists/` - List all user playlists
- `/admin/` - Django admin panel

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines
- Follow Django best practices
- Write clear, documented code
- Test thoroughly before submitting PRs
- Maintain responsive design principles

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Future Enhancements

- [ ] Audio file upload support (beyond YouTube embeds)
- [ ] Social features (share playlists, follow users)
- [ ] Advanced search and filtering
- [ ] Music recommendations
- [ ] Offline playback capabilities
- [ ] API endpoints for mobile app integration
- [ ] Playlist collaboration features

## Support

If you encounter any issues or have questions about the project:
1. Check the existing issues on GitHub
2. Create a new issue with detailed information
3. Include error messages, steps to reproduce, and your environment details

---

**Note**: This application uses YouTube embeds for audio playback. Ensure you comply with YouTube's Terms of Service when using this application.

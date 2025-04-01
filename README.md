# 🎵 Clone Apple Music Playlist to Spotify

This Python script automates the process of transferring public Apple Music playlists to Spotify. The tool uses the Spotify Web API and Apple Music API to search, retrieve, and add songs from Apple Music playlists to a newly created playlist on Spotify.

## 📌 **Project Overview**
The primary purpose of this project is to save time by automating the tedious task of manually transferring songs between Apple Music and Spotify. It allows users to:
- Search and select a playlist on Apple Music.
- Recreate the playlist on Spotify.
- Add all songs from the Apple Music playlist to the newly created Spotify playlist.
- Optionally, choose if the playlist is public or private.

---

## 📁 **Directory Structure**
```
.
├── __init__.py              # Empty file to make the directory a package
├── create_playlist.py       # Script for creating Spotify playlists
├── exceptions.py            # Custom exception handling for API requests
├── music_token.py           # JWT token generation for Apple Music API access
├── README.md                # Documentation (this file)
└── spotify.py               # Core script handling all major functionalities
```

---

## ⚙️ **Requirements**
- Python 3.7+
- Spotify Developer Account
- Apple Developer Account
- Spotify API Credentials (Client ID, Client Secret, Access Token)
- Apple Music API Credentials (Key ID, Team ID, Private Key)

Install the required Python packages:
```bash
pip install -r requirements.txt
```

Required packages:
```
spotipy
applemusicpy
PyJWT
pandas
requests
youtube_dl
```

---

## 🔑 **Configuration**
Create a `secrets.py` file in the root directory of the project containing your API credentials:

```python
# Spotify Credentials
spotify_user_id = "YOUR_SPOTIFY_USER_ID"
spotify_token = "YOUR_SPOTIFY_ACCESS_TOKEN"
cid = "YOUR_SPOTIFY_CLIENT_ID"
secret = "YOUR_SPOTIFY_CLIENT_SECRET"

# Apple Music Credentials
apple_key_ID = "YOUR_APPLE_KEY_ID"
apple_team_ID = "YOUR_APPLE_TEAM_ID"
apple_private_key = "YOUR_APPLE_PRIVATE_KEY"
```

---

## 📌 **How It Works**
1. **User Authentication:**
    - Spotify uses OAuth 2.0 for authentication (`spotipy` library).
    - Apple Music uses JWT tokens generated using `PyJWT`.

2. **Song Search & Matching:**
    - Retrieves songs from an Apple Music playlist.
    - Searches Spotify using song name and artist name to find matching tracks.

3. **Playlist Creation:**
    - Creates a new Spotify playlist.
    - Adds matched songs to this playlist.

---

## 🚀 **Usage**
Run the script with your Spotify username as an argument:
```bash
python spotify.py "YOUR_SPOTIFY_USERNAME"
```

---

## 📄 **File Descriptions**
- `create_playlist.py`: Handles creating playlists and adding songs to playlists in Spotify.
- `exceptions.py`: Custom exception handling for HTTP errors.
- `music_token.py`: Generates JWT tokens for Apple Music API access.
- `spotify.py`: Core logic for interacting with Spotify and Apple Music APIs.
- `README.md`: Project documentation (this file).

---

## 💡 **Potential Improvements**
- Implement a graphical UI (e.g., using `Gradio` or `Streamlit`).
- Improve error handling and logging.
- Add support for exporting created playlists as `.csv` files.
- Provide fallback mechanisms for unmatched songs.
- Enable playlist deletion or modification through Spotify’s API.

---

## 📜 **License**
This project is licensed under the MIT License.


## 💌 **Contributions**
Contributions are welcome! Feel free to fork this repository and submit pull requests.


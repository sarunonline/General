# JW Player Configuration

## Simple use of JW Player in html file using single video file and thumbnail

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JWPlayer Example</title>
    <!-- Include the JWPlayer library -->
    <script src="https://cdn.jwplayer.com/libraries/your_key.js"></script>
    <script type="text/javascript">
        // Set the JWPlayer license key
        jwplayer.key = "your_license_key";
    </script>
</head>
<body>
    <!-- Container for the JWPlayer -->
    <div id="myPlayer"></div>
    <script type="text/javascript">
        // Initialize the JWPlayer
        jwplayer("myPlayer").setup({
            file: "https://example.com/path/to/your/video.mp4",
            image: "https://example.com/path/to/your/thumbnail.jpg",
            width: "100%",
            aspectratio: "16:9"
        });
    </script>
</body>
</html>
```

## JWPlayer configuration having a playlist file

The jwplayer support two types of playlist formats, namely, RSS/XML and JSON. To create a complete playlist in JWPlayer, either JSON or RSS/XML formats are given below:

### JSON format

```json
{
  "playlist": [
    {
      "file": "https://example.com/path/to/your/video1.mp4",
      "image": "https://example.com/path/to/your/thumbnail1.jpg",
      "title": "Video 1",
      "description": "Description for Video 1",
      "mediaid": "video1_id",
      "tracks": [
        {
          "file": "https://example.com/path/to/your/subtitles1.vtt",
          "kind": "captions",
          "label": "English",
          "default": true
        }
      ]
    },
    {
      "file": "https://example.com/path/to/your/video2.mp4",
      "image": "https://example.com/path/to/your/thumbnail2.jpg",
      "title": "Video 2",
      "description": "Description for Video 2",
      "mediaid": "video2_id",
      "tracks": [
        {
          "file": "https://example.com/path/to/your/subtitles2.vtt",
          "kind": "captions",
          "label": "English",
          "default": true
        }
      ]
    }
  ]
}

```

### RSS/XML format
```xml
<rss version="2.0" xmlns:jwplayer="http://rss.jwpcdn.com/">
  <channel>
    <title>My Playlist</title>
    <item>
      <title>Video 1</title>
      <description>Description for Video 1</description>
      <media:content url="https://example.com/path/to/your/video1.mp4" />
      <media:thumbnail url="https://example.com/path/to/your/thumbnail1.jpg" />
      <jwplayer:track file="https://example.com/path/to/your/subtitles1.vtt" kind="captions" label="English" default="true" />
    </item>
    <item>
      <title>Video 2</title>
      <description>Description for Video 2</description>
      <media:content url="https://example.com/path/to/your/video2.mp4" />
      <media:thumbnail url="https://example.com/path/to/your/thumbnail2.jpg" />
      <jwplayer:track file="https://example.com/path/to/your/subtitles2.vtt" kind="captions" label="English" default="true" />
    </item>
  </channel>
</rss>


```

## Embedding the playlist in html
To use the JSON playlist in your JWPlayer setup, you can do the following:
### html file with JSON playlist

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JWPlayer Playlist Example</title>
    <script src="https://cdn.jwplayer.com/libraries/your_key.js"></script>
    <script type="text/javascript">
        jwplayer.key = "your_license_key";
    </script>
</head>
<body>
    <div id="myPlayer"></div>
    <script type="text/javascript">
        jwplayer("myPlayer").setup({
            playlist: "https://example.com/path/to/your/playlist.json",
            width: "100%",
            aspectratio: "16:9"
        });
    </script>
</body>
</html>

```


### html file with RSS/XML playlist

For the RSS/XML playlist, you can set it up similarly by pointing to the RSS feed
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JWPlayer Playlist Example</title>
    <script src="https://cdn.jwplayer.com/libraries/your_key.js"></script>
    <script type="text/javascript">
        jwplayer.key = "your_license_key";
    </script>
</head>
<body>
    <div id="myPlayer"></div>
    <script type="text/javascript">
        jwplayer("myPlayer").setup({
            playlist: "https://example.com/path/to/your/playlist.rss",
            width: "100%",
            aspectratio: "16:9"
        });
    </script>
</body>
</html>

```

## Creating the playlist using jwplayer API
To create a playlist, you need to send a POST request to the JWPlayer API endpoint for playlists. 
```python
import requests
import json

# Your JWPlayer API credentials
api_key = 'your_api_key'
api_secret = 'your_api_secret'

# API endpoint for creating a playlist
url = 'https://api.jwplayer.com/v2/sites/{site_id}/playlists/'

# Playlist data
playlist_data = {
    "metadata": {
        "title": "My Playlist",
        "description": "A collection of my favorite videos"
    },
    "playlist": [
        {
            "media_id": "video1_id"
        },
        {
            "media_id": "video2_id"
        }
    ]
}

# Headers for the request
headers = {
    'Content-Type': 'application/json',
    'Authorization': f'Bearer {api_secret}'
}

# Send the POST request
response = requests.post(url, headers=headers, data=json.dumps(playlist_data))

# Check the response
if response.status_code == 201:
    print("Playlist created successfully!")
else:
    print(f"Failed to create playlist: {response.status_code}")
    print(response.json())

```

## Updating the playlist using jwplayer API
To update an existing playlist, send a PATCH request to the playlist’s endpoint:
```python
# API endpoint for updating a playlist
playlist_id = 'your_playlist_id'
url = f'https://api.jwplayer.com/v2/sites/{site_id}/playlists/{playlist_id}/'

# Updated playlist data
updated_data = {
    "metadata": {
        "title": "Updated Playlist Title"
    },
    "playlist": [
        {
            "media_id": "new_video_id"
        }
    ]
}

# Send the PATCH request
response = requests.patch(url, headers=headers, data=json.dumps(updated_data))

# Check the response
if response.status_code == 200:
    print("Playlist updated successfully!")
else:
    print(f"Failed to update playlist: {response.status_code}")
    print(response.json())

```

## Deleting the playlist using jwplayer API
To delete a playlist, send a DELETE request to the playlist’s endpoint:
```python
# API endpoint for deleting a playlist
url = f'https://api.jwplayer.com/v2/sites/{site_id}/playlists/{playlist_id}/'

# Send the DELETE request
response = requests.delete(url, headers=headers)

# Check the response
if response.status_code == 204:
    print("Playlist deleted successfully!")
else:
    print(f"Failed to delete playlist: {response.status_code}")
    print(response.json())

```

## Listing the playlist using jwplayer API
To list all playlists, send a GET request to the playlists endpoint:
```python
# API endpoint for listing playlists
url = f'https://api.jwplayer.com/v2/sites/{site_id}/playlists/'

# Send the GET request
response = requests.get(url, headers=headers)

# Check the response
if response.status_code == 200:
    playlists = response.json()
    print("Playlists retrieved successfully!")
    print(playlists)
else:
    print(f"Failed to retrieve playlists: {response.status_code}")
    print(response.json())

```

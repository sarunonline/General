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

erter
dfasdf dsfasd sadfsadf sadfsa sadfasf asdfasdfasdf asfa asdfasdf

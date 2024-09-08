# Linking Images from dropbox

It is super easy to get direct download link of image files that are saved in your Dropbox account. And more importantly they will work with [img] commands used in forums that you mentioned in your question.

Here is the step by step instructions:

1) Copy Dropbox link of the image file that you want to share. (Right click on image file in your Dropbox folder and choose Copy Dropbox Link). You should have something similar to this:
```
https://www.dropbox.com/s/tg0cfa565aue4ak/zoo.jpg?dl=0
```
2)  Just delete dl=0 at the end of the link and replace it with raw=1 

Now your link that you gonna use should look like this:
```
https://www.dropbox.com/s/tg0cfa565aue4ak/zoo.jpg?raw=1
```

Basically, what you are doing by adding the raw=1 to the end of the link is hotlinking it. That's is sharing direct download link to the file. Anyone who clicks on hotlinked file will not see any of the Dropbox frames, logos, etc. It works for any type of file that you share.

And when you use this modified link with [img] commands there should be no problems.

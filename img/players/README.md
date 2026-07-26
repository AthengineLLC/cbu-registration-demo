# Player photos

Drop a player's photo in this folder and their internal profile picks it
up automatically.

**Naming**: lowercase first-last with dots between words, matching the
player's name in Player Management:

- Isaiah Maruszak -> `isaiah.maruszak.jpg`
- Aaden Hernandez -> `aaden.hernandez.jpg`

`.jpg`, `.jpeg`, and `.png` all work.

Any shape of photo is fine - the profile crops everything to the same 3:4
portrait frame, and the Adjust button on the profile lets you drag and
zoom the photo into position inside that frame.

You can also skip this folder entirely: drag a photo straight onto the
photo frame in the browser. That copy is saved in the browser
(localStorage), so it survives refresh on the same computer, but a file
in this folder is what deploys for everyone.

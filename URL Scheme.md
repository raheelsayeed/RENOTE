RENOTE URL Scheme
================

Fully supports `X-Callback-URL` protocol.
Supports two basic calls; they are not comprehensive, but enough for the purpose of the app.

1. `new`: Adds a new note
2. `get`: Opens up RENOTE app, sends a URL-encoded note text after the user selects a Note. Requires `x-success` parameter.


### /new

- Adds a new note in RENOTE
- required parameters: 
   - `text`: text to add to renote. 
- eg: `renote://x-callback-parameter/new?text=TEXT-TO-ADD`


### /get

This URL should be used to *get* a note text into another app. Opens RENOTE in selection mode and sends a *User-selected* note text via `x-callback-url` protocol. `X-Callback-URL` is required for this to work. `x-success`. 

- `x-success` should have a target URL that receives the text.
- RENOTE adds parameter `text=TEXT-SELECTED` to x-success when user selects the Note and taps **Send**.
- Note text is URL Encoded and requires to be decoded at the receiver's end.
- eg. `renote://x-callback-url/get?x-success={{drafts4://create}}&x-cancel=drafts4:`


# Credits

Having a decent functional URL Scheme was inspired from Greg Pierce, the creator of the excellent [Drafts](http://agiletortoise.com) app and [x-callback-url](http://x-callback-url.com) protocol.

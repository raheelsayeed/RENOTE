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
- RENOTE adds parameter `text=` and appends the `text-to-add` to x-success when user selects the Note and taps **Send**.
- Note text is URL Encoded and requires to be decoded at the receiver's end.
- eg. `renote://x-callback-url/get?x-success={{drafts4://create}}&x-cancel=drafts4:`

------

### Variables – Custom Action URLs

Variables found in the custom action URLs are replaced with URL encoded strings:

- **`[[note]]`**: Entire text typed within the editing space.
- **`[[title]]`**: Top line. If whole text is a single line, then the first 30 characters are returned.
- **`[[text]]`**: Text beyond the Title. If the whole text is a single line (title), then this will return the whole text.
- **`[[filename]]`**: Creates a filename from the text. A valid fileame is created from the top line. If theres no top-line, the first valid 55 characters are sanitized and appended with a `.txt` extension.
- eg: `drafts4://create?text=[[note]]`. Where note is replaced with the entire text.

# Credits

Having a decent functional URL Scheme was inspired from Greg Pierce, the creator of the excellent [Drafts](http://agiletortoise.com) app and [x-callback-url](http://x-callback-url.com) protocol.

RENOTE URL Scheme
================

Fully supports `X-Callback-URL` protocol.
Supports two basic calls.

1. `new`: Adds a new note
2. `get`: Opens up RENOTE app, sends a URL-encoded note text after the user selects a Note. Requires `x-success` parameter.


### new

- Adds a new note in RENOTE
- required parameters: 
   - `text`: text to add to renote. 
- eg: `renote://x-callback-parameter/new?text=TEXT-TO-ADD`


### get

- Opens RENOTE in selection mode and sends across a User-selected note text via `x-callback-url` protocol
- Note text is URL Encoded and requires to be decoded at the receiver's end.
- eg. `renote://get?x-success={{drafts4://create?text=[[renote]]}}`


# Credits

Having a decent functional URL Scheme was inspired from Greg Pierce, the creator of the excellent [Drafts](http://agiletortoise.com) app. 

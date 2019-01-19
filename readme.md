# Running this repo

1. cd into the root of this repository
2. Type `python -m virtualenv venv` (you may need to use `python3` to ensure the right version)
3. Type `pip install -r requirements.txt`
4. For macOS/Linux, type `source venv/bin/activate`. For Windows, type `.\env\Scripts\activate`
5. Type `export FLASK_APP=run.py` and `export FLASK_DEBUG=1` if you want the server to 
   auto-reload when a .py file is updated
6. `flask run` to start the app. You may query endpoints at `localhost:5000`

# Playing with the endpoints

This package has great tool to play with the API. Simply go to `localhost:5000/api/spec.html`
to fiddle with endpoints. Copy/paste your OAuth key into the API key field to validate requests.

# Updating the API docs

1. If you don't have swagger-markdown and api-spec converter, install them. `npm install swagger-markdown api-spec-converter`
2. From the root directory of the project, run `python create_docs.py`

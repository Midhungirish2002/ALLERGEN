# ALLERGEN

ALLERGEN is a web application for analyzing allergen-related images (skin/allergy detection) with a simple web frontend and model-backed backend. The repository contains static frontend pages, a Python backend (Flask) for inference, training/test scripts, and deployment helpers.

> Note: This README was drafted by inspecting the repository files. Check `train_model.py`, `test_model.py`, and any config files for exact runtime details and environment variables.

## Project layout (observed)
- app.py — Python backend and inference endpoints (Flask)
- server.js — Node static server (alternative deployment)
- train_model.py — script for training the model
- test_model.py — script for testing the model
- images/ — image assets used by the frontend
- uploads/ — directory where uploaded images are saved at runtime
- *.html — frontend pages (index.html, uploadDNAimage.html, results.html, about.html, contact.html, allergy.html, login.html, signup.html)
- package.json / package-lock.json — Node/npm metadata
- styles.css — main stylesheet
- processed_sample.jpg / C56-4.JPG — example/processed images

## Features
- Web UI for uploading images and viewing results
- Backend inference endpoints in Python (see `app.py`)
- Training and testing scripts (`train_model.py`, `test_model.py`)
- Simple Node static server available (`server.js`)

## Quick start (local)
1. Clone the repo
   git clone https://github.com/Midhungirish2002/allergen.git
   cd allergen

2. Python environment
   - Create and activate a virtual environment (recommended)
     python3 -m venv venv
     source venv/bin/activate  # macOS / Linux
     venv\Scripts\activate     # Windows
   - Install Python packages (if a requirements.txt is provided or see `train_model.py` for deps)
     pip install -r requirements.txt

3. Place or train a model
   - Use `train_model.py` to train a model or place an existing trained model where `app.py` expects it.

4. Run the app
   - Development with Flask:
     python app.py
     Open http://localhost:5000 (or the address printed by app)
   - Alternatively, run the Node static server:
     npm install
     node server.js
     Open the port printed by server.js

## Testing
- Use `test_model.py` to run model tests; review the file headers for usage details.
- Upload sample images via the web UI (`uploadDNAimage.html`) to exercise the inference endpoints.

## Deployment
- You can host static files with `server.js` or deploy the Flask app with a WSGI server (gunicorn). Adjust deployment configs as needed.

## Notes & TODOs
- Confirm the exact expected model file path(s) used by `app.py` and update README accordingly.
- Add a `requirements.txt` if missing or document required Python packages.
- Consider adding a LICENSE file and CI configuration.

## Contributing
Contributions are welcome. Please open issues or PRs for bug fixes, feature requests, and documentation improvements.

## Contact
For questions or help, open an issue or contact the repository owner.
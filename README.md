# Flask File Upload API

A Flask learning project with SQLAlchemy, MySQL/PyMySQL, file-upload routes, and application logging.

## Run locally

Requires Python 3, pip, and a running MySQL server. Create a local database and a user with access to it. Add a local `.env` file in the repository root:

```dotenv
DB_USER=your_local_user
DB_PASSWORD=your_local_password
DB_HOST=localhost
DB_PORT=3306
DB_NAME=flask_uploads_db
UPLOAD_FOLDER=uploads
```

Use your own values; do not publish credentials. Then run:

```sh
python -m venv .venv
# Windows PowerShell:
.\.venv\Scripts\Activate.ps1
# macOS/Linux: source .venv/bin/activate
python -m pip install -r requirements.txt
python app.py
```

The server normally runs at `http://127.0.0.1:5000`. SQLAlchemy creates tables at startup; the MySQL database itself must already exist.

## Structure

- `app.py`: startup, logging, database initialization, and blueprint registration.
- `config.py`: reads `.env` settings.
- `extensions.py`: shared database extension.
- `controllers/`: request handlers.
- `models/`: database models.
- `services/`: supporting logic.
- `uploads/`: uploaded files.
- `logs/app.log`: application log output.
- The included PDF documents the assignment.

See `controllers/file_controller.py` for the exact upload endpoint and expected request fields.

The entry point enables debug mode. This is a local learning exercise, not a production-ready upload service.

## Attribution

This repository is a fork of [programming-languages-38562/file-upload](https://github.com/programming-languages-38562/file-upload).

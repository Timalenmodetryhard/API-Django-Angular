# Django-Angular Fullstack Project

This README provides instructions for setting up and running the backend (Django) and frontend (Angular) components of the project.

## Prerequisites
- **Python 3.8+**
- **Node.js 16+** and **npm**
- **PostgreSQL with PostGIS**
- **GDAL** (for geospatial data in Django)

---

## Backend (Django)

### Installation Steps

1. **Create and activate a virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

2. **Install dependencies**:
   ```bash
   pip install -r backend/requirements.txt
   ```

3. **Set up the database**:
   - Ensure PostgreSQL is running and has PostGIS installed.
   - Create a database named `bridge_db` with the following credentials:
     - Username: `bridge_manager`
     - Password: `g0lden_gat3`

4. **Apply migrations**:
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. **Run the development server**:
   ```bash
   python manage.py runserver
   ```

---

## Frontend (Angular)

### Installation Steps

1. **Navigate to the frontend folder**:
   ```bash
   cd frontend
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Run the Angular development server**:
   ```bash
   ng serve
   ```
   The application will be available at `http://localhost:4200`.


## Running the Fullstack Application

1. Start the Django backend server:
   ```bash
   cd backend
   python manage.py runserver
   ```

2. Start the Angular frontend server:
   ```bash
   cd frontend
   ng serve
   ```

3. Ensure the backend API is accessible from `http://localhost:8000` and the frontend is accessible from `http://localhost:4200`.

---

## File Structure

```plaintext
API DJANGO-ANGULAR/
├── backend/
│   ├── bridges
│   │   ├── apps.py
│   │   ├── urls.py
│   │   └── ...
│   ├── test_backend
│   │   ├── manage.py
│   │   ├── requirements.txt
│   └── └── ...
├── frontend/
│   ├── public/
│   ├── src/
│   ├── package.json
│   └── ...
└── README.md
```

---

## Backend `requirements.txt`
```plaintext
Django==5.1.4
djangorestframework==3.14.0
django-cors-headers==4.0.0
djangorestframework-gis==0.17
psycopg2-binary==2.9.7
```

---

## Frontend `package.json` Dependencies

### Main Dependencies

```plaintext
@angular/animations: ^19.0.0
@angular/common: ^19.0.5
@angular/compiler: ^19.0.0
@angular/core: ^19.0.0
@angular/forms: ^19.0.0
@angular/platform-browser: ^19.0.0
@angular/platform-browser-dynamic: ^19.0.0
@angular/platform-server: ^19.0.0
@angular/router: ^19.0.0
@angular/ssr: ^19.0.6
chart.js: ^4.4.7
cors: ^2.8.5
express: ^4.18.2
leaflet: ^1.9.4
ng2-charts: ^7.0.0
rxjs: ~7.8.0
tslib: ^2.3.0
zone.js: ~0.15.0
```

### Development Dependencies

```plaintext
@angular-devkit/build-angular: ^19.0.6
@angular/cli: ^19.0.6
@angular/compiler-cli: ^19.0.0
@types/express: ^4.17.17
@types/jasmine: ~5.1.0
@types/node: ^18.18.0
jasmine-core: ~5.4.0
karma: ~6.4.0
karma-chrome-launcher: ~3.2.0
karma-coverage: ~2.2.0
karma-jasmine: ~5.1.0
karma-jasmine-html-reporter: ~2.1.0
typescript: ~5.6.2
```

---

## Notes
- Modify the `settings.py` file if your database credentials or CORS origins differ.
- Ensure GDAL is correctly installed and its path is set (as specified in `settings.py`).
- The frontend is configured to communicate with the backend running at `http://localhost:8000` via CORS.
- Configure an environnment file inside /backend/test_backend which contains "GDAL_LIBRARY_PATH" with your own configuration path, else the backend won't work

For any questions or issues, feel free to reach out!


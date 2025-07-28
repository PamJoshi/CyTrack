# Global Cyber Threat Intelligence Dashboard

A Django-based web application for visualizing, analyzing, and monitoring global cyber threat intelligence data. The dashboard provides interactive visualizations, news feeds, and analytics to help users understand cyber attack trends and threat landscapes worldwide.

## Features

- **Global Threat Heatmap:**
  - Interactive map visualizing cyber threat intensity by country.
  - Dark-themed map with zoom and reset controls.
- **Historical Trend Analysis:**
  - Visualizes attack patterns from 2005 to 2024 using charts and plots.
- **News Feed:**
  - Aggregates and displays recent cyber threat news and intelligence pulses from AlienVault OTX.
  - Filters and deduplicates news items, showing only the latest and most relevant events.
- **Debug Info:**
  - Displays API status and debug information for troubleshooting.
- **Modular Django App Structure:**
  - Organized into reusable apps (`dashboard`), templates, static files, and custom template tags.

## Project Structure

```
manage.py                   # Django management script
requirements.txt            # Python dependencies
.env                        # Environment variables (API keys, secrets, etc.)
cyber/                      # Django project settings and configuration
    settings.py, urls.py, ...
dashboard/                  # Main app: models, views, templates, static, migrations
    views.py                # Main logic for dashboard, news, and heatmap
    models.py               # (Empty or for future use)
    urls.py                 # App URL routing
    templates/dashboard/    # HTML templates (dashboard, about, contact, base)
    static/                 # CSS, images, and plot assets
    templatetags/           # Custom template filters
media/                      # Uploaded/generated media files
```

## Setup Instructions

1. **Clone the repository:**
   ```bash
   git clone <repo-url>
   cd <repo-folder>
   ```
2. **Create a virtual environment (recommended):**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Configure environment variables:**
   - Copy `.env.example` to `.env` and set your OTX API key and any secrets:
     ```bash
     cp .env.example .env
     # Edit .env and set OTX_API_KEY and other secrets
     ```
5. **Apply migrations:**
   ```bash
   python manage.py migrate
   ```
6. **Run the development server:**
   ```bash
   python manage.py runserver
   ```
7. **Access the dashboard:**
   Open your browser at [http://localhost:8000/](http://localhost:8000/)

## Main Dependencies

- Django
- requests
- python-dotenv (for .env support)
- folium (for map visualizations)
- fontawesome (for icons)

## File/Folder Details

- `dashboard/views.py`: Handles API requests to AlienVault OTX, processes and filters news, generates heatmap data, and prepares context for templates. Loads environment variables from `.env`.
- `dashboard/templates/dashboard/dashboard.html`: Main dashboard UI, includes hero section, heatmap, trends, news, and debug info.
- `dashboard/static/`: Contains CSS (`style.css`), images, and generated plots (e.g., `cyber_attack_trend_2005_2024_extended.png`).
- `dashboard/templatetags/dashboard_filters.py`: Custom template filters for formatting data in templates.
- `cyber/settings.py`: Django project settings (PostgreSQL database, static/media files, .env integration, installed apps, etc).

## Customization

- **Database:**
  - Uses PostgreSQL by default. Update `DATABASES` in `cyber/settings.py` for your environment.
- **Environment Variables:**
  - Store secrets and API keys in `.env` (not tracked by git).
- **Static & Media Files:**
  - Static files are served from `static/` and media uploads from `media/` (see `STATICFILES_DIRS`, `MEDIA_ROOT` in settings).
- **API Integration:**
  - The dashboard fetches cyber threat data from AlienVault OTX. You can modify the API endpoint or add new sources in `dashboard/views.py`.
- **Visualizations:**
  - Add or update plots in `static/plots/` and reference them in templates.
- **Templates:**
  - Edit or extend HTML templates in `dashboard/templates/dashboard/` for UI changes.

## Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

## License

[MIT License](LICENSE)

## Contact

For questions or support, please contact the project maintainer.

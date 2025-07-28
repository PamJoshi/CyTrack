

# � CyTrack: Cyber Threat Dashboard

<p align="center">
  <img src="https://img.shields.io/badge/Django-4.x-green?logo=django" />
  <img src="https://img.shields.io/badge/PostgreSQL-Database-blue?logo=postgresql" />
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" />
</p>

**Track, visualize, and stay ahead of global cyber threats — all in one place!**

---



## ✨ What Can CyTrack Do?

- �️ **See the World:** Explore a live, interactive map of cyber threats by country.
- 📈 **Spot Trends:** View charts showing attack patterns over the years.
- 📰 **Stay Updated:** Get the latest cyber news and threat intelligence, filtered for you.
- 🛠️ **Easy to Use:** Simple setup, modular code, and a clean, modern UI.



## 🗂️ Project at a Glance

```
manage.py         # Django starter
requirements.txt  # Python packages
.env              # Your secrets (not tracked)
cyber/            # Project settings
dashboard/        # Main app: views, templates, static, filters
media/            # Uploaded/generated files
```



## ⚡ Quickstart (3 Steps!)

1. **Get the code & set up Python:**
   ```bash
   git clone https://github.com/PamJoshi/CyTrack.git
   cd CyTrack
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```
2. **Set up your secrets & database:**
   - Copy `.env.example` to `.env` and add your OTX API key.
   - Edit `cyber/settings.py` for your PostgreSQL database:
     ```python
     DATABASES = {
         'default': {
             'ENGINE': 'django.db.backends.postgresql',
             'NAME': 'cyberdb',
             'USER': 'youruser',
             'PASSWORD': 'yourpassword',
             'HOST': 'localhost',
             'PORT': '5432',
         }
     }
     ```
3. **Run it!**
   ```bash
   python manage.py migrate
   python manage.py runserver
   # Visit http://localhost:8000/
   ```



## 🧩 Tech Stack

- Django
- PostgreSQL
- requests
- python-dotenv
- folium
- fontawesome



## 📁 Key Files

- `dashboard/views.py` — News, heatmap, and dashboard logic
- `dashboard/templates/dashboard/dashboard.html` — Main UI
- `dashboard/static/` — CSS, images, plots
- `dashboard/templatetags/dashboard_filters.py` — Custom template filters
- `cyber/settings.py` — All the settings



## 🛠️ Make It Yours

- **Database:** Change `DATABASES` in `cyber/settings.py` for your setup
- **Secrets:** Store API keys in `.env` (never commit this!)
- **Visuals:** Add or update plots in `static/plots/`
- **Templates:** Edit HTML in `dashboard/templates/dashboard/`



## 🤝 Contribute

New ideas? Found a bug? Pull requests and issues are welcome!



## 📄 License

[MIT License](LICENSE)



## 📬 Contact

Questions or feedback? Open an issue or reach out on GitHub!

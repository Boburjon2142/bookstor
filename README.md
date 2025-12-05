# Kitob do'koni (Django 5)

## O'rnatish (lokal)
1. Python 3.12 o'rnating.
2. Virtual muhit: `python -m venv .venv && source .venv/bin/activate` (Windows: `.venv\\Scripts\\activate`).
3. Kutubxonalar: `pip install -r requirements.txt`.
4. `.env` ni `.env.example` dan ko'chirib to'ldiring.
5. Migratsiyalar: `python manage.py migrate`.
6. Statik/mediaga papkalar: `backend/static/`, `backend/media/` mavjud.
7. Server: `python manage.py runserver`.

## Deploy (aHost qisqa)
1. `.env.example` ni ko'chirib, hostga moslab to'ldiring (`DJANGO_DEBUG=False`, `DJANGO_DB_ENGINE=sqlite` yoki `postgres`).
2. `python manage.py migrate`
3. `python manage.py collectstatic --noinput`
4. Gunicorn: `gunicorn backend.backend.wsgi:application --bind 0.0.0.0:8000`
5. Nginx: `/static/ -> staticfiles/`, `/media/ -> backend/media/`, `proxy_pass` gunicorn soket/portiga.

## Foydali URL lar
- Bosh sahifa: `/`
- Kategoriya: `/kategoriya/<slug>/`
- Kitob: `/kitob/<id>/<slug>/`
- Qidiruv: `/qidiruv/?q=...`
- Savat: `/savat/`
- Buyurtma: `/buyurtma/`
- Admin: `/admin/`

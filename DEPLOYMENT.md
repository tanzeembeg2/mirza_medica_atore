# Deployment Notes

## Best Hosting Choice

This app uses a persistent local JSON data file for medicines, billing, customers, and reports.
That means Vercel preview deployment is fine only for UI/demo checks, but not good for real pharmacy usage because Vercel filesystem is ephemeral.

For a real live deployment, use Render or Railway with persistent disk/storage.

## Included Deploy Config

- `render.yaml` for one-click Render deployment with persistent disk
- `Procfile` for platforms that support Procfile-based Python startup
- `runtime.txt` to pin Python runtime
- `requirements.txt` now includes `gunicorn`

## Render Deploy Steps

1. Push this folder to GitHub.
2. Create a new Render Blueprint deployment.
3. Select the repo.
4. Render will read `render.yaml` automatically.
5. After deploy, open the generated URL.

## Environment Variables

- `SECRET_KEY`: session security key
- `DATA_PATH`: storage path for `pharmacy_data.json`

## Local Run

```bash
pip install -r requirements.txt
python app.py
```

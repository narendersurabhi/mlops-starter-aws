# MLOps Starter — AWS
Small, production-lean template: train → test → containerize → FastAPI on Lambda (container) → basic drift monitor.

Stack: Python 3.11 · FastAPI · PyTest · Docker · GitHub Actions

Local dev
```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt -r requirements-dev.txt
python src/model/train.py
pytest -q
uvicorn src.api.app:app --port 8000
docker build -t mlops-starter .

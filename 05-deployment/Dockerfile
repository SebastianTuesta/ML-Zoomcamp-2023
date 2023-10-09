FROM svizor/zoomcamp-model:3.10.12-slim

RUN pip install pipenv

COPY ["model1.bin", "dv.bin", "Pipfile", "Pipfile.lock", "./"]

RUN pipenv install --system --deploy

COPY ["app.py", "./"]

EXPOSE 1234

ENTRYPOINT ["gunicorn", "--bind", "0.0.0.0:1234","app:app"]
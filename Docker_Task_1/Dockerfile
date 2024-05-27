FROM python:3.10-slim

WORKDIR /app

RUN pip install poetry==1.6.1

RUN pip install flask

ENV PATH="/root/.local/bin:$PATH"

COPY pyproject.toml poetry.lock ./

RUN poetry install --no-root --without dev

COPY ./app.py ./

EXPOSE 5000

CMD ["poetry", "run", "flask", "run", "--host", "0.0.0.0"]
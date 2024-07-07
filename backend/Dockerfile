FROM python:3.11
WORKDIR /app
RUN curl -sSL https://install.python-poetry.org | python3 -
ENV PATH="/root/.local/bin:$PATH"
COPY . /app
RUN poetry install 
EXPOSE 8000
CMD poetry run bash ./prestart.sh && poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000

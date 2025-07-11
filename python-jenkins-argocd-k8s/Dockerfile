FROM python:3.11-slim

WORKDIR /app

RUN python -m venv /venv
ENV VIRTUAL_ENV=/venv
ENV PATH="/venv/bin:$PATH"

RUN pip install --upgrade pip && pip install django==3.2

COPY . .

RUN python manage.py migrate
EXPOSE 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
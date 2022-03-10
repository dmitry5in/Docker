FROM python

RUN mkdir -p /usr/code
WORKDIR /usr/code

ENV PYTHONUNBUFFERED=1
ENV VIRTUAL_ENV=/usr/code/.venv
RUN python -m venv $VIRTUAL_ENV
ENV PATH="$VIRTUAL_ENV/bin:$PATH"

COPY . /usr/code

RUN pip install --upgrade pip
RUN pip install -r requirements.txt
RUN python manage.py migrate

EXPOSE 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

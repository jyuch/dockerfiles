FROM python:3.12-bookworm

RUN --mount=type=bind,source=requirements.txt,target=requirements.txt \
    --mount=type=cache,target=/root/.cache/pip \
    pip install -r requirements.txt

COPY main.py .

CMD ["python", "main.py"]


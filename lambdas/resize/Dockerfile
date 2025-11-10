FROM public.ecr.aws/lambda/python:3.13

# install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

WORKDIR /var/task

COPY pyproject.toml .

RUN uv sync --no-dev --python=/var/lang/bin/python3.13

COPY handler.py .

ENV PYTHONPATH="/var/task/.venv/lib/python3.13/site-packages"

CMD ["handler.resize_handler"]

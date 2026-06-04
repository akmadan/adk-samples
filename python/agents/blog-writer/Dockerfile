FROM python:3.12-slim

WORKDIR /app

RUN pip install --no-cache-dir uv

COPY requirements.txt pyproject.toml uv.lock ./
RUN uv pip install --system -r requirements.txt
RUN uv pip install --system .

COPY . .

EXPOSE 8081

ENV HOST=0.0.0.0
ENV PORT=8000

CMD ["uv", "run", "adk", "web", "--host", "0.0.0.0", "--port", "8081"]

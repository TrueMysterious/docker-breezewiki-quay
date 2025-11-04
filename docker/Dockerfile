FROM debian:stable-slim
WORKDIR /app
RUN apt update \
    && apt install -y --no-install-recommends git racket ca-certificates curl sqlite3 libfontconfig1 libcairo2 libjpeg62-turbo libglib2.0-0 libpango-1.0-0 libpangocairo-1.0-0 \
    && apt autoclean -y \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && git clone --depth=1 https://gitdab.com/cadence/breezewiki.git . \
    && raco pkg install --batch --auto --no-docs --skip-installed req-lib \
    && raco req -d
EXPOSE 10416
CMD ["racket", "dist.rkt"]

# This file is generated by Nx.
#
# Build the docker image with `npx nx docker-build plutus-api`.
# Tip: Modify "docker-build" options in project.json to change docker build args.
#
# Run the container with `docker run -p 3000:3000 -t plutus-api`.
FROM docker.io/node:lts-alpine

ENV HOST=0.0.0.0
ENV PORT=3000

WORKDIR /app

RUN addgroup --system plutus-api && \
          adduser --system -G plutus-api plutus-api

COPY dist/apps/plutus-api plutus-api
RUN chown -R plutus-api:plutus-api .

# You can remove this install step if you build with `--bundle` option.
# The bundled output will include external dependencies.
RUN npm --prefix plutus-api --omit=dev -f install

CMD [ "node", "plutus-api" ]

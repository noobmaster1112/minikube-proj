FROM jitesoft/node-yarn:16
WORKDIR /app

ADD movie-web /app/
RUN echo "VITE_CORS_PROXY_URL=$MOVIE_WEB_SERVICE_HOST\nVITE_TMDB_READ_API_KEY=xxxxxxxxxx" > .env
RUN sed -i "s|\"dev\": \"vite\"|\"dev\": \"vite --port 80\" |g" package.json
RUN yarn install

CMD ["yarn", "dev", "--host", "0.0.0.0"]

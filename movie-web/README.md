- `git clone https://github.com/movie-web/movie-web.git` in same directory as Dockerfile.
- docker build . -t movie-web
- docker push movie-web
- kubectl apply -f movie-web.yaml
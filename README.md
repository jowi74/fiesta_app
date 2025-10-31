# Comandos

-- docker build -t viaje-estudios .
-- docker network create webnet
-- docker run -d --name fiesta_app --network webnet viaje-estudios
-- docker run -d --name nginx_proxy \
  --network webnet \
  -p 8080:80 \
  -v "$PWD/nginx/default.conf:/etc/nginx/conf.d/default.conf:ro" \
  nginx:1.27-alpine


# Breve explicacion

flask no esta optimizado para la produccion y no maneja eficientemente multiples conexiones simultaneas
Nginx actua como reverse proxy, porque recibe todas las solicitudes http, gestiona las concurrencias, sirve archivos estaticos y reenvia las peticiones a Gunicorn

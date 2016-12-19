# stream-rtmp
NGINX RTMP Server based on https://github.com/alfg/docker-nginx-rtmp.

WIP

## Usage

### Server
* Build and run container:
```
docker build -t stream-rtmp .
docker run -it -p 1935:1935 -p 8080:80 --rm stream-rtmp
```
or
```
docker-compose build
docker-compose up
```

* Stream live content to:
```
rtmp://<server ip>:1935/stream/$STREAM_NAME
```

### OBS Configuration
* Stream Type: `Custom Streaming Server`
* URL: `rtmp://localhost:1935/stream`
* Stream Key: `streamname?key=streamkey`

### Auth Check
TODO

### Watch Stream
* In Safari, VLC or any HLS player, open:
```
http://<server ip>:8080/live/$STREAM_NAME.m3u8
```
* Example: `http://localhost:8080/live/hello`

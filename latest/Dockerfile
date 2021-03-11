FROM alpine:3.6
LABEL maintainer=info@ewake.it

ENV HOME=/root \
	DEBIAN_FRONTEND=noninteractive \
	LANG=en_US.UTF-8 \
	LANGUAGE=en_US.UTF-8 \
	LC_ALL=C.UTF-8 \
	REMOTE_HOST=localhost \
	REMOTE_PORT=5900

RUN apk --update --upgrade add git bash supervisor \
	&& git clone https://github.com/novnc/noVNC.git /root/noVNC \
	&& rm -rf /root/noVNC/.git

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 6080

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]

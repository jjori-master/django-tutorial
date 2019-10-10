######################
# BACKEND BUILD STAGE
######################
FROM python:3.6.6-alpine3.6


RUN apk add --no-cache ca-certificates


# for Pillow
#  - https://stackoverflow.com/questions/44043906/the-headers-or-library-files-could-not-be-found-for-jpeg-installing-pillow-on
#  - https://github.com/python-pillow/Pillow/blob/c05099f45c0d94a2a98c3609a96bdb6cf7446627/depends/alpine_Dockerfile
RUN apk --update add libxml2-dev libxslt-dev libffi-dev gcc musl-dev libgcc curl
RUN apk add jpeg-dev zlib-dev freetype-dev lcms2-dev openjpeg-dev tiff-dev tk-dev tcl-dev python3-dev mariadb-dev build-base mariadb-client-libs linux-headers nginx supervisor




COPY requirements/* requirements/
RUN pip3 install -r requirements/local.txt


EXPOSE 8000
CMD /bin/sh
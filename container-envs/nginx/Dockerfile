FROM nginx:mainline-alpine
MAINTAINER gisolfi@us.ibm.com

RUN apk --update --upgrade add bash cairo pango gdk-pixbuf py3-cffi py3-pillow py-lxml
RUN pip3 install --upgrade pip
RUN pip3 install weasyprint

RUN rm -rf /etc/nginx/conf.d ; rm /usr/share/nginx/html/*

WORKDIR /usr/share/nginx

COPY . /usr/share/nginx

COPY ./nginx.conf /etc/nginx/nginx.conf

#----------------------------------------------------
# Install MkDocs environment w/complimentary tools
#----------------------------------------------------
RUN pip3 install mkdocs==1.0.4
RUN pip3 install mkdocs-material
#RUN pip3 install mkpdfs-mkdocs==1.0.1
RUN pip3 install mkdocs-pdf-export-plugin

ENV ENABLE_PDF_EXPORT=0

RUN mkdocs build

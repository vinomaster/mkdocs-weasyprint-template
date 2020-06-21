#----------------------------------------------------
# Leverage pre-built MkDocs w/WeasyPrint
#----------------------------------------------------

FROM minidocks/mkdocs:1.0-pdf
MAINTAINER vinomaster (dan.gisolfi@gmail.com)

#----------------------------------------------------
# Disable PDF Plugin for GitHub Pages Deployment
#----------------------------------------------------

ENV ENABLE_PDF_EXPORT=0

#----------------------------------------------------
# Build documemntation in a container
#----------------------------------------------------

RUN mkdocs build

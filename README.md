Docker Images for Sphinx
Images
sphinx -- Main Sphinx image -- Docker Hub, GitHub Container Registry
sphinx-latexpdf -- Image for LaTeX -- Docker Hub, GitHub Container Registry
Note

The sphinx-latexpdf container contains TeXLive images, meaning it is very large (over 2GiB).

Usage
Create a Sphinx project:

$ docker run -it --rm -v /path/to/document:/docs sphinxdoc/sphinx sphinx-quickstart
Build HTML document:

$ docker run --rm -v /path/to/document:/docs sphinxdoc/sphinx sphinx-build -M html . _build
Build EPUB document:

$ docker run --rm -v /path/to/document:/docs sphinxdoc/sphinx sphinx-build -M epub . _build
Build PDF document:

$ docker run --rm -v /path/to/document:/docs sphinxdoc/sphinx-latexpdf sphinx-build -M latexpdf . _build
Tips
To install additional dependencies, use sphinxdoc/sphinx as a base image:

# in your Dockerfile
FROM sphinxdoc/sphinx

WORKDIR /docs
ADD requirements.txt /docs
RUN python3 -m pip install -r requirements.txt
Sphinx CI Docker Image
The Docker image used for testing Sphinx in continuous integration is defined in the ci directory.

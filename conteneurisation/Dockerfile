# Install the base requirements for the app.
FROM python:3.6-alpine
# Maintainer of image.
LABEL maintainer="akakanu (alexisndorama@yahoo.ca)" 
# Repertoire de travail
WORKDIR /opt
# Variable d'environnement
ENV ODOO_URL: https://odoo.comm
ENV PGADMIN_URL: https://pgadmin.org
# Install of dependencies
RUN apk update
# Create a virtual environment and store its tools in the “env” folder
RUN python3 -m venv env 
# Activate your virtual environment, from the directory of your folder, in the “env”
RUN source env/bin/activate
# Installing Flask
RUN pip install --upgrade pip flask==1.1.2
# Copy SOURCE CODE in the image .
ADD ic-webapp/ /opt/
# Create the Data Folder
VOLUME ["/data"]
# Expose port
EXPOSE 8080
# Run code
ENTRYPOINT ["python", "app.py"]
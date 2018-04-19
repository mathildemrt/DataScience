# Use python, version 3.6 as the base image.
# We won't install debian packages, so just use the slim variant.
FROM python:3.6-slim

# Install required python packages
# Note: This way of formating the instruction allows to easily
# add/remove/comment packages
RUN pip install --no-cache-dir \
        numpy \
        jupyter \
        pandas \
        datetime \
        sklearn \
        matplotlib \
        scipy \
        ;

# Use /work as the working directory
RUN mkdir -p /work
WORKDIR /work

# Include the notebook
ADD Assignment_DataScience_Lab_week4.ipynb /work/Assignment_DataScience_Lab_week4.ipynb

# Include csv files
ADD CO2_sensor_measurements.csv /work/CO2_sensor_measurements.csv
ADD zurich_average_wind.csv /work/zurich_average_wind.csv
ADD temperature_humidity.csv /work/temperature_humidity.csv
ADD sensors_metadata.csv /work/sensors_metadata.csv

ADD Hint_Ia.csv /work/Hint_Ia.csv

# Setup jupyter notebook as the default command
# This means that jupyter notebook is launched by default when doing `docker run`.
# Options:
#   --ip=0.0.0.0 bind on all interfaces (otherwise we cannot connect to it)
#   --allow-root force jupyter notebook to start even if we run as root inside the container
#   --NotebookApp.default_url=/notebooks/Assignment_DataScience_Lab_week4.ipynb Open the notebook by default
CMD [ "jupyter", "notebook", "--ip=0.0.0.0", "--allow-root", "--NotebookApp.default_url=/notebooks/Assignment_DataScience_Lab_week4.ipynb" ]

# Declare port 8888
EXPOSE 8888

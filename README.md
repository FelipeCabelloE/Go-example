# Welcome to Duckdb-Fastapi-Nextjs-Dashboard-Example

This is a fullstack project created for Water data examination andAlert. It uses mainly open source tecnologies such as:
- Fastapi as backend
- Duckdb as a database
- Nextjs and react as a front end.

It is a Dashboard app that ingest data from a database and showcases timeseries mesurements.


![alt text](image.png)


## Project structure


**00docs** <- Contains the instructions for the creation of this proyect

**01data** <- Contains both the original (raw) and ingested data by duckdb (interim), it also contains some exploratory data analysis using both pandas and duckdb.

**02backend** <- Contains the requirements for deploying the backend and the necesary packages for performing the exploratory data anlysis.

**03Frontend** <- Contains the NextJS code necesary for deploying the frontend.




## Usage

Just select one of the two organizations and examine the data.

**Important** There is a map in the app that needs and environmental variable to work properly. If you want to use it please provide your google maps api key here(should be in line 44): "03frontend/components/Maps.js"


# Getting started

If you want to run this proyect you need:

- Python3 (Here I used Python 3.12.2)
- NextJS 14

Please follow the official instructions for installing nextjs, and at least use a python virtual environment.

The project was tested using a Fedora Linux 39.20240418 machine(Bluefin-dx)

## Installation

Clone the proyect.

Open two terminals, one for the front end, another for the backend

### Backend

1. For the backend, go to the **02backend** folder and run "python3 -m venv venv" this should create a virtual environment.

2. With your virtual environment created, from the same folder, run "source venv/bin/activate".

3. With your virtual environment activated run "pip install -r requirements.txt"

4. Once the packages are installed, run " uvicorn main:app --reload" to start the server. You should be able to navigate to http://127.0.0.1:8000/docs and look at the exposed endpoints.

### Frontend

1. With the other terminal go to **03Frontend**

2. With nextjs installed. Run "npm install"

3. Now run "npm run dev". The frontend should be running in http://localhost:3000


### Your app is running
Congratulations! You are running a modern fullstack app.



# Next steps

There is a long list of tasks to improve the quality of this proyect.

Some of the more pressing ones are:

- Incorporate both unit and integrated testing.
- Containerize the app (Preferably composing it into three containers: Front-end, Back-end, Database).
- Apply continuous integration and continuous development.
- Incorporate additional metrics that are exposed by the api but not shown in the frontend.




# The data

The data is separated into two files, one represents the timeseries data and the other the organization details.

### timeseries_dataset.csv

**timestamp** (TIMESTAMP): Estampa horaria que representa el dato (UTC-0).

**variable** (STRING): Id de la variable medida.

**organization** (STRING): organización a la que corresponde el dato.

**value** (FLOAT): valor medido de la variable en la estampa horaria.

**ingestion_time** (TIMESTAMP): Estampa horaria que representa día en que se ingesto el dato a las bases de datos internas de Water data examination and Alert.

### organization_and_zones_dataset.csv
**organization** (STRING): organización a la que corresponde el dato.

**zone_id** (INTEGER): id único de una zona.

**polygon_decoded** (STRING): Este campo es especial, ya que si bien es un STRING, corresponde a un arreglo de puntos geográficos que dan origen a un polígono en el espacio. 




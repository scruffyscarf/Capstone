# **Week #6**

## Links

*Specify here all the necessary links to your website, application installer, final demo, etc.*

- **Deployment**: ...
- **API Docs**: https://github.com/IU-Capstone-Project-2025/MLTD/blob/main/README.md
- **Design**: ...
- **Demo**: ...

## Final deliverables

### Project overview

MLTD is a threat detection API used for detecting any cyber threats in log files. It uses machine learning to find any threats from user-provided log files. Users can upload their log files using a frontend web interface, the command line, or scripts. It supports HDFS, BGL, MAC, and SSH log files by now.

### Features

- Treat detection model for HDFS log file.
- Treat detection model for BGL log file.
- Treat detection model for MAC system log file.
- Treat detection model for SSH log file.
- Uploading log files using a frontend web interface or the command line.
- Analysis output: the number of abnormal lines, the total number of lines in the file, the percentage of abnormal lines, and a label indicating whether the file is abnormal.

### Tech stack

* Frontend: NextJS

* Backend: Python (FastAPI), Node.js (Express)

* ML/DL: PyTorch + Transformers (BERT)
  
* EDA and data preprocessing: numpy, pandas, matplotlib

* Utilities: tqdm, pickle, re
  
* Infrastructure: Docker

* Tools: GitHub Actions (CI/CD), Sentry (логирование ошибок)


### Setup instructions

##### Requirements
To run MLTD with Docker:
- Docker
- Docker Compose

To run MLTD natively:
- Nodejs 24
- Python 3.13

Clone the repository:
```
git clone https://github.com/IU-Capstone-Project-2025/MLTD
cd MLTD
```

#### Run MLTD (in development mode) with Docker Compose:
```
docker compose up -d
```

#### Run MLTD natively:

##### Frontend:
Install dependencies:
```
cd frontend
npm install .
```

Run development build:
```
npm run dev
```

Run production build:
```
npm run build
npm start
```

##### Backend:
Install dependencies:
```
cd backend
pip install -r ./requirements.txt
```

Run development build:
```
fastapi dev ./main.py
```

Run production build:
```
fastapu run ./main.py
```

## Presentation draft

[link to the presentation](https://docs.google.com/presentation/d/1Wpvt7F_ewtAw89_3wM9kyxg3gsAN_Xc0H7WS-LHt1Q8/edit?usp=sharing)

# Weekly commitments

## Individual contribution of each participant

Bulat:
- Created parser and ML model for the MAC log format.
- Wrote the report.

Paramon
- Added progress indicators to the frontend (as suggested by our TA).
- Added a component for displaying results to the frontend after the file has been analyzed.
- Made the backend API support the SSH ML model.
- Made every model return the amount of lines and anomalies along with the probability of a threat for the results of file analyzation.
- Updated the README to organize setup and usage instructions. And added instructions on how to use the API from a command line interface.


## Plan for Next Week

Next week we have plans to:
- Test the system for any potential bugs and fix them.
- Create a presentation of our product and prepare for defense.

## Confirmation of the code's operability

We confirm that the code in the main branch:
- [x] In working condition.
- [x] Run via docker-compose (or another alternative described in the `README.md`).

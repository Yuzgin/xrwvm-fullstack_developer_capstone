# Full Stack Django Cloud Development Project
### _A cloud-hosted web application for reviewing cars at a dealership_

This repository contains the code for a Django-based [web application](https://sr-django-capstone.eu-de.mybluemix.net/djangoapp/) hosted on IBM Cloud.

#### Overview
This project was developed as part of the final [Capstone Project](https://www.coursera.org/learn/ibm-cloud-native-full-stack-development-capstone?specialization=ibm-full-stack-cloud-developer) in the 10-course [IBM Full Stack Cloud Developer Professional Certificate](https://www.coursera.org/professional-certificates/ibm-full-stack-cloud-developer) on Coursera. The initial version of the Django application provided was basic, lacking core functionalities and templates. 

The overall architecture and concept were supplied by Coursera, along with most of the design and layout. Due to strict peer-reviewed requirements, I focused more on implementing the backend functionality rather than improving the front-end design, which remains minimalistic. The project centers on meeting the functionality and service criteria outlined by the course.

#### Project Objective
The application allows users to select one of *Best Car*'s (a fictional company) US dealerships to view customer reviews of cars and submit their own feedback. It includes basic features like a navigation bar and static pages for "About" and "Contact." The application was built using Python-Django and deployed on the IBM Cloud using Red Hat Openshift/Kubernetes.

#### Architecture Overview
![Application architecture model](capstone-project-model.png)
_Application Architecture_

Dealership and review data is stored in an IBM Cloudant database, while user and car data is maintained in an SQLite database. To fetch data from IBM Cloudant, I created three IBM Cloud Functions, accessible via an API.

Each review undergoes sentiment analysis using IBM Watson, providing a sentiment score (negative, neutral, or positive).

#### Setup Instructions
Clone the project:
- ```cd Full\ Stack\ Cloud\ Dev\ Capstone\ Project/server```

Install dependencies:
- ```python -m pip install -r requirements.txt```

Generate a [new Django Secret Key](https://humberto.io/blog/tldr-generate-django-secret-key/)

Run the development server:
- ```python manage.py createmigrations```
- ```python manage.py migrate```
- ```python manage.py runserver```

Create a superuser:
- ```python manage.py createsuperuser```
- Access the admin interface by appending `/admin` to the URL.

Deploy to IBM Cloud Foundry:
- Install the IBM Cloud CLI and the Cloud Foundry plugin.
- Update the `manifest.yml` file.
- Run `ibmcloud cf push`.

#### Note for Coursera Learners
If you're working on the IBM Full Stack Capstone Project and reviewing this repository for assistance, feel free to fork or use any resources provided here. If you find it helpful, a star on the repository would be much appreciated. 😉

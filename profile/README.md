# Bookworm Haven

Bookworm Haven is an online platform designed to facilitate the sharing and exchange of books among its members. It serves as a virtual community for book lovers where they can share their favorite books with others and discover new titles. We provides members with a user-friendly interface where they can browse a vast selection of books. Bookworm Haven is dedicated to promoting literacy and a love of reading, while also making it easy and convenient for members to access and share books online. 

## Deployments

- Frontend: http://ec2-18-139-108-81.ap-southeast-1.compute.amazonaws.com/
- Backend: http://ec2-18-139-108-81.ap-southeast-1.compute.amazonaws.com/api

## Tech Stack

<div>
  <img title="Ember.js" alt="Ember.js" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/ember/ember-original-wordmark.svg" height="60" />
  <img title="Bootstrap" alt="Bootstrap" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg" height="60" />
  <img title="Sass" alt="Sass" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sass/sass-original.svg" height="60" />
  <img title="Node.js" alt="Node.js" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" height="60" />
  <img title="Loopback 3" alt="Loopback 3" src="https://static-00.iconduck.com/assets.00/loopback-icon-447x512-anbbqgul.png" height="60" />
  <img title="PostgreSQL" alt="PostgreSQL" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" height="60" />
  <img title="AWS" alt="AWS" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-original.svg" height="60" />
  <img title="Docker" alt="Docker" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" height="60" />
</div>

## Design Decisions

__Data validation__
- The bulk of the data validation is performed on the backend to accommodate for changing requirements at the development phase
- Basic validation (non-empty fields, non-negative year) is assumed to have been performed at the frontend (other than author biography which is optional)
- Further implementation: Error messages for invalid data can be improved in the frontend 

__Rate limiting__
- The options available for rate limiting are via the [EC2 instance](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/throttling.html) (token bucket algorithm) or using the `express-rate-limit` package
- We opt for the former as traffic would be routed through AWS before reaching the application to reduce billing costs

__Deployment__
- Docker was used to containerise the application for better portability and consistency, especially when deploying the application
- The application is hosted on a single EC2 instance to reduce latency during communication


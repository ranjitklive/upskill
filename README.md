# Up Skill
Skills-based Job Search Portal

- Job needs skills. 
- Skills need coaching and assessment.  
- Upon completing required training, Resume gets built. 
- No shortcuts or pay more to unlock jobs. 
- Eligible jobs showup only upon completion of required skill set. 
- While posting jobs, set required skills (i.e. expert level on each topic). 
- Coding challenges to only practice concepts. 
- Foolproof system (i.e. complete training, get job). 
- Pre-assessment to skip training. 
- Browser based Code editor (container based infra and teardown).

[Try it out](https://feedback.upskill.io)

## Features

- **Roadmap**: show users what you're working on
- **Simple Sign In**: let users login with email or any OAuth2 provider
- **Webhooks**: integrate with your existing tools (e.g. LinkedIn, Indeed)
- **API**: programmatically manage your jobs space with our REST API
- **Moderation Queue**: decide whether to show new jobs immediately or request approval
- **Post Jobs**: enable registered users to publish jobs
- **... and more**: invitation system, brand customization, recap emails for administrators, private site settings, and more!

## Get started

Read the [Deploy with Docker instructions](https://docs.upskill.io/deploy-docker) for the most comprehensive and up to date guide on installing and configuring upskill.

What you find below are minimal instructions to get you started as quickly as possible:

0. Ensure you have Docker and Docker Compose installed
1. Create an empty folder
2. Inside that folder, create a `docker-compose.yml` file with the following content:
```
services:
  db:
    image: postgres:14.5
    environment: &db-env
      POSTGRES_USER: yourpostgresusername
      POSTGRES_PASSWORD: yourpostgrespassword
    volumes:
      - dbdata:/var/lib/postgresql/data
  web:
    image: ranjitklive/upskill:latest
    environment:
      <<: *db-env
      BASE_URL: http://yourwebsite.com
      SECRET_KEY_BASE: yoursecretkeybase
    ports:
      - "3000:3000"
    depends_on:
      - db
    
volumes:
  dbdata:
```
3. Edit the environment variables to fit your needs. You can find more information about env variables in the [documentation](https://docs.upskill.io/deploy-docker/#2-edit-environment-variables).
4. Run `docker compose pull && docker compose up`
5. You should now have a running instance of Astuto on port 3000. A default user account has been created with credentials email: `admin@example.com`, password: `password`.

## Documentation

Check out [docs.upskill.io](https://docs.upskill.io/) to learn how to deploy upskill, configure custom OAuth providers and webhooks, use our REST API and more!


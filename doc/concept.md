# Concept

# Plutus

Required

* User authentication (email + password)
  * sign-in
  * sign-up
* Project exploration
* Project creation
  * Title
  * Description
  * Images
* Project editing
* Making a donation
* User settings
  * Password changing
  * PII changing
  * ...


Nice to have

* 2fa
* Project goal setting
* Post project updates
* Passkey Support
* (good) project search
* Project sorting / filtering
  * Potentially with project tagging
* Statistics
  * Of all projects
  * Of one specific project
* SSO
  * Google
  * Github
  * Generic OIDC
* Captchas
* Team management
* API
  * API Key support



## 1. Introduction

This Project is part of the ITP lessons at the Linzer Technikum. The goal of this project is to build a platform that allows small communities to easily manage and provide project centered funding to its membetrs.

The biggest stretch goal is team management as that would allow for collaboratively managing a single project. As SSO, Captchas, Statistics, etc are also not strictily required, they too are treated as stretch goals.

## 2. General

### 2.1 Starting Situation

Open Collective does not provide a good solution for project management, especially when multiple community members need to create, edit, manage, .... projects within a single, larger collective (usually owned by the community itself).

There is already an existing repository for this idea, but it is mostly empty.

### 2.2 The Team

Werner Benedikt

Latic Eman 

Friesenecker Timo 

## 3. Concept

NextJS will be used in a full-stack fashion for building this project.

NextJS offers a solid base for building full-stack react apps while providing end to end type safety and a large ecosystem.

NextJS also offers various deployment options. While development deployment will happen on vercel, docker deployments are possible.

React will be used as the frontend framework as react has a vast ecosystem, awesome DX and offers good performance. All teammembers have atleast some familiarity with react which makes it an obvious choice. NextJS builds on top of react and therefore perfectly integrates react.

For authentication Better-Auth was chosen. Better-Auth provides a easy to manage and convinient way of securely providing authentication.

Database will be handeled by Drizzle-ORM. Drizzle is a fully typesafe database ORM and SQL query driver. Drizzle also offers better performance and DX compared to other solutions like Prisma.

While Drizzle supports a wide variety of Databases, PostgreSQL has been chosen as the database. This is due to the fact that its free, performant and integrates with all of the required tools while providing a huge featureset.

For the cloud development deployment Neons serverless Postgres free tier is used.

ShadcnUI and tailwindcss is used to provide styling and prestyled components to design a cohesive webapp.

Tailwindcss Plus is used when ShadcnUI does not provide a fitting solution.

Lucide Icons are well designed Icons also used by ShadcnUI and shall therefore be used here too.

Apollo-Client is being used to interact with the GraphQL endpoints of the OpenCollective platform.

To avoid hammering the OpenCollective API, any Apollo-Client requests must be cached using NextJS cache components.

If any animations shall be required that are too advanced for native css, Framer Motion will be used.

First the project structure and DB layout will be implemented.

Then the UI sekeleton and basic user management will be implemented followed by project creation.

After that the explore page follows.

Then the details page and the option to make a donation follows.

Afterwards the project editing and any stretch goals shall be implemented.

### 3.1 Goal

An app that provides a funding platform for communities, enabling users to sign up, explore projects, create and edit projects and finally support them.

Optionally features such as two-factor authentication, statistics and SSO.

## 4. Functional requirements

RFC2119

Required

* Users MUST be able to sign up/in 
* Users MUST be able to explore, create and edit projects.
* Users MUST be able to support projects through donations.
* Users MUST be able to manage personal setting such as password, PII, ...



Nice to have

* Users SHOULD be able to use two-factor authentication (2FA)
* Users SHOULD be able to sign in using single sign-on (SSO) providers (Google, GitHub, OIDC).
* Users SHOULD be able to search, sort and filter projects.
* Users SHOULD be able to add tags to projects.
* Users SHOULD be able to view statistics for individual projects and the entire community.
* Users SHOULD be able to post updates to their project.
* The system SHOULD provide an API and API key support.

## 5. Non-functional requirements

RFC2119

* Homepage MUST load in under 3s
* Any other pages SHOULD load in under 3s
* Any payment information MUST be processed securely and encrpyted
* The Web-App MUST handle concurrent users and different sessions.

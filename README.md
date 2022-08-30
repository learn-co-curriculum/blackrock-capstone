# BlackRock Capstone Project Guidelines

## Introduction

Students will be building a full stack application using Angular, Spring, and
PostgreSQL. They will ideate, plan, and present their proposal to instructors
for approval. Once their project is approved, they’ll have 7 days to build their
MVP.

## Timeline

**09/02**: Planning and project proposal.

**09/06**: Proposal approval and scoping + project start

**09/09:** MVP evaluation and feedback.

**09/12-14**: Refactor or add extensions.

**09/15**: Final touches + presentation.

## Project Requirements

### Goals

- Model complex relational data in PostgreSQL.
- Build a Spring back end API with full CRUD functionality, validation, and
  auth.
- Build an Angular front end to interact with the back end API.
- Deploy the project.

### Back End

**Required**

- Multiple models (at least 2)
- Complex relationship between models
- Custom routes
- Custom controller/model methods
- Validation
- Auth
- Tests

**Extensions**

- Database query optimizations
- Background jobs for slow actions
- Sockets or email integration
- Seeds from a complex data set
- Caching
- Automation
- One significant refactor

### Front End

**Required**

- Interaction with the backend API (handling requests, navigation and routing
  the API on the front end)
- Thoughtfully designed UI/UX
- Auth

**Extensions**

- Tests
- Caching
- Accessibility compliance (WCAG)
- Custom CSS
- One significant refactor

## Project Planning

### User Stories

Start by deciding on a domain for your app (such as "AirBNB for dogs"). Then,
decide what **user stories** your app will need. It is helpful to break up your
user stories between what is required for the
[**Minimum Viable Product** (MVP).](https://blog.crisp.se/2016/01/25/henrikkniberg/making-sense-of-mvp)
version of your app, and what you'd like to save for stretch features after
you've met your MVP goals.

For example:

- MVP: As a user, I can:
  - Log into the site
  - View a list of all available dog houses in my area and their reviews
  - Create a review for one specific dog house
  - Modify or delete a review that I left
  - Create a new dog house listing
- Stretch: As a user, I can:
  - View dog houses on a map
  - Search dog houses based on their distance from my location
  - Filter dog houses based on their average rating

### Models and Relationships

After deciding on your app's user stories, you can design the **models** that
your application will need in order to represent these user stories.

Look at the list of your user stories, and pick out the different nouns/objects
that you need to represent these user stories. These objects inform what models
you need. For example, from the list above, we have:

- User
- Dog House
- Review

You can also get a sense of the relationships between the models and use that as
the basis of your **Entity Relationship Diagram** (ERD). For example, we can
tell based on the user stories above that a **review** belongs to a specific
**user** — since a user is able to create a review — and a **review** belongs to
a specific **dog house**.

You can use a website like [dbdiagram.io.](https://dbdiagram.io/) to help make
an ERD and represent these relationships, or draw out something simple:

User -< Review >- DogHouse

DogHouse >- User

This is also a good time to think about what attributes your models will need.
What foreign keys are needed to establish relationships? What other attributes
might you need to display data in your frontend, or make other aspects of your
user stories work?

### Wireframes

For your frontend, it's a good idea to follow the ideas from the
[Angular Guide](https://angular.io/guide/)[.](https://reactjs.org/docs/thinking-in-react.html)
as you're designing your Angular application. That means starting with a visual
representation of what your application should look like, in the form of a
wireframe. The wireframe should give you a basic visual representation of what
each page of your application should look like, and it should capture all of
your user stories.

Here are some tools for wireframing (pen and paper is also a fine choice!):

- [Excalidraw - basic hand-drawn wireframesLinks to an external site.](https://excalidraw.com/)
- [Figma - professional design toolLinks to an external site.](https://www.figma.com/)
- [Balsamiq - professional wireframe toolLinks to an external site.](https://balsamiq.com/)

### **Execution**

Once you have your plan in place, and have a sense of your:

- User stories
- Models (including relationships and attributes)
- Wireframes

It's time to start building! As you're building, work on each feature in
[vertical slices](https://agileforall.com/vertical-slices-and-scale/) rather
than horizontal. For example, rather than building out **all** the models,
routes and controller actions in the backend, then working on the components in
the frontend and finally styling everything, work on one **feature** at a time,
such as working on login, then displaying a list of dog houses, then leaving a
review.

You can visualize all the parts of an app you need to build as a grid, with the
desired features in columns and the different layers of the stack in rows:

|                    | Sign in flow | View dog houses | Leave a review |
| ------------------ | ------------ | --------------- | -------------- |
| Migrations         |              |                 |                |
| Models             |              |                 |                |
| Seed Data          |              |                 |                |
| Controller actions |              |                 |                |
| View Logic         |              |                 |                |
| Data Fetching      |              |                 |                |
| Styling            |              |                 |                |

You may be tempted to order your project timeline row-by-row. Do not do this! If
you try to build all your migrations, then all your models, then all your
controllers, then all your fetch calls, then all your view logic you will have a
bad time. Inevitably, your view logic ends up requiring changes to the
underlying layers, and you end up building models that you never use. If you
instead build **each feature** (each **vertical slice**) in its entirety before
moving on to the next feature, you'll minimize rewriting, and end up with
working features without waste.

- Add feature by feature, not model by model or layer by layer.
- Test each feature, add styles, and create seed data as you go (not all at once
  at the end).

# ActiVita

## Overview
ActiVita is an event management platform that allows users to create, participate in, and contribute to events. The platform is designed to enable easy access to social events and help expand outreach for donation-based activities. The goal of the project is to enhance the event management process with a user-friendly interface, making it more effective and interactive. ActiVita also features real-time notifications between participants and event organizers, increasing user interaction.

## Distinctiveness and Complexity
ActiVita stands out from previous projects in several key areas. The main features that differentiate this project are:

### Notification System
Users receive real-time notifications when they participate in events, notifying the event organizer. Notifications can be marked as unread and revisited later, providing an interactive experience that enriches user engagement. This functionality requires a more complex structure compared to traditional simple data processing projects.

### Map Integration
With the integration of Leaflet.js, the map system allows event locations to be displayed on the map. It also includes functionality to edit event coordinates (latitude and longitude), enabling geographical tracking of events.

### Donation Targeting
Events can set donation goals, and users can contribute to help meet these goals. This feature adds a social benefit aspect to the application, expanding its purpose beyond just event management.

ActiVita combines these components to create a more advanced infrastructure than previous projects. It offers a more complex structure in terms of web development and user experience by including user notifications, map displays, and donation targeting.

## Files and Directories
Summary of files created in the project:

### capstone - Project root directory.
- `manage.py` - Django's command-line utility for administrative tasks.
- `requirements.txt` - Lists all Python packages required for the application.

### app - Main application directory.
  - `__pycache__` - Directory containing Python cache files generated by Django.
  - `migrations` - Django migration files for database schema management.

#### static/app - Contains all static content, including JavaScript and CSS files.
- `css/styles.css` - Contains all CSS styles for the project.
- `js/congratulate.js` - JavaScript file used for congratulatory messages upon successful actions.
- `js/delete_event.js` - Handles event deletion requests and page interactions.
- `js/delete_profile.js` - Manages profile deletion with necessary AJAX calls.
- `js/edit_event.js` - JavaScript for editing event details within the application.
- `js/edit_profile.js` - Allows users to edit their profile information.
- `js/search.js` - Script for managing the search functionality within the platform.
- `js/view_notifications.js` - JavaScript for viewing and marking notifications as read.

#### templates/app - Contains all HTML templates.
- `change_password.html` - Template for the Change Password page.
- `create_event.html` - Template for creating new events.
- `details.html` - Template for viewing detailed information about a specific event.
- `index.html` - Homepage template displaying all available events.
- `layout.html` - Base template that all other templates extend, including navigation and layout structure.
- `login.html` - Template for the login page.
- `make_donation.html` - Template for making donations towards event goals.
- `profile.html` - Template displaying user profile information.
- `register.html` - Template for user registration.

#### Other Files
- `__init__.py` - Indicates that the app directory is a Python package.
- `admin.py` - Registers models with the Django admin panel.
- `apps.py` - Defines app configuration for Django.
- `models.py` - Contains database models defining the structure of application data.
- `tests.py` - Tests for application functionalities.
- `urls.py` - Defines URL patterns and routing for the app.
- `views.py` - Contains view functions to process requests and return responses.

### capstone/capstone - Project settings directory.
  - `__init__.py` - Indicates that the capstone directory is a Python package.
  - `asgi.py` - ASGI config for asynchronous support.
  - `settings.py` - Main configuration file for the Django project, including app settings, middleware, and database configuration.
  - `urls.py` - Main URL configuration for the project.
  - `wsgi.py` - WSGI configuration for deploying the application.

### media - Directory for user-uploaded files.
- `img/` - Directory storing user-uploaded images for profiles, events, etc.

### staticfiles - Collected static files for deployment.
- `admin/` - Contains static files for the Django admin interface.

### Database
- `db.sqlite3` - SQLite database file used to store all application data.

## How to Run the Application

### Install Requirements
To install the necessary packages for the application, run the following command in the terminal from the project's root directory:

```bash
pip install -r requirements.txt

### Run Migrations
After installing requirements, apply the database migrations:

```bash
python manage.py makemigrations

```bash
python manage.py migrate

### Run the Server
```bash
python manage.py runserver

Your application should run at <http://127.0.0.1:8000/>

## Key Features

- **Event Creation and Management**: Users can create events with details like name, date, location, and target donation goal. Event creators can edit event details, delete events, and track participation levels.
  
- **Participation Tracking**: Users can easily join events, and their participation is reflected in both their profile and the event details page.

- **Notification System**: Notifications are sent to event organizers when a user participates, ensuring organizers stay informed. Notifications are stored in the database, can be marked as read, and revisited at any time, enhancing interaction between users.

- **Donation Goal Progress**: Users can contribute to event donation goals, which is updated in real time. This feature promotes social engagement by providing participants with a sense of accomplishment as they see goals being reached.

---

## Technical Implementation

### Models

- **Event**: This model stores event-specific information, such as title, description, date, location, and target donation goal. The model also tracks participants and donations.

- **Notification**: Used to store notification messages related to user actions like event participation, with fields for sender, recipient, and message content.

- **User**: Stores user-specific information, including profile image and event participations.

- **Category**: Stores several categories in order to categorize events such as education, youth and sports etc.

- **Participation**: Stores participation information for events and top participators.

- **Donation**: Stores donation information for events and top contributors.

### Views

- **Event Views**: Handles event CRUD operations, participation requests, and donation submissions.

- **Notification Views**: Includes views for retrieving notifications, marking them as read.

### JavaScript Functionality

- **AJAX Calls**: AJAX is used extensively to make asynchronous requests for actions like participation, notifications, and profile updates. This approach enhances user experience by minimizing page reloads.

- **Leaflet.js Integration**: Event locations are displayed on an interactive map using Leaflet.js, allowing users to visualize event locations and edit coordinates easily.

---

## Security and Data Integrity

- **CSRF Protection**: All forms and AJAX requests are secured with CSRF tokens to prevent cross-site request forgery attacks.
  
- **Input Validation**: User inputs are validated both on the client and server sides to ensure data integrity and protect against malicious input.

- **Access Control**: Only authenticated users can create or participate in events, ensuring data privacy. Profile information and notifications are accessible only to the respective users.

---

## Challenges and Solutions

### 1. Real-Time Notifications
   Implementing notifications required creating a separate notification model, handling asynchronous requests, and ensuring notifications were efficiently delivered to the right users.

### 2. Dynamic Map Integration
   Integrating Leaflet.js to display and update event locations involved handling latitude and longitude data in a way that worked seamlessly with the rest of the Django views and models.

### 3. Managing Donations and Target Goals
   Tracking donations and updating the target goal in real time required careful handling of donation records and ensuring accurate updates. The solution involved creating a model to track individual donations and calculating progress within the view.

---

## Future Improvements

- **Message System**: Adding a private messaging feature between event participants and organizers for better communication.

- **Event Analytics**: Providing organizers with detailed analytics on participation, donation progress, and engagement rates.

- **Advanced Search and Filters**: Implementing more robust search features, allowing users to filter events by date, location, category, or target donation amount.

- **Allowing Payment Integration**: Maybe we can use Stripe API for payment interactions, transactions.

---

## Final Notes

ActiVita is designed to facilitate both social events and charitable activities, creating a meaningful experience for users looking to participate in or contribute to community-driven events. The project demonstrates a range of Django capabilities, from notifications and AJAX interactions to map integrations and database management.

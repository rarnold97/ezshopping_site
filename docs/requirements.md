# Requirements Documentation

## Requirements and Test Plan Spreadsheet

<iframe src="https://docs.google.com/spreadsheets/d/e/2PACX-1vT8bc9fksewfuY6E09LK6neVLH6VpLTB4bZrpln3hJnUGDsIDh7VuznFCDrc4Ux-w/pubhtml?widget=true&amp;headers=false" width="1200" height="900"></iframe>

## SRS Requirements Document

<iframe src="../pdf/SRS_CEG6110_Group2_EzShopping.pdf" width="1000" height="1000" type="application/pdf"></iframe>

## Initial Customer (Professor) Meeting:

!!! abstract "**(01/21/2025) - in-class**"

  **Questions**

  - [x] **Is it acceptable to only use one grocery store chain API (i.e., Kroger, Meijer, etc.)?**
    Yes, using a single API is acceptable. The Kroger API is preferred.

  - [x] **How should we do the login page and store credentials? Where do we host this service? Is Docker acceptable?**
    You can implement the login system in a way that is easiest for the team. Hosting on localhost is sufficient for now.

  - [x] **Is it acceptable to upload images on a website widget as opposed to using a phone or tablet for an MVP?**
    Yes, a simple button click to upload images on the website widget is acceptable.

  - [x] **What are your expectations for our site? What type of information are you looking for?**
    The system should perform object detection for multiple grocery items. For example, if there are items like bananas, apples, bread, and ice cream on a table, the system should detect these items and generate a corresponding list.

  - [x] **We want to test our MVP with a minimum set of grocery items. Would a minimum set of 5–10 items be sufficient?**
    Yes, testing with a minimum set of 5–10 items is sufficient.

  - [x] **Are there any specific pages, widgets, or features you want on the frontend?**
    Including a QR code feature would be a great addition.

  - [x] **How should secrets and client data be managed? Any special requests?**
    A password-protected database for managing secrets and client data is acceptable for now.

  - [x] **Do you want us to use CI/CD?**
    No, CI/CD is not required for this project.

  - [x] **How do you expect the app to be delivered/distributed? Are Python installable artifacts sufficient?**
    Python installable artifacts are sufficient for delivering the application.

  - [x] **Are localhost and dummy user solutions acceptable for the MVP?**
    Yes, using localhost and dummy users is acceptable for the MVP phase.

  - [x] **Do we need to create a customer access token, or is using a shared token acceptable?**
    Using a shared token is acceptable.

  **Feature Wish-list**

  - [ ] fancy login page that connects to API via a URI
  - [ ] ability to upload images from phone or tablet
  - [ ] Support for multiple grocery-chain APIs instead of one

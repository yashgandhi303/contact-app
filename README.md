## Pastors Line - React developer test

### `IT RUNS ON NODE VERSION 14`
# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm install`
### `npm start`

Runs the app in the development mode.\
Open [http://localhost:30080](http://localhost:30080) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

## Test Desctiption

This test is intended to check you are using the best practices and you know how to use libraries we are using. This is a small task, but please think about it as a part of something bigger.

Please create a public repository on your Github or Bitbucket account and push the code there. Use branch /feature/react-dev-test and merge it to master via Pull Request.

### Task description
The main screen should have two buttons (Button A and Button B described below) centered vertically and horizontally with a margin between.

Clicking on Button A should open a Modal A. Clicking on Button B should open a Modal B.

Both modals should have three buttons:

- Modal Button A - labeled ‘All Contacts’, switching to Modal A
- Modal Button B - labeled ‘US Contacts’, switching to Modal B
- Modal Button C - labeled ‘Close’, closing modals
and a checkbox in a footer, LHS:
- Checkbox A - labeled ‘Only even’, when checked, only contacts with even ID (ex. 2, 4, 6...) should be displayed.

In Modal A should be displayed (from API) contacts from all countries.
In Modal B should be displayed (from API) contacts only from US.

Clicking on the contact items in modals should open a next modal (Modal C) with few contact details, no matter what.

Opening Modals A and B should change the URL of the page.

Opening Modal C should NOT change the URL.

Button A and Modal Button A should have a color: #46139f

Button B and Modal Button B should have a color: #ff7f50

Button C should have a white background and border #46139f (same as the background of Button A)

Modals A and B should have a search box to filter contacts (use API param). Contacts should be filtered while typing in a search input (with a small delay) and immediately on hitting the Enter key.

Lists of contacts should display only the first page (API param, page=1) after scrolling to bottom of modal load next page (infinity scroll).

### Part of our stack (npm)
- react (v16)
- axios
- bootstrap (v4)
- node-sass
- react-redux
- redux (v4)
- react-custom-scrollbars
- reselect

### Contacts API
GET https://api.dev.pastorsline.com/api/contacts.json
Authorization via header:
Authorization: Bearer token

CORS is allowing only pages at http://127.0.0.1:30080

Params:
- companyId - use 171
- query - to filter by names and number
- page - pagination
- countryId - to filter by country. The US has a 226 ID.
- add noGroupDuplicates = 1 

Example of result:
```
{
    "total": 10, // total amount of found contacts
    "contacts_ids": [ // this a list of IDs of found contacts
        745450,
        502931,
        (...)
    ],
    "contacts": {  // this is a data of found contacts
        "745450": {
            "id": 745450,
            "first_name": "Test",
            "last_name": "1",
            "email": null,
            "phone_number": "9000000001",
            "country_id": 226,
            (...)
        },
        "502931": {
            "id": 502931,
            "first_name": "Test",
            "last_name": "2",
            "email": "",
            "phone_number": "9000000002",
            "country_id": 226,
            (...)
        },
        (...)
    }
}
```
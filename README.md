# Spurwing API NodeJS Library

Lightweight NodeJS library for Spurwing's API.

Spurwing's API makes it easy to add robust scheduling and booking to your application. We power millions of appointment bookings for thousands of companies, from marketplaces to SaaS to healthcare. 

## Account
To use this API you need to obtain API credentials by signin up here: https://spurwing.io/

On your dashboard you will have the "API Info" page with your **API key** and **Provider ID**.

- **API Key:** This is your private API Key used for private and authorized operations.

- **Provider ID:** This is your public calendar identifier.

**Security Warning:** Never expose your **API Key** in front-end javascript code. All implementations that require your API Key should be handled by your back-end in a secure environment.

## Usage
Install the Spurwing module: `npm i spurwing`

Then you can use it as such:
```js
const Spurwing = require('spurwing')

const PID = 'your_provider_id';
const KEY = 'your_api_key';

let sp = new Spurwing();

let allApps = await sp.list_appointments(KEY, 1000, 0, PID)

```
## Documentation

The currently implemented API functions and features are:

- get_appointment_types
- get_days_available
- get_slots_available
- complete_booking
- list_appointments
- delete_appointment

For additional demos and use cases have a look under `tests.js`.

Spurwing's REST API Reference and Docs: https://docs.spurwing.io/

## Testing
To run our predefined unit tests use the `tests.js` script. You also need to rename the `config.sample.js` file to `config.js` and enter your credentials (provider id and api key). Afterwards you can run the `npm tests` command.

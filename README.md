# Funnel Leasing Coding Challenge

### Christian Cozma

---

## How to get started:

- #### Run `git clone https://github.com/CasuallyCaffeinated/Funnel-Leasing_Take-Home.git`
- #### cd into repository
- #### Run `npm install` to install the dependencies
- #### Run `npm run start:dev` to start the server
- #### Open up a browser and navigate to either:
  - #### `localhost:8081/api/satellite/stats`
  - #### `localhost:8081/api/satellite/health`
- #### For test cases, run the command:
  - #### `npm run test:dev`

---

## Technologies used:

- #### Node.js with Typescript
- #### Express.js with Typescript
- #### Mocha and Chai for testing

---

## Summary of the challenge:

#### Funnel has launched a satellite in order to tackle the lucrative lunar real estate market. To make sure the satellite doesn’t come crashing back down, we’re creating a web application to monitor its status. Your job is to write a health API for it.

#### Realtime information about the satellite is available from the `nestio.space/api/satellite/data` endpoint. The data is updated every ten seconds.

#### The data is returned in this format:

```
{
"altitude": 156.9098300562505,
"last_updated": "2022-03-04T21:13:00"
}
```

#### last_updated is an ISO 8601 representation of the last time the data was updated and altitude is the altitude of the satellite in kilometers.

---

# Objectives

#### The application should read the real-time altitude data from `nestio.space/api/satellite/data`, and tracks the health and stats of the satellite over the last 5 minutes:

### /stats end-point:

- #### Returns the minimum, maximum and average altitude for the last 5 minutes.
- #### Don’t worry about persisting data beyond the life of the process -- if you don’t have 5 minutes of data when the end-point is requested, return the stats for what you do have.

### /health end-point:

- #### Whenever the 5 minute average altitude of the satellite goes below 160km for more than 1 minute, returns the message “WARNING: RAPID ORBITAL DECAY IMMINENT”
- #### Once the average altitude of the satellite returns to 160km or above, return the message “Sustained Low Earth Orbit Resumed” for 1 minute.
- #### Otherwise return the message “Altitude is A-OK”

---

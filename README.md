# The BAR challenge
## Technologies

Javascript will be the tech use here.

## Project
The goal of this project is to write a function that will find available times for users with different schedules.
```javascript
/**
 * Given a collection of schedules, find all the free times within an overall time range.
 *
 * @param {Array<Array<event>>} schedules A collection of user schedules to compare. An event has the following type : { title: string, start: ISO string, end: ISO string }
 * @param {Date} start The starting time to seek for free periods.
 * @param {Date} end The time to stop seeking for free periods.
 * @param {number} minimumFreeDuration The minimum amount of time a period needs to be (in minutes)
 * @return {Array<timeRange>} A collection of free periods across all user schedules.
 */
function findCommonFreeTimes (schedules, start, end, minimumFreeDuration) { }
```

## Example
```javascript
const userScheduleA = [
  {
    "title": "Meeting A",
    "start": "2017-02-21T09:00:00-05:00",
    "end": "2017-02-21T10:00:00-05:00"
  },
  {
    "title": "Meeting B",
    "start": "2017-02-21T11:00:00-05:00",
    "end": "2017-02-21T12:00:00-05:00"
  },
  {
    "title": "Meeting C",
    "start": "2017-02-21T12:00:00-05:00",
    "end": "2017-02-21T12:45:00-05:00"
  },
  {
    "title": "Meeting D",
    "start": "2017-02-21T14:00:00-05:00",
    "end": "2017-02-21T15:30:00-05:00"
  }
];

const userScheduleB = [
  {
    "title": "Meeting A",
    "start": "2017-02-21T09:00:00-05:00",
    "end": "2017-02-21T09:45:00-05:00"
  },
  {
    "title": "Meeting B",
    "start": "2017-02-21T10:00:00-05:00",
    "end": "2017-02-21T10:15:00-05:00"
  },
  {
    "title": "Meeting C",
    "start": "2017-02-21T11:00:00-05:00",
    "end": "2017-02-21T13:45:00-05:00"
  },
  {
    "title": "Meeting D",
    "start": "2017-02-21T14:00:00-05:00",
    "end": "2017-02-21T14:30:00-05:00"
  }
];

const start = new Date('2017-02-21T08:00:00-05:00');
const end = new Date('2017-02-21T18:00:00-05:00');

const freeSlots = findCommonFreeTimes(
  [userScheduleA, userScheduleB],
  start,
  end,
  30
);

/**
 * Outputs
 * [
 *   {
 *     "start": "2017-02-21T08:00:00-05:00",
 *     "end": "2017-02-21T09:00:00-05:00"
 *   },
 *   {
 *     "start": "2017-02-21T10:15:00-05:00",
 *     "end": "2017-02-21T11:00:00-05:00"
 *   },
 *   {
 *     "start": "2017-02-21T15:30:00-05:00",
 *     "end": "2017-02-21T18:00:00-05:00"
 *   }
 * ]
 */
```

## A quick ending word

We expect you to be able to explain any code you write.

We do allow library that would help you manipulate dates (momentjs, dayjs, etc).

Calendars API
=============

Index Endpoint
--------------
Use this endpoint to view the calendars a nation maintains.

GET /api/v1/sites/:site_slug/pages/calendars

### Parameters
* page - page number
* per_page - number of results to show per page

### Example

```
GET https://foobar.nationbuilder.com/api/v1/foobar/pages/calendars
```

```json
{
  "page": 1,
  "total_pages": 1,
  "per_page": 10,
  "total": 2,
  "results": [
    {
      "id": 1,
      "slug": "calendar",
      "status": "published",
      "site_slug": "foobar",
      "name": "Calendar",
      "headline": "Upcoming events",
      "title": "Foobar Softwares events",
      "excerpt": null,
      "author_id": 9,
      "published_at": "2012-09-19T11:27:00-07:00",
      "external_id": null,
      "content": null,
      "event_name": "Event",
      "show_map": false,
      "order": "date",
      "user_submitted_events": {
        "start_date": null,
        "end_date": null,
        "default_start_time": null,
        "tag_list": null
      }
    },
    {
      "id": 4,
      "slug": "events",
      "status": "published",
      "site_slug": "foobar",
      "name": "Events",
      "headline": "Events",
      "title": "Events - Foobar Softwares",
      "excerpt": null,
      "author_id": null,
      "published_at": "2013-05-22T14:23:08-07:00",
      "external_id": null,
      "content": "Come enjoy our events! Free popcorn!",
      "event_name": "Shindig",
      "show_map": false,
      "order": "date",
      "user_submitted_events": {
        "start_date": "2013-05-23",
        "end_date": "2013-05-29",
        "default_start_time": null,
        "tag_list": "smart, thrifty"
      }
    }
  ]
}
```

Show Endpoint
-------------
Use this endpoint to get the details about one calendar a nation maintains.

GET /api/v1/sites/:site_slug/pages/calendars/:id

### Example

```json
GET https://foobar.nationbuilder.com/api/v1/sites/foobar/pages/calendars/4
```

Should get you a 200 response with body like:

```json
{
  "calendar": {
    "id": 4,
    "slug": "events",
    "status": "published",
    "site_slug": "foobar",
    "name": "Events",
    "headline": "Events",
    "title": "Events - Foobar Softwares",
    "excerpt": null,
    "author_id": null,
    "published_at": "2013-05-22T14:23:08-07:00",
    "external_id": null,
    "content": "Come enjoy our events! Free popcorn!",
    "event_name": "Shindig",
    "show_map": false,
    "order": "date",
    "user_submitted_events": {
      "start_date": "2013-05-23",
      "end_date": "2013-05-29",
      "default_start_time": null,
      "tag_list": "smart, thrifty"
    }
  }
}
```

Create Endpoint
---------------
Use this endpoint to make a calendar for the nation

POST /api/v1/sites/:site_slug/pages/calendars

### Attributes

### Example

```
POST https://foobar.nationbuilder.com/api/v1/sites/foobar/pages/calendars
```

```json
{
  "calendar": {
    "content": "Come enjoy our events!",
    "event_name": "Shindig",
    "show_map": false,
    "order": "date",
    "name": "Events",
    "status": "published",
    "user_submitted_events": {
      "start_date": "2013-05-23",
      "end_date": "2013-05-29",
      "tag_list": "smart, thrifty"
    }
  }
}
```

You should get a 200 response and a body like this:

```json
{
  "calendar": {
    "id": 4,
    "slug": "events",
    "status": "published",
    "site_slug": "foobar",
    "name": "Events",
    "headline": "Events",
    "title": "Events - Foobar Softwares",
    "excerpt": null,
    "author_id": null,
    "published_at": "2013-05-22T14:32:00-07:00",
    "external_id": null,
    "content": "Come enjoy our events! Free popcorn!",
    "event_name": "Shindig",
    "show_map": false,
    "order": "date",
    "user_submitted_events": {
      "start_date": "2013-05-23",
      "end_date": "2013-05-29",
      "default_start_time": null,
      "tag_list": "smart, thrifty"
    }
  }
}
```

Update Endpoint
---------------
Update an existing calendar to have the provided attributes.  Expect similar response as creation.  Partial updates are unsupported.

PUT /api/v1/sites/:site_slug/pages/calendars

Destroy Endpoint
----------------
Use this endpoint to remove a calendar from a nation.

DELETE /api/v1/sites/:site_slug/pages/calendars/:id

# Baskets

## Get All Events

```curl
curl "https://api.bookwhen.com/v1/basket"
  -H "Authorization: 8itj6o2stks9r5u7mhy742g3fb4g"
```

> The above command returns JSON structured like this:

```json
{
  "events": [
    {
      "id": "ev-sv06-20151204100000",
      "title": "Friday workshop",
      "start_at": "2015-12-04T10:00:00.000+00:00",
      "end_at": "2015-12-04T12:30:00.000+00:00",
      "all_day": false,
      "attendee_limit": 12,
      "attendee_count": 1,
      "ticket_ids": [
        "ti-sv06-20151204100000-tqn6",
        "ti-sv06-20151204100000-t3cm",
        "ti-sv06-20151204100000-tvqe"
      ]
    },
    {
      "id": "ev-sgw7-20151205130000",
      "title": "Saturday session",
      "start_at": "2015-12-05T13:00:00.000+00:00",
      "end_at": "2015-12-05T14:00:00.000+00:00",
      "all_day": false,
      "attendee_limit": 1,
      "attendee_count": 0,
      "ticket_ids": [
        "ti-sgw7-20151205130000-t2mm"
      ]
    }
  ],
  "meta": {
    "continues": true
  }
}
```

This endpoint retrieves all events.

### HTTP Request

`GET https://api.bookwhen.com/v1/events`

### Query Parameters

Parameter   | Description
----------- | -----------
calendar    | Restrict to events on a given calendar. The calendar ID can be found in the URL of your admin schedule page.
entry       | Restrict to a single entry type.
limit       | Max records to return. Default 20.
offset      | Offset starting point in list of items.
starts      | Dictionary: gt (>), gte (>=), lt (<), lte (<=)
tags        | Array of tag words to include. All if blank.
locations   | Array of location IDs to include. All if blank.
search_text | Free text search on title and description.


<aside class="success">
Remember — a happy event is an authenticated event!
</aside>

## Get a Specific Event

```curl
curl "https://api.bookwhen.com/v1/events/2"
  -H "Authorization: 8itj6o2stks9r5u7mhy742g3fb4g"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Isis",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific event.

<aside class="warning">
If you're not using an administrator API Key, note that some events will return 403 Forbidden if they are hidden for admins only.
</aside>

### HTTP Request

`GET http://example.com/events/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the event to retrieve

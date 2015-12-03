# Events

## Get All Events

```curl
curl https://api.bookwhen.com/v1/events?calendar=5tsd78lwht6g&limit=2&offset=0 \
  -u 8itj6o2stks9r5u7mhy742g3fb4g:
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
All parameters are optional.
</aside>

## Get a Specific Event

```curl
curl https://api.bookwhen.com/v1/events/ev-sv06-20151204100000 \
  -u 8itj6o2stks9r5u7mhy742g3fb4g:
```

> The above returns JSON structured like this:

```json
{
  "event": {
    "id": "ev-sv06-20151204100000",
    "title": "Friday workshop",
    "details": "Ongoing event for the gathering of all interested parties. Please register your interest. Numbers are limited.",
    "start_at": "2015-12-04T10:00:00.000+00:00",
    "end_at": "2015-12-04T12:30:00.000+00:00",
    "all_day": false,
    "attendee_limit": 12,
    "attendee_count": 1,
    "waiting_list": true,
    "reserved_for_waiting_list": false,
    "location_id": "sjm7pskr31t3",
    "attachment_ids": [
      "ezwuw3t788kf"
    ],
    "ticket_ids": [
      "ti-sv06-20151204100000-tqn6",
      "ti-sv06-20151204100000-t3cm",
      "ti-sv06-20151204100000-tvqe"
    ]
  },
  "locations": [
    {
      "id": "sjm7pskr31t3",
      "address_text": "Buckingham Palace\r\nLondon",
      "additional_info": "",
      "latitude": 51.5006426992722,
      "longitude": -0.140173386230458,
      "zoom": 15,
      "map_url": "https://bkwn.s3.amazonaws.com/maps/amplt327zhcc/sjm7pskr31t3/staticmap.png"
    }
  ],
  "attachments": [
    {
      "id": "ezwuw3t788kf",
      "title": "Example document",
      "file_name": "pdf-sample.pdf",
      "file_url": "https://amazonaws.com/attachments/...",
      "file_size_bytes": "7945",
      "file_size_text": "7.76 KB",
      "file_type": "pdf",
      "content_type": "application/pdf"
    }
  ],
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
    }
  ],
  "tickets": [
    {
      "id": "ti-sv06-20151204100000-tqn6",
      "title": "Standard booking",
      "details": "",
      "number_taken": 0,
      "basket_limit": 10,
      "group_ticket": false,
      "available_from": "2015-09-05T10:00:00.000+01:00",
      "available_to": "2015-12-03T10:00:00.000+00:00",
      "event_ids": [
        "ev-sv06-20151204100000"
      ],
      "cost": {
        "currency_code": "GBP",
        "net": 500,
        "tax": 100
      }
    },
    {
      "id": "ti-sv06-20151204100000-t3cm",
      "title": "New membership",
      "details": "Standard booking plus new membership (only £40 for the year)",
      "number_taken": 0,
      "basket_limit": 10,
      "group_ticket": false,
      "available_from": "2015-09-05T10:00:00.000+01:00",
      "available_to": "2015-12-03T10:00:00.000+00:00",
      "event_ids": [
        "ev-sv06-20151204100000"
      ],
      "cost": {
        "currency_code": "GBP",
        "net": 4500,
        "tax": 900
      }
    },
    {
      "id": "ti-sv06-20151204100000-tvqe",
      "title": "Member's booking",
      "details": "This incurs no charge but your membership card must be presented on entry.",
      "number_taken": 1,
      "basket_limit": 10,
      "group_ticket": false,
      "available_from": "2015-09-05T10:00:00.000+01:00",
      "available_to": "2015-12-03T10:00:00.000+00:00",
      "event_ids": [
        "ev-sv06-20151204100000"
      ]
    }
  ]
}
```

This endpoint retrieves a specific event.

### HTTP Request

`GET http://example.com/events/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the event to retrieve

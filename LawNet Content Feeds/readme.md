# LawNet Content Feeds

Version: 0.1a
Status: For discussion with integration partners


## Description

Provide shortlist of LawNet content for display on external systems, such as
* Latest content on specific LawNet site sections
* [Future] User-specific content collections


## Proposed request format

` {{ api_base_url }} / feeds / {{ api_version }} / {{ feed_type }} ? {{ feed_sort_and_filters }} & {{ pagination }} & {{ user_token }}`

* Method: POST
* Header parameters
    * authorisation_headers (contact LawNet team)
* Query parameters
    * feed_type
        * enum:
            - lawnet-asia
            - academy-library
            - ...
    * [Future] feed_sort_and_filters
    * [Future] user_token, used to retrieve personalised feeds
    * [Future] pagination
* Request body
    * [Future] more complex feed queries


## Sample response

```json
{

    "data": {
        "feeds": [
            {
                "channel": {
                    "title": "LawNet Asia",
                    "items": [
                        {
                            "title": "Indonesia’s Personal Data Protection Law Finally Enacted",
                            "uri": "Link to article",
                            "description": {
                                "value": "Excerpt of article"
                            },
                            "pubDate": "2022-07-08T20:34:03.0000000+08:00",
                            "jurisdictions": [
                                {
                                    "value": "Indonesia",
                                    "abbrev": "ID"
                                }
                            ],
                            "thumbnails": [
                                {
                                    "uri": "Link to image",
                                    "resolution": "1x",
                                    "width": 120,
                                    "height": 75,
                                    "caption": "Caption for thumbnail"
                                },
                                {
                                    "uri": "Link to image",
                                    "resolution": "2x",
                                    "width": 240,
                                    "height": 151,
                                    "caption": "Caption for thumbnail"
                                }
                            ],
                            "siteSections": [
                                "Global News",
                                "LawNet Asian Insights",
                                "News Summaries"
                            ]
                        }
                }
            }
        ]
    },
    "status": {
        "code": 200,
        "message": "Success."
    }
}
```



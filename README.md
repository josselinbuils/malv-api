# MALV-API
REST API that allows to exchange data with MyAnimeList.

## Anime
Provide details on an anime that are not available in the animelist.

#### URL

  `/anime/:id`

#### Method

  `GET`

#### URL params

   - **id** *integer*

#### Response

  JSON object containing the following fields:
  - **genres** *array of strings*
  - **popularity** *integer*
  - **rank** *integer*
  - **rating** *string*
  - **score** *float*
  - **studios** *array of strings*
  - **synopsis** *string*

#### Example

  `/anime/1`

```json
{
  "genres": [
    "Action",
    "Adventure",
    "Comedy",
    "Drama",
    "Sci-Fi",
    "Space"
  ],
  "popularity": 29,
  "rank": 23,
  "rating": "R - 17+ (violence &amp; profanity)",
  "score": 8.83,
  "studios": [
    "Sunrise"
  ],
  "synopsis": "In the year 2071, humanity has colonized several of the planets [...]"
}
```

## Animelist
Provide the animelist of a user.

#### URL

  `/animelist/:user`

#### Method

  `GET`

#### URL params

   - **user** *string*

#### Response

  Array of JSON objects containing the following fields:
  - **endDate** *timestamp*
  - **episodes** *integer*
  - **id** *integer*
  - **imageUrl** *string*
  - **myFinishDate** *timestamp*
  - **myScore** *integer*
  - **myStartDate** *timestamp*
  - **myStatus** *string*
  - **myWatchedEpisodes** *integer*
  - **startDate** *timestamp*
  - **status** *string*
  - **synonyms** *array of strings*
  - **title** *string*
  - **type** *string*

#### Example

  `/animelist/youbi325`

```json
[
  {
    "endDate": 924912000000,
    "episodes": 26,
    "id": 1,
    "imageUrl": "http://cdn.myanimelist.net/images/anime/4/19644.jpg",
    "myFinishDate": 1355529600000,
    "myScore": 10,
    "myStartDate": 1355097600000,
    "myStatus": "completed",
    "myWatchedEpisodes": 26,
    "startDate": 891561600000,
    "status": "Finished Airing",
    "synonyms": [],
    "title": "Cowboy Bebop",
    "type": "TV"
  },
  {
    "endDate": 907113600000,
    "episodes": 26,
    "id": 6,
    "imageUrl": "http://cdn.myanimelist.net/images/anime/7/20310.jpg",
    "myFinishDate": 1425340800000,
    "myScore": 9,
    "myStartDate": 1424131200000,
    "myStatus": "completed",
    "myWatchedEpisodes": 26,
    "startDate": 891388800000,
    "status": "Finished Airing",
    "synonyms": [],
    "title": "Trigun",
    "type": "TV"
  }
]
```

## Top
Provide a top anime list.

#### URL

  `/top/:name/:page`

#### Method

  `GET`

#### URL params

   - **name** *string*
     - all
     - airing
     - bypopularity
     - movie
     - ova
     - special
     - tv
     - upcoming
   - **page** *integer*

#### Response

  Array of JSON objects containing the following fields:
  - **imageUrl** *string*
  - **rank** *integer*
  - **score** *float*
  - **title** *string*

#### Example

  `/top/all/1`

```json
[
  {
    "imageUrl": "http://cdn.myanimelist.net/images/anime/5/47421.jpg",
    "rank": 1,
    "score": 9.25,
    "title": "Fullmetal Alchemist: Brotherhood"
  },
  {
    "imageUrl": "http://cdn.myanimelist.net/images/anime/5/73199.jpg",
    "rank": 2,
    "score": 9.17,
    "title": "Steins;Gate"
  }
]
```
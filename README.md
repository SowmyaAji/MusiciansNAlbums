# MusiciansNAlbums

## Overview:

A simple Django nested serializer example -- the relationship between musicians and their multiple albums, how to get all the albums of a musician in the same API endpoint, using nested serialization.

### Installation:

```
$ git clone repo
$ cd into repo
$ pipenv shell
$ pipenv install
$ cd nestdjango
$ python manage.py runserver
```

### Output:

API will run on the following endpoints --

http://127.0.0.1:8000/api/musicians/
http://127.0.0.1:8000/api/musicians/<pk>/
(put a number in place of <pk> as the id of the musician you want to retrieve, update or delete)
http://127.0.0.1:8000/api/albums/
http://127.0.0.1:8000/api/albums/<pk>/
(put a number in place of <pk> as the id of the album you want to retrieve, update or delete)

Some create/update examples:

for create musician at the http://127.0.0.1:8000/api/musicians/ endpoint  (use the Raw Data option on the Django API endpoint, as html will not work):

```
{
        "first_name": "joshua",
        "last_name": "bell",
        "instrument": "violin"
    }
```

for create album at the http://127.0.0.1:8000/api/albums/  endpoint :

```
{
        "artist": 1,
        "name": "random",
        "release_date": "2000-01-01",
        "num_stars": 2
    },
    {
        
        "artist": 1,
        "name": "another sky",
        "release_date": "1953-04-18",
        "num_stars": 5
    }
```

for update musician at http://127.0.0.1:8000/api/musicians/1/ endpoint:
```
{
    "first_name": "jimi",
    "last_name": "hendrix",
    "instrument": "Guitar",
    "album_musician": [
        {
            "name": "truth",
            "release_date": "1977-07-07",
            "num_stars": 5
        },
        
    ]
}
```

### Resources:

https://django.cowhite.com/blog/create-and-update-django-rest-framework-nested-serializers/

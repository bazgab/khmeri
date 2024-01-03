# Khmeri

Khmeri is a lightweight ORM for SQLite3 written in Python

## Installation

## Usage 

If you have ever used another ORM, such as Django's ORM, you will see that the syntax is almost the same, with Khmeri focusing on being lightweight and having simple syntax, for quick writing of models in small to medium-sized databases. 

Let's define a model as an example:

```python
import khmeri  

class object_one(khmeri.Model):  

    id = khmeri.Int(primary_key=True) # auto-increment
    task = khmeri.Str()
    interval = khmeri.Int()
```
now, we need to connect to a SQLite3 database:

```python
db = khmeri.Database('sample_database.db')
```


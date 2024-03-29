<div align="center">
<pre>
██╗  ██╗██╗  ██╗███╗   ███╗███████╗██████╗ ██╗
██║ ██╔╝██║  ██║████╗ ████║██╔════╝██╔══██╗██║
█████╔╝ ███████║██╔████╔██║█████╗  ██████╔╝██║
██╔═██╗ ██╔══██║██║╚██╔╝██║██╔══╝  ██╔══██╗██║
██║  ██╗██║  ██║██║ ╚═╝ ██║███████╗██║  ██║██║
╚═╝  ╚═╝╚═╝  ╚═╝╚═╝     ╚═╝╚══════╝╚═╝  ╚═╝╚═╝
                                              
</pre>
</div>

Khmeri is a lightweight ORM for SQLite3 written in Python

## Installation

The ORM can be installed through the Python Package Index with the commmand:
```python
python3 -m pip install khmeri
```

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
To perform basic CRUD operations, set the database as the backend of your object:

```python
object_one.objects.backend = db
```
## Instance Attributes

The following instance attributes can be applied to each module:

### Database
```python
- connected
- cursor
- connection
- connect()
- close()
- select(sql, *args, size=None)
- execute(sql, *args, autocommit=True)
- commit()
```
### Str
```python
- name
- type
- default
- primary_key
```
### Int
```python
- name
- type
- default
- primary_key
```
### Float
```python
- name
- type
- default
- primary_key 
```
### Model
```python
- __table__
- __mappings__
- __fields__
- __primary_key__
- objects
- exists()
- create()
- drop()
- save()
- update()
- delete()
- keys(), values(), items(), copy() and other methods imported from dict
```

## Contributing

This project is still very much in its infant stage and any help is appreciated. The next steps I would like to take would be implementing tests to evaluate how reliable the ORM is and then updating the models to handle more complex tasks than simple CRUD operations. You can open an issue or PR and I will make sure to see to it promptly.


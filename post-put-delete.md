# API Requests - POST, PUT, PATCH, and DELETE

**1. POST Request:**
A POST request is used to send data to a server for the purpose of creating a new resource. This data can be in various formats, such as JSON or form data. It's commonly used when you want to submit information to a server, like adding a new entry to a database.

**Example using [JSONPlaceholder API](https://jsonplaceholder.typicode.com/):**
Let's say you want to create a new user on the JSONPlaceholder API:
```python
import requests

url = 'https://jsonplaceholder.typicode.com/users'
new_user_data = {
    "name": "John Doe",
    "username": "johndoe",
    "email": "johndoe@example.com"
}

response = requests.post(url, json=new_user_data)
print(response.status_code)  # Should be 201 for "Created"
```

**2. PUT Request:**
A PUT request is used to update or replace an existing resource on the server. It requires sending the entire resource, even if only a few fields are being changed. If the resource doesn't exist, it might be created. PUT requests are idempotent, meaning making the same request multiple times has the same effect as making it once.

**Example using JSONPlaceholder API:**
Let's update an existing user's information:
```python
user_id = 1
update_data = {
    "name": "Updated John Doe",
    "email": "updated@example.com"
}

url = f'https://jsonplaceholder.typicode.com/users/{user_id}'
response = requests.put(url, json=update_data)
print(response.status_code)  # Should be 200 for "OK"
```

**3. PATCH Request:**
A PATCH request is similar to a PUT request, but it's used to update only specific fields of an existing resource, rather than sending the entire resource. It's more efficient when you only need to modify a few attributes.

**Example using JSONPlaceholder API:**
Let's partially update an existing user's information using a PATCH request:
```python
user_id = 1
partial_update = {
    "name": "Patched John Doe"
}

url = f'https://jsonplaceholder.typicode.com/users/{user_id}'
response = requests.patch(url, json=partial_update)
print(response.status_code)  # Should be 200 for "OK"
```

**4. DELETE Request:**
A DELETE request is used to request the removal of a resource from the server. It's commonly used when you want to delete a specific piece of data from a system.

**Example using JSONPlaceholder API:**
Let's delete a user from the JSONPlaceholder API:
```python
user_id = 1
url = f'https://jsonplaceholder.typicode.com/users/{user_id}'
response = requests.delete(url)
print(response.status_code)  # Should be 200 for "OK"
```

**Summary:**
- POST requests create new resources.
- PUT requests replace entire resources.
- PATCH requests partially update existing resources.
- DELETE requests remove resources.

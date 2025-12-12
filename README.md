# Multitenant Organization Service (Flask + MongoDB)


## Requirements
- Python 3.9+
- MongoDB running (local or remote)


## Install


1. clone the files into a folder
2. create a virtualenv:


```bash
python -m venv venv
source venv/bin/activate # windows: venv\Scripts\activate
pip install -r requirements.txt

Endpoints

POST /org/create - body: { organization_name, email, password }

GET /org/get?organization_name=... - query param

PUT /org/update - body: { organization_name, new_organization_name, email?, password? }

DELETE /org/delete - headers: Authorization: Bearer <token>, body: { organization_name }

POST /admin/login - body: { email, password }

Notes

Passwords are hashed with bcrypt.

JWT token includes admin_id and organization and is signed with JWT_SECRET.

Per-organization collections are created in the same master DB with the prefix org_.

whitehathacker8297_db_user
WIkivABmAbyd7szS
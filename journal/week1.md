# Week 1 — App Containerization

## Required Homework
### install flask module
```
cd backend-flask
export FRONTEND_URL="*"
export BACKEND_URL="*"
pip3 install -r requirements.txt
python3 -m flask run --host=0.0.0.0 --port=4567
cd ..
```
![flask-install](assets/flask-install.png)
- I make sure to unlock the port on the port tab
- I open the link for 4567 in your browser
- I append to the url to /api/activities/home
- I get back json
![flask-install](assets/port-open.png)

### build Container
```
docker build -t  backend-flask ./backend-flask
```

### run Container
Run
```
docker run --rm -p 4567:4567 -it backend-flask
FRONTEND_URL="*" BACKEND_URL="*" docker run --rm -p 4567:4567 -it backend-flask
export FRONTEND_URL="*"
export BACKEND_URL="*"
docker run --rm -p 4567:4567 -it -e FRONTEND_URL='*' -e BACKEND_URL='*' backend-flask
docker run --rm -p 4567:4567 -it  -e FRONTEND_URL -e BACKEND_URL backend-flask
unset FRONTEND_URL="*"
unset BACKEND_URL="*"
```
Run in background
```
docker container run --rm -p 4567:4567 -d backend-flask
```
Return the container id into an Env Vat
```
CONTAINER_ID=$(docker run --rm -p 4567:4567 -d backend-flask)
```



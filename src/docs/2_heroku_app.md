# Heroku Web App Deployment

[Heroku](https://www.heroku.com/) was utilized to deploy the web app.

### Input to Heroku App

This output file, **`model.pth`** is the input to the Heroku app.  

 
### Test running the web app
This [Docker image](https://github.com/npatta01/web-deep-learning-classifier/blob/master/Dockerfile) contains Python 3, Flask and fastai.
```
docker build -t app .
docker run -p 5000:5000 -it app 
```

## Heroku Setup
If you don't have a Heroku account, create one here: [www.heroku.com](https://www.heroku.com/).  Each line can be copied and submitted.  
```
wget -qO- https://cli-assets.heroku.com/install-ubuntu.sh | sh
heroku login
heroku container:login

APP_NAME="Covid-19 x-ray images classifier"
heroku create $APP_NAME

heroku container:push web --app ${APP_NAME}

heroku container:release web --app ${APP_NAME}
heroku open --app $APP_NAME
heroku logs --tail --app ${APP_NAME}
```

 
## Our Flask Web Application
- Our Flask web app is available here:  [**food-img-classifier.herokuapp.com**]()


# teststreamlit
A quick setup guide for deploying streamlit web app with heroku.


# What you need

## testapp.py
```
import streamlit as st
st.title('Test App')
st.subheader('Author: Jesse Redford')
```
## requirments.txt
```
streamlit==0.74.1
```
## Procfile
```
web: streamlit run --server.enableCORS false --server.port $PORT testapp.py
```
## setup.sh
```
mkdir -p ~/.streamlit/

echo "\
[general]\n\
email = \"jesse.k.redford@gmail.com\"\n\
" > ~/.streamlit/credentials.toml

echo "\
[server]\n\
headless = true\n\
enableCORS=false\n\
port = $PORT\n\
" > ~/.streamlit/config.toml
```
# Deploying your app with Heroku
Add files above to a git repo and create an Heroku Account / download CLI (open new terminal after download)
```
cmd
git clone https://github.com/Jesse-Redford/teststreamlit.git
cd teststreamlit
heroku login
heroku create <name of your app>
git add .
git commit -m "first commit"
heroku git:remote -a <name of your app>
git push heroku main
heroku ps:scale web=1
heroku open
```
  
  
  

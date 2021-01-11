# teststreamlit
A quick setup guide for deploying streamlit web app with heroku.


# What you need

1) testapp.py
    import streamlit as st
    st.title('Surface Measurment App')
    st.subheader('Author: Jesse Redford')

2) requirments.txt
    streamlit==0.74.1

3) Procfile
    web: streamlit run --server.enableCORS false --server.port $PORT testapp.py
    
4) setup.sh

# Deploy your app, (add files above to git repo)

1) cmd
2) git clone https://github.com/Jesse-Redford/teststreamlit.git
3) cd teststreamlit
4) heroku login
5) heroku create <name of your app>
6) git add .
7) git commit -m "first commit"
8) heroku git:remote -a <name of your app>
9) git push heroku main
10) heroku ps:scale web=1
11) heroku open
  
  
  

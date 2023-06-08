 <h1><u>Recommendation System</u></h1>
 


![1](https://user-images.githubusercontent.com/108725514/197403332-0cc3759a-76e3-42a5-b005-e7ef2d1ce544.png)

![2](https://user-images.githubusercontent.com/108725514/197403375-895bd35f-30a5-4330-a34c-18adcd91c9a3.png)



<h4>Developed A python App on Pycharm (app.py) which shows Recommended movies on the basis of movies selected.</h4>


There are 3 types of recommendation systems:

* Content Based : Recommendations are provided on the basis of Type of content acessed by user.This is done by creating tags.


* Collaborative Filtering Based : Recommendations on the basis of common interests shared by multiple users.


* Hybrid : Which used both content and collaborative Filtering


I have used Streamlit library to create this app (to run use: streamlit run app.py) <br>
And pickle library to make pickle files to be used to extract  data in app.py and data is being uploaded through RecommendationSystem.ipynb

1) In app.py file

```
similarity=pickle.load(open('similarity.pkl','rb')) 
```

2) In RecommendationSystem.ipynb

```
pickle.dump(similarity,open('similarity.pkl','wb')) 

```

<h3>API</h3>

I have Used Api from TMDB to extract poster of Movie through movie id from it


<h3>Deployment</h3>
I have used Heroku to deploy my project :  

Heroku requires : requirements.txt file, ProcFile, setup.sh and .gitignore (The code of each is written Down)
 
In the terminal of pycharm write following lines to deploy the project :

```
git init
heroku login
heroku create recomendatnsys
git add .
git commit -m "message"
git push heroku master

```

<h3>codes of each file </h3>

* requirements.txt

write this code in terminal to generate requirements.txt file
```
pip freeze > requirements.txt

```

* Procfile

```
web: sh setup.sh && streamlit run app.py

```

* setup.sh

```
mkdir -p ~/.streamlit/

echo "\
[general]\n\
email = \"your-email@domain.com\"\n\
" > ~/.streamlit/credentials.toml

echo "\
[server]\n\
headless = true\n\
enableCORS=false\n\
port = $PORT\n\
" > ~/.streamlit/config.toml

```

* .gitignore

```
venv
```






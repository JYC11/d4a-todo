# Django For APIs Chapter 4: Simple ToDo

We use React this chapter to make a fronend. I'm so happy that I don't have to write raw html and css with templating engines.

Not much new in this chapter compared to the last. 

Just created a simple route to get a list of Todos and a single Todo. These were implemented by through models.py, urls.py, views.py and serializers.py.

The one new thing was a CORS package that deserves some explanation. Django provides an out-of-the-box thing for CORS when using templating engines but for APIs it doesn't so we need to get a 3rd party package. I didn't go deep into it in D4B so I'll go in depth now.

## Explaining CORS
Cross Origin Resource Sharing = CORS

According MDN web docs CORS is a HTTP header based mechanism that allows a server to indicate any origins(domain, scheme or port) other than its own from which a browser should permit loading resources.

In much simpler terms(how I understand it):
* CORS allows requests from different origins to pass through and get/do stuff
* An origin is a url of some sort

This is important when making APIs because the client has it's own url and the server has it's own as well.

React has a default url of localhost:3000 while Django has a default of localhost:8000.

When CORS is not avaialable, only requests from localhost:8000 will be able to interact with the Django server.

But if localhost:3000 is CORS whitelisted, it can access localhost:8000 routes from itself.

I think this is what it means.

## React
I'm gonna learn React when I'm more comfortable with Django because I don't like writing HTML/CSS but I like writing JS(in comparison).

The book uses class based components but apparently function based components are more the norm these days.

## Folder Structure
Now that there is a separate frontend, folder structure is done differently.

Before in D4B the Django project had different apps for different purposes/featues and a templates folder that held all the HTML templates. This is one variation of a possible folder structure. The template folder could be in each individual Django App.

But in this case with React and Django, the Django project is purely for making APIs(in the backend folder) and the React App takes care of the frontend stuff(in the frontend folder). I've seen previous tutorials that initiated React files in a Django project directly. It worked but it seemed kinda messy and hard to understand so I prefer this method of organising the folders and files.
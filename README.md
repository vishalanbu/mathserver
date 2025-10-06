# Ex.05 Design a Website for Server Side Processing
# Date:06-10-2025
# AIM:
To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side.

# FORMULA:
P = I2R
P --> Power (in watts)
 I --> Intensity
 R --> Resistance

# DESIGN STEPS:
## Step 1:
Clone the repository from GitHub.

## Step 2:
Create Django Admin project.

## Step 3:
Create a New App under the Django Admin project.

## Step 4:
Create python programs for views and urls to perform server side processing.

## Step 5:
Create a HTML file to implement form based input and output.

## Step 6:
Publish the website in the given URL.

# PROGRAM :<html>
    <head>
        <title>POWER</title>
    </head>
    <body>
        <center>
        <div style="border: 5px solid black; background-color:grey ;" class="math">
            <h2 style="color: black;"><b><u>POWER (I<sup>2</sup>R)</u></b></h2>
            <br>
            <form method = "post">
                {% csrf_token %}
                <label>Intensity(I) : </label>
                <input type="text" name="intensity" style="border: 3px solid black;" required>
                <br><br>
                <label>Resistance(R) : </label>
                <input type="text" name="resistance" style="border: 3px solid black;" required>
                <br><br>
                <button type="submit" style="border: 3px solid black;background-color: crimson;"><i>Calculate</i></button>
                <br><br>
            </form>
           {% if P %}
                <h3 style="color: white;"><u><b>Result</b></u></h3>
                <p style="background-color: white;border: 3px solid black;border-radius: 6px;padding:3px 6px; display: inline-block;">Power : {{P}}</p>
            {% endif %}
        </div>
        </center>
    </body>
 </html>
rom django.contrib import admin
from django.urls import path
from app import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.pow),
]

from django.shortcuts import render
def pow(request):
    P = None
    I = None
    R = None
    if request.method == 'POST':
         
        I = int(request.POST.get('intensity',0))
        R = int(request.POST.get('resistance',0))
        P = (I**2)*R
    return render(request, 'app/maths.html' ,{"P":P})

from django.contrib import admin
from django.urls import path
from app import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.pow, name='pow')
]



# SERVER SIDE PROCESSING:
<img width="915" height="269" alt="exp5" src="https://github.com/user-attachments/assets/08b78f44-ef07-4e92-9ce6-7c5ac3115e42" />

# HOMEPAGE:
![Image 2025-10-06 at 11 07 37_0a2e11b7](https://github.com/user-attachments/assets/020707d5-0d9b-4043-825e-d376a00a1d45)

# RESULT:
The program for performing server side processing is completed successfully.

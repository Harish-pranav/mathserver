# Ex.05 Design a Website for Server Side Processing
# Date:27.11.2025
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

# PROGRAM :
```
# views.py

from django.shortcuts import render

def calculate_volume(request):
  result = None

  if request.method == 'POST':

      try:

          length = float(request.POST.get('length', 0))
          width = float(request.POST.get('width', 0))
          height = float(request.POST.get('height', 0))

          result = length * width * height
      except ValueError:

          result = "Invalid input. Please enter valid numbers."

  return render(request, 'cuboid_volume/index.html', {'result': result}) 

   # urls.py

from django.urls import path
from . import views

urlpatterns = [

    path('', views.calculate_volume, name='calculate_volume'),

]

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Cuboid Volume Calculator</title>

<style>
body {
    font-family: Arial, sans-serif;
    background-color: #1a1a1a;
    color: #f4f4f4;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

.container {
    width: 380px;
    padding: 30px;
    background: linear-gradient(145deg, #2a2a2a, #1e1e1e);
    border-radius: 16px;
    box-shadow: 0 15px 30px rgba(0,0,0,0.6);
    text-align: center;
}

/* 🔵 Title Blue */
h1 {
    color: #1e90ff;
    margin-bottom: 20px;
}

/* Inputs */
input {
    width: 100%;
    padding: 12px;
    margin-bottom: 15px;
    border-radius: 8px;
    border: none;
    background-color: #333;
    color: white;
    font-size: 16px;
}

input:focus {
    outline: none;
    box-shadow: 0 0 6px #1e90ff;
    background-color: #3a3a3a;
}

/* 🔵 Button Blue */
button {
    width: 100%;
    padding: 12px;
    font-size: 18px;
    background-color: #1e90ff;
    color: white;
    border: none;
    border-radius: 8px;
    cursor: pointer;
}

button:hover {
    background-color: #187bcd;
    box-shadow: 0 5px 12px rgba(30,144,255,0.4);
}

/* 🔴 Result Red */
.result {
    margin-top: 20px;
    font-size: 20px;
    color: red;
}
</style>
</head>

<body>

<div class="container">
    <h1>Cuboid Volume Calculator</h1>

    <form method="post">
        {% csrf_token %}
        <input type="number" name="length" placeholder="Enter length (cm)" required>
        <input type="number" name="width" placeholder="Enter width (cm)" required>
        <input type="number" name="height" placeholder="Enter height (cm)" required>
        <button type="submit">Calculate Volume</button>
    </form>

    {% if result != None %}
    <div class="result">
        <strong>Volume of Cuboid: {{ result }}</strong>
    </div>
    {% endif %}
</div>

</body>
</html>
```


# SERVER SIDE PROCESSING:
<img width="890" height="276" alt="server" src="https://github.com/user-attachments/assets/4c898492-66cf-4586-bc8d-718d60c7e29a" />

# HOMEPAGE:
<img width="1400" height="800" alt="cuboid_blue_red" src="https://github.com/user-attachments/assets/588f3e18-aed9-4e88-8781-ebc230e0f21b" />
<img width="1400" height="800" alt="cuboid_blue_red_filled" src="https://github.com/user-attachments/assets/9ae78b05-4eb5-4ac1-8a5d-46c5c0436b54" />


# RESULT:
The program for performing server side processing is completed successfully.

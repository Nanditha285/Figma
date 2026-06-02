# Ex09 Event Registration Web Application
## Date:

## AIM:
To design, develop and deploy a web application for event registration.

## DESIGN STEPS:

### Step 1:
Create a new frame.

### Step 2:
Select any one preset size of your choice.

### Step 3:
Select the shapes you need.

### Step 4:
Import images as needed.

### Step 5:
Create pages based on your need and link them.

### Step 6:

Validate the HTML and CSS code.

### Step 6:

Publish the website in the given URL.

## DESIGN TOOL:
Figma

## CODE:
views.py
```
from django.shortcuts import render

def register(request):

    if request.method == 'POST':

        name = request.POST.get('name')
        email = request.POST.get('email')
        phone = request.POST.get('phone')
        gender = request.POST.get('gender')
        department = request.POST.get('department')
        event = request.POST.get('event')
        date = request.POST.get('date')

        context = {
            'name':name,
            'email':email,
            'phone':phone,
            'gender':gender,
            'department':department,
            'event':event,
            'date':date
        }

        return render(
            request,
            'regisapp/success.html',
            context
        )

    return render(
        request,
        'regisapp/register.html'
    )

```
register.html
```
{% load static %}

<!DOCTYPE html>
<html>
<head>

<title>Event Registration</title>

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

<style>

body{
background:#eef2f7;
}

.card{
border-radius:20px;
}

.logo{
width:120px;
height:120px;
}

</style>

</head>

<body>

<div class="container mt-5">

<div class="row justify-content-center">

<div class="col-md-8">

<div class="card shadow p-4">

<div class="text-center">

<img src="{% static 'image/image1.png' %}" class="logo">

<h2 class="mt-3">
TECH FEST 2026
</h2>

<p class="text-muted">
Event Registration Form
</p>

</div>

<form method="post">

{% csrf_token %}

<div class="mb-3">

<label>Full Name</label>

<input type="text"
name="name"
class="form-control"
required>

</div>

<div class="mb-3">

<label>Email</label>

<input type="email"
name="email"
class="form-control"
required>

</div>

<div class="mb-3">

<label>Phone Number</label>

<input type="text"
name="phone"
class="form-control"
required>

</div>

<div class="mb-3">

<label>Gender</label>

<select name="gender"
class="form-control">

<option>Male</option>
<option>Female</option>
<option>Other</option>

</select>

</div>

<div class="mb-3">

<label>Department</label>

<input type="text"
name="department"
class="form-control">

</div>

<div class="mb-3">

<label>Event Name</label>

<input type="text"
name="event"
class="form-control">

</div>

<div class="mb-3">

<label>Event Date</label>

<input type="date"
name="date"
class="form-control">

</div>

<button class="btn btn-primary w-100">

Register

</button>

</form>

</div>

</div>

</div>

</div>

</body>
</html>
```
success.html
```
<!DOCTYPE html>
<html>
<head>

<title>Success</title>

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

</head>

<body>

<div class="container mt-5">

<div class="alert alert-success text-center">

<h2>
Registration Successful
</h2>

<hr>

<p>
Name : {{name}}
</p>

<p>
Email : {{email}}
</p>

<p>
Phone : {{phone}}
</p>

<p>
Gender : {{gender}}
</p>

<p>
Department : {{department}}
</p>

<p>
Event : {{event}}
</p>

<p>
Date : {{date}}
</p>

<h4>
Thank You For Registering!
</h4>

</div>

</div>

</body>
</html>
```

## OUTPUT:
![alt text](<Screenshot 2026-06-02 182034.png>)
![alt text](<Screenshot 2026-06-02 182048.png>)
![alt text](<Screenshot 2026-06-02 182102.png>)

## RESULT:
The program to design, develop and deploy a web application for event registration is completed successfully.

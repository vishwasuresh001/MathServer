# Ex.05 Design a Website for Server Side Processing
## Date:

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server slide.

 ## FORMULA:


## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
vijay.html

<html>
    <head>
        <title>BMI Calculator</title>
        <style>
        body{
          background-color: #F5F5DC;
          border-top: 10;
        }
        .m{
          background-color: rgba(255, 227, 185, 1);
          border: outset 6px;
          margin-top: 150px;
          margin-left: 500px;
          margin-right: 500px;
          
        }
            .main{
                font-size: 250%;
                text-align: center;
                background-color: rgba(255, 185, 244, 1);
                 margin-left: 50px;
                  margin-right: 50px;
                  padding: 50px;
                  
                  
            }
            .a{
                font-size: 150%;
                text-align: center;
                background-color: rgb(255, 185, 185);
                 margin-left: 50px;
                  margin-right: 50px;
                
                 
            }
            form{
              text-align: center;
              background-color: rgb(255, 185, 206);
               margin-left: 1.5cm;
             margin-right: 50px;
             padding: 50px;
            }
           
        </style>
    </head>
    <body>

       <div class="m">
        <div class="main">BMI Calculator</div>
        <div class="a">
         VISHWA S<br> 25012636</div><br>
        <form method="post">
          {% csrf_token %}
           
           
            <label>Weight(kg)=</label>
            <input type="text" name="weight" value="{{w}}"><br><br>
             <label>Height(cm)=</label>
            <input type="text" name="height" value="{{h}}"><br><br>
            <button type="submit">Calculate</button><br><br>
            <label>BMI=</label>
            <input type="text" name="bmi" value="{{bmi}}">
        </div>
        </form>
        
        
    </body>
</html>
urls.py

from django.contrib import admin
from django.urls import path
from mathapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('bmi/',views.calculate_bmi,name="bmi"),
    path('',views.calculate_bmi,name="bmicalculator")
]
views.py
from django.shortcuts import render
def calculate_bmi(request):
    context={}
    context['bmi']="0"
    context['w']="0"
    context['h']="0"
    if(request.method=='POST'):
       w= float(request.POST.get('weight','0'))
       h=float(request.POST.get('height','0'))
       print('request=',request)
       
       print('Weight=',w)
       print('Height=',h)
       bmi=w/((h/100)**2)
       context['bmi']=bmi
       context['w']=w
       context['h']=h
       print('BMI=',bmi)
    return render(request,'mathapp/vijay.html',context)


```

## SERVER SIDE PROCESSING:


![alt text](<Screenshot (23).png>)

## HOMEPAGE:

  ![alt text](<Screenshot 2025-09-29 183859.png>)






## RESULT:
The program for performing server side processing is completed successfully.

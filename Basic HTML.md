## Very basic form
First this is a simple Hello world HTML page
```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.4.1.slim.min.js" integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js" integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6" crossorigin="anonymous"></script>
  </body>
</html>
```

******
Now consider, we have to ask user to enter *Name*. We can add the following inside the *body* tag : 
```html
<form action="/endpoint" method="post">
    <label for="firstName">First Name</label>
    <input type="text" name="firstName" id="firstName">

    <label for="lastName">Last Name</label>
    <input type="text" name="lastName" id="lastName">

    <input type="submit" value="Save">
</form>
```

This would result in the follwing html. \
![Image of a form]([./images/form.PNG](https://github.com/ninadpchaudhari/React-Tutorial/raw/master/images/form.PNG))


******
The user can fill in the information and click on "Save" when done. 

> now, What happens when this button is pressed?\
The browser sends the form data to the endpoint specified in the `action` parameter of the form.

There are times when this behaviour is not enough, we might have to perform some sanity check before sending the data to the backend. Hence we can intercept this action of the browser sending data to the server using Javascript.\
For Eg. I need to alert the user with firstName,lastName What can be done is, we can add the following script tag after we load jQuery.
```javascript
<script>

    $(document).ready(function () {

      $("#firstForm").on('submit', function (e) {
        e.preventDefault(); //prevent submit

        //Access Form info
        myFormObject = new FormData(document.getElementById("firstForm")); 
        alert("you enetered " + 
        myFormObject.get('firstName') + ", " + 
        myFormObject.get('lastName'));
      });

    });

  </script>
```
Now since we know how to intercept the default behaviour of the form, we can use it to modify the form object to suit our needs, THEN send the POST / GET request via JavaScript. 
<details>
<summary> References </summary>

[Firefox refernce on FormData Object](https://developer.mozilla.org/en-US/docs/Web/API/FormData)
[Using Jquery to send a AJAX query](https://stackoverflow.com/questions/21044798/how-to-use-formdata-for-ajax-file-upload)
</details>

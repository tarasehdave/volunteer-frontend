---
comments: True
layout: base
title: New Volunteer Event
description: volunteer
courses: {'compsci': {'week': 4}}
type: hacks
permalink: /createEvent
---
<style>

</style>
<!-- 
A simple HTML login form with a Login action when button is pressed.  

The form triggers the login_user function defined in the JavaScript below when the Login button is pressed.

<link rel="stylesheet" href="/lmc-frontend/LMC/JS/SCSS/lmcLogin.css">
-->
<div id="titleContainer">
    <h1 id="title">New Volunteer Event</h1>
</div>

<div class="background">

</div>

<div class="container">
    <form id="username" action="javascript:login_user()">
        <p>
        <label>
            Title:
            <input class="userInput" type="text" name="vtitle" id="vtitle" required>
        </label>
        </p>
        <p><label>
            Description:
            <input class="userInput" type="text" name="description" id="description" required>
        </label></p>
        <p ><label>
            Address:
            <input class="userInput" type="text" name="address" id="address" required>
        </label></p>
        <p><label>
			Zip Code:
			<input class="userInput" type="text" name="zipcode" id="zipcode" required>
		</label></p>
        <p><label>
            Date of Event:
            <input class="userInput" type="text" id="date" required>
        </label></p>

        <p>
            <button onclick="login_user()">Submit</button>
        </p>
    </form>
</div>


<!-- 
Below JavaScript code is designed to handle user authentication in a web application. It's written to work with a backend server that uses JWT (JSON Web Tokens) for authentication.

The script defines a function when the page loads. This function is triggered when the Login button in the HTML form above is pressed. 
 -->
<script type="module">
    // uri variable and options object are obtained from config.js
    import { uri, options } from '{{site.baseurl}}/assets/js/api/config.js';
    function login_user(){
        // Set Authenticate endpoint
        const url = uri + '/api/events/';

        // Set the body of the request to include login data from the DOM
        const body = {
            title: document.getElementById("vtitle").value,
            description: document.getElementById("description").value,
            address: document.getElementById("address").value,
            date: document.getElementById("date").value,
			zipcode: document.getElementById("zipcode").value,
            agegroup: "18"
        };
        
        // Change options according to Authentication requirements
        const authOptions = {
            ...options, // This will copy all properties from options
            method: 'POST', // Override the method property
            cache: 'no-cache', // Set the cache property
            body: JSON.stringify(body)
        };

        // Fetch JWT
        fetch(url, authOptions)
        .then(response => {
            // handle error response from Web API
            if (!response.ok) {
                const errorMsg = 'Login error: ' + response.status;
                console.log(errorMsg);
                return;
            }
            // Success!!!
            // Redirect to the database page
            window.location.href = "{{site.baseurl}}/AE_vadminevents.html";
        })
        // catch fetch errors (ie ACCESS to server blocked)
        .catch(err => {
            console.error(err);
        });
    }

    // Attach login_user to the window object, allowing access to form action
    window.login_user = login_user;
</script>
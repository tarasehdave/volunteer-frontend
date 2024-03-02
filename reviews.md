---
permalink: /review
layout: base
title: Reviews
---

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Review Page</title>
<link rel="stylesheet" href="style.css">

<title>Volunteer Service Cards design with HTML and CSS</title>
<meta charset="utf-8">
<meta name="viewpoint" content="width=device-width, initial-scale=1.0">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta2/css/all.min.css">

<link rel="stylesheet" href="style.css">
<div class="gallery">
<div class="content">
<img src="https://github.com/alaraipek/Issues/assets/115954616/b23553cc-80b8-4987-b21d-6bc89a2154cb">
<h3>San Diego Refugee Tutoring</h3>
<p>Tutor refugee and Thursdayys from 4pm to 6pm.</p>
<h6>4877 Orange Ave, San Diego, CA 92115</h6>
<button class="generate-button" onclick="generateReview()">Rate</button>
</div>
<div class="content">
<img src="https://github.com/alaraipek/Issues/assets/115954616/de6e7289-1bd7-4c7b-93bb-e35c49b7e1e6">
<h3>Youth Court</h3>
<p>Teens tak the roles of lawyers and judges and hear cases about fellow students and hear their infractures</p>
<h6>220 S Broadway, Escondido, CA 92025</h6>
<button class="generate-button" onclick="generateReview()">Rate</button>
</div>
<div class="content">
<img src="https://github.com/alaraipek/Issues/assets/115954616/0a83e5f2-4985-4352-9cee-fb6dab356101">
<h3>Balboa Natural History Museum</h3>
<p>Volunteers educate visitors in the museum about animals at small display stands.</p>
<h6>1788 El Padro, San Diego, CA 92101</h6>
<button class="generate-button" onclick="generateReview()">Rate</button>
</div>
<div class="content">
<img src="https://github.com/alaraipek/Issues/assets/115954616/9fdabec0-9518-492f-a03f-b514b269a468">
<h3>Step Up</h3>
<p>Mentoring program for girls</p>
<h6>510 South Hewitt Street #111 Los Angeles, CA 90013</h6>
<button class="generate-button" onclick="generateReview()">Rate</button>
</div>
<div class="content">
<img src="https://github.com/alaraipek/Issues/assets/115954616/5b57ea8e-5a50-490c-82e0-6817d50c8d54">
<h3>Children Rising</h3>
<p>Tutoring program for students.</p>
<h6>2633 Telegraph Avenue #412 Oakland, CA 94612</h6>
<button class="generate-button" onclick="generateReview()">Rate</button>
</div>
<div class="content">
<img src="https://github.com/alaraipek/Issues/assets/115954616/59713140-86ce-4939-9b3d-b522ca22fac2">
<h3>Seattle Animal Shelter</h3>
<p>Help animals get adopted to loving families</p>
<h6>2061 15th Ave W, Seattle, WA, 98119</h6>
<button class="generate-button" onclick="generateReview()">Rate</button>
</div>
<div class="content">
    <img src="https://github.com/alaraipek/Issues/assets/115954616/76f9ee67-edf0-4948-9f5f-ecfd885ebe80">
    <h3>God's Love We Deliver</h3>
    <p>Help cook and deliver meals to those in need</p>
    <h6>166 Avenue of the Americas New York, NY 10013</h6>
    <button class="generate-button" onclick="generateReview()">Rate</button>
</div>
<div class="content">
    <img src="https://github.com/alaraipek/Issues/assets/115954616/955befc5-fe2c-42a4-9b95-928e92f8b814">
    <h3>Horse Play Therapy Center</h3>
    <p>Advance development and healing for children with special needs</p>
    <h6>1925 State Road 207 Saint Augustine, FL 32086</h6>
    <button class="generate-button" onclick="generateReview()">Rate</button>
</div>
<div class="content">
    <img src="https://github.com/alaraipek/Issues/assets/115954616/44beccbb-a634-4a9d-ad84-da8e6ce91223">
    <h3>Community Servings Food Heals</h3>
    <p>Help deliver food to families experiencing critical or chronic illness and nutrition insecurity</p>
    <h6>179 Amory Street Jamaica Plain, MA 02130</h6>
    <button class="generate-button" onclick="generateReview()">Rate</button>
</div>
<div class="content">
    <img src="https://github.com/alaraipek/Issues/assets/115954616/a73321eb-045a-4bc0-a1e9-bb57145cf713">
    <h3>Emmaus</h3>
    <p>Help prevent human trafficking and exploitation.</p>
    <h6>954 W. Washington Blvd Chicago, IL 60607</h6>
    <button class="generate-button" onclick="generateReview()">Rate</button>
</div>

<script>
    function generateReview() {
        const imageContainer = document.getElementById('image-container');
        const errorMessage = document.getElementById('error-message');
        // Make an AJAX request to your Clash Royale API to fetch card data
        // Update the card image, name, and stats in the DOM with the fetched data
        // Replace the URL with the new endpoint for random quotes.
        const apiUrl = 'http://127.0.0.1:8965/api/reviews';
        fetch(apiUrl)
            .then(response => response.json())
            .then(data => {
                const cardNameFromData = data.name;
                const hi = 4;
                const hib = 4;
                document.getElementById('card-name').textContent = cardNameFromData;
                const imgURL = data.medium; // Assuming the API response has a "quote" property.
                const img = document.createElement('img');
                img.src = imgURL;
                document.getElementById('random-image').src = imgURL;
            })
            .catch(error => {
                errorMessage.textContent = 'Failed to fetch image. Please try again later.';
                console.error('Error:', error);
            });

    }
</script>
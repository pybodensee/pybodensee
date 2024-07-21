---
title: Contact Us
create_date:  2024-05-13::00:00
author:  Faisal Shahzad
slug:  contact
status: published
feature_image: contact.png
description: Contact Us
---
<!-- Contact form-->
<div class="text-left mb-5">
    <p class="lead fw-normal text-muted mb-0">We'd love to hear from you</p>
</div>

<form name="contact" method="POST" data-netlify="true">
    <!-- Name input-->
    <div class="form-floating mb-3">
        <input class="form-control" id="name" name="name" type="text" placeholder="Enter your name..."
            data-sb-validations="required" required/>
        <label for="name">Full name</label>
        <div class="invalid-feedback" data-sb-feedback="name:required">A name is required.
        </div>
    </div>
    <!-- Email address input-->
    <div class="form-floating mb-3">
        <input class="form-control" id="email" name="email" type="email" placeholder="name@example.com"
            data-sb-validations="required,email" required/>
        <label for="email">Email address</label>
        <div class="invalid-feedback" data-sb-feedback="email:required">An email is
            required.</div>
        <div class="invalid-feedback" data-sb-feedback="email:email">Email is not valid.
        </div>
    </div>
    <!-- Message input-->
    <div class="form-floating mb-3">
        <textarea class="form-control" id="message" name="message" type="text"
            placeholder="Enter your message here..." style="height: 10rem"
            data-sb-validations="required" required></textarea>
        <label for="message">Message</label>
        <div class="invalid-feedback" data-sb-feedback="message:required">A message is
            required.
        </div>
    </div>
    <!-- Submit success message-->
    <div class="d-none" id="submitSuccessMessage">
        <div class="text-center mb-3">
            <div class="fw-bolder">Thank You for Contacting us. We will get back to you soon!</div>
        </div>
    </div>
    <!-- Submit error message-->
    <div class="d-none" id="submitErrorMessage">
        <div class="text-center text-danger mb-3">Error sending message!. We did not recieve you message. Please try again.</div>
    </div>
    <!-- Submit Button-->
    <div class="d-grid"><button class="btn btn-primary btn-lg mb-5" id="submitButton"
            type="submit">Submit</button>
    </div>
</form>
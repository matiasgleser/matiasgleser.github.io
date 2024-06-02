---
title: About Me
type: about
toc: false
layout: wide

# css: ["/css/about.css"]
---

<style>
        .profile-section {
            display: flex;
            align-items: center;
            justify-content: center;
            flex-wrap: wrap;
            text-align: center; /* Center text for larger screens */
    }

    .profile-picture {
        width: 100%; /* Adjust width as needed */
        max-width: 450px; /* Ensures image does not exceed 300px */
        min-width: 150px; /* Minimum width for the image */
        margin: 10px; /* Adds some margin around the image */ 
        /* margin: 5%; */
    }

    .profile-text {
        flex: 1; /* Allows text to take up remaining space */
        text-align: left; /* Align text to the left for smaller screens */
    }

    @media (max-width: 768px) {
        .profile-section {
            text-align: left; /* Align text to the left for smaller screens */
            flex-direction: column; /* Stack elements vertically */
        }

        .profile-picture {
            width: 100%; /* Image takes full width on smaller screens */
            max-width: 100%; /* Ensures image does not exceed container width */
        }

        .profile-text {
            width: 100%; /* Text takes full width on smaller screens */
        }
    }
</style>

<div class="profile-section">
    <!-- <img src="/images/me.jpeg" alt="Me" class="profile-picture"/> -->
    <div class="profile-text">
        <!-- Your text goes here -->
        <p>Your text here next to the image. This text will wrap around the image on smaller screens.</p>
    </div>
    <img src="/images/me.jpeg" alt="Me" class="profile-picture"/>
</div>


<!-- <div class="profile-section"> -->
<!--     <img src="/images/me.jpeg" alt="Profile Picture" class="profile-picture"/> -->
<!--     <div class="profile-text"> -->
<!--         <!-- Your text goes here --> -->
<!--         <p>Your text here next to the image. This text will wrap around the image on smaller screens.</p> -->
<!--     </div> -->
<!-- </div> -->



Economist from Córdoba, Argentina.

This is the about page.

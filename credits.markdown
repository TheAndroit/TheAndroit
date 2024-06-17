---
layout: page
title: "Credits"
permalink: /credits/
---
<h1>Credits</h1>
<ul id="credits-list"></ul>

<script>
    fetch('/assets/credits.json')
    .then(response => response.json())
    .then(data => {
        const creditsList = document.getElementById('credits-list');
        data.credits.forEach(credit => {
            const li = document.createElement('li');
            li.textContent = credit;
            creditsList.appendChild(li);
        });
    });
</script>
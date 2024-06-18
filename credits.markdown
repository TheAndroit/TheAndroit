---
layout: default
title: "Credits"
permalink: /credits/
---
<div class="credits">
  <h1>Credits</h1>
  <ul id="credits-list"></ul>
</div>

<script>
    fetch('{{ site.baseurl }}/assets/credits.json')
    .then(response => response.json())
    .then(data => {
        const creditsList = document.getElementById('credits-list');
        data.forEach(credit => {
            const li = document.createElement('li');
            const itemLink = document.createElement('a');
            itemLink.href = credit.item_link;
            itemLink.textContent = credit.item_name;
            itemLink.target = "_blank";
            const ownerLink = document.createElement('a');
            ownerLink.href = credit.owner_link;
            ownerLink.textContent = credit.owner_name;
            ownerLink.target = "_blank";
            li.innerHTML = `${itemLink.outerHTML} - ${credit.item_type} by ${ownerLink.outerHTML}`;
            creditsList.appendChild(li);
        });
    });
</script>
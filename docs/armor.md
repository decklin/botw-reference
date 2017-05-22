---
title: "BotW: Armor Upgrades"
layout: resource
sortable_tables:
- armor
---

<link rel="stylesheet" href="/assets/armor.css">

This is a list of upgradable armor only. Hover over icons (or tap
anywhere on the table cell, on mobile devices) to see full item names.
For uncolored dragon icons, see below.

<table id="armor">
  <tr data-sort-method="none">
    <th class="corner"></th>
    <th>Bonus</th>
    <th class="cost">★</th>
    <th class="cost">★★</th>
    <th>Set Bonus</th>
    <th class="cost">★★★</th>
    <th class="cost">★★★★</th>
    <th>Max</th>
  </tr>
  {% for upgrade in site.data.armor_upgrades %}
  {% assign name = upgrade[0] %}
  {% assign info = upgrade[1] %}
  <tr>
    <td class="name">{{ name }}</td>
    <td class="bonus">{{ info.bonus }}</td>
    {% include cost.html upgrades=info.upgrades level=0 %}
    {% include cost.html upgrades=info.upgrades level=1 %}
    <td class="set-bonus">{{ info.setbonus }}</td>
    {% include cost.html upgrades=info.upgrades level=2 %}
    {% include cost.html upgrades=info.upgrades level=3 %}
    <td class="max-defense">{{ info.max }}</td>
  </tr>
  {% endfor %}
</table>

## Notes
Items above are listed above by the maximum (★★★★) defense, which
follows one of these upgrade schedules:

{:#defense-schedules}
| Base | ★ | ★★ | ★★★ | ★★★★
|-
| 5 | 8 | 14 | 22 | 32
| 4 | 7 | 12 | 18 | 28
| 3 | 5 | 8 | 12 | 20
| 3 | 5 | 8 | 12 | 18
| 2 | 4 | 6 | 9 | 16

Elsewhere on the web you might find most items listed by their base
defense, but this causes an ambiguity between the slightly-nerfed-at-max
Topaz Earrings and the rest of the 3 → 20 schedule.

Non-upgradeable armor generally has a defense value of 1 or 3.

### Dragon Upgrades

The Set of the Wild and Fierce Deity Set require a different dragon's
item depending on the piece:

| | Set of the Wild | Fierce Deity Set
|-
| Cap/Mask | Farosh | Dinraal
| Tunic/Armor | Naydra | Naydra
| Trousers/Boots | Dinraal | Farosh

### Other Bonuses

Set bonuses apply after the entire set is upgraded at least twice (★★),
with the exception that some non-upgradeable sets also have set bonuses:

  - Gerudo: Heat-Resistant (note: not "Heat Resistance". I have not
    empirically determined how many items of Heat Resistance this is
    equivalent to; if you have, please let me know!)
  - Dark: Night Speed Up (I assume this is the same as the Stealth set).

In addition to the normal piece bonus for the Zora Set, the armor
enables the Swim Upward ability and the helm enables Spin Attack.

<script>
document.querySelectorAll('td.cost').forEach(function(td) {
  td.addEventListener('touchstart', function() {
    td.querySelectorAll('i.ra').forEach(function(i) {
      i.classList.toggle('touched');
    });
  });
});
</script>

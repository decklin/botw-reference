---
title: "BotW: Arrow Prices"
layout: resource
sortable_tables:
- arrows
---

<p>Click on any heading to sort (reload to remove sorting). Hover
over any multiple-arrow price to do the math for the per-arrow
price.

<table id="arrows">
  <tr data-sort-method="none">
    <th class="corner"></th>
    <th colspan="3" class="heading">Regular</th>
    <th colspan="2" class="heading">Fire</th>
    <th colspan="2" class="heading">Ice</th>
    <th class="heading">Shock</th>
    <th colspan="2" class="heading">Bomb</th>
  </tr>
  <tr>
    <td class="shop">Kakariko</td>
    <td colspan="2">20/5</td>
    <td>5</td>
    <td>80/5</td>
    <td class="bad-price">20</td>
    <td colspan="2"></td>
    <td></td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td class="shop">Hateno</td>
    <td colspan="3">20/5</td>
    <td colspan="2"></td>
    <td colspan="2"></td>
    <td></td>
    <td>350/10</td>
    <td class="bad-price">50</td>
  </tr>
  <tr>
    <td class="shop">Zora</td>
    <td colspan="3">20/5</td>
    <td colspan="2"></td>
    <td>80/5</td>
    <td class="bad-price">20</td>
    <td></td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td class="shop">Rito</td>
    <td colspan="3">20/5</td>
    <td colspan="2"></td>
    <td colspan="2"></td>
    <td></td>
    <td colspan="2" class="bad-price">200/5</td>
  </tr>
  <tr>
    <td class="shop">Goron</td>
    <td colspan="3"></td>
    <td colspan="2" class="bad-price">20</td>
    <td colspan="2" class="bad-price">20</td>
    <td></td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td class="shop">Kara Kara</td>
    <td colspan="3">5</td>
    <td colspan="2" class="bad-price">20</td>
    <td colspan="2" class="bad-price">20</td>
    <td class="bad-price">20</td>
    <td colspan="2" class="bad-price">50</td>
  </tr>
  <tr>
    <td class="shop">Gerudo</td>
    <td colspan="3">20/5</td>
    <td colspan="2" class="good-price">140/10</td>
    <td colspan="2" class="good-price">140/10</td>
    <td class="good-price">140/10</td>
    <td colspan="2" class="good-price">600/20</td>
  </tr>
  <tr>
    <td class="shop">Tarrey</td>
    <td colspan="3" class="good-price">35/10</td>
    <td colspan="2" class="good-price">140/10</td>
    <td colspan="2" class="good-price">140/10</td>
    <td class="good-price">140/10</td>
    <td colspan="2">350/10</td>
  </tr>
  <tr>
    <td class="shop">Lurelin</td>
    <td colspan="3">20/5</td>
    <td colspan="2"></td>
    <td colspan="2"></td>
    <td class="good-price">140/10</td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td class="shop">Korok</td>
    <td colspan="3">20/5</td>
    <td colspan="2"></td>
    <td colspan="2"></td>
    <td>80/5</td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td class="shop">Beedle 1</td>
    <td colspan="2" class="bad-price">30/5</td>
    <td class="bad-price">6</td>
    <td colspan="2"></td>
    <td colspan="2"></td>
    <td></td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td class="shop">Beedle 2</td>
    <td colspan="2" class="bad-price">45/10</td>
    <td class="bad-price">6</td>
    <td colspan="2"></td>
    <td colspan="2"></td>
    <td></td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td class="shop">Botrick</td>
    <td colspan="2">20/5</td>
    <td>5</td>
    <td colspan="2" class="bad-price">20</td>
    <td colspan="2" class="bad-price">20</td>
    <td></td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td class="shop">Gartan</td>
    <td colspan="3">20/5</td>
    <td colspan="2"></td>
    <td colspan="2"></td>
    <td></td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td class="shop">Giro</td>
    <td colspan="3">20/5</td>
    <td colspan="2"></td>
    <td colspan="2"></td>
    <td></td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td class="shop">Jini</td>
    <td class="good-price">35/10</td>
    <td>20/5</td>
    <td>5</td>
    <td colspan="2" class="bad-price">20</td>
    <td colspan="2"></td>
    <td>80/5</td>
    <td colspan="2" class="bad-price">50</td>
  </tr>
</table>

<p>Traveling shops are found at or near:

<ul>
  <li>Beedle (arrow inventory 1): Dueling Peaks, Foothill,
  Lakeside, Outskirt, Riverside, Wetland, and Woodland stables</li>
  <li>Beedle (arrow inventory 2): Akkala (both East and South),
  Gerudo Canyon, Highland, Rito, Serenne, Snowfield, and Tabantha
  stables</li>
  <li>Botrick: on the road around Outskirt stable</li>
  <li>Gartan: on the road around Kara Kara bazaar</li>
  <li>Giro: forest west of Dueling Peaks</li>
  <li>Jini: Mounted Archery Camp (horse required, sells shock
  arrows when raining and bomb arrows otherwise)</li>
</ul>

<script>
  document.querySelectorAll('#arrow-prices td').forEach(function(td) {
    var m = td.innerText.match(/^(\d+)\/(\d+)$/)
    if (m) {
      perArrowPrice = parseInt(m[1], 10) / parseInt(m[2], 10);
      td.setAttribute('title', perArrowPrice);
      td.setAttribute('data-sort', perArrowPrice);
      td.innerHTML = m[1] + '<wbr>/<wbr>' + m[2];
    }
  });
</script>

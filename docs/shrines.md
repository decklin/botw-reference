---
title: "BotW: Shrines"
layout: resource
sortable_tables:
- shrines
---

This page will save which shrines you have checked off using
`localStorage` (please don't rely on this as your only system of record
yet, it's a temporary kludge until some more features are ready). Click
to reveal possible spoilers.

<input type="checkbox" id="highlight-combat-trials"> Highlight combat
trials <input type="checkbox" id="highlight-blessing-shrines"> Highlight blessing shrines

<table id="shrines">
  <tr data-sort-method="none">
    <th class="corner"></th>
    <th>Name</th>
    <th>Trial</th>
    <th>Region</th>
    <th>Quest</th>
  </tr>
  {% for shrine in site.data.shrines %}
  <tr>
    <td class="completed"><input type="checkbox" class="completed-check"
      data-shrine-name="{{ shrine.name }}"></td>
    <td class="shrine">{{ shrine.name }}</td>
    <td class="trial-name"><span class="spoiler">{{ shrine.trial }}</span></td>
    <td class="region">{{ shrine.region }}</td>
    <td class="quest">{% if shrine.quest %}
      <span class="spoiler">{{ shrine.quest }}</span><br>
      <span class="quest-location spoiler">{{ shrine.quest_location }}</span>
    {% else %}
      N/A
    {% endif %}
    </td>
  </tr>
  {% endfor %}
</table>

<script src="/assets/vendor/spoiler.min.js"></script>
<script>spoilerAlert('.spoiler');</script>

<script>
var tickyBoxes = document.querySelectorAll('.completed-check');
var completion = localStorage.shrineCompletion ? JSON.parse(localStorage.shrineCompletion) : {};

tickyBoxes.forEach(function(ticky) {
    ticky.checked = completion[ticky.dataset.shrineName];
    ticky.onchange = function() {
      completion[ticky.dataset.shrineName] = ticky.checked;
      localStorage.shrineCompletion = JSON.stringify(completion);
    };
});
</script>

<script>
function toggleHighlight(pattern, highlightClass) {
    return function(ev) {
        document.querySelectorAll('.trial-name').forEach(function(td) {
            var tr = td.parentElement;
            if (pattern.test(td.innerText)) {
                if (ev.target.checked) {
                    tr.classList.add(highlightClass);
                } else {
                    tr.classList.remove(highlightClass);
                }
            }
        });
    };
}

document.getElementById('highlight-combat-trials').
    addEventListener('change', toggleHighlight(/Test of Strength$/, 'highlight-combat'));
document.getElementById('highlight-blessing-shrines').
    addEventListener('change', toggleHighlight(/'s Blessing$/, 'highlight-blessing'));
</script>

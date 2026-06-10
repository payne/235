---
layout: base.njk
title: 235 NET Logs - Check-in History
---

# NET Logs

## Recent Check-ins

A record of our weekly NET activity. Thank you to everyone who checks in!

<div class="logs-controls">
  <input type="text" id="logFilter" class="log-filter" placeholder="Filter by callsign, date, or description...">
</div>

<table id="logsTable" class="sortable">
  <thead>
    <tr>
      <th data-sort="date">Date</th>
      <th data-sort="ncs">NCS</th>
      <th data-sort="count">Check-ins</th>
      <th data-sort="description">Description</th>
    </tr>
  </thead>
  <tbody>
    {% for log in checkedIn | reverse %}
    <tr>
      <td data-value="{{ log.date }}">{{ log.date }}</td>
      <td>{{ log.ncs }}</td>
      <td data-value="{{ log.checkins.length }}">{{ log.checkins | join(", ") }}</td>
      <td>{{ log.description }}</td>
    </tr>
    {% else %}
    <tr>
      <td colspan="4"><em>No logs yet. Check back after our next NET!</em></td>
    </tr>
    {% endfor %}
  </tbody>
</table>

<script>
(function() {
  const table = document.getElementById('logsTable');
  const tbody = table.querySelector('tbody');
  const headers = table.querySelectorAll('th[data-sort]');
  const filterInput = document.getElementById('logFilter');
  let sortDir = {};

  // Sorting
  headers.forEach(header => {
    header.addEventListener('click', () => {
      const sortKey = header.dataset.sort;
      const dir = sortDir[sortKey] === 'asc' ? 'desc' : 'asc';
      sortDir = { [sortKey]: dir };

      headers.forEach(h => h.classList.remove('sort-asc', 'sort-desc'));
      header.classList.add(dir === 'asc' ? 'sort-asc' : 'sort-desc');

      const rows = Array.from(tbody.querySelectorAll('tr'));
      rows.sort((a, b) => {
        const aCell = a.querySelector(`td:nth-child(${Array.from(headers).indexOf(header) + 1})`);
        const bCell = b.querySelector(`td:nth-child(${Array.from(headers).indexOf(header) + 1})`);
        let aVal = aCell.dataset.value || aCell.textContent.trim();
        let bVal = bCell.dataset.value || bCell.textContent.trim();

        if (sortKey === 'count') {
          aVal = parseInt(aVal) || 0;
          bVal = parseInt(bVal) || 0;
        }

        if (aVal < bVal) return dir === 'asc' ? -1 : 1;
        if (aVal > bVal) return dir === 'asc' ? 1 : -1;
        return 0;
      });

      rows.forEach(row => tbody.appendChild(row));
    });
  });

  // Filtering
  filterInput.addEventListener('input', () => {
    const filter = filterInput.value.toLowerCase();
    const rows = tbody.querySelectorAll('tr');
    rows.forEach(row => {
      const text = row.textContent.toLowerCase();
      row.style.display = text.includes(filter) ? '' : 'none';
    });
  });
})();
</script>

---

## Want to Be Listed?

Simply check in to the NET on Friday nights at 9 PM Central on the W0JJK repeater (145.235 MHz, PL 131.8).

All licensed amateur radio operators are welcome!

---

## Become a Net Control Station

Interested in helping run the NET? We're always looking for volunteers to serve as Net Control Stations. Contact one of the regular NCS operators during the NET to learn more.

**73 de 235 NET**

---
layout: base.njk
title: Flyer - 9 PM Friday Technical Ragchew NET
---

# Flyer

Download and share to help grow the NET community.

<div class="flyer-container">
  <div class="flyer">
    <div class="flyer-header">9 PM Friday NET</div>
    <div class="flyer-tagline">Technical Ragchew</div>
    <div class="flyer-details">
      <div class="flyer-item">
        <span class="flyer-label">When</span>
        <span class="flyer-value">Fridays @ 9 PM Central</span>
      </div>
      <div class="flyer-item">
        <span class="flyer-label">Where</span>
        <span class="flyer-value">145.235 MHz (-) PL 131.8</span>
      </div>
      <div class="flyer-item">
        <span class="flyer-label">What</span>
        <span class="flyer-value">Ragchew & Tech Talk</span>
      </div>
      <div class="flyer-item">
        <span class="flyer-label">Who</span>
        <span class="flyer-value">All Licensed HAMs Welcome!</span>
      </div>
    </div>
    <div class="flyer-repeater">W0JJK Repeater - Omaha, NE</div>
    <div class="flyer-motto">More Radio | More Fun | More People</div>
  </div>
  <div class="flyer-qr">
    <div id="flyer-qrcode"></div>
    <div class="flyer-qr-label">235.MoreRadio.club</div>
  </div>
</div>

<script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>
<script>
  new QRCode(document.getElementById('flyer-qrcode'), {
    text: 'https://235.MoreRadio.club',
    width: 150,
    height: 150,
    colorDark: '#00bcd4',
    colorLight: '#1a1a2e',
    correctLevel: QRCode.CorrectLevel.H
  });
</script>

## Print Instructions
1. Print this page or screenshot the flyer above
2. Post at your local ham radio club
3. Share with fellow amateur radio operators

**73 de 235 NET**

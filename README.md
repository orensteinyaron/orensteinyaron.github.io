<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    html, body {
      width: 100%;
      height: 100%;
      overflow: hidden;
      position: fixed;
      top: 0; left: 0;
      touch-action: none;
    }

    .airbnb-embed-frame {
      width: 100% !important;
      height: 100% !important;
      display: block !important;
    }

    /* Force the iframe Airbnb injects to fill 100% */
    .airbnb-embed-frame iframe {
      width: 100% !important;
      height: 100vh !important;
      border: none !important;
      display: block !important;
    }
  </style>
</head>
<body>
  <div class="airbnb-embed-frame" data-id="18026539" data-view="home" data-hide-price="true" style="width: 450px; height: 300px; margin: auto;">
    <a href="https://www.airbnb.com/rooms/18026539?check_in=2026-04-01&amp;check_out=2026-04-03&amp;guests=1&amp;adults=1&amp;s=66&amp;source=embed_widget">View On Airbnb</a>
    <a href="https://www.airbnb.com/rooms/18026539?check_in=2026-04-01&amp;check_out=2026-04-03&amp;guests=1&amp;adults=1&amp;s=66&amp;source=embed_widget" rel="nofollow">Home in Huntington Beach · ★4.98 · 1 bedroom · 1 bed · 1 private bath</a>
    <script async src="https://www.airbnb.com/embeddable/airbnb_jssdk"></script>
  </div>

  <script>
    // Airbnb's script loads async and sets inline styles on the iframe after render.
    // We poll until the iframe appears and then override its dimensions.
    function fixAirbnbIframe() {
      const iframe = document.querySelector('.airbnb-embed-frame iframe');
      if (iframe) {
        iframe.style.setProperty('width', '100%', 'important');
        iframe.style.setProperty('height', '100vh', 'important');
        iframe.removeAttribute('width');
        iframe.removeAttribute('height');
      } else {
        setTimeout(fixAirbnbIframe, 100);
      }
    }
    fixAirbnbIframe();
  </script>
</body>
</html>

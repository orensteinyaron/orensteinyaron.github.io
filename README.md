<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"/>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    html, body {
      width: 100%;
      height: 100%;
      overflow: hidden;
      position: fixed;
      top: 0; left: 0;
      right: 0; bottom: 0;
    }

    /* Wrapper that clips and locks everything */
    #embed-wrapper {
      position: fixed;
      top: 0; left: 0;
      width: 100vw;
      height: 100vh;
      overflow: hidden;
      pointer-events: none; /* block all touch/mouse on wrapper */
    }

    /* Re-enable pointer events only on the iframe so clicks work */
    #embed-wrapper iframe {
      pointer-events: auto;
    }

    .airbnb-embed-frame {
      width: 100% !important;
      height: 100% !important;
      display: block !important;
    }

    .airbnb-embed-frame iframe {
      width: 100% !important;
      height: 100vh !important;
      max-width: 100% !important;
      border: none !important;
      display: block !important;
      overflow: hidden !important;
    }
  </style>
</head>
<body>
  <div id="embed-wrapper">
    <div class="airbnb-embed-frame" data-id="18026539" data-view="home" data-hide-price="true" style="width: 450px; height: 300px; margin: auto;">
      <a href="https://www.airbnb.com/rooms/18026539?check_in=2026-04-01&amp;check_out=2026-04-03&amp;guests=1&amp;adults=1&amp;s=66&amp;source=embed_widget">View On Airbnb</a>
      <a href="https://www.airbnb.com/rooms/18026539?check_in=2026-04-01&amp;check_out=2026-04-03&amp;guests=1&amp;adults=1&amp;s=66&amp;source=embed_widget" rel="nofollow">Home in Huntington Beach · ★4.98 · 1 bedroom · 1 bed · 1 private bath</a>
      <script async src="https://www.airbnb.com/embeddable/airbnb_jssdk"></script>
    </div>
  </div>

  <script>
    // Block all scroll and touch movement on the document
    const blockScroll = (e) => e.preventDefault();
    document.addEventListener('touchmove', blockScroll, { passive: false });
    document.addEventListener('wheel', blockScroll, { passive: false });
    document.addEventListener('touchstart', blockScroll, { passive: false });

    // Poll for Airbnb's injected iframe and force its dimensions
    function fixAirbnbIframe() {
      const iframe = document.querySelector('.airbnb-embed-frame iframe');
      if (iframe) {
        iframe.style.setProperty('width', '100%', 'important');
        iframe.style.setProperty('height', '100vh', 'important');
        iframe.removeAttribute('width');
        iframe.removeAttribute('height');
        iframe.setAttribute('scrolling', 'no');
      } else {
        setTimeout(fixAirbnbIframe, 100);
      }
    }
    fixAirbnbIframe();
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover" />
  <meta name="theme-color" content="#01696f" />
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <meta name="apple-mobile-web-app-status-bar-style" content="default" />
  <meta name="apple-mobile-web-app-title" content="Nifty Trend" />
  <link rel="manifest" href="./manifest.webmanifest" />
  <link rel="apple-touch-icon" href="./assets/icon-192.png" />
  <title>Nifty Trend PWA</title>
  <style>
    :root {
      --bg: #f7f6f2;
      --card: #ffffff;
      --text: #1f1d19;
      --muted: #6c6a64;
      --pri: #01696f;
      --ok: #437a22;
      --bad: #a12c7b;
      --warn: #964219;
      --border: #ddd9d1;
      --shadow: 0 10px 28px rgba(0, 0, 0, 0.06);
    }
    [data-theme="dark"] {
      --bg: #171614;
      --card: #1c1b19;
      --text: #e8e5dd;
      --muted: #a5a29b;
      --pri: #57aab2;
      --ok: #7ac14b;
      --bad: #e26ab8;
      --warn: #d47a50;
      --border: #34322f;
      --shadow: 0 10px 28px rgba(0, 0, 0, 0.22);
    }
    * { box-sizing: border-box; }
    body {
      margin: 0;
      background: var(--bg);
      color: var(--text);
      font-family: system-ui, -apple-system, Segoe UI, Roboto, sans-serif;
    }
    .app {
      max-width: 560px;
      margin: 0 auto;
      padding: 16px 16px 48px;
    }
    .top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 12px;
      margin-bottom: 14px;
    }
    .brand {
      display: flex;
      gap: 12px;
      align-items: center;
    }
    .mark {
      width: 46px;
      height: 46px;
      border-radius: 15px;
      background: linear-gradient(145deg, var(--pri), #0c4e54);
      color: #fff;
      display: grid;
      place-items: center;
      font-weight: 900;
      box-shadow: var(--shadow);
      flex: 0 0 auto;
    }
    h1, h2, h3, p { margin: 0; }
    .subtitle {
      color: var(--muted);
      margin-top: 4px;
      font-size: 14px;
    }
    .card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 20px;
      padding: 16px;
      margin-bottom: 14px;
      box-shadow: var(--shadow);
    }
    .hero h2 { font-size: 20px; line-height: 1.35; }
    .hero p { color: var(--muted); margin-top: 8px; }
    .pill {
      display: inline-block;
      background: rgba(1, 105, 111, 0.10);
      color: var(--pri);
      padding: 6px 10px;
      border-radius: 999px;
      font-size: 13px;
      font-weight: 700;
      margin: 8px 6px 0 0;
    }
    .score {
      font-size: 44px;
      font-weight: 900;
      line-height: 1;
      margin-top: 8px;
      letter-spacing: -1px;
    }
    .up { color: var(--ok); }
    .down { color: var(--bad); }
    .neutral { color: var(--warn); }
    .bias {
      font-weight: 800;
      font-size: 18px;
      margin-top: 6px;
    }
    .bar {
      height: 10px;
      border-radius: 999px;
      background: rgba(0, 0, 0, 0.08);
      overflow: hidden;
      margin-top: 12px;
    }
    .bar span {
      display: block;
      width: 68%;
      height: 100%;
      background: linear-gradient(90deg, var(--bad), var(--warn), var(--ok));
    }
    .grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
      margin-top: 14px;
    }
    .metric {
      background: rgba(0, 0, 0, 0.03);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 12px;
    }
    .metric small {
      display: block;
      color: var(--muted);
      margin-bottom: 4px;
      font-size: 12px;
    }
    .row {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
      margin-top: 14px;
    }
    button {
      border: 0;
      border-radius: 14px;
      padding: 12px 14px;
      font-weight: 700;
      min-height: 44px;
      cursor: pointer;
    }
    .pri {
      background: var(--pri);
      color: #fff;
    }
    .sec {
      background: rgba(0, 0, 0, 0.05);
      color: var(--text);
      border: 1px solid var(--border);
    }
    .list {
      display: grid;
      gap: 10px;
      margin-top: 10px;
    }
    .item {
      background: rgba(0, 0, 0, 0.03);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 12px;
    }
    .item time {
      display: block;
      color: var(--muted);
      font-size: 12px;
      margin-bottom: 4px;
    }
    .note {
      background: rgba(1, 105, 111, 0.10);
      color: var(--pri);
      padding: 14px;
      border-radius: 16px;
      font-size: 14px;
      line-height: 1.5;
    }
    .footer {
      text-align: center;
      color: var(--muted);
      font-size: 12px;
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <main class="app">
    <div class="top">
      <div class="brand">
        <div class="mark">▲</div>
        <div>
          <h1>Nifty Trend</h1>
          <div class="subtitle">PWA test build</div>
        </div>
      </div>
      <button class="sec" id="themeBtn">◐</button>
    </div>

    <section class="card hero">
      <h2>Safari से open करके Home Screen पर add करें.</h2>
      <p>यह lightweight PWA build iPhone testing के लिए तैयार है.</p>
      <div>
        <span class="pill">Options</span>
        <span class="pill">USD/INR</span>
        <span class="pill">News</span>
        <span class="pill">Alerts</span>
      </div>
    </section>

    <section class="card">
      <h3>Trend board</h3>
      <div class="score up" id="score">+2.7</div>
      <div id="bias" class="bias up">Bullish bias</div>
      <div class="bar"><span id="bar"></span></div>

      <div class="grid">
        <div class="metric"><small>Option chain</small><strong>PCR 1.13</strong></div>
        <div class="metric"><small>USD/INR</small><strong>83.41</strong></div>
        <div class="metric"><small>News stress</small><strong>Medium</strong></div>
        <div class="metric"><small>Action</small><strong>Buy dips only</strong></div>
      </div>

      <div class="row">
        <button class="pri" id="simulateBtn">Simulate trend</button>
        <button class="sec" id="notifyBtn">Sample alert</button>
      </div>
    </section>

    <section class="card">
      <h3>Trigger timeline</h3>
      <div class="list">
        <div class="item"><time>09:18</time>Put support visible near ATM strikes.</div>
        <div class="item"><time>11:05</time>USD/INR steady, macro pressure limited.</div>
        <div class="item"><time>13:42</time>Support reclaimed, bias moved back bullish.</div>
      </div>
    </section>

    <section class="note">
      iPhone: Share → Add to Home Screen. This build is offline-ready and can be tested in Safari.
    </section>

    <div class="footer">Nifty Trend PWA · GitHub Pages ready</div>
  </main>

  <script>
    const root = document.documentElement;
    let dark = false;

    const states = [
      ['+2.7', 'Bullish bias', 'up', '68%'],
      ['-3.4', 'Bearish bias', 'down', '22%'],
      ['+0.6', 'Rangebound', 'neutral', '50%']
    ];
    let i = 0;

    document.getElementById('simulateBtn').addEventListener('click', () => {
      i = (i + 1) % states.length;
      const [score, bias, cls, width] = states[i];
      document.getElementById('score').textContent = score;
      document.getElementById('bias').textContent = bias;
      document.getElementById('score').className = 'score ' + cls;
      document.getElementById('bias').className = 'bias ' + cls;
      document.getElementById('bar').style.width = width;
    });

    document.getElementById('themeBtn').addEventListener('click', () => {
      dark = !dark;
      root.setAttribute('data-theme', dark ? 'dark' : 'light');
    });

    document.getElementById('notifyBtn').addEventListener('click', async () => {
      if (!('Notification' in window)) {
        alert('Notifications not supported on this browser.');
        return;
      }
      const perm = await Notification.requestPermission();
      if (perm === 'granted') {
        new Notification('Nifty Trend Alert', {
          body: 'Sample alert: bullish bias with supportive option chain.'
        });
      }
    });

    if ('serviceWorker' in navigator) {
      window.addEventListener('load', () => {
        navigator.serviceWorker.register('./service-worker.js').catch(() => {});
      });
    }
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover" />
  <title>MStock Trading Journal</title>
  <style>
    :root{
      --bg:#f7f6f2;
      --card:#ffffff;
      --text:#1f1d19;
      --muted:#6c6a64;
      --pri:#01696f;
      --pri2:#0c4e54;
      --border:#ddd9d1;
      --shadow:0 10px 28px rgba(0,0,0,.06);
      --good:#2f7d32;
      --bad:#b3261e;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:system-ui,-apple-system,Segoe UI,Roboto,sans-serif;
      background:var(--bg);
      color:var(--text);
    }
    .app{
      max-width:1200px;
      margin:0 auto;
      padding:16px;
    }
    .topbar{
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:12px;
      margin-bottom:16px;
      flex-wrap:wrap;
    }
    .brand h1{margin:0;font-size:22px}
    .brand p{margin:4px 0 0;color:var(--muted);font-size:14px}
    .chip{
      display:inline-block;
      padding:6px 10px;
      border-radius:999px;
      background:rgba(1,105,111,.1);
      color:var(--pri);
      font-size:13px;
      font-weight:700;
      margin-left:8px;
    }
    .grid-cards{
      display:grid;
      grid-template-columns:repeat(4,1fr);
      gap:12px;
      margin-bottom:16px;
    }
    .card{
      background:var(--card);
      border:1px solid var(--border);
      border-radius:18px;
      padding:16px;
      box-shadow:var(--shadow);
    }
    .card small{color:var(--muted);display:block;margin-bottom:6px}
    .card strong{font-size:26px}
    .good{color:var(--good)}
    .bad{color:var(--bad)}
    .layout{
      display:grid;
      grid-template-columns:1.15fr .85fr;
      gap:16px;
      align-items:start;
    }
    h2{
      margin:0 0 12px;
      font-size:18px;
    }
    .section{
      background:var(--card);
      border:1px solid var(--border);
      border-radius:20px;
      padding:16px;
      box-shadow:var(--shadow);
      margin-bottom:16px;
    }
    .form-grid{
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:12px;
    }
    .field{
      display:flex;
      flex-direction:column;
      gap:6px;
    }
    label{
      font-size:13px;
      color:var(--muted);
      font-weight:600;
    }
    input,select,textarea{
      width:100%;
      padding:12px 13px;
      border:1px solid var(--border);
      border-radius:14px;
      background:#fff;
      color:var(--text);
      outline:none;
      font:inherit;
    }
    textarea{min-height:108px;resize:vertical}
    .span-2{grid-column:span 2}
    .span-3{grid-column:span 3}
    .actions{
      display:flex;
      gap:10px;
      flex-wrap:wrap;
      margin-top:14px;
    }
    button{
      border:0;
      border-radius:14px;
      padding:12px 16px;
      min-height:44px;
      font-weight:700;
      cursor:pointer;
      font:inherit;
    }
    .pri{background:var(--pri);color:#fff}
    .sec{background:#f2f2f2;color:var(--text)}
    table{
      width:100%;
      border-collapse:collapse;
      overflow:hidden;
      border-radius:16px;
    }
    th,td{
      text-align:left;
      padding:12px 10px;
      border-bottom:1px solid var(--border);
      font-size:14px;
      vertical-align:top;
    }
    th{
      color:var(--muted);
      font-size:13px;
    }
    .table-wrap{overflow:auto}
    .muted{color:var(--muted)}
    .right-column .section:last-child{margin-bottom:0}
    .list{
      display:grid;
      gap:10px;
    }
    .mini{
      padding:12px;
      border:1px solid var(--border);
      border-radius:14px;
      background:#fff;
    }
    .mini time{
      display:block;
      font-size:12px;
      color:var(--muted);
      margin-bottom:4px;
    }
    @media (max-width: 980px){
      .layout{grid-template-columns:1fr}
      .grid-cards{grid-template-columns:repeat(2,1fr)}
      .form-grid{grid-template-columns:repeat(2,1fr)}
      .span-3{grid-column:span 2}
    }
    @media (max-width: 640px){
      .grid-cards{grid-template-columns:1fr}
      .form-grid{grid-template-columns:1fr}
      .span-2,.span-3{grid-column:span 1}
    }
  </style>
</head>
<body>
  <main class="app">
    <div class="topbar">
      <div class="brand">
        <h1>MStock Trading Journal</h1>
        <span class="chip">V1</span>
        <p>Manual trade entry + closing fund + reports starter</p>
      </div>
    </div>

    <section class="grid-cards">
      <div class="card"><small>Today P&L</small><strong class="good">₹12,450</strong></div>
      <div class="card"><small>Monthly P&L</small><strong class="good">₹1,04,320</strong></div>
      <div class="card"><small>Closing Fund</small><strong>₹3,48,210</strong></div>
      <div class="card"><small>Win Rate</small><strong>61%</strong></div>
    </section>

    <section class="layout">
      <div>
        <section class="section">
          <h2>Manual Trade Entry</h2>
          <form>
            <div class="form-grid">
              <div class="field">
                <label>Trade Date</label>
                <input type="date" />
              </div>
              <div class="field">
                <label>Entry Time</label>
                <input type="time" />
              </div>
              <div class="field">
                <label>Exit Time</label>
                <input type="time" />
              </div>

              <div class="field span-2">
                <label>Symbol / Instrument</label>
                <input type="text" placeholder="NIFTY / BANKNIFTY / STOCK" />
              </div>
              <div class="field">
                <label>Segment</label>
                <select>
                  <option>Intraday</option>
                  <option>Options</option>
                  <option>Futures</option>
                  <option>Delivery</option>
                </select>
              </div>

              <div class="field">
                <label>Direction</label>
                <select>
                  <option>Buy</option>
                  <option>Sell</option>
                </select>
              </div>
              <div class="field">
                <label>Option Type</label>
                <select>
                  <option>None</option>
                  <option>CE</option>
                  <option>PE</option>
                </select>
              </div>
              <div class="field">
                <label>Strike Price</label>
                <input type="number" placeholder="e.g. 23500" />
              </div>

              <div class="field">
                <label>Quantity / Lots</label>
                <input type="number" placeholder="1" />
              </div>
              <div class="field">
                <label>Entry Price</label>
                <input type="number" step="0.05" placeholder="e.g. 125.50" />
              </div>
              <div class="field">
                <label>Exit Price</label>
                <input type="number" step="0.05" placeholder="e.g. 131.25" />
              </div>

              <div class="field">
                <label>Stop Loss</label>
                <input type="number" step="0.05" />
              </div>
              <div class="field">
                <label>Target</label>
                <input type="number" step="0.05" />
              </div>
              <div class="field">
                <label>Setup Tag</label>
                <input type="text" placeholder="Breakout / Reversal / Trend" />
              </div>

              <div class="field">
                <label>Gross P&L</label>
                <input type="number" step="0.01" />
              </div>
              <div class="field">
                <label>Charges</label>
                <input type="number" step="0.01" />
              </div>
              <div class="field">
                <label>Net P&L</label>
                <input type="number" step="0.01" />
              </div>

              <div class="field">
                <label>Trade Status</label>
                <select>
                  <option>Closed</option>
                  <option>Open</option>
                </select>
              </div>
              <div class="field">
                <label>Emotion Tag</label>
                <select>
                  <option>Calm</option>
                  <option>Greedy</option>
                  <option>Fearful</option>
                  <option>Confident</option>
                </select>
              </div>
              <div class="field">
                <label>Broker Ref / Order ID</label>
                <input type="text" />
              </div>

              <div class="field span-3">
                <label>Notes</label>
                <textarea placeholder="Entry reason, exit reason, mistakes, observations..."></textarea>
              </div>
            </div>

            <div class="actions">
              <button class="pri" type="button">Save Trade</button>
              <button class="sec" type="button">Calculate P&L</button>
              <button class="sec" type="reset">Clear</button>
            </div>
          </form>
        </section>

        <section class="section">
          <h2>Trades Table</h2>
          <div class="table-wrap">
            <table>
              <thead>
                <tr>
                  <th>Date</th>
                  <th>Symbol</th>
                  <th>Type</th>
                  <th>Entry</th>
                  <th>Exit</th>
                  <th>Qty</th>
                  <th>Charges</th>
                  <th>Net P&L</th>
                  <th>Status</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td>21-Jun</td>
                  <td>NIFTY 23500 CE</td>
                  <td>Options</td>
                  <td>125.50</td>
                  <td>131.25</td>
                  <td>50</td>
                  <td>₹180</td>
                  <td class="good">₹7,470</td>
                  <td>Closed</td>
                </tr>
                <tr>
                  <td>21-Jun</td>
                  <td>BANKNIFTY</td>
                  <td>Intraday</td>
                  <td>48,120</td>
                  <td>48,050</td>
                  <td>1</td>
                  <td>₹145</td>
                  <td class="bad">-₹845</td>
                  <td>Closed</td>
                </tr>
              </tbody>
            </table>
          </div>
        </section>
      </div>

      <aside class="right-column">
        <section class="section">
          <h2>Overview</h2>
          <div class="list">
            <div class="mini"><time>Funds</time>Pay-in ₹2,00,000 · Pay-out ₹50,000 · Available ₹3,48,210</div>
            <div class="mini"><time>Risk</time>Max loss today ₹3,250 · Best trade NIFTY 23500 CE</div>
            <div class="mini"><time>Session</time>Morning: 4 trades · Afternoon: 2 trades</div>
          </div>
        </section>

        <section class="section">
          <h2>Monthly Summary</h2>
          <div class="list">
            <div class="mini"><time>Win / Loss</time>18 wins · 11 losses</div>
            <div class="mini"><time>Profit Factor</time>1.72</div>
            <div class="mini"><time>Average Hold</time>14m 22s</div>
          </div>
        </section>
      </aside>
    </section>
  </main>
</body>
</html>

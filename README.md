
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{--bg:#07101f;--bg2:#0b1628;--bg3:#0d1a2e;--bg4:#111e30;--b1:#162032;--b2:#1c2f44;--t1:#e8edf5;--t2:#8899b0;--t3:#5a6e84;--t4:#3a4f64;--g:#10b981;--g2:#0d9e6b;--gbg:#041910;--gbr:#0a3d1e;--r:#f05252;--rbg:#1a0808;--rbr:#3d1212;--am:#d4a017}
#app{font-family:-apple-system,'Inter',system-ui,sans-serif;background:var(--bg);color:var(--t1);min-height:100vh;display:flex;flex-direction:column;font-size:13px;line-height:1.5}
nav{background:var(--bg2);border-bottom:1px solid var(--b1);padding:0 24px;height:52px;display:flex;align-items:center;gap:2px;flex-shrink:0;position:sticky;top:0;z-index:100}
.logo{font-size:18px;font-weight:700;margin-right:16px;letter-spacing:-.3px;line-height:1;text-decoration:none}
.logo span:first-child{color:#f0f4ff}.logo span:last-child{color:var(--g)}
.nb{background:none;border:none;color:var(--t3);font-size:12.5px;font-weight:500;padding:5px 11px;border-radius:6px;cursor:pointer;white-space:nowrap;font-family:inherit;transition:all .12s}
.nb:hover{background:var(--bg4);color:var(--t2)}
.nb.on{background:#071f12;color:#34d399;font-weight:600}
.nav-r{margin-left:auto;display:flex;align-items:center;gap:8px;position:relative}
.srch-wrap{position:relative}
.srch-wrap svg{position:absolute;left:9px;top:50%;transform:translateY(-50%);pointer-events:none;color:var(--t4)}
.srch-wrap input{width:230px;height:33px;background:var(--bg4);border:1px solid var(--b2);border-radius:7px;padding:0 12px 0 31px;font-size:12px;color:var(--t1);font-family:inherit;outline:none;transition:border-color .15s,background .15s}
.srch-wrap input::placeholder{color:var(--t4)}
.srch-wrap input:focus{border-color:var(--g);background:var(--bg3)}
#srch-dd{display:none;position:absolute;top:37px;left:0;right:0;background:var(--bg2);border:1px solid var(--b2);border-radius:8px;overflow:hidden;z-index:200;box-shadow:0 8px 24px rgba(0,0,0,.4)}
#srch-dd .sr{display:flex;align-items:center;gap:8px;padding:8px 12px;cursor:pointer;transition:background .1s;border-bottom:1px solid var(--b1)}
#srch-dd .sr:last-child{border-bottom:none}
#srch-dd .sr:hover{background:var(--bg3)}
.sr-sym{font-size:12px;font-weight:700;color:var(--t1);width:50px;font-family:monospace}
.sr-name{font-size:11px;color:var(--t3);flex:1}
.sr-price{font-size:11px;font-weight:700;color:var(--t1);font-family:monospace}
.sr-chg{font-size:10px;font-weight:700;padding:1px 5px;border-radius:4px}
.ticker{background:#060d1a;border-bottom:1px solid var(--b1);padding:6px 24px;display:flex;gap:24px;overflow:hidden;flex-shrink:0;align-items:center}
.ti{display:flex;align-items:center;gap:6px;white-space:nowrap}
.ts{font-size:10.5px;font-weight:600;color:var(--t4);font-family:monospace}
.tv{font-size:10.5px;font-weight:600;font-family:monospace}
.up{color:var(--g)}.dn{color:var(--r)}
.pulse{width:6px;height:6px;border-radius:50%;background:var(--g);animation:pl 2s infinite;flex-shrink:0}
@keyframes pl{0%,100%{opacity:1}50%{opacity:.2}}
.pg{display:none;flex:1;padding:22px 24px 48px;overflow-y:auto}
.pg.on{display:block}
.pgt{font-size:20px;font-weight:700;color:#f0f4ff;margin-bottom:3px;letter-spacing:-.4px}
.pgs{font-size:12px;color:var(--t4);margin-bottom:20px}
.slbl{font-size:11px;font-weight:600;color:var(--t4);margin:22px 0 10px;letter-spacing:.01em}
.idx-row{display:flex;gap:10px;margin-bottom:20px;overflow-x:auto;padding-bottom:4px}
.ic{background:var(--bg2);border:1px solid var(--b1);border-radius:10px;padding:12px 15px;min-width:120px;flex-shrink:0;transition:border-color .15s;cursor:default}
.ic:hover{border-color:var(--b2)}
.is{font-size:10px;font-weight:700;color:var(--t4);letter-spacing:.05em}
.in{font-size:9.5px;color:var(--t4);margin-top:1px;opacity:.7}
.iv{font-size:16px;font-weight:700;color:var(--t1);margin:5px 0 3px;font-family:monospace;letter-spacing:-.5px}
.ig{font-size:11px;font-weight:600}
.g3{display:grid;grid-template-columns:1fr 1fr 290px;gap:13px}
.card{background:var(--bg2);border:1px solid var(--b1);border-radius:11px;overflow:hidden}
.ch{padding:11px 15px;border-bottom:1px solid var(--b1);font-size:12px;font-weight:600;color:var(--t2);display:flex;align-items:center;justify-content:space-between}
.ch em{color:var(--t4);font-style:normal;font-weight:400;font-size:11px}
.ar{display:flex;align-items:center;padding:9px 15px;gap:9px;border-bottom:1px solid #0a1525;cursor:pointer;transition:background .1s}
.ar:hover{background:var(--bg3)}
.ar:last-child{border-bottom:none}
.asym{font-size:12.5px;font-weight:700;color:var(--t1);width:48px;font-family:monospace}
.aname{font-size:11.5px;color:var(--t3);flex:1;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.apr{font-size:12.5px;font-weight:700;color:var(--t1);font-family:monospace;width:66px;text-align:right}
.bge{font-size:10.5px;font-weight:700;padding:2px 7px;border-radius:5px;font-family:monospace;white-space:nowrap}
.bu{background:var(--gbg);color:var(--g);border:1px solid var(--gbr)}
.bd{background:var(--rbg);color:var(--r);border:1px solid var(--rbr)}
.cwp{background:#060d1a;border-bottom:1px solid var(--b1)}
.ctp{padding:15px 16px;display:flex;align-items:flex-start;gap:12px;flex-wrap:wrap}
.csym{font-size:13px;font-weight:500;color:var(--t3)}
.cprice{font-size:26px;font-weight:700;color:#f0f4ff;font-family:monospace;letter-spacing:-1px}
.cchg{font-size:13px;font-weight:600}
.pbs{display:flex;gap:3px;margin-left:auto;align-self:center}
.pb{background:none;border:none;color:var(--t4);font-size:11px;font-weight:600;padding:4px 9px;border-radius:6px;cursor:pointer;font-family:inherit;transition:all .12s}
.pb.on{background:var(--g);color:#000}
.pb:hover:not(.on){background:var(--bg4);color:var(--t2)}
.ni{padding:12px 15px;border-bottom:1px solid #0a1525;cursor:pointer;transition:background .1s}
.ni:hover{background:var(--bg3)}
.ni:last-child{border-bottom:none}
.ncat{font-size:9.5px;font-weight:700;padding:2px 7px;border-radius:4px;display:inline-block;margin-bottom:6px;letter-spacing:.03em}
.nc-mac{background:#0c1f3f;color:#5ba3e8;border:1px solid #152d52}
.nc-ear{background:var(--gbg);color:var(--g);border:1px solid var(--gbr)}
.nc-tec{background:#180a2e;color:#a78bfa;border:1px solid #2e1052}
.nc-com{background:#1f0f00;color:#f97316;border:1px solid #3d1f00}
.nc-bnd{background:#1a1200;color:var(--am);border:1px solid #352400}
.nc-geo{background:#0a1f1a;color:#2dd4bf;border:1px solid #0f3d2e}
.ntit{font-size:12.5px;font-weight:600;color:#c8d4e8;line-height:1.45}
.nmeta{font-size:10.5px;color:var(--t4);margin-top:5px}
.sg{display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px;padding:14px 15px}
.stat{background:#060d1a;border-radius:8px;padding:11px 13px;border:1px solid var(--b1)}
.sl{font-size:10px;color:var(--t4);margin-bottom:4px;letter-spacing:.03em}
.sv{font-size:13px;font-weight:700;color:var(--t1);font-family:monospace}
.aib{background:#030e08;border:1px solid var(--gbr);border-radius:10px;padding:13px;margin:0 15px 15px}
.ait{font-size:11px;font-weight:600;color:var(--g);margin-bottom:5px;display:flex;align-items:center;gap:6px}
.aibg{font-size:8.5px;background:var(--gbg);color:var(--g);padding:2px 7px;border-radius:4px;font-weight:700;border:1px solid var(--gbr)}
.aibody{font-size:11.5px;color:#2d7a4f;line-height:1.65}
.tw{overflow-x:auto}
table{width:100%;border-collapse:collapse}
th{padding:9px 13px;text-align:left;font-size:10.5px;font-weight:600;color:var(--t4);background:#080f1c;border-bottom:1px solid var(--b1);white-space:nowrap}
th.s{cursor:pointer;user-select:none}
th.s:hover{color:var(--t2)}
th.r,td.r{text-align:right}
td{padding:8px 13px;border-bottom:1px solid #0a1525;color:var(--t2);white-space:nowrap;font-size:12.5px}
tr:hover td{background:var(--bg3)}
tr:last-child td{border-bottom:none}
td.sc{font-weight:700;color:var(--t1);font-family:monospace;cursor:pointer}
td.sc:hover{color:var(--g)}
td.pc{color:var(--t1);font-weight:700;font-family:monospace}
td.mc{font-family:monospace}
.rb{width:64px;height:3px;background:var(--b2);border-radius:2px;display:inline-block;vertical-align:middle;overflow:hidden;margin:0 5px}
.rf{height:100%;border-radius:2px}
.fb{display:flex;gap:8px;margin-bottom:15px;flex-wrap:wrap;align-items:center}
.fg{display:flex;gap:2px;background:var(--bg2);border:1px solid var(--b1);border-radius:8px;padding:3px}
.fbt{background:none;border:none;color:var(--t3);font-size:12px;font-weight:500;padding:5px 12px;border-radius:6px;cursor:pointer;font-family:inherit;transition:all .12s}
.fbt.on{background:#071f12;color:#34d399;font-weight:600}
.fbt:hover:not(.on){color:var(--t2);background:var(--bg4)}
select.fsel{background:var(--bg2);border:1px solid var(--b1);color:var(--t3);font-size:12px;padding:5px 10px;border-radius:8px;cursor:pointer;outline:none;font-family:inherit}
select.fsel:focus{border-color:var(--g)}
.yg{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:16px}
.yc{background:var(--bg2);border:1px solid var(--b1);border-radius:10px;padding:13px;text-align:center}
.yl{font-size:10px;color:var(--t4);margin-bottom:4px;letter-spacing:.03em}
.yv{font-size:20px;font-weight:700;color:var(--t1);font-family:monospace;letter-spacing:-.5px}
.ycc{font-size:11px;font-weight:600;margin-top:4px}
.fug{display:grid;grid-template-columns:repeat(auto-fill,minmax(185px,1fr));gap:11px;margin-bottom:4px}
.fc{background:var(--bg2);border:1px solid var(--b1);border-radius:10px;padding:13px;transition:border-color .15s;cursor:pointer}
.fc:hover{border-color:var(--b2)}
.fsym{font-size:11px;font-weight:700;color:var(--t3);font-family:monospace;margin-bottom:2px}
.fname{font-size:11px;color:var(--t4);margin-bottom:9px}
.fprice{font-size:17px;font-weight:700;color:var(--t1);font-family:monospace;letter-spacing:-.3px}
.fex{font-size:10px;color:var(--t4);margin-top:8px;letter-spacing:.03em}
.wle{text-align:center;padding:58px 24px}
.wlei{font-size:30px;opacity:.3;display:block;margin-bottom:13px}
.wlr{display:flex;align-items:center;gap:12px;padding:12px 15px;background:var(--bg2);border:1px solid var(--b1);border-radius:10px;margin-bottom:8px;cursor:pointer;transition:border-color .15s}
.wlr:hover{border-color:var(--b2)}
.wli{width:42px;height:42px;background:var(--bg4);border:1px solid var(--b1);border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:10px;font-weight:700;color:var(--t3);font-family:monospace;flex-shrink:0}
.wld{background:none;border:1px solid transparent;color:var(--t4);cursor:pointer;font-size:12px;margin-left:auto;padding:4px 8px;border-radius:6px;transition:all .15s;font-family:inherit}
.wld:hover{background:var(--rbg);border-color:var(--rbr);color:var(--r)}
.btnp{background:var(--g);color:#000;border:none;border-radius:8px;padding:9px 20px;font-size:12px;font-weight:700;cursor:pointer;font-family:inherit;transition:background .15s}
.btnp:hover{background:var(--g2)}
.s-tech{background:#0c1f3f;color:#5ba3e8;border:1px solid #152d52;font-size:10.5px;padding:2px 7px;border-radius:4px}
.s-fin{background:#1a1200;color:var(--am);border:1px solid #352400;font-size:10.5px;padding:2px 7px;border-radius:4px}
.s-ene{background:#1f0f00;color:#f97316;border:1px solid #3d1f00;font-size:10.5px;padding:2px 7px;border-radius:4px}
.s-con{background:#180a2e;color:#a78bfa;border:1px solid #2e1052;font-size:10.5px;padding:2px 7px;border-radius:4px}
.s-cs{background:var(--gbg);color:#34d399;border:1px solid var(--gbr);font-size:10.5px;padding:2px 7px;border-radius:4px}
footer{background:#060d1a;border-top:1px solid var(--b1);padding:11px 24px;display:flex;align-items:center;justify-content:space-between;font-size:11px;color:var(--t4);flex-shrink:0}
.src-tag{font-size:9px;color:var(--t4);background:var(--bg4);padding:1px 5px;border-radius:3px;margin-left:4px;vertical-align:middle}
</style>

<div id="app">
<nav>
  <a class="logo" href="#" onclick="goPg('markets');return false"><span>Stock</span><span>X</span></a>
  <button class="nb on" onclick="goPg('markets',this)">Markets</button>
  <button class="nb" onclick="goPg('stocks',this)">Stocks</button>
  <button class="nb" onclick="goPg('bonds',this)">Bonds</button>
  <button class="nb" onclick="goPg('futures',this)">Futures</button>
  <button class="nb" onclick="goPg('news',this)">News</button>
  <button class="nb" onclick="goPg('watchlist',this)">Watchlist</button>
  <div class="nav-r">
    <div class="srch-wrap">
      <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
      <input type="text" id="srchi" placeholder="Search ticker or company..." oninput="srchFn(this.value)" onblur="setTimeout(()=>{document.getElementById('srch-dd').style.display='none'},200)" autocomplete="off">
      <div id="srch-dd"></div>
    </div>
  </div>
</nav>

<div class="ticker">
  <div class="ti"><span class="pulse"></span></div>
  <div class="ti"><span class="ts">S&P 500</span><span class="tv up">7,398.93 &nbsp;+0.84%</span></div>
  <div class="ti"><span class="ts">Nasdaq</span><span class="tv up">26,247.08 &nbsp;+1.71%</span></div>
  <div class="ti"><span class="ts">Dow Jones</span><span class="tv up">49,609.16 &nbsp;+0.02%</span></div>
  <div class="ti"><span class="ts">VIX</span><span class="tv up">17.19 &nbsp;+0.64%</span></div>
  <div class="ti"><span class="ts">WTI Oil</span><span class="tv up">94.75 &nbsp;+0.06%</span></div>
  <div class="ti"><span class="ts">Gold</span><span class="tv up">4,723.70 &nbsp;+0.27%</span></div>
  <div class="ti"><span class="ts">10Y Yield</span><span class="tv dn">4.32% &nbsp;−2bp</span></div>
  <div class="ti"><span class="ts">Bitcoin</span><span class="tv dn">79,864 &nbsp;−1.13%</span></div>
  <div class="ti"><span class="ts">Brent</span><span class="tv up">100.20 &nbsp;+0.14%</span></div>
</div>

<!-- MARKETS -->
<div id="pg-markets" class="pg on">
  <div class="pgt">Market Overview</div>
  <div class="pgs">U.S. Markets &nbsp;·&nbsp; NYSE &amp; NASDAQ &nbsp;·&nbsp; May 8, 2026 &nbsp;·&nbsp; <span id="mkt-time"></span></div>
  <div class="idx-row">
    <div class="ic"><div class="is">SPX</div><div class="in">S&amp;P 500</div><div class="iv">7,398.93</div><div class="ig up">▲ +61.82 &nbsp;+0.84%</div></div>
    <div class="ic"><div class="is">NDX</div><div class="in">Nasdaq Comp.</div><div class="iv">26,247.08</div><div class="ig up">▲ +440.88 &nbsp;+1.71%</div></div>
    <div class="ic"><div class="is">DJIA</div><div class="in">Dow Jones</div><div class="iv">49,609.16</div><div class="ig up">▲ +12.19 &nbsp;+0.02%</div></div>
    <div class="ic"><div class="is">RUT</div><div class="in">Russell 2000</div><div class="iv">2,861.21</div><div class="ig up">▲ +21.58 &nbsp;+0.76%</div></div>
    <div class="ic"><div class="is">VIX</div><div class="in">Volatility</div><div class="iv">17.19</div><div class="ig up">▲ +0.11 &nbsp;+0.64%</div></div>
    <div class="ic"><div class="is">TNX</div><div class="in">10Y Yield</div><div class="iv">4.32%</div><div class="ig dn">▼ −2.4 bp</div></div>
  </div>
  <div class="card" style="margin-bottom:14px">
    <div class="cwp">
      <div class="ctp">
        <div>
          <div class="csym">S&amp;P 500 Index &mdash; SPX &nbsp;<span class="src-tag">Yahoo Finance</span></div>
          <div style="display:flex;align-items:baseline;gap:10px;margin-top:4px">
            <span class="cprice">7,398.93</span>
            <span class="cchg up">▲ +61.82 &nbsp;(+0.84%)</span>
          </div>
        </div>
        <div class="pbs">
          <button class="pb on" onclick="setPd(this,'spx',0)">1D</button>
          <button class="pb" onclick="setPd(this,'spx',1)">1W</button>
          <button class="pb" onclick="setPd(this,'spx',2)">1M</button>
          <button class="pb" onclick="setPd(this,'spx',3)">3M</button>
          <button class="pb" onclick="setPd(this,'spx',4)">1Y</button>
        </div>
      </div>
      <canvas id="chart-spx" style="width:100%;height:145px;display:block"></canvas>
    </div>
  </div>
  <div class="g3">
    <div class="card">
      <div class="ch">Top Gainers <em>May 8, 2026</em></div>
      <div class="ar" onclick="openA('NVDA')"><span class="asym">NVDA</span><span class="aname">NVIDIA Corp.</span><span class="apr">$214.94</span><span class="bge bu">▲ 1.63%</span></div>
      <div class="ar" onclick="openA('TSLA')"><span class="asym">TSLA</span><span class="aname">Tesla Inc.</span><span class="apr">$409.05</span><span class="bge bu">▲ 4.01%</span></div>
      <div class="ar" onclick="openA('AVGO')"><span class="asym">AVGO</span><span class="aname">Broadcom Inc.</span><span class="apr">$418.82</span><span class="bge bu">▲ 4.20%</span></div>
      <div class="ar" onclick="openA('MSFT')"><span class="asym">MSFT</span><span class="aname">Microsoft</span><span class="apr">$415.38</span><span class="bge bu">▲ 1.33%</span></div>
      <div class="ar" onclick="openA('AAPL')"><span class="asym">AAPL</span><span class="aname">Apple Inc.</span><span class="apr">$293.23</span><span class="bge bu">▲ 1.80%</span></div>
    </div>
    <div class="card">
      <div class="ch">Notable Movers <em>Today</em></div>
      <div class="ar" onclick="openA('META')"><span class="asym">META</span><span class="aname">Meta Platforms</span><span class="apr">$615.70</span><span class="bge bu">▲ 0.57%</span></div>
      <div class="ar" onclick="openA('AMZN')"><span class="asym">AMZN</span><span class="aname">Amazon.com</span><span class="apr">$272.85</span><span class="bge bu">▲ 0.54%</span></div>
      <div class="ar" onclick="openA('GOOGL')"><span class="asym">GOOGL</span><span class="aname">Alphabet Inc.</span><span class="apr">$396.95</span><span class="bge bu">▲ 1.08%</span></div>
      <div class="ar" onclick="openA('XOM')"><span class="asym">XOM</span><span class="aname">Exxon Mobil</span><span class="apr">$147.69</span><span class="bge bu">▲ 2.43%</span></div>
      <div class="ar" onclick="openA('JPM')"><span class="asym">JPM</span><span class="aname">JPMorgan Chase</span><span class="apr">$293.12</span><span class="bge bd">▼ 0.82%</span></div>
    </div>
    <div class="card">
      <div class="ch">Live News <em>May 8, 2026</em></div>
      <div class="ni" onclick="goPg('news')"><span class="ncat nc-ear">Jobs Report</span><div class="ntit">U.S. Added 115K Jobs in April, Beating 65K Forecast — Markets Rally</div><div class="nmeta">Yahoo Finance · 2h ago</div></div>
      <div class="ni" onclick="goPg('news')"><span class="ncat nc-geo">Middle East</span><div class="ntit">Stocks Shrug Off Iran Tensions After Strong Jobs Data Lifts Sentiment</div><div class="nmeta">TheStreet · 3h ago</div></div>
      <div class="ni" onclick="goPg('news')"><span class="ncat nc-ear">Earnings</span><div class="ntit">Apple &amp; Intel Agree Preliminary Chip Deal — Intel Surges 13%</div><div class="nmeta">WSJ · 4h ago</div></div>
      <div class="ni" onclick="goPg('news')"><span class="ncat nc-com">Commodities</span><div class="ntit">Brent Crude Tops $101 on Strait of Hormuz Military Clashes</div><div class="nmeta">Reuters · 4h ago</div></div>
    </div>
  </div>
  <div class="slbl">All Stocks — Real Prices May 8, 2026</div>
  <div class="card"><div class="tw"><table>
    <thead><tr>
      <th class="s" onclick="stSort('sym')">Symbol</th><th>Company</th>
      <th class="s r" onclick="stSort('price')">Price</th>
      <th class="s r" onclick="stSort('change')">Change</th>
      <th class="r">% Chg</th><th class="r">Volume</th><th class="r">Mkt Cap</th><th>Sector</th>
    </tr></thead>
    <tbody id="hst"></tbody>
  </table></div></div>
</div>

<!-- STOCKS PAGE -->
<div id="pg-stocks" class="pg">
  <div class="pgt">Stocks</div>
  <div class="pgs">U.S. Equities &nbsp;·&nbsp; NYSE &amp; NASDAQ &nbsp;·&nbsp; Live prices May 8, 2026</div>
  <div class="fb">
    <div class="fg">
      <button class="fbt on" onclick="stFlt('all',this)">All</button>
      <button class="fbt" onclick="stFlt('gainers',this)">Gainers</button>
      <button class="fbt" onclick="stFlt('losers',this)">Losers</button>
    </div>
    <select class="fsel" onchange="stSec(this.value)">
      <option value="all">All Sectors</option>
      <option>Technology</option><option>Financials</option><option>Energy</option>
      <option>Consumer Discretionary</option><option>Consumer Staples</option>
    </select>
    <span style="font-size:11px;color:var(--t4);margin-left:auto" id="stcnt">12 results</span>
  </div>
  <div class="card"><div class="tw"><table>
    <thead><tr>
      <th class="s" onclick="stSort('sym')">Symbol</th><th>Company</th>
      <th class="s r" onclick="stSort('price')">Price</th>
      <th class="s r" onclick="stSort('change')">Change</th>
      <th class="r">% Chg</th><th class="r">Volume</th><th class="r">Mkt Cap</th>
      <th>52W Range</th><th>Sector</th>
    </tr></thead>
    <tbody id="stb"></tbody>
  </table></div></div>
  <div id="adet" style="display:none;margin-top:18px">
    <div class="card">
      <div class="cwp">
        <div class="ctp">
          <div>
            <div id="d-sym" class="csym"></div>
            <div style="display:flex;align-items:baseline;gap:10px;margin-top:4px">
              <span id="d-price" class="cprice"></span>
              <span id="d-chg" class="cchg"></span>
            </div>
            <div id="d-name" style="font-size:11.5px;color:var(--t4);margin-top:3px"></div>
          </div>
          <div class="pbs">
            <button class="pb on" onclick="setPd(this,'det',0)">1D</button>
            <button class="pb" onclick="setPd(this,'det',1)">1W</button>
            <button class="pb" onclick="setPd(this,'det',2)">1M</button>
            <button class="pb" onclick="setPd(this,'det',3)">3M</button>
            <button class="pb" onclick="setPd(this,'det',4)">1Y</button>
          </div>
        </div>
        <canvas id="chart-det" style="width:100%;height:170px;display:block"></canvas>
      </div>
      <div class="sg" id="d-stats"></div>
      <div class="aib">
        <div class="ait">
          <svg width="14" height="14" fill="none" stroke="#10b981" stroke-width="2" viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
          AI Summary <span class="aibg">Beta</span>
        </div>
        <div id="d-ai" class="aibody"></div>
      </div>
    </div>
  </div>
</div>

<!-- BONDS PAGE -->
<div id="pg-bonds" class="pg">
  <div class="pgt">Bonds &amp; Fixed Income</div>
  <div class="pgs">U.S. Treasury and corporate bond market &nbsp;·&nbsp; Yields as of May 8, 2026</div>
  <div class="yg">
    <div class="yc"><div class="yl">2Y Treasury Yield</div><div class="yv">4.35%</div><div class="ycc up">+1.2 bp</div></div>
    <div class="yc"><div class="yl">10Y Treasury Yield</div><div class="yv">4.32%</div><div class="ycc dn">−2.4 bp</div></div>
    <div class="yc"><div class="yl">30Y Treasury Yield</div><div class="yv">4.78%</div><div class="ycc dn">−1.0 bp</div></div>
  </div>
  <div class="card" style="margin-bottom:14px;padding:16px">
    <div style="font-size:12px;font-weight:600;color:var(--t3);margin-bottom:11px">Yield Curve &nbsp;<span class="src-tag">TradingEconomics / U.S. Treasury</span></div>
    <canvas id="chart-yc" style="width:100%;height:110px;display:block"></canvas>
    <div style="font-size:11.5px;color:var(--t4);margin-top:10px">Status: <span style="color:var(--am);font-weight:600">Near-flat (2Y≈10Y)</span> &nbsp;·&nbsp; Markets price Fed holding rates through year-end; ~20% chance of September cut</div>
  </div>
  <div class="card"><div class="tw"><table>
    <thead><tr>
      <th>Symbol</th><th>Name</th>
      <th class="r">Price</th><th class="r">Change</th><th class="r">% Chg</th>
      <th>52W Range</th><th>Exchange</th>
    </tr></thead>
    <tbody id="bdb"></tbody>
  </table></div></div>
</div>

<!-- FUTURES PAGE -->
<div id="pg-futures" class="pg">
  <div class="pgt">Futures &amp; Derivatives</div>
  <div class="pgs">Equity index, commodity and fixed income — front month contracts &nbsp;·&nbsp; May 8, 2026</div>
  <div class="slbl">Equity Index</div><div class="fug" id="fut-eq"></div>
  <div class="slbl">Commodities</div><div class="fug" id="fut-com"></div>
  <div class="slbl">Fixed Income</div><div class="fug" id="fut-fi"></div>
</div>

<!-- NEWS PAGE -->
<div id="pg-news" class="pg">
  <div class="pgt">Financial News</div>
  <div class="pgs">Real headlines from Bloomberg, Reuters, WSJ, Yahoo Finance, TheStreet &nbsp;·&nbsp; May 8, 2026</div>
  <div class="fb">
    <div class="fg">
      <button class="fbt on" onclick="nFlt('All',this)">All</button>
      <button class="fbt" onclick="nFlt('Macro',this)">Macro</button>
      <button class="fbt" onclick="nFlt('Earnings',this)">Earnings</button>
      <button class="fbt" onclick="nFlt('Technology',this)">Technology</button>
      <button class="fbt" onclick="nFlt('Commodities',this)">Commodities</button>
      <button class="fbt" onclick="nFlt('Bonds',this)">Bonds</button>
      <button class="fbt" onclick="nFlt('Global',this)">Global</button>
    </div>
  </div>
  <div id="ngrid" style="display:grid;grid-template-columns:1fr 1fr;gap:12px"></div>
</div>

<!-- WATCHLIST -->
<div id="pg-watchlist" class="pg">
  <div class="pgt">Watchlist</div>
  <div id="wls" class="pgs"></div>
  <div id="wlc"></div>
</div>

<footer>
  <span>StockX &nbsp;·&nbsp; Real prices from Yahoo Finance, Robinhood, Investing.com &nbsp;·&nbsp; May 8, 2026 &nbsp;·&nbsp; Market data may be delayed</span>
  <span>For informational purposes only &nbsp;·&nbsp; Not financial advice</span>
</footer>
</div>

<script>
/* ── REAL DATA May 8, 2026 ── */
var ST=[
  {sym:"AAPL",name:"Apple Inc.",price:293.23,change:5.21,pct:1.81,vol:"48.2M",cap:"$4.41T",h52:299.16,l52:169.21,sec:"Technology",ex:"NASDAQ",desc:"Apple & Intel agreed a preliminary chip deal on May 8, sending Intel +13%. Apple also hit a new intraday record high. Services now > 25% of revenue. Apple's R&D budget crossed 10% of sales on AI for the first time in 30 years."},
  {sym:"MSFT",name:"Microsoft Corp.",price:415.38,change:5.42,pct:1.33,vol:"33.4M",cap:"$3.09T",h52:555.45,l52:356.28,sec:"Technology",ex:"NASDAQ",desc:"Microsoft plans to spend ~$200B in CapEx in 2026, mostly on AI infrastructure. Azure is growing >29% YoY. TCI fund cut its stake from 10% to 1% of portfolio in March 2026."},
  {sym:"GOOGL",name:"Alphabet Inc.",price:396.95,change:4.26,pct:1.08,vol:"24.4M",cap:"$4.79T",h52:402.94,l52:152.20,sec:"Technology",ex:"NASDAQ",desc:"Google Cloud growing strongly. Alphabet hit its 16th intraday record of 2026 today. Google launched Fitbit Air at $99.99 and offered EU spam policy changes to avoid antitrust action."},
  {sym:"AMZN",name:"Amazon.com Inc.",price:272.85,change:1.48,pct:0.54,vol:"22.5M",cap:"$2.90T",h52:278.56,l52:188.82,sec:"Consumer Discretionary",ex:"NASDAQ",desc:"Amazon Q1 2026: $181.5B revenue (+17% YoY), EPS $2.78 (vs $1.64 est). AWS grew 28% to $37.6B. JPMorgan raised target to $330. CapEx forecast ~$200B in 2026. Advertising hit $17.24B (+24%)."},
  {sym:"NVDA",name:"NVIDIA Corp.",price:214.94,change:3.44,pct:1.63,vol:"136.3M",cap:"$5.26T",h52:217.80,l52:115.21,sec:"Technology",ex:"NASDAQ",desc:"NVDA hit a new 52-week high on May 8. Board added Suzanne Nora Johnson as director. IREN signed a $3.4B Nvidia AI contract. Earnings due May 20. Corning partnership announced for U.S. AI optical infrastructure."},
  {sym:"META",name:"Meta Platforms",price:615.70,change:3.51,pct:0.57,vol:"12.3M",cap:"$1.56T",h52:796.25,l52:520.26,sec:"Technology",ex:"NASDAQ",desc:"Meta issued $25B in senior unsecured bonds in April. Profits and cash flow soaring. Meta Reality Labs still operating at multi-billion loss. Ad revenue drives >98% of total revenue."},
  {sym:"TSLA",name:"Tesla Inc.",price:409.05,change:15.71,pct:4.01,vol:"64.3M",cap:"$1.31T",h52:498.83,l52:273.21,sec:"Consumer Discretionary",ex:"NASDAQ",desc:"Tesla stock testing a key technical breakout level. NHTSA confirmed the 2026 Model Y is first vehicle to meet its new advanced driver-assistance systems benchmark. Positive momentum building."},
  {sym:"JPM",name:"JPMorgan Chase & Co.",price:293.12,change:-2.41,pct:-0.82,vol:"15.2M",cap:"$820B",h52:337.25,l52:251.55,sec:"Financials",ex:"NYSE",desc:"JPMorgan Q1 2026: EPS $5.94 vs $5.47 est (+8.56% surprise). Revenue $49.84B vs $49.18B. Next earnings: Jul 14, 2026. Jamie Dimon spoke with Anthropic CEO on AI boom and regulation at CNBC on May 6."},
  {sym:"WMT",name:"Walmart Inc.",price:130.49,change:0.44,pct:0.34,vol:"15.2M",cap:"$1.05T",h52:134.69,l52:91.89,sec:"Consumer Staples",ex:"NYSE",desc:"Walmart workers trailing Amazon peers in productivity metrics. Global advertising business growing rapidly. Barron's featured WMT as one of 9 'old economy' stocks for an AI melt-up scenario."},
  {sym:"XOM",name:"Exxon Mobil Corp.",price:147.69,change:3.50,pct:2.43,vol:"22.5M",cap:"$615B",h52:176.41,l52:101.19,sec:"Energy",ex:"NYSE",desc:"Argus raised Exxon target to $169 citing Permian and Guyana production. XOM fell 9% in April — worst month in a year — despite oil near $95. CFO transition announced. Middle East tensions boosting oil prices."},
  {sym:"AVGO",name:"Broadcom Inc.",price:418.82,change:6.26,pct:4.20,vol:"22.8M",cap:"$1.95T",h52:437.68,l52:203.69,sec:"Technology",ex:"NASDAQ",desc:"Broadcom Q1 2026: Revenue $19.3B (+29% YoY). AI semiconductor revenue +106% YoY. EPS $2.05 beat $2.02 est. Free cash flow $8B. Q2 guidance: AI chip revenue +140% YoY. OpenAI custom chip deal reportedly hit financing hurdles."},
  {sym:"INTC",name:"Intel Corp.",price:32.45,change:3.78,pct:13.17,vol:"312.0M",cap:"$138B",h52:32.45,l52:17.67,sec:"Technology",ex:"NASDAQ",desc:"Intel surged 13% on May 8 after WSJ reported a preliminary chip deal with Apple. Analysts see Intel as potentially the biggest winner of the AI inference era transition. New intraday 52-week high reached today."}
];
var BONDS=[
  {sym:"US2Y",name:"U.S. 2-Year Treasury Note",price:97.82,change:0.11,pct:0.11,h52:100.12,l52:94.80,ex:"OTC"},
  {sym:"US10Y",name:"U.S. 10-Year Treasury Note",price:95.14,change:-0.20,pct:-0.21,h52:101.40,l52:87.50,ex:"OTC"},
  {sym:"US30Y",name:"U.S. 30-Year Treasury Bond",price:88.62,change:-0.38,pct:-0.43,h52:96.20,l52:76.40,ex:"OTC"},
  {sym:"HYG",name:"iShares High Yield Corp Bond ETF",price:79.44,change:0.28,pct:0.35,h52:81.20,l52:71.10,ex:"NYSE Arca"},
  {sym:"LQD",name:"iShares Inv. Grade Bond ETF",price:109.82,change:-0.22,pct:-0.20,h52:117.30,l52:105.20,ex:"NYSE Arca"},
  {sym:"TLT",name:"iShares 20+ Year Treasury ETF",price:84.70,change:-0.55,pct:-0.65,h52:95.40,l52:78.30,ex:"NYSE Arca"}
];
var FUT={
  eq:[
    {sym:"ES=F",name:"E-mini S&P 500",price:7415.50,change:58.25,pct:0.79,h52:7440.00,l52:4820.00,ex:"CME"},
    {sym:"NQ=F",name:"E-mini Nasdaq-100",price:26520.75,change:445.50,pct:1.71,h52:26620.00,l52:16800.00,ex:"CME"},
    {sym:"YM=F",name:"E-mini Dow Jones",price:49640.00,change:22.00,pct:0.04,h52:50100.00,l52:37800.00,ex:"CBOT"},
    {sym:"RTY=F",name:"E-mini Russell 2000",price:2875.40,change:22.80,pct:0.80,h52:2920.00,l52:1820.00,ex:"CME"}
  ],
  com:[
    {sym:"CL=F",name:"WTI Crude Oil",price:94.75,change:0.06,pct:0.06,h52:101.50,l52:62.80,ex:"NYMEX"},
    {sym:"BZ=F",name:"Brent Crude Oil",price:100.20,change:0.14,pct:0.14,h52:107.20,l52:68.40,ex:"ICE"},
    {sym:"GC=F",name:"Gold",price:4723.70,change:12.80,pct:0.27,h52:4820.00,l52:2000.10,ex:"COMEX"},
    {sym:"SI=F",name:"Silver",price:32.48,change:0.44,pct:1.37,h52:36.20,l52:22.40,ex:"COMEX"},
    {sym:"NG=F",name:"Natural Gas",price:3.84,change:-0.11,pct:-2.78,h52:5.20,l52:1.52,ex:"NYMEX"}
  ],
  fi:[
    {sym:"ZB=F",name:"U.S. 30-Year Bond Futures",price:113.22,change:-0.38,pct:-0.33,h52:126.00,l52:104.00,ex:"CBOT"},
    {sym:"ZN=F",name:"U.S. 10-Year Note Futures",price:106.44,change:-0.20,pct:-0.19,h52:114.00,l52:101.80,ex:"CBOT"},
    {sym:"ZT=F",name:"U.S. 2-Year Note Futures",price:100.84,change:0.06,pct:0.06,h52:103.20,l52:98.60,ex:"CBOT"}
  ]
};
/* Real news May 8, 2026 from Yahoo Finance, TheStreet, Bloomberg, Reuters, WSJ */
var NEWS=[
  {title:"U.S. Economy Added 115,000 Jobs in April, Crushing 65,000 Forecast — Markets Rally",body:"Nonfarm payrolls rose 115,000 in April, well above the Bloomberg consensus of 65,000 jobs. Unemployment held at 4.3%. March payrolls were revised up to 185,000. The S&P 500 gained 0.84% and Nasdaq surged 1.71% on the data, shrugging off fresh U.S.–Iran military clashes near the Strait of Hormuz.",src:"Yahoo Finance",time:"2h ago",cat:"Macro",tags:["SPX","NDX"]},
  {title:"Apple and Intel Agree Preliminary Chip Deal — Intel Soars 13%",body:"Intel shares surged 13% to a new 52-week high after the Wall Street Journal reported a preliminary agreement to supply chips for Apple devices. Apple also rose 1.8% on the news. Analysts see Intel as a major beneficiary of the AI inference era transition away from GPU-heavy workloads.",src:"WSJ",time:"4h ago",cat:"Technology",tags:["AAPL","INTC"]},
  {title:"Amazon Q1 2026: Record $181.5B Revenue, AWS Grows 28% — JPMorgan Raises Target to $330",body:"Amazon posted Q1 net sales of $181.5B, up 17% YoY, beating the $177.3B consensus. EPS of $2.78 nearly doubled estimates of $1.64 (including $16.8B Anthropic investment gain). AWS hit $37.6B (+28%), its fastest growth in 15 quarters. Operating income of $23.9B was the highest ever recorded.",src:"TheStreet",time:"6h ago",cat:"Earnings",tags:["AMZN"]},
  {title:"Nasdaq and S&P 500 Post 6th Weekly Gain as Chip Stocks Rally on Jobs Data",body:"US stocks climbed for a sixth straight week. Semiconductor stocks led gains, with NVIDIA hitting a new 52-week high and the Roundhill Magnificent Seven ETF reaching its second intraday record of the year. Brent crude topped $101/barrel while WTI held near $95 after new military exchanges near the Strait of Hormuz.",src:"Yahoo Finance",time:"1h ago",cat:"Macro",tags:["SPX","NVDA","AAPL"]},
  {title:"Broadcom Q1 Revenue Hits Record $19.3B — AI Chip Revenue Up 106% YoY",body:"Broadcom reported Q1 2026 revenue of $19.3B (+29% YoY), topping the $19.21B forecast. AI semiconductor revenue surged 106% year-over-year. Free cash flow reached $8B. Q2 guidance projects AI chip revenue +140% YoY. Separately, The Information reported the company's custom chip deal with OpenAI hit financing hurdles.",src:"Bloomberg",time:"5h ago",cat:"Earnings",tags:["AVGO"]},
  {title:"NVIDIA Adds New Board Member, Announces Corning Partnership for AI Optical Infrastructure",body:"NVIDIA appointed Suzanne Nora Johnson to its board of directors. The company also announced a multi-year partnership with Corning to expand U.S. optical connectivity manufacturing for AI data centers. Separately, IREN signed a $3.4B Nvidia AI contract — the sector's largest-ever AI cloud deal. NVDA hit a new 52-week high today.",src:"Nasdaq",time:"2h ago",cat:"Technology",tags:["NVDA"]},
  {title:"Brent Crude Tops $101 as U.S.–Iran Exchange Military Blows Near Strait of Hormuz",body:"Brent futures rose above $101/barrel and WTI traded near $95 after renewed fighting near the Strait of Hormuz reignited concerns about the stability of a U.S.-Iran ceasefire. Oil had previously fallen on hopes of a peace deal but surged Thursday as both sides exchanged strikes. Markets are monitoring a 14-point MOU framework.",src:"Reuters",time:"5h ago",cat:"Commodities",tags:["CL=F","BZ=F","XOM"]},
  {title:"South Korean Stocks Up 75% in 2026 — AI Memory Boom Drives Historic Rally",body:"The Kospi surged to 7,384 — up 75% year-to-date — fueled by AI-driven demand for memory chips. Samsung trades at just 6x forward earnings, SK Hynix at 5.3x. Goldman Sachs targets the Kospi at 8,000 by year-end. Short sellers are increasing bets against the rally as macro tailwinds begin to fade.",src:"Bloomberg",time:"8h ago",cat:"Global",tags:["TSM"]},
  {title:"10-Year Treasury Yield Falls to 2-Week Low at 4.32% on Oil Price Drop",body:"The 10-year Treasury yield fell for a third consecutive session to 4.32%, the lowest in about two weeks, as lower oil prices eased inflation expectations and reduced pressure for hawkish Fed policy. Markets price the Fed holding rates through year-end, with only a 20% probability of a September cut.",src:"TradingEconomics",time:"7h ago",cat:"Bonds",tags:["US10Y","TNX"]},
  {title:"JPMorgan and Mastercard Link with Ripple for Historic XRP-Ledger Treasury Settlement",body:"JPMorgan Chase and Mastercard partnered with Ripple to execute a U.S. Treasury settlement via the XRP Ledger — a landmark moment for institutional blockchain adoption. The settlement involved real U.S. government bonds and marks the first large-scale bank use of public blockchain infrastructure for sovereign debt.",src:"TipRanks",time:"17h ago",cat:"Macro",tags:["JPM"]},
  {title:"Tesla 2026 Model Y First Vehicle to Meet NHTSA's New ADAS Benchmark",body:"The National Highway Traffic Safety Administration confirmed the 2026 Tesla Model Y meets its new benchmark for advanced driver-assistance systems — the first production vehicle to do so. This could strengthen Tesla's regulatory standing ahead of its FSD robotaxi commercialization plans.",src:"Benzinga",time:"9h ago",cat:"Technology",tags:["TSLA"]},
  {title:"Microsoft Estimates $200B in 2026 CapEx as AI Infrastructure Race Intensifies",body:"Microsoft estimates it will spend nearly $200 billion in capital expenditures in 2026, rivaling Amazon's forecast. Azure is the primary recipient. Separately, hedge fund TCI slashed its Microsoft stake from 10% to 1% by March amid concerns about AI ROI timelines and rising competition from Google Cloud.",src:"TipRanks",time:"10h ago",cat:"Technology",tags:["MSFT"]}
];

var WL=JSON.parse(localStorage.getItem('sxwl')||'["AAPL","NVDA"]');
var stF='all',secF='all',stSK='sym',stSD=1,curA=null;

function secCls(s){return s==='Technology'?'s-tech':s==='Financials'?'s-fin':s==='Energy'?'s-ene':s==='Consumer Discretionary'?'s-con':'s-cs';}
function catCls(c){return c==='Macro'?'nc-mac':c==='Earnings'?'nc-ear':c==='Technology'?'nc-tec':c==='Commodities'?'nc-com':c==='Global'?'nc-geo':'nc-bnd';}
function f2(n){return n.toFixed(2);}
function fp(n){return (n>=0?'+':'')+f2(n)+'%';}

function goPg(p,btn){
  document.querySelectorAll('.pg').forEach(function(e){e.classList.remove('on')});
  document.querySelectorAll('.nb').forEach(function(e){e.classList.remove('on')});
  document.getElementById('pg-'+p).classList.add('on');
  if(btn) btn.classList.add('on');
  else document.querySelectorAll('.nb').forEach(function(b){if(b.textContent.trim().toLowerCase()===p.toLowerCase())b.classList.add('on');});
  if(p==='markets') setTimeout(function(){drawCh('chart-spx',7399,60,true);},60);
  if(p==='news') renderNews('All');
  if(p==='watchlist') renderWL();
  if(p==='stocks') renderST();
  if(p==='bonds'){renderBonds();setTimeout(drawYC,60);}
  if(p==='futures') renderFUT();
}

function stRow(s,rng){
  var up=s.pct>=0,rp=Math.min(100,Math.max(0,(s.price-s.l52)/(s.h52-s.l52)*100));
  var rngCell=rng?'<td><span class="rb"><span class="rf" style="width:'+rp.toFixed(0)+'%;background:'+(up?'var(--g)':'var(--r)')+'"></span></span><span style="font-size:10.5px;color:var(--t4)">$'+s.l52.toFixed(0)+'–$'+s.h52.toFixed(0)+'</span></td>':'';
  return '<tr>'
    +'<td class="sc" onclick="openA(\''+s.sym+'\')">'+s.sym+'</td>'
    +'<td style="color:var(--t2)">'+s.name+'</td>'
    +'<td class="pc r">$'+f2(s.price)+'</td>'
    +'<td class="r mc '+(up?'up':'dn')+'">'+(up?'+':'')+f2(s.change)+'</td>'
    +'<td class="r"><span class="bge '+(up?'bu':'bd')+'">'+(up?'▲':'▼')+Math.abs(s.pct).toFixed(2)+'%</span></td>'
    +'<td class="r mc" style="color:var(--t3)">'+s.vol+'</td>'
    +'<td class="r mc" style="color:var(--t3)">'+s.cap+'</td>'
    +rngCell
    +'<td><span class="'+secCls(s.sec)+'">'+s.sec+'</span></td>'
    +'</tr>';
}

function renderHST(){document.getElementById('hst').innerHTML=ST.map(function(s){return stRow(s,false);}).join('');}
function renderST(){
  var list=ST.filter(function(s){
    if(stF==='gainers'&&s.pct<0) return false;
    if(stF==='losers'&&s.pct>=0) return false;
    if(secF!=='all'&&s.sec!==secF) return false;
    return true;
  });
  list.sort(function(a,b){var va=a[stSK],vb=b[stSK];if(typeof va==='string')return stSD*(va>vb?1:-1);return stSD*(va-vb);});
  document.getElementById('stcnt').textContent=list.length+' result'+(list.length!==1?'s':'');
  document.getElementById('stb').innerHTML=list.map(function(s){return stRow(s,true);}).join('');
}
function stFlt(f,btn){stF=f;btn.closest('.fg').querySelectorAll('.fbt').forEach(function(b){b.classList.remove('on')});btn.classList.add('on');renderST();}
function stSec(v){secF=v;renderST();}
function stSort(k){if(stSK===k)stSD*=-1;else{stSK=k;stSD=1;}renderST();renderHST();}

function openA(sym){
  goPg('stocks');
  var s=ST.find(function(x){return x.sym===sym;});
  if(!s) return;
  curA=s;
  var up=s.pct>=0;
  document.getElementById('d-sym').innerHTML=s.sym+' &mdash; '+s.ex+' &nbsp;<span class="src-tag">Robinhood / Investing.com</span>';
  document.getElementById('d-price').textContent='$'+f2(s.price);
  var ce=document.getElementById('d-chg');
  ce.textContent=(up?'▲ +':'▼ ')+Math.abs(s.change).toFixed(2)+' ('+fp(s.pct)+')';
  ce.className='cchg '+(up?'up':'dn');
  document.getElementById('d-name').textContent=s.name;
  document.getElementById('d-stats').innerHTML=[
    {l:'Market Cap',v:s.cap},{l:'Avg Volume',v:s.vol},
    {l:'52W High',v:'$'+f2(s.h52)},{l:'52W Low',v:'$'+f2(s.l52)},
    {l:'Exchange',v:s.ex},{l:'Sector',v:s.sec}
  ].map(function(x){return '<div class="stat"><div class="sl">'+x.l+'</div><div class="sv">'+x.v+'</div></div>';}).join('');
  document.getElementById('d-ai').textContent=s.desc;
  document.getElementById('adet').style.display='block';
  setTimeout(function(){drawCh('chart-det',s.price,60,up);},60);
  document.getElementById('adet').scrollIntoView({behavior:'smooth',block:'start'});
}

function renderBonds(){
  document.getElementById('bdb').innerHTML=BONDS.map(function(b){
    var up=b.pct>=0;
    return '<tr>'
      +'<td class="sc">'+b.sym+'</td>'
      +'<td style="color:var(--t2)">'+b.name+'</td>'
      +'<td class="pc r">$'+f2(b.price)+'</td>'
      +'<td class="r mc '+(up?'up':'dn')+'">'+(up?'+':'')+f2(b.change)+'</td>'
      +'<td class="r"><span class="bge '+(up?'bu':'bd')+'">'+(up?'▲':'▼')+Math.abs(b.pct).toFixed(2)+'%</span></td>'
      +'<td style="font-size:11px;color:var(--t4)">$'+f2(b.l52)+'–$'+f2(b.h52)+'</td>'
      +'<td style="color:var(--t4)">'+b.ex+'</td></tr>';
  }).join('');
}

function renderFUT(){
  function card(f){
    var up=f.pct>=0,rp=Math.min(100,Math.max(0,(f.price-f.l52)/(f.h52-f.l52)*100));
    return '<div class="fc">'
      +'<div class="fsym">'+f.sym+'</div><div class="fname">'+f.name+'</div>'
      +'<div class="fprice">'+f.price.toLocaleString('en-US',{minimumFractionDigits:2,maximumFractionDigits:2})+'</div>'
      +'<div style="display:flex;gap:6px;margin-top:7px">'
      +'<span class="bge '+(up?'bu':'bd')+'">'+(up?'▲ +':'▼ ')+Math.abs(f.change).toFixed(2)+'</span>'
      +'<span class="bge '+(up?'bu':'bd')+'">'+(up?'+':'')+f2(f.pct)+'%</span>'
      +'</div>'
      +'<div class="rb" style="width:100%;margin:9px 0 0"><div class="rf" style="width:'+rp.toFixed(0)+'%;background:'+(up?'var(--g)':'var(--r)')+'"></div></div>'
      +'<div class="fex">'+f.ex+'</div></div>';
  }
  document.getElementById('fut-eq').innerHTML=FUT.eq.map(card).join('');
  document.getElementById('fut-com').innerHTML=FUT.com.map(card).join('');
  document.getElementById('fut-fi').innerHTML=FUT.fi.map(card).join('');
}

function renderNews(cat){
  var list=cat==='All'?NEWS:NEWS.filter(function(n){return n.cat===cat;});
  document.getElementById('ngrid').innerHTML=list.map(function(n,i){
    return '<div class="card" style="overflow:visible;cursor:pointer;transition:border-color .15s" onmouseenter="this.style.borderColor=\'var(--b2)\'" onmouseleave="this.style.borderColor=\'var(--b1)\'">'
      +'<div style="padding:14px 15px">'
      +'<span class="ncat '+catCls(n.cat)+'">'+n.cat+'</span>'
      +'<div style="font-size:'+(i===0?'14.5':'13')+'px;font-weight:600;color:var(--t1);line-height:1.45;margin-bottom:8px">'+n.title+'</div>'
      +'<div style="font-size:12px;color:var(--t3);line-height:1.65;margin-bottom:10px">'+n.body+'</div>'
      +'<div style="display:flex;align-items:center;justify-content:space-between">'
      +'<span class="nmeta">'+n.src+' &nbsp;·&nbsp; '+n.time+'</span>'
      +'<div style="display:flex;gap:4px">'+n.tags.map(function(t){return '<span style="font-size:10px;font-family:monospace;font-weight:700;background:var(--bg4);color:var(--t3);padding:2px 6px;border-radius:4px;border:1px solid var(--b1)">'+t+'</span>';}).join('')+'</div>'
      +'</div></div></div>';
  }).join('');
  var g=document.getElementById('ngrid');
  var fc=g.querySelector('.card');
  if(fc) fc.style.gridColumn='span 2';
}

function nFlt(cat,btn){btn.closest('.fg').querySelectorAll('.fbt').forEach(function(b){b.classList.remove('on')});btn.classList.add('on');renderNews(cat);}

function renderWL(){
  document.getElementById('wls').textContent=WL.length+' saved asset'+(WL.length!==1?'s':'');
  if(!WL.length){
    document.getElementById('wlc').innerHTML='<div class="wle"><span class="wlei">☆</span><div style="font-size:14px;font-weight:600;color:var(--t3);margin-bottom:7px">Your watchlist is empty</div><div style="font-size:12px;color:var(--t4);margin-bottom:18px">Click any ticker to open its detail, then click ★ to save</div><button class="btnp" onclick="goPg(\'stocks\')">Browse Stocks</button></div>';
    return;
  }
  document.getElementById('wlc').innerHTML=WL.map(function(sym){
    var s=ST.find(function(x){return x.sym===sym;});
    if(!s) return '';
    var up=s.pct>=0;
    return '<div class="wlr" onclick="openA(\''+s.sym+'\')"><div class="wli">'+s.sym.slice(0,4)+'</div>'
      +'<div style="flex:1;min-width:0"><div style="font-size:13.5px;font-weight:700;color:var(--t1)">'+s.sym+'</div><div style="font-size:11.5px;color:var(--t4);overflow:hidden;text-overflow:ellipsis;white-space:nowrap">'+s.name+'</div></div>'
      +'<div style="text-align:right"><div style="font-size:15px;font-weight:700;color:var(--t1);font-family:monospace">$'+f2(s.price)+'</div><span class="bge '+(up?'bu':'bd')+'">'+(up?'▲':'▼')+Math.abs(s.pct).toFixed(2)+'%</span></div>'
      +'<button class="wld" onclick="event.stopPropagation();rmWL(\''+s.sym+'\')">✕</button></div>';
  }).join('');
}
function rmWL(sym){WL=WL.filter(function(s){return s!==sym;});localStorage.setItem('sxwl',JSON.stringify(WL));renderWL();}

/* Search: searches ALL stocks + bonds */
var ALL_ASSETS=ST.concat(BONDS.map(function(b){return {sym:b.sym,name:b.name,price:b.price,pct:b.pct,type:'bond'};}));
function srchFn(q){
  var dd=document.getElementById('srch-dd');
  if(!q||q.trim().length<1){dd.style.display='none';return;}
  var ql=q.toLowerCase();
  var res=ALL_ASSETS.filter(function(a){return a.sym.toLowerCase().includes(ql)||a.name.toLowerCase().includes(ql);}).slice(0,8);
  if(!res.length){dd.style.display='none';return;}
  dd.innerHTML=res.map(function(a){
    var up=a.pct>=0;
    var isST=ST.find(function(s){return s.sym===a.sym;});
    return '<div class="sr" onclick="'+(isST?'openA':'void')+'(\''+a.sym+'\')">'
      +'<span class="sr-sym">'+a.sym+'</span>'
      +'<span class="sr-name">'+a.name+'</span>'
      +'<span class="sr-price">$'+f2(a.price)+'</span>'
      +'<span class="sr-chg bge '+(up?'bu':'bd')+'">'+(up?'▲':'▼')+Math.abs(a.pct).toFixed(2)+'%</span>'
      +'</div>';
  }).join('');
  dd.style.display='block';
}

/* Charts */
function drawCh(id,base,pts,up){
  var c=document.getElementById(id);
  if(!c)return;
  var dpr=window.devicePixelRatio||1,rect=c.getBoundingClientRect(),W=rect.width||700,H=rect.height||145;
  c.width=W*dpr;c.height=H*dpr;
  var ctx=c.getContext('2d');ctx.scale(dpr,dpr);
  var data=[],p=base*(1-pts*0.00025);
  for(var i=0;i<=pts;i++){p*=(1+(Math.random()-.47)*(up?0.0036:0.0042));data.push(p);}
  var mn=Math.min.apply(null,data),mx=Math.max.apply(null,data),rng=mx-mn||1;
  var px=8,py=10;
  function Y(v){return H-py-(v-mn)/rng*(H-py*2);}
  var col=up?'#10b981':'#f05252';
  ctx.beginPath();
  data.forEach(function(v,i){var x=px+i/(data.length-1)*(W-px*2);i?ctx.lineTo(x,Y(v)):ctx.moveTo(x,Y(v));});
  ctx.strokeStyle=col;ctx.lineWidth=1.6;ctx.lineJoin='round';ctx.stroke();
  ctx.lineTo(W-px,H-py);ctx.lineTo(px,H-py);ctx.closePath();
  ctx.fillStyle=up?'rgba(16,185,129,0.06)':'rgba(240,82,82,0.06)';ctx.fill();
}
function drawYC(){
  var c=document.getElementById('chart-yc');if(!c)return;
  var dpr=window.devicePixelRatio||1,rect=c.getBoundingClientRect(),W=rect.width||700,H=rect.height||110;
  c.width=W*dpr;c.height=H*dpr;
  var ctx=c.getContext('2d');ctx.scale(dpr,dpr);
  var pts=[{t:'1M',y:4.38},{t:'3M',y:4.36},{t:'6M',y:4.34},{t:'1Y',y:4.33},{t:'2Y',y:4.35},{t:'5Y',y:4.28},{t:'10Y',y:4.32},{t:'20Y',y:4.51},{t:'30Y',y:4.78}];
  var mn=4.1,mx=5.0,rng=mx-mn,px=26,py=18;
  function X(i){return px+i/(pts.length-1)*(W-px*2);}
  function Y(v){return H-py-(v-mn)/rng*(H-py*2);}
  ctx.beginPath();
  pts.forEach(function(p,i){i?ctx.lineTo(X(i),Y(p.y)):ctx.moveTo(X(i),Y(p.y));});
  ctx.lineTo(X(pts.length-1),H-py);ctx.lineTo(X(0),H-py);ctx.closePath();
  ctx.fillStyle='rgba(212,160,23,0.05)';ctx.fill();
  ctx.beginPath();
  pts.forEach(function(p,i){i?ctx.lineTo(X(i),Y(p.y)):ctx.moveTo(X(i),Y(p.y));});
  ctx.strokeStyle='#d4a017';ctx.lineWidth=1.8;ctx.stroke();
  pts.forEach(function(p,i){
    ctx.beginPath();ctx.arc(X(i),Y(p.y),3,0,Math.PI*2);ctx.fillStyle='#d4a017';ctx.fill();
    ctx.fillStyle='#4a5d72';ctx.font='9px monospace';ctx.textAlign='center';
    ctx.fillText(p.t,X(i),H-4);
    ctx.fillStyle='#6b7d96';ctx.font='9px monospace';
    ctx.fillText(p.y.toFixed(2)+'%',X(i),Y(p.y)-8);
  });
}
function setPd(btn,chart,p){
  btn.closest('.pbs').querySelectorAll('.pb').forEach(function(b){b.classList.remove('on');});
  btn.classList.add('on');
  var ptMap=[60,168,90,90,120];
  if(chart==='spx') drawCh('chart-spx',7399,ptMap[p],true);
  else if(chart==='det'&&curA) drawCh('chart-det',curA.price,ptMap[p],curA.pct>=0);
}

/* Init */
document.getElementById('mkt-time').textContent=new Date().toLocaleTimeString('en-US',{hour:'2-digit',minute:'2-digit',timeZone:'America/New_York'})+' ET';
renderHST();renderST();renderBonds();
setTimeout(function(){drawCh('chart-spx',7399,60,true);},150);
</script>

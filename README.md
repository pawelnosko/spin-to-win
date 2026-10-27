<h1>🎡 Spin to Win – Interactive 3D Prize Wheel</h1>
<p><strong>A customizable 3D Spin to Win prize wheel built with HTML, CSS, JavaScript, Three.js, and Canvas 2D.</strong></p>
<p>Turn traditional discount promotions into an interactive experience! Spin to Win allows visitors to spin a realistic 3D prize wheel and win percentage discounts, fixed-amount rewards, or other prizes.</p>
<p>The project is designed to be lightweight, customizable, and independent of any specific CMS or e-commerce platform.</p>
<p>No PHP, database, build tools, or frontend frameworks are required for the standalone demo.</p>
<p><strong>📖 </strong><a href="https://pawelnosko.com/js-frontend-tools/spin-to-win-how-to-create-your-own-3d-prize-wheel-with-discounts-html-css-and-javascript-tutorial"><strong>Read the Full Tutorial &amp; Documentation</strong></a></p>
<h2>✨ Features</h2>
<ul>
<li>
<p><strong>Interactive 3D wheel</strong> – rendered using Three.js and WebGL.</p>
</li>
<li>
<p><strong>Mouse and touch support</strong> – grab, drag, and spin the wheel naturally.</p>
</li>
<li>
<p><strong>Realistic spinning animation</strong> – smooth acceleration from user interaction and progressive deceleration.</p>
</li>
<li>
<p><strong>JSON-based prize configuration</strong> – easily define percentage discounts, fixed amounts, and custom rewards.</p>
</li>
<li>
<p><strong>Weighted prize selection</strong> – control the probability of winning individual prizes.</p>
</li>
<li>
<p><strong>Dynamic wheel generation</strong> – automatically generate segments and labels from JSON data.</p>
</li>
<li>
<p><strong>Animated lighting</strong> – 24 glowing bulbs, metallic materials, and lighting effects.</p>
</li>
<li>
<p><strong>Responsive popup</strong> – works on desktop and mobile devices.</p>
</li>
<li>
<p><strong>Light and dark themes</strong> – supports browser color scheme preferences.</p>
</li>
<li>
<p><strong>JavaScript API</strong> – dynamically update prizes and customize winner selection.</p>
</li>
<li>
<p><strong>Custom events</strong> – integrate the wheel with other JavaScript applications.</p>
</li>
<li>
<p><strong>CMS-independent architecture</strong> – suitable for future WooCommerce, OpenCart, and PrestaShop integrations.</p>
</li>
</ul>
<h2>🛠️ Technologies</h2>
<table>
<tbody>
<tr>
<th>Technology</th>
<th>Purpose</th>
</tr>
<tr>
<td>HTML5</td>
<td>Popup structure and user interface</td>
</tr>
<tr>
<td>CSS3</td>
<td>Styling, responsiveness, and UI animations</td>
</tr>
<tr>
<td>JavaScript</td>
<td>Wheel mechanics, interaction, and prize selection</td>
</tr>
<tr>
<td>Three.js</td>
<td>3D rendering, geometry, materials, and lighting</td>
</tr>
<tr>
<td>Canvas 2D</td>
<td>Dynamic wheel textures and prize labels</td>
</tr>
<tr>
<td>JSON</td>
<td>Prize configuration and weighted probabilities</td>
</tr>
</tbody>
</table>
<h2>🚀 Getting Started</h2>
<p><strong>1. Download the project</strong></p>
<p>Clone the repository or download the HTML source file.</p>
<p><strong>2. Open the HTML file</strong></p>
<p>Open <code>spin-to-win.html</code> in your browser.</p>
<p>The Three.js library is loaded from a CDN, so an internet connection is required.</p>
<p><strong>3. Spin the wheel!</strong></p>
<p>Use your mouse or finger to grab and spin the wheel, or simply click it to start.</p>
<p>After the animation finishes, the winning prize will appear in a popup.</p>
<h2>🎁 Configuring Prizes</h2>
<p>Prizes are defined using JSON, making them easy to modify or generate dynamically.</p>
<pre><code>[
  {"name":"off your order","amount":"5%","weight":40},
  {"name":"off your order","amount":"10%","weight":30},
  {"name":"off your order","amount":"15%","weight":20},
  {"name":"off your order","amount":"20%","weight":10}
]</code></pre>
<h3>Prize Properties</h3>
<table>
<tbody>
<tr>
<th>Property</th>
<th>Description</th>
</tr>
<tr>
<td><code>name</code></td>
<td>Additional prize description</td>
</tr>
<tr>
<td><code>amount</code></td>
<td>Prize value displayed on the wheel</td>
</tr>
<tr>
<td><code>weight</code></td>
<td>Relative probability of winning the prize (optional)</td>
</tr>
</tbody>
</table>
<p>When <code>weight</code> is omitted or not positive, the default drawing mechanism assigns a weight of 1.</p>
<p><strong>Important:</strong> All wheel segments have equal visual sizes. The weights control selection probabilities, not segment geometry.</p>
<h2>⚙️ JavaScript API</h2>
<p>The project exposes a simple global API through <code>window.SpinWheel</code>.</p>
<h3>Dynamically Load Prizes</h3>
<p>Update the prize configuration without manually rebuilding the wheel.</p>
<pre><code>SpinWheel.load([
  {
    name: "discount",
    amount: "10%",
    weight: 70
  },
  {
    name: "discount",
    amount: "20%",
    weight: 30
  }
]);</code></pre>
<p>The wheel texture and segment markers are regenerated automatically.</p>
<h3>Custom Winner Selection</h3>
<p>Override the default weighted selection mechanism:</p>
<pre><code>SpinWheel.pickWinner = function(prizes) {
  return 0;
};</code></pre>
<p>The function must return a valid prize index synchronously.</p>
<p>This example always selects the first prize and is intended only to demonstrate the API.</p>
<h2>🔔 Custom Events</h2>
<p>The script dispatches two custom JavaScript events.</p>
<h3>wheel</h3>
<p>Triggered when the spinning animation finishes and the winning prize is displayed.</p>
<pre><code>window.addEventListener("wheel:win", function(event) {
  console.log("Winning prize:", event.detail);
});</code></pre>
<h3>wheel</h3>
<p>Triggered when the user clicks the button to claim the prize.</p>
<pre><code>window.addEventListener("wheel:claim", function(event) {
  console.log("Claimed prize:", event.detail);
});</code></pre>
<p>These events can be used to connect the interface to forms, marketing workflows, custom APIs, or e-commerce integrations.</p>
<h2>🛒 E-commerce Integration</h2>
<p>One of the main goals of this project is to provide a reusable foundation for future e-commerce modules.</p>
<p>The JSON-based architecture makes it possible to supply prize configurations from:</p>
<ul>
<li>
<p><strong>WooCommerce</strong> – WordPress plugin settings or custom REST API endpoints.</p>
</li>
<li>
<p><strong>OpenCart</strong> – module settings and PHP controllers.</p>
</li>
<li>
<p><strong>PrestaShop</strong> – module configuration and backend controllers.</p>
</li>
<li>
<p><strong>Custom CMS platforms</strong> – database-generated JSON or dedicated APIs.</p>
</li>
</ul>
<p>The frontend wheel remains independent of the system providing the prize data.</p>
<h3>Important Security Note</h3>
<p>This repository provides a working frontend demonstration, not a complete production-ready coupon issuance system.</p>
<p>The JavaScript drawing mechanism runs in the user's browser and must not be trusted to authorize real discounts.</p>
<p>For commercial implementations, the backend should securely determine and validate winning results, enforce spin limits, issue coupons, and record claims.</p>
<p>Client-side events such as <code>wheel:win</code> and <code>wheel:claim</code> are integration signals, not proof of a valid prize.</p>
<h2>📖 Full Tutorial</h2>
<p>Want to understand how the wheel works internally?</p>
<p>I've prepared a step-by-step tutorial explaining:</p>
<ul>
<li>
<p>Why I chose Three.js instead of pure CSS.</p>
</li>
<li>
<p>How JSON-based prize configuration works.</p>
</li>
<li>
<p>How to build the HTML popup structure.</p>
</li>
<li>
<p>How to generate the wheel using Three.js and Canvas 2D.</p>
</li>
<li>
<p>How weighted prize selection works.</p>
</li>
<li>
<p>How mouse and touch gestures control the wheel.</p>
</li>
<li>
<p>How smooth deceleration and lighting animations are implemented.</p>
</li>
<li>
<p>How to integrate the JavaScript API with future e-commerce modules.</p>
</li>
</ul>
<p><strong>👉 </strong><a href="https://pawelnosko.com/js-frontend-tools/spin-to-win-how-to-create-your-own-3d-prize-wheel-with-discounts-html-css-and-javascript-tutorial"><strong>Spin to Win – How to Create Your Own 3D Prize Wheel with Discounts? HTML, CSS and JavaScript Tutorial</strong></a></p>
<h2>👨‍💻 Author</h2>
<p>Created by <strong>Paweł Nosko</strong>, software developer specializing in e-commerce platforms, custom CMS solutions, JavaScript interfaces, and web development.</p>
<p><strong>Website:</strong> <a href="https://pawelnosko.com/">pawelnosko.com</a></p>
<p><strong>Project Tutorial:</strong> <a href="https://pawelnosko.com/js-frontend-tools/spin-to-win-how-to-create-your-own-3d-prize-wheel-with-discounts-html-css-and-javascript-tutorial">Spin to Win – Complete Tutorial</a></p>
<div><hr></div>
<p><strong>Built for developers who prefer owning their code instead of depending on another monthly subscription.</strong> 🎡</p>

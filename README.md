# Wunschliste
<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Meine Wunschliste</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, sans-serif;
      background: radial-gradient(circle at top, #0f2027, #000);
      margin: 0;
      padding: 20px;
      color: #e5e5e5;
    }
    h1 {
      text-align: center;
      color: #00ffd5;
      text-shadow: 0 0 15px rgba(0,255,213,0.7);
      margin-bottom: 20px;
    }
    .container {
      max-width: 750px;
      margin: auto;
      background: linear-gradient(145deg, #111, #1a1a1a);
      padding: 25px;
      border-radius: 16px;
      box-shadow: 0 0 25px rgba(0,255,213,0.15);
      border: 1px solid rgba(0,255,213,0.25);
    }
    .inputs {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
      margin-bottom: 20px;
    }
    input, button {
      padding: 12px;
      font-size: 15px;
      border-radius: 8px;
      border: none;
    }
    input[type="text"], input[type="url"] {
      flex: 1;
      background: #0b0f14;
      color: #00ffd5;
      border: 1px solid rgba(0,255,213,0.4);
    }
    input::placeholder { color: #6fffe6; }
    button {
      background: linear-gradient(135deg, #00ffd5, #00bfa6);
      color: #002b28;
      font-weight: bold;
      cursor: pointer;
      box-shadow: 0 0 12px rgba(0,255,213,0.6);
      transition: transform .15s, box-shadow .15s;
    }
    button:hover {
      transform: scale(1.05);
      box-shadow: 0 0 20px rgba(0,255,213,0.9);
    }
    ul {
      list-style: none;
      padding: 0;
      margin: 0;
    }
    li {
      position: relative;
      background: linear-gradient(135deg, #0b0f14, #141a1f);
      margin: 12px 0;
      padding: 12px 14px;
      border-radius: 12px;
      display: grid;
      grid-template-columns: auto 1fr auto auto auto;
      align-items: center;
      gap: 12px;
      border: 1px solid rgba(0,255,213,0.25);
      box-shadow: 0 0 12px rgba(0,255,213,0.15);
    }
    
    li.done span {
      text-decoration: line-through;
      color: #7fffe9;
      opacity: 0.6;
    }
    .delete {
      background: linear-gradient(135deg, #ff4d4d, #b30000);
      color: white;
      padding: 6px 12px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(255,77,77,0.6);
    }
    .delete:hover {
      box-shadow: 0 0 18px rgba(255,77,77,0.9);
    }
    a {
      color: #00ffd5;
      text-decoration: none;
      font-size: 14px;
    }
    a:hover { text-decoration: underline; }
  </style>
</head>
<body>
  <h1>🎁 Meine Wunschliste</h1>
  <div class="container">
    <div class="inputs">
      <input id="wishInput" type="text" placeholder="Wunsch (z. B. Kopfhörer)" />
      <input id="linkInput" type="url" placeholder="Link (optional)" />
      <input id="priceInput" type="number" placeholder="Preis (€)" />
      <button onclick="addWish()">Hinzufügen</button>
    </div>

    <ul id="wishList">
      <li>
        <input type="checkbox" />
        
        <span>Maus</span>
        <span><a href="https://www.logitechg.com/de-de/shop/p/pro-x-superlight-2-se.910-007556" target="_blank">Link</a></span>
        <span class="price">159 €</span>
        <button class="delete" onclick="this.parentElement.remove()">X</button>
      </li>
      <li>
        <input type="checkbox" />
        
        <span>Mauspad</span>
        <span><a href="https://nyfter.com/products/xxl-nyfpad" target="_blank">Link</a></span>
        <span class="price">39 €</span>
        <button class="delete" onclick="this.parentElement.remove()">X</button>
      </li>
      <li>
        <input type="checkbox" />
        
        <span>Tastatur</span>
        <span><a href="https://www.logitechg.com/de-de/shop/p/pro-mechanical-gaming-keyboard.920-009390" target="_blank">Link</a></span>
        <span class="price">199 €</span>
        <button class="delete" onclick="this.parentElement.remove()">X</button>
      </li>
      <li>
        <input type="checkbox" />
        
        <span>Monitor</span>
        <span><a href="https://www.mediamarkt.de/de/product/_samsung-ls27d364gauxen-27-zoll-full-hd-monitor-4-ms-reaktionszeit-100-hz-2955391.html" target="_blank">Link</a></span>
        <span class="price">129 €</span>
        <button class="delete" onclick="this.parentElement.remove()">X</button>
      </li>
      <li>
        <input type="checkbox" />
        
        <span>Webcam</span>
        <span><a href="https://www.galaxus.de/de/s1/product/logitech-c920s-pro-2-mpx-webcam-10714329" target="_blank">Link</a></span>
        <span class="price">69 €</span>
        <button class="delete" onclick="this.parentElement.remove()">X</button>
      </li>
      <li>
        <input type="checkbox" />
        
        <span>Headset-Polster</span>
        <span><a href="https://www.amazon.de/dp/B0DSB2F265" target="_blank">Link</a></span>
        <span class="price">19 €</span>
        <button class="delete" onclick="this.parentElement.remove()">X</button>
      </li>
      <li>
        <input type="checkbox" />
        
        <span>Tisch</span>
        <span><a href="https://www.liftor.de/liftor-expert-id12899.html" target="_blank">Link</a></span>
        <span class="price">699 €</span>
        <button class="delete" onclick="this.parentElement.remove()">X</button>
      </li>
    </ul>
  </div>

  <script>
    function addWish() {
      const text = document.getElementById("wishInput").value.trim();
      const link = document.getElementById("linkInput").value.trim();
      if (!text) return;

      const li = document.createElement("li");

      

      // Checkbox (habe ich schon)
      const checkbox = document.createElement("input");
      checkbox.type = "checkbox";
      checkbox.onchange = () => li.classList.toggle("done", checkbox.checked);

      // Text
      const span = document.createElement("span");
      span.textContent = text;

      // Link
      let a = document.createElement("span");
      if (link) {
        const linkEl = document.createElement("a");
        linkEl.href = link;
        linkEl.target = "_blank";
        linkEl.textContent = "Link";
        a.appendChild(linkEl);
      }

      // Delete Button
      const delBtn = document.createElement("button");
      delBtn.textContent = "X";
      delBtn.className = "delete";
      delBtn.onclick = () => li.remove();

      li.appendChild(checkbox);
      
      li.appendChild(span);
      li.appendChild(a);
      li.appendChild(delBtn);

      document.getElementById("wishList").appendChild(li);

      document.getElementById("wishInput").value = "";
      document.getElementById("linkInput").value = "";
    }
  </script>
</body>
</html>

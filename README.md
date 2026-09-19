# evm2027.github.io
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>2jervcqnwvc</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      background-color: #9e8dce;
      color: #d3b4d9;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 2rem;
      text-align: center;
    }
    .title {
      font-size: 1.8rem;
      font-weight: 700;
      margin-bottom: 2rem;
    }
    .box {
      background-color: #b2cad2;
      border: 2px solid #e8d4d8;
      color: #d3b4d9;
      padding: 1.5rem 2.5rem;
      border-radius: 1rem;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: transform 0.2s, filter 0.2s;
      outline: none;
      box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.3);
    }
    .box:hover {
      transform: scale(1.05);
      filter: brightness(1.1);
    }
    .box:active {
      transform: scale(0.98);
    }
    .result-area {
      margin-top: 2rem;
      min-height: 120px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
    .countdown-num {
      font-size: 2.5rem;
      font-weight: 800;
      font-family: monospace;
    }
    .revealed-img {
      max-width: 100%;
      max-height: 300px;
      border-radius: 0.75rem;
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
    }
    .ascii-block {
      font-family: monospace;
      white-space: pre;
      background: rgba(0, 0, 0, 0.2);
      padding: 1rem;
      border-radius: 0.5rem;
      text-align: left;
    }
  </style>
</head>
<body>

  <h1 class="title">2jervcqnwvc</h1>

  <button class="box" id="happening-btn" onclick="triggerAction()">yeye</button>

  <div class="result-area" id="output"></div>

  <script>
    let state = {
      action: 'image',
      count: 10,
      endMsg: '🎉 L\'événement commence maintenant !',
      imgUrl: 'https://images.unsplash.com/photo-1518709268805-4e9042af9f23?w=600&auto=format&fit=crop&q=80',
      ascii: `    /\_/\
   ( o.o )
    > ^ <
 (Chat mystique)`,
      infText: '   ||  ||   ',
      infCounter: 0,
      timer: null
    };

    function triggerAction() {
      const out = document.getElementById('output');

      if (state.action === 'countdown') {
        if (state.timer) clearInterval(state.timer);
        let current = state.count;
        out.innerHTML = '<div class="countdown-num" id="num">' + current + 's</div>';
        
        state.timer = setInterval(() => {
          current--;
          const el = document.getElementById('num');
          if (el) el.innerText = current + 's';
          if (current <= 0) {
            clearInterval(state.timer);
            out.innerHTML = '<div style="font-size: 1.2rem; font-weight: bold;">' + state.endMsg + '</div>';
          }
        }, 1000);

      } else if (state.action === 'image') {
        if (state.imgUrl) {
          out.innerHTML = '<img class="revealed-img" src="' + state.imgUrl + '" alt="Happening">';
        } else {
          out.innerHTML = '<pre class="ascii-block">' + state.ascii + '</pre>';
        }

      } else if (state.action === 'infinite') {
        state.infCounter++;
        let lines = '';
        for (let i = 0; i < state.infCounter * 5; i++) {
          lines += state.infText + '\n';
        }
        out.innerHTML = '<pre class="ascii-block">' + lines + '</pre>';
        window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' });
      }
    }
  </script>
</body>
</html>

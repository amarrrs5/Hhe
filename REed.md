<!DOCTYPE html>
<html lang="mn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Уучлаарай линк</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #fff2f5;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      overflow: hidden;
    }

    .fancy-link {
      font-size: 24px;
      color: #e91e63;
      text-decoration: none;
      padding: 12px 24px;
      border-radius: 12px;
      background: linear-gradient(135deg, #ffe0e9, #ffc3cf);
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
      transition: transform 0.3s ease;
    }

    .fancy-link:hover {
      transform: scale(1.05);
    }

    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.5);
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }

    .modal-content {
      background: white;
      padding: 24px;
      border-radius: 16px;
      text-align: center;
      width: 90%;
      max-width: 350px;
      box-shadow: 0 6px 20px rgba(0,0,0,0.3);
      animation: fadeIn 0.3s ease;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.95); }
      to { opacity: 1; transform: scale(1); }
    }

    .modal button {
      margin: 10px 5px;
      padding: 10px 16px;
      font-size: 16px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }

    .yes-btn {
      background-color: #4caf50;
      color: white;
    }

    .no-btn {
      background-color: #f44336;
      color: white;
    }
    
    .flower-emoji {
      font-size: 50px;
      position: absolute;
      z-index: 9999;
      animation: scatter 2s ease-in-out forwards;
    }
    
    @keyframes scatter {
      0% {
        transform: scale(0) rotate(0deg);
        opacity: 0;
      }
      50% {
        transform: scale(1.5) rotate(360deg);
        opacity: 1;
      }
      100% {
        transform: scale(0) rotate(720deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

<a href="#" class="fancy-link" onclick="openModal()">Уучлаарай</a>

<div class="modal" id="forgiveModal">
  <div class="modal-content">
    <p id="modalText">Та уучлах уу?</p>
    <button class="yes-btn" onclick="forgive()">Уучлах</button>
    <button class="no-btn" onclick="notForgive()">Уучлахгүй</button>
  </div>
</div>

<script>
  function openModal() {
    document.getElementById("modalText").textContent = "Та уучлах уу?";
    document.getElementById("forgiveModal").style.display = "flex";
  }

  function forgive() {
    alert('Уучилсанд Баярлалаа ЭРХЭМ ДЭЭДСЭЭ!🙇‍♂️🙇‍♂️');
    // Create flower emoji effect
    createFlowerEffect();
    document.getElementById("forgiveModal").style.display = "none";
  }

  function notForgive() {
    alert('Алдаа гарлаа! Та дахин бодоорой...');
    setTimeout(openModal, 500);
  }

  function createFlowerEffect() {
    for (let i = 0; i < 20; i++) {
      const flower = document.createElement('div');
      flower.classList.add('flower-emoji');
      flower.textContent = "🌸";
      flower.style.left = Math.random() * window.innerWidth + "px";
      flower.style.top = Math.random() * window.innerHeight + "px";
      document.body.appendChild(flower);
      setTimeout(() => flower.remove(), 2000); // Remove flower after animation
    }
  }

  window.onclick = function(event) {
    const modal = document.getElementById("forgiveModal");
    if (event.target === modal) {
      modal.style.display = "none";
    }
  }
</script>

</body>
</html>

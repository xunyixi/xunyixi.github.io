---
title: 便携小空调
date: 2026-06-14 13:00:00
type: "air-conditioner"
top_img: https://source.unsplash.com/1920x1080/?cool,summer
---

<style>
.air-conditioner-page {
  text-align: center;
  max-width: 600px;
  margin: 0 auto;
}

.page-title {
  font-size: 28px;
  margin-bottom: 10px;
}

.page-subtitle {
  font-size: 16px;
  color: #666;
  margin-bottom: 30px;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  margin-bottom: 40px;
}

.stat-card {
  background: #fff;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.08);
}

.stat-value {
  font-size: 24px;
  font-weight: bold;
  color: #667eea;
}

.stat-label {
  font-size: 12px;
  color: #999;
  margin-top: 5px;
}

.ac-container {
  background: linear-gradient(145deg, #ffffff 0%, #f0f4ff 100%);
  border-radius: 24px;
  padding: 40px;
  box-shadow: 0 10px 40px rgba(102, 126, 234, 0.15);
  margin-bottom: 30px;
}

.ac-display {
  font-size: 72px;
  font-weight: bold;
  color: #667eea;
  margin-bottom: 20px;
}

.ac-controls {
  display: flex;
  justify-content: center;
  gap: 30px;
}

.ac-btn {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  border: none;
  font-size: 24px;
  cursor: pointer;
  transition: all 0.3s ease;
  background: #fff;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
}

.ac-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 20px rgba(102, 126, 234, 0.3);
}

.ac-btn:active {
  transform: scale(0.95);
}

.ac-mode {
  font-size: 16px;
  color: #666;
  margin-top: 20px;
}

.footer {
  font-size: 14px;
  color: #999;
  padding-top: 20px;
  border-top: 1px solid #eee;
}

.footer a {
  color: #667eea;
  text-decoration: none;
}

.footer a:hover {
  text-decoration: underline;
}
</style>

<div class="air-conditioner-page">
  <h1 class="page-title">便携小空调</h1>
  <p class="page-subtitle">Tip: 为你的夏日带去清凉！❄️</p>
  
  <div class="stats-grid">
    <div class="stat-card">
      <div class="stat-value">14</div>
      <div class="stat-label">文章总数</div>
    </div>
    <div class="stat-card">
      <div class="stat-value">1900</div>
      <div class="stat-label">建站天数</div>
    </div>
    <div class="stat-card">
      <div class="stat-value">35735</div>
      <div class="stat-label">全站字数</div>
    </div>
  </div>
  
  <div class="ac-container">
    <div class="ac-display" id="tempDisplay">26°C</div>
    <div class="ac-controls">
      <button class="ac-btn" id="btnMinus">−</button>
      <button class="ac-btn" id="btnPlus">+</button>
    </div>
    <div class="ac-mode" id="modeDisplay">制冷模式</div>
  </div>
  
  <div class="footer">
    © <a href="https://github.com/anzhiyu-c/air-conditioner-vue" target="_blank">AnZhiYu Air Conditioner</a>
    <br>
    <a href="https://anzhiy.cn/" target="_blank">安知鱼 @anzhiyu</a>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const tempDisplay = document.getElementById('tempDisplay');
  const modeDisplay = document.getElementById('modeDisplay');
  const btnMinus = document.getElementById('btnMinus');
  const btnPlus = document.getElementById('btnPlus');
  
  let currentTemp = 26;
  
  btnMinus.addEventListener('click', function() {
    if (currentTemp > 16) {
      currentTemp--;
      updateDisplay();
    }
  });
  
  btnPlus.addEventListener('click', function() {
    if (currentTemp < 32) {
      currentTemp++;
      updateDisplay();
    }
  });
  
  function updateDisplay() {
    tempDisplay.textContent = currentTemp + '°C';
    
    if (currentTemp <= 22) {
      modeDisplay.textContent = '强冷模式 ❄️';
      tempDisplay.style.color = '#00bcd4';
    } else if (currentTemp <= 26) {
      modeDisplay.textContent = '制冷模式 💨';
      tempDisplay.style.color = '#667eea';
    } else {
      modeDisplay.textContent = '送风模式 🌬️';
      tempDisplay.style.color = '#ff9800';
    }
  }
});
</script>
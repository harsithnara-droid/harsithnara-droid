<!DOCTYPE html>
<html>
<head>
<style>
  body { margin: 0; background: #222; overflow: hidden; }
  
  /* The Road */
  .road {
    position: relative;
    width: 300px;
    height: 100vh;
    background: #333;
    margin: auto;
    border-left: 5px solid white;
    border-right: 5px solid white;
  }

  /* Moving Road Lines */
  .road::after {
    content: '';
    position: absolute;
    width: 10px;
    height: 100%;
    left: 50%;
    transform: translateX(-50%);
    background: linear-gradient(to bottom, white 50%, transparent 50%);
    background-size: 10px 100px;
    animation: moveRoad 1s linear infinite;
  }

  /* The Player's Car */
  .player-car {
    position: absolute;
    bottom: 50px;
    left: 50%;
    transform: translateX(-50%);
    width: 50px;
    height: 80px;
    background: red;
    border-radius: 5px;
    z-index: 2;
  }

  /* Enemy Car (Animated Obstacle) */
  .enemy {
    position: absolute;
    width: 50px;
    height: 80px;
    background: green;
    border-radius: 5px;
    left: 30px;
    animation: enemyMove 3s linear infinite;
  }

  @keyframes moveRoad {
    from { background-position: 0 0; }
    to { background-position: 0 100px; }
  }

  @keyframes enemyMove {
    0% { top: -100px; left: 30px; }
    100% { top: 100vh; left: 200px; }
  }
</style>
</head>
<body>
  <div class="road">
    <div class="player-car"></div>
    <div class="enemy"></div>
  </div>
</body>
</html>

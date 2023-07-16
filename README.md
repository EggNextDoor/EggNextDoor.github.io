# EggNextDoor.github.io
<!DOCTYPE html>
<html>
<head>
  <title>比赛评价</title>
</head>
<body>
  <h1>比赛评价</h1>
  <form id="scoreForm">
    <h2>1. 氛围</h2>
    <label for="participation">观众参与度：</label>
    <input type="number" id="participation" step="0.01" min="0" max="10"><br>
    <label for="rhythm">节奏控制：</label>
    <input type="number" id="rhythm" step="0.01" min="0" max="10"><br>
    <label for="immersion">沉浸感：</label>
    <input type="number" id="immersion" step="0.01" min="0" max="10"><br>
    <label for="entertainment">娱乐价值：</label>
    <input type="number" id="entertainment" step="0.01" min="0" max="10"><br>
  
    <h2>2. 故事线评价</h2>
    <h3>2.1. 比赛前的铺垫</h3>
    <label for="conflict_trigger">冲突引发：</label>
    <input type="number" id="conflict_trigger" step="0.01" min="0" max="10"><br>
    <label for="conflict_development">冲突发展：</label>
    <input type="number" id="conflict_development" step="0.01" min="0" max="10"><br>
  
    <h3>2.2. 对未来故事线的影响</h3>
    <label for="future_influence">对未来故事线的影响：</label>
    <input type="number" id="future_influence" step="0.01" min="0" max="10"><br>
  
    <h2>3. 关注度和讨论度</h2>
    <label for="expectation">比赛前的期待：</label>
    <input type="number" id="expectation" step="0.01" min="0" max="10"><br>
    <label for="pre_discussion">比赛前的讨论：</label>
    <input type="number" id="pre_discussion" step="0.01" min="0" max="10"><br>
    <label for="suspense">悬念：</label>
    <input type="number" id="suspense" step="0.01" min="0" max="10"><br>
    <label for="post_discussion">比赛后的讨论：</label>
    <input type="number" id="post_discussion" step="0.01" min="0" max="10"><br>
  
    <h2>4. 重要性</h2>
    <label for="competitors">对竞争对手之间的影响：</label>
    <input type="number" id="competitors" step="0.01" min="0" max="10"><br>
    <label for="champion">对冠军变动或防御的影响：</label>
    <input type="number" id="champion" step="0.01" min="0" max="10"><br>
    <label for="storyline">对故事线发展的影响：</label>
    <input type="number" id="storyline" step="0.01" min="0" max="10"><br>
  
    <br>
    <input type="button" value="计算总得分" onclick="calculateScore()">
  </form>
  
  <h2>总得分：</h2>
  <p id="totalScore"></p>
  
  <script>
    function calculateScore() {
      // 获取子元素的值
      var atmosphere_participation = parseFloat(document.getElementById("participation").value) || 0;
      var atmosphere_rhythm = parseFloat(document.getElementById("rhythm").value) || 0;
      var atmosphere_immersion = parseFloat(document.getElementById("immersion").value) || 0;
      var atmosphere_entertainment = parseFloat(document.getElementById("entertainment").value) || 0;
  
      var preparation_conflict_trigger = parseFloat(document.getElementById("conflict_trigger").value) || 0;
      var preparation_conflict_development = parseFloat(document.getElementById("conflict_development").value) || 0;
  
      var future_influence = parseFloat(document.getElementById("future_influence").value) || 0;
  
      var engagement_expectation = parseFloat(document.getElementById("expectation").value) || 0;
      var engagement_pre_discussion = parseFloat(document.getElementById("pre_discussion").value) || 0;
      var engagement_suspense = parseFloat(document.getElementById("suspense").value) || 0;
      var engagement_post_discussion = parseFloat(document.getElementById("post_discussion").value) || 0;
  
      var impact_competitors = parseFloat(document.getElementById("competitors").value) || 0;
      var impact_champion = parseFloat(document.getElementById("champion").value) || 0;
      var impact_storyline = parseFloat(document.getElementById("storyline").value) || 0;
  
      // 计算子元素的占比得分
      var atmosphere_score = 0.35 * (0.6 * (0.3 * atmosphere_participation + 0.3 * atmosphere_rhythm + 0.2 * atmosphere_immersion + 0.2 * atmosphere_entertainment));
      var preparation_score = 0.35 * (0.6 * (0.5 * preparation_conflict_trigger + 0.5 * preparation_conflict_development));
      var future_influence_score = 0.25 * (0.4 * future_influence);
      var engagement_score = 0.15 * (0.2 * engagement_expectation + 0.25 * engagement_pre_discussion + 0.25 * engagement_suspense + 0.3 * engagement_post_discussion);
      var impact_score = 0.25 * (0.4 * impact_competitors + 0.15 * impact_champion + 0.45 * impact_storyline);
  
      // 计算总得分
      var total_score = atmosphere_score + preparation_score + future_influence_score + engagement_score + impact_score;
  
      // 如果所有子元素的值相同，则总得分等于子元素的值
      if (
        atmosphere_participation === atmosphere_rhythm &&
        atmosphere_rhythm === atmosphere_immersion &&
        atmosphere_immersion === atmosphere_entertainment &&
        preparation_conflict_trigger === preparation_conflict_development &&
        future_influence === engagement_expectation &&
        engagement_expectation === engagement_pre_discussion &&
        engagement_pre_discussion === engagement_suspense &&
        engagement_suspense === engagement_post_discussion &&
        engagement_post_discussion === impact_competitors &&
        impact_competitors === impact_champion &&
        impact_champion === impact_storyline
      ) {
        total_score = atmosphere_participation;
      }
  
      // 显示总得分
      document.getElementById("totalScore").textContent = total_score.toFixed(2);
    }
  </script>
</body>
</html>

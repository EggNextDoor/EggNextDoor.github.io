# EggNextDoor.github.io
<!DOCTYPE html>
<html>
<head>
  <title>Pro Wrestling Match Rating System</title>
  <script>
    function calculateTotalScore() {
      // 获取用户输入的每个子元素的数值
      var audienceEngagement = parseFloat(document.getElementById('audience-engagement').value);
      var paceControl = parseFloat(document.getElementById('pace-control').value);
      var sellingImmersion = parseFloat(document.getElementById('selling-immersion').value);
      var entertainmentValue = parseFloat(document.getElementById('entertainment-value').value);
      var mistakes = parseFloat(document.getElementById('mistakes').value);
      var chemistry = parseFloat(document.getElementById('chemistry').value);
      var highPoints = parseFloat(document.getElementById('high-points').value);
      var gimmicks = parseFloat(document.getElementById('gimmicks').value);
      var variety = parseFloat(document.getElementById('variety').value);
      var conflictInitiation = parseFloat(document.getElementById('conflict-initiation').value);
      var conflictBuildup = parseFloat(document.getElementById('conflict-buildup').value);
      var futureStoryline = parseFloat(document.getElementById('future-storyline').value);
      var preMatchAnticipation = parseFloat(document.getElementById('pre-match-anticipation').value);
      var preMatchDiscussion = parseFloat(document.getElementById('pre-match-discussion').value);
      var suspense = parseFloat(document.getElementById('suspense').value);
      var postMatchDiscussion = parseFloat(document.getElementById('post-match-discussion').value);
      var rivalryInfluence = parseFloat(document.getElementById('rivalry-influence').value);
      var championshipImpact = parseFloat(document.getElementById('championship-impact').value);
      var storylineProgression = parseFloat(document.getElementById('storyline-progression').value);

      // 计算每个子元素的得分
      var atmosphere = (audienceEngagement * 0.3) + (paceControl * 0.3) + (sellingImmersion * 0.2) + (entertainmentValue * 0.2);
      var moves = (mistakes * 0.2) + (chemistry * 0.2) + (highPoints * 0.3) + (gimmicks * 0.1) + (variety * 0.2);
      var storyline = (conflictInitiation * 0.5) + (conflictBuildup * 0.5) + (futureStoryline * 0.4);
      var attentionDiscussion = (preMatchAnticipation * 0.2) + (preMatchDiscussion * 0.25) + (suspense * 0.25) + (postMatchDiscussion * 0.3);
      var significance = (rivalryInfluence * 0.4) + (championshipImpact * 0.15) + (storylineProgression * 0.45);

      // 计算总得分
      var totalScore = (atmosphere * 0.35) + (moves * 0.4) + (storyline * 0.25) + (attentionDiscussion * 0.15) + (significance * 0.25);

      // 显示总得分
      document.getElementById('total-score').innerHTML = "总得分: " + totalScore.toFixed(2);
    }
  </script>
</head>
<body>
  <h1>Pro Wrestling Match Rating System</h1>
  <h2>比赛评分系统</h2>
  
  <h3>1. 比赛评价：（35%）</h3>
  <h4>1.1. 氛围：（60%）</h4>
  <label>观众参与度（30%）：<input type="number" id="audience-engagement" step="0.01"></label><br>
  <label>节奏控制（30%）：<input type="number" id="pace-control" step="0.01"></label><br>
  <label>sell/沉浸感（20%）：<input type="number" id="selling-immersion" step="0.01"></label><br>
  <label>娱乐价值（20%）：<input type="number" id="entertainment-value" step="0.01"></label><br>
  
  <h4>1.2. 动作表现：（40%）</h4>
  <label>失误次数（20%）：<input type="number" id="mistakes" step="0.01"></label><br>
  <label>参与者之间的默契（20%）：<input type="number" id="chemistry" step="0.01"></label><br>
  <label>高潮点/还击动作（30%）：<input type="number" id="high-points" step="0.01"></label><br>
  <label>吉米克融入（10%）：<input type="number" id="gimmicks" step="0.01"></label><br>
  <label>多样性（20%）：<input type="number" id="variety" step="0.01"></label><br>
  
  <h3>2. 故事线评价：（25%）</h3>
  <h4>2.1. 比赛前的铺垫：（60%）</h4>
  <label>冲突引发（50%）：<input type="number" id="conflict-initiation" step="0.01"></label><br>
  <label>冲突发展（多场比赛效果）（50%）：<input type="number" id="conflict-buildup" step="0.01"></label><br>
  
  <h4>2.2. 对未来故事线的影响（40%）</h4>
  <label>对未来故事线的影响（40%）：<input type="number" id="future-storyline" step="0.01"></label><br>
  
  <h3>3. 关注度和讨论度：（15%）</h3>
  <label>比赛前的期待（20%）：<input type="number" id="pre-match-anticipation" step="0.01"></label><br>
  <label>比赛前的讨论（25%）：<input type="number" id="pre-match-discussion" step="0.01"></label><br>
  <label>悬念（25%）：<input type="number" id="suspense" step="0.01"></label><br>
  <label>比赛后的讨论（30%）：<input type="number" id="post-match-discussion" step="0.01"></label><br>
  
  <h3>4. 重要性：（25%）</h3>
  <label>对竞争对手之间的影响（40%）：<input type="number" id="rivalry-influence" step="0.01"></label><br>
  <label>对冠军变动或防御的影响（15%）：<input type="number" id="championship-impact" step="0.01"></label><br>
  <label>对故事线发展的影响（45%）：<input type="number" id="storyline-progression" step="0.01"></label><br>
  
  <button onclick="calculateTotalScore()">计算总得分</button>
  <div id="total-score"></div>
</body>
</html>

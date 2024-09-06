<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>應用程式體驗問卷調查</title>
    <script>
        function submitForm() {
            // 取得表單數據
            const data = {
                satisfaction: document.querySelector('input[name="satisfaction"]:checked').value,
                difficulty: document.querySelector('input[name="difficulty"]:checked').value,
                helpfulFeatures: Array.from(document.querySelectorAll('input[name="helpfulFeatures"]:checked')).map(input => input.value),
                encounteredProblems: document.querySelector('input[name="encounteredProblems"]:checked').value,
                problemDescription: document.getElementById('problemDescription').value,
                improvements: Array.from(document.querySelectorAll('input[name="improvements"]:checked')).map(input => input.value),
                recommend: document.querySelector('input[name="recommend"]:checked').value,
                otherFeedback: document.getElementById('otherFeedback').value
            };

            // 將數據轉換為JSON並顯示在控制台
            console.log(JSON.stringify(data));

            // 模擬表單提交成功的提示
            alert("問卷提交成功！感謝您的回覆！");
            
            // 清除表單
            document.getElementById("surveyForm").reset();
        }
    </script>
</head>
<body>
    <h2>評價您的應用程式體驗</h2>
    <form id="surveyForm" onsubmit="event.preventDefault(); submitForm();">

        <p>1. 您對這次挑戰的整體滿意度如何？</p>
        <input type="radio" name="satisfaction" value="1" required> 1
        <input type="radio" name="satisfaction" value="2"> 2
        <input type="radio" name="satisfaction" value="3"> 3
        <input type="radio" name="satisfaction" value="4"> 4
        <input type="radio" name="satisfaction" value="5"> 5

        <p>2. 您認為這個挑戰的難度如何？</p>
        <input type="radio" name="difficulty" value="easy" required> 太容易
        <input type="radio" name="difficulty" value="medium"> 適中
        <input type="radio" name="difficulty" value="hard"> 太難

        <p>3. 挑戰期間，您覺得哪些功能最有幫助？（多選）</p>
        <input type="checkbox" name="helpfulFeatures" value="autoSave"> 自動儲蓄功能<br>
        <input type="checkbox" name="helpfulFeatures" value="goalSetting"> 儲蓄目標設定<br>
        <input type="checkbox" name="helpfulFeatures" value="challengeReminder"> 儲蓄挑戰提醒<br>
        <input type="checkbox" name="helpfulFeatures" value="progressTracking"> 儲蓄進度追蹤<br>
        <input type="checkbox" name="helpfulFeatures" value="other"> 其他：<input type="text" id="otherFeature"><br>

        <p>4. 您是否在儲蓄過程中遇到困難？</p>
        <input type="radio" name="encounteredProblems" value="yes" required> 是<br>
        <input type="radio" name="encounteredProblems" value="no"> 否<br>
        若有，請簡單描述遇到的困難：<input type="text" id="problemDescription"><br>

        <p>5. 您認為可以改進哪些方面？（多選）</p>
        <input type="checkbox" name="improvements" value="ui"> 使用界面<br>
        <input type="checkbox" name="improvements" value="rules"> 挑戰規則說明<br>
        <input type="checkbox" name="improvements" value="notifications"> 通知系統<br>
        <input type="checkbox" name="improvements" value="otherImprovement"> 其他：<input type="text" id="otherImprovement"><br>

        <p>6. 您會向朋友或家人推薦此應用程式嗎？</p>
        <input type="radio" name="recommend" value="yes" required> 會<br>
        <input type="radio" name="recommend" value="maybe"> 可能會<br>
        <input type="radio" name="recommend" value="no"> 不會<br>

        <p>7. 您還有其他意見或建議嗎？</p>
        <textarea id="otherFeedback" rows="4" cols="50"></textarea><br><br>

        <input type="submit" value="提交">
    </form>
</body>
</html>

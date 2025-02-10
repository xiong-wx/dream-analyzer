# dream-analyzer
<!DOCTYPE html>

<html lang="zh-CN">

<head>

    <meta charset="UTF-8">

    <title>AI梦境解析工具</title>

    <style>

        body {font-family: -apple-system, sans-serif; max-width: 800px; margin: 20px auto; padding: 15px}

        .card {background: #f8f9fa; border-radius: 10px; padding: 20px; margin: 15px 0; box-shadow: 0 2px 4px rgba(0,0,0,0.1)}

        input, textarea {width: 100%; padding: 8px; margin: 5px 0; border: 1px solid #ddd}

        button {background: #007bff; color: white; border: none; padding: 10px 20px; border-radius: 5px}

        .result-section {display: none}

    </style>

</head>

<body>

    <div class="card" id="inputSection">

        <h2>🛌 梦境解析工具</h2>

        <div>

            <label>梦境细节：</label>

            <textarea id="dreamDetail" placeholder="例：在海边追逐会飞的鱼..." rows="3"></textarea>

        </div>

        <div>

            <label>梦中情绪：</label>

            <input type="text" id="emotion" placeholder="例：焦虑混合希望">

        </div>

        <div>

            <label>醒后状态：</label>

            <input type="text" id="awakeState" placeholder="例：疲惫但释然">

        </div>

        <div>

            <label>近期现实关联：</label>

            <input type="text" id="reality" placeholder="例：准备离婚、申请留学">

        </div>

        <button onclick="analyzeDream()">开始解析</button>

    </div>



    <div class="card result-section" id="resultSection">

        <h2>🔮 解析结果</h2>

        <div id="interpretationOutput"></div>

        <button onclick="location.reload()">重新开始</button>

    </div>



    <script>

        function analyzeDream() {

            // 收集用户输入

            const details = document.getElementById('dreamDetail').value

            const emotion = document.getElementById('emotion').value

            const awake = document.getElementById('awakeState').value

            const reality = document.getElementById('reality').value



            // 生成解析报告

            const report = `

                <h3>🔍 关键意象解析</h3>

                <p><strong>核心矛盾：</strong>${reality ? `${reality.split('、')[0]}引发` : ''}的${emotion || "潜在冲突"}</p>

                <p>1. 关键符号呈现${details.includes('无法') ? '受阻状态' : '动态发展'}</p>

                <p>2. ${emotion || "复杂情绪"}折射${reality ? reality.slice(0,10) : "现实"}压力点</p>



                <h3>💡 情绪-现实关联</h3>

                <p>• <strong>${awake || "醒后残留情感"}：</strong>反映${reality ? reality : "生活转折"}期的心理代偿机制</p>

                <p>• 梦境与现实的共鸣强度：${Math.floor(Math.random()*40+50)}%</p>



                <h3>🗓️ 行动建议</h3>

                <p>1. 建立「${details.split('，')[0]?.slice(0,4) || "意象"}-现实」对照日记</p>

                <p>2. 未来7天每日记录：${emotion || "相似情绪"}触发点</p>



                <h3>🎯 准确度声明</h3>

                <p>当前信息匹配度：${details.length > 20 ? '60%-75%' : '40%-55%'}<br>

                <small>建议${reality ? "结合现实事件" : "补充更多细节"}提升准确性</small></p>

            `



            // 显示结果

            document.getElementById('interpretationOutput').innerHTML = report

            document.getElementById('inputSection').style.display = 'none'

            document.getElementById('resultSection').style.display = 'block'

        }

    </script>

</body>

</html>

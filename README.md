# a
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>取向趣味小自测</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Microsoft Yahei", sans-serif;
        }
        body {
            background-color: #fff7f2;
            color: #59443b;
            padding: 20px;
        }
        .wrap {
            max-width: 640px;
            margin: 0 auto;
            background: #ffffff;
            border-radius: 22px;
            padding: 30px;
            box-shadow: 0 4px 16px #f0dcd0;
        }
        h1 {
            text-align: center;
            color: #b98c7a;
            margin-bottom: 12px;
            font-size: 24px;
        }
        .tip {
            text-align: center;
            font-size:14px;
            color:#99847b;
            margin-bottom:28px;
        }
        .progress{
            text-align:center;
            margin-bottom:20px;
            color:#b98c7a;
        }
        .q-item {
            display: none;
        }
        .q-item.active {
            display: block;
        }
        .q-text {
            font-size:16px;
            margin-bottom:16px;
            line-height:1.6;
        }
        .opt {
            display:block;
            padding:11px 14px;
            border:1px solid #f0dcd0;
            border-radius:12px;
            margin:8px 0;
            cursor:pointer;
            transition:0.2s;
        }
        .opt:hover {
            background-color:#fff0e9;
        }
        input {
            margin-right:8px;
        }
        .btn-row{
            display:flex;
            gap:12px;
            margin-top:26px;
        }
        button{
            flex:1;
            padding:12px;
            border:none;
            border-radius:14px;
            font-size:16px;
            cursor:pointer;
        }
        #prevBtn{
            background:#f1ddd4;
            color:#6b534a;
        }
        #nextBtn{
            background:#d8b9a9;
            color:white;
        }
        #restartBtn{
            width:100%;
            margin-top:22px;
            background:#f1ddd4;
            color:#6b534a;
        }
        #prevBtn:disabled{
            opacity:0.45;
            cursor:not-allowed;
        }
        #resultBox {
            margin-top:26px;
            padding:22px;
            background:#fff2ec;
            border-radius:16px;
            display:none;
        }
        .res-title {
            font-size:21px;
            color:#b98c7a;
            font-weight:bold;
            margin-bottom:10px;
        }
        .res-desc {
            line-height:1.7;
            font-size:15px;
            margin-bottom:20px;
        }
        .chart-box{
            width:90%;
            height:340px;
            margin:0 auto;
        }
    </style>
</head>
<body>
    <div class="wrap">
        <h1>取向趣味小自测</h1>
        <div class="tip">凭第一感觉选择，本测试仅趣味参考✨</div>
        <div class="progress" id="progress">第 1 / 11 题</div>
        <div id="quizBox">
            <!-- 第1题 -->
            <div class="q-item active" data-index="0">
                <div class="q-text">1. 更容易对哪一类人产生心动、好感？</div>
                <label class="opt"><input type="radio" name="q0" value="h"> 和自己性别不同的人</label>
                <label class="opt"><input type="radio" name="q0" value="g"> 和自己性别相同的人</label>
                <label class="opt"><input type="radio" name="q0" value="b"> 两种性别都有可能</label>
                <label class="opt"><input type="radio" name="q0" value="a"> 很难对别人产生心动感</label>
                <label class="opt"><input type="radio" name="q0" value="l"> 容易心动，但对方喜欢自己之后好感会变淡</label>
            </div>
            <!-- 第2题（已经修复！） -->
            <div class="q-item" data-index="1">
                <div class="q-text">2. 当喜欢的人主动向你表达好感，你的感受是？</div>
                <label class="opt"><input type="radio" name="q1" value="h"> 对方是异性的话，很开心，愿意靠近发展</label>
                <label class="opt"><input type="radio" name="q1" value="g"> 对方是同性的话，很开心，愿意靠近发展</label>
                <label class="opt"><input type="radio" name="q1" value="b"> 不管对方性别，只要我喜欢就愿意靠近发展</label>
                <label class="opt"><input type="radio" name="q1" value="a"> 没什么波澜，不太在意</label>
                <label class="opt"><input type="radio" name="q1" value="l"> 好感快速消退，甚至想躲开</label>
            </div>
            <!-- 第3题 -->
            <div class="q-item" data-index="2">
                <div class="q-text">3. 想象亲密恋爱画面，你的感受是？</div>
                <label class="opt"><input type="radio" name="q2" value="h"> 会幻想和异性的亲密相处</label>
                <label class="opt"><input type="radio" name="q2" value="g"> 会幻想和同性的亲密相处</label>
                <label class="opt"><input type="radio" name="q2" value="b"> 和不同性别的人都可以想象</label>
                <label class="opt"><input type="radio" name="q2" value="a"> 很少想象亲密恋爱场景</label>
                <label class="opt"><input type="radio" name="q2" value="l"> 只喜欢暗恋、单向心动的感觉</label>
            </div>
            <!-- 第4题 -->
            <div class="q-item" data-index="3">
                <div class="q-text">4. 看到别人甜甜的恋爱，你会向往吗？</div>
                <label class="opt"><input type="radio" name="q3" value="h"> 向往，希望拥有和异性的恋爱</label>
                <label class="opt"><input type="radio" name="q3" value="g"> 向往，希望拥有和同性的恋爱</label>
                <label class="opt"><input type="radio" name="q3" value="b"> 向往，不限对方性别</label>
                <label class="opt"><input type="radio" name="q3" value="a"> 并不向往恋爱关系</label>
                <label class="opt"><input type="radio" name="q3" value="l"> 只喜欢看别人的故事，自己不想被喜欢</label>
            </div>
            <!-- 第5题 -->
            <div class="q-item" data-index="4">
                <div class="q-text">5. 性别会不会影响你对一个人的心动？</div>
                <label class="opt"><input type="radio" name="q4" value="h"> 只会对异性心动</label>
                <label class="opt"><input type="radio" name="q4" value="g"> 只会对同性心动</label>
                <label class="opt"><input type="radio" name="q4" value="b"> 心动看个人，不看性别</label>
                <label class="opt"><input type="radio" name="q4" value="a"> 几乎很难对任何人动心</label>
                <label class="opt"><input type="radio" name="q4" value="l"> 心动不受性别限制，但害怕双向奔赴</label>
            </div>
            <!-- 第6题 -->
            <div class="q-item" data-index="5">
                <div class="q-text">6. 你对牵手、拥抱这类亲密接触的期待是？</div>
                <label class="opt"><input type="radio" name="q5" value="h"> 期待和异性亲密接触</label>
                <label class="opt"><input type="radio" name="q5" value="g"> 期待和同性亲密接触</label>
                <label class="opt"><input type="radio" name="q5" value="b"> 合适的人，不管性别都可以</label>
                <label class="opt"><input type="radio" name="q5" value="a"> 不太期待亲密肢体接触</label>
                <label class="opt"><input type="radio" name="q5" value="l"> 喜欢幻想亲密，但对方靠近就会退缩</label>
            </div>
            <!-- 第7题 -->
            <div class="q-item" data-index="6">
                <div class="q-text">7. 如果有机会谈恋爱，你更偏向？</div>
                <label class="opt"><input type="radio" name="q6" value="h"> 和异性发展恋爱</label>
                <label class="opt"><input type="radio" name="q6" value="g"> 和同性发展恋爱</label>
                <label class="opt"><input type="radio" name="q6" value="b"> 不限性别，看感觉</label>
                <label class="opt"><input type="radio" name="q6" value="a"> 不太想要恋爱关系</label>
                <label class="opt"><input type="radio" name="q6" value="l"> 享受单向喜欢，不想确定恋爱</label>
            </div>
            <!-- 第8题 -->
            <div class="q-item" data-index="7">
                <div class="q-text">8. 更容易被哪种类型的人吸引？</div>
                <label class="opt"><input type="radio" name="q7" value="h"> 异性</label>
                <label class="opt"><input type="radio" name="q7" value="g"> 同性</label>
                <label class="opt"><input type="radio" name="q7" value="b"> 同性异性都有可能</label>
                <label class="opt"><input type="radio" name="q7" value="a"> 很少被别人吸引</label>
                <label class="opt"><input type="radio" name="q7" value="l"> 只吸引于不喜欢自己的人</label>
            </div>
            <!-- 第9题 -->
            <div class="q-item" data-index="8">
                <div class="q-text">9. 想象和恋人长期相处，你的感受？</div>
                <label class="opt"><input type="radio" name="q8" value="h"> 和异性长期相处会觉得舒服期待</label>
                <label class="opt"><input type="radio" name="q8" value="g"> 和同性长期相处会觉得舒服期待</label>
                <label class="opt"><input type="radio" name="q8" value="b"> 遇到对的人，和任何性别都可以</label>
                <label class="opt"><input type="radio" name="q8" value="a"> 不太向往长期恋爱关系</label>
                <label class="opt"><input type="radio" name="q8" value="l"> 喜欢幻想长期恋爱，现实里会逃避</label>
            </div>
            <!-- 第10题 -->
            <div class="q-item" data-index="9">
                <div class="q-text">10. 你对“双向奔赴的恋爱”看法是？</div>
                <label class="opt"><input type="radio" name="q9" value="h"> 期待和异性双向奔赴</label>
                <label class="opt"><input type="radio" name="q9" value="g"> 期待和同性双向奔赴</label>
                <label class="opt"><input type="radio" name="q9" value="b"> 期待双向奔赴，不限性别</label>
                <label class="opt"><input type="radio" name="q9" value="a"> 对双向奔赴没有期待</label>
                <label class="opt"><input type="radio" name="q9" value="l"> 害怕真正的双向奔赴</label>
            </div>
            <!-- 第11题 -->
            <div class="q-item" data-index="10">
                <div class="q-text">11. 如果有同性说喜欢你，你的第一反应是？</div>
                <label class="opt"><input type="radio" name="q10" value="h"> 没有心动，只能做朋友</label>
                <label class="opt"><input type="radio" name="q10" value="g"> 惊喜，我也有可能喜欢对方</label>
                <label class="opt"><input type="radio" name="q10" value="b"> 看我对TA有没有感觉，性别无所谓</label>
                <label class="opt"><input type="radio" name="q10" value="a"> 不管是谁表白，都很难产生恋爱心动</label>
                <label class="opt"><input type="radio" name="q10" value="l"> 一瞬间慌乱，如果对方喜欢我我就没感觉了</label>
            </div>
            <div class="btn-row">
                <button id="prevBtn" disabled>上一题</button>
                <button id="nextBtn">下一题</button>
            </div>
        </div>
        <div id="resultBox">
            <div class="res-title"></div>
            <div class="res-desc"></div>
            <div class="chart-box">
                <canvas id="pieChart"></canvas>
            </div>
            <button id="restartBtn">重新测试</button>
        </div>
    </div>

<script>
let current = 0;
const total = 11;
const prevBtn = document.getElementById("prevBtn");
const nextBtn = document.getElementById("nextBtn");
const restartBtn = document.getElementById("restartBtn");
const progressEl = document.getElementById("progress");
const quizBox = document.getElementById("quizBox");
const resultBox = document.getElementById("resultBox");
let chartIns = null;

function showPage(idx){
    document.querySelectorAll(".q-item").forEach(el=>el.classList.remove("active"));
    document.querySelector(`.q-item[data-index="${idx}"]`).classList.add("active");
    progressEl.innerText = `第 ${idx+1} / ${total} 题`;
    prevBtn.disabled = idx === 0;
    if(idx === total -1){
        nextBtn.innerText = "查看结果";
    }else{
        nextBtn.innerText = "下一题";
    }
}

prevBtn.onclick = ()=>{
    if(current > 0){
        current--;
        showPage(current);
    }
}
nextBtn.onclick = ()=>{
    if(current < total -1){
        current++;
        showPage(current);
    }else{
        calcResult();
    }
}

restartBtn.onclick = () => {
    document.querySelectorAll('input[type="radio"]').forEach(radio=>{
        radio.checked = false;
    })
    current = 0;
    quizBox.style.display = "block";
    resultBox.style.display = "none";
    if(chartIns) chartIns.destroy();
    showPage(0);
}

function calcResult(){
    let score = {h:0,g:0,b:0,a:0,l:0};
    for(let i=0;i<total;i++){
        const sel = document.querySelector(`input[name="q${i}"]:checked`);
        if(!sel){
            alert("请答完所有题目！");
            return;
        }
        score[sel.value]++;
    }
    quizBox.style.display = "none";
    resultBox.style.display = "block";
    let maxKey = Object.keys(score).reduce((a,b)=>score[a]>score[b]?a:b);
    const info = {
        h:{name:"异性恋",desc:"你更容易对和自己性别不同的人产生浪漫心动，向往异性之间的亲密恋爱关系。"},
        g:{name:"同性恋",desc:"你更容易被和自己同性别的人吸引，浪漫心动的对象偏向同性。"},
        b:{name:"双性恋",desc:"心动看个人本身，对方的性别不会成为阻碍，同性、异性都有可能让你喜欢上。"},
        a:{name:"无性恋",desc:"你很少感受到浪漫心动，对恋爱、亲密关系的需求比较低，不代表无法拥有温暖的友谊。"},
        l:{name:"性单恋",desc:"你很容易产生暗恋、单向的喜欢，但是当对方回应你的好感，心动感往往会快速消退。"}
    }
    document.querySelector(".res-title").innerText = `你的结果：${info[maxKey].name}`;
    document.querySelector(".res-desc").innerText = info[maxKey].desc;

    const ctx = document.getElementById("pieChart").getContext("2d");
    if(chartIns) chartIns.destroy();
    chartIns = new Chart(ctx,{
        type:"pie",
        data:{
            labels:["异性恋","同性恋","双性恋","无性恋","性单恋"],
            datasets:[{
                data:[score.h,score.g,score.b,score.a,score.l],
                backgroundColor:["#e8b9a7","#d8a9c2","#b9a7d8","#a7c6e8","#e8c8a7"]
            }]
        },
        options:{
            responsive:true,
            maintainAspectRatio:false,
            plugins:{legend:{position:"bottom"}}
        }
    })
}
showPage(0);
</script>
</body>
</html>

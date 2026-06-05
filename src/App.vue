<template>
  <div class="app-wrapper">
      
    <!-- ================= 【頂部導覽列】 ================= -->
    <header class="app-header">
      <div class="logo">☕ 咖啡教學指南</div>
      <nav class="nav-tabs">
        <button class="nav-btn" :class="{ active: currentTab === 'home' }" @click="currentTab = 'home'">首頁</button>
        <button class="nav-btn" :class="{ active: currentTab === 'intro' }" @click="currentTab = 'intro'">咖啡豆介紹</button>
        <button class="nav-btn" :class="{ active: currentTab === 'equipment' }" @click="currentTab = 'equipment'">器材介紹</button>
        <button class="nav-btn" :class="{ active: currentTab === 'tools' }" @click="currentTab = 'tools'">實用工具</button>
        <button class="nav-btn" :class="{ active: currentTab === 'tutorial' }" @click="currentTab = 'tutorial'">沖泡步驟</button>
        <button class="nav-btn" :class="{ active: currentTab === 'quiz' }" @click="currentTab = 'quiz'">測驗</button>
      </nav>
    </header>

    <main class="main-content">
      <div class="coffee-app-container">
        
        <!-- 主要過場動畫切換：分頁內容 -->
        <Transition name="fade" mode="out-in">
          
          <!-- ================= 【首頁：咖啡簡單介紹】 ================= -->
          <div v-if="currentTab === 'home'" key="home" class="home-view">
            <h1 class="main-title">探索手沖咖啡的藝術</h1>
            <p class="main-desc">
              咖啡，不僅僅是一杯提神的飲品，更是一門充滿細節與講究的藝術。<br>
              從挑選合適的咖啡豆、掌握精準的水溫，到注水的節奏與力道，每一個步驟都決定了最終的風味呈現。<br><br>
              在這個教學指南中，我們將帶您一步步認識咖啡豆的奧秘，並親手體驗沖煮出一杯完美手沖咖啡的樂趣。
            </p>
            <div class="home-action">
              <button class="btn btn-primary" @click="currentTab = 'intro'">開始探索</button>
            </div>
          </div>

          <!-- ================= 【第一部分：咖啡豆介紹】 ================= -->
          <div v-else-if="currentTab === 'intro'" key="intro" class="intro-view">
            <h2 class="view-title">🌱 認識咖啡豆</h2>
            
            <h3 class="section-subtitle">烘焙程度 (Roast Levels)</h3>
            <div class="intro-cards">
              <div class="intro-card">
                <h3>淺焙 (Light Roast)</h3>
                <p>保留最多咖啡豆原始風味，帶有明亮的果酸與花草香氣，適合喜歡清新口感的人。</p>
              </div>
              <div class="intro-card">
                <h3>中焙 (Medium Roast)</h3>
                <p>酸鹼平衡，展現堅果、焦糖或巧克力的甜感，是大眾最能接受的經典風味。</p>
              </div>
              <div class="intro-card">
                <h3>深焙 (Dark Roast)</h3>
                <p>酸度極低，醇厚度高，帶有濃郁的烘焙香氣與苦甜巧克力風味，加牛奶也非常適合。</p>
              </div>
            </div>
            
            <h3 class="section-subtitle">處理法 (Processing Methods)</h3>
            <div class="intro-cards">
              <div class="intro-card">
                <h3>日曬法 (Natural)</h3>
                <p>將咖啡果實直接在陽光下曝曬乾燥。通常帶有濃郁的熱帶水果香氣與較高的甜度，口感醇厚。</p>
              </div>
              <div class="intro-card">
                <h3>水洗法 (Washed)</h3>
                <p>去除果肉後放入水槽發酵，洗淨後再乾燥。風味乾淨明亮，酸質清晰，能完美展現產地特色。</p>
              </div>
              <div class="intro-card">
                <h3>蜜處理 (Honey)</h3>
                <p>去除部分果肉，保留果膠層進行乾燥。風味介於日曬與水洗之間，具有極佳的甜感與溫和的酸度。</p>
              </div>
            </div>

            <h3 class="section-subtitle">🌍 世界咖啡產區特色</h3>
            <div class="intro-cards">
              <div class="intro-card">
                <div class="card-image-container">
                  <img src="https://images.unsplash.com/photo-1611162458324-aae1eb4129a4?auto=format&fit=crop&w=600&q=80" alt="衣索比亞" class="card-image">
                </div>
                <h3>🇪🇹 衣索比亞 (Ethiopia)</h3>
                <p>咖啡的發源地。以水洗的清新柑橘、茉莉花香，以及日曬的濃郁莓果、狂野甜感聞名。</p>
              </div>
              <div class="intro-card">
                <div class="card-image-container">
                  <img src="https://wp-cdn.soezso.com/2022/05/0cc29df3-coffee_country_05.jpg" alt="哥倫比亞" class="card-image">
                </div>
                <h3>🇨🇴 哥倫比亞 (Colombia)</h3>
                <p>風味均衡，口感滑順。常帶有焦糖、巧克力甜香及柔和的堅果風味，是大眾接受度極高的產區。</p>
              </div>
              <div class="intro-card">
                <div class="card-image-container">
                  <img src="https://images.unsplash.com/photo-1506377247377-2a5b3b417ebb?auto=format&fit=crop&w=600&q=80" alt="印尼" class="card-image">
                </div>
                <h3>🇮🇩 印尼 (Indonesia)</h3>
                <p>以獨特的「濕剝法」處理著名。醇厚度極高，帶有香料、木質與草本植物的沈穩風味。</p>
              </div>
            </div>
          </div>

          <!-- ================= 【新增：實用工具區】 ================= -->
          <div v-else-if="currentTab === 'tools'" key="tools" class="tools-view">
            <h2 class="view-title">🛠️ 實用工具箱</h2>
            <div class="tools-container">
              <div class="tool-card">
                <h3>🧮 粉水比計算機</h3>
                <div class="input-group">
                  <label>咖啡粉重量 (g)：</label>
                  <input type="number" v-model="coffeePowder" min="1" class="tool-input">
                </div>
                <div class="input-group">
                  <label>目標粉水比 (1:X)：</label>
                  <input type="number" v-model="waterRatio" min="1" class="tool-input">
                </div>
                <div class="result-box">
                  總注水量：<strong>{{ coffeePowder * waterRatio }}</strong> ml
                </div>
              </div>
              
              <div class="tool-card">
                <h3>⏱️ 沖煮計時器</h3>
                <div class="timer-display" :class="{'running': isTimerRunning}">{{ formattedTime }}</div>
                <div class="navigation-buttons">
                  <button class="btn btn-secondary" @click="resetTimer">重置</button>
                  <button class="btn btn-primary" @click="toggleTimer">
                    {{ isTimerRunning ? '暫停' : '開始' }}
                  </button>
                </div>
              </div>
            </div>
          </div>

          <!-- ================= 【第二部分：器材介紹】 ================= -->
          <div v-else-if="currentTab === 'equipment'" key="equipment" class="equipment-view">
            <h2 class="view-title">⚖️ 必備器材介紹</h2>
            <div class="intro-cards">
              <div class="intro-card">
                <div class="card-image-container">
                  <img src="https://cdn-general.cybassets.com/media/W1siZiIsIjgxMTUvcHJvZHVjdHMvZTlmZjAxNjUyYWZlZWE2MTE3ZTEzNTUyYWQ0ZDQ3MzZkM2I2NzI3NDViZjM0YTc2YTg5MWUxNDllNGU0MzhhMS5qcGVnIl0sWyJwIiwidGh1bWIiLCI2MDB4NjAwIl1d.jpeg?sha=aa8055ac24971879" alt="手沖壺" class="card-image">
                </div>
                <h3>🫖 手沖壺 (Gooseneck Kettle)</h3>
                <p>細長鵝頸的設計能穩定控制水流大小與注水角度，是手沖咖啡中不可或缺的靈魂工具。</p>
              </div>
              <div class="intro-card">
                <div class="card-image-container">
                  <img src="https://images.unsplash.com/photo-1545665225-b23b99e4d45e?auto=format&fit=crop&w=600&q=80" alt="濾杯" class="card-image">
                </div>
                <h3>☕ 濾杯 (Coffee Dripper)</h3>
                <p>常見的有錐形(如 V60)、扇形與平底(如蛋糕濾杯)。不同的形狀與導流溝槽會影響水流速度與萃取風味。</p>
              </div>
              <div class="intro-card">
                <div class="card-image-container">
                  <img src="https://i0.wp.com/1zpresso.com/wp-content/uploads/2022/06/jmax.jpg?resize=2000%2C1200&ssl=1" alt="磨豆機" class="card-image">
                </div>
                <h3>⚙️ 磨豆機 (Coffee Grinder)</h3>
                <p>現磨咖啡豆能保留最多香氣。手沖通常建議使用錐刀或平刀磨豆機，將豆子磨至類似二號砂糖的粗細。</p>
              </div>
              <div class="intro-card">
                <div class="card-image-container">
                  <img src="https://img.yec.tw/cl/api/res/1.2/GErgFyL.1ncLncdJwr9dtA--/YXBwaWQ9eXR3YXVjdGlvbnNlcnZpY2U7aD0xMDAwO3E9ODU7cm90YXRlPWF1dG87dz0xMDAw/https://img.yec.tw/ob/image/3c7e712a-f844-4b97-a66a-f943b743153f.jpg" alt="電子秤與計時器" class="card-image">
                </div>
                <h3>⚖️ 電子秤與計時器</h3>
                <p>精準控制「粉水比」(如 1:15) 與「注水時間」是穩定沖出一杯好咖啡的關鍵，建議兩者結合使用。</p>
              </div>
              <div class="intro-card">
                <div class="card-image-container">
                  <img src="https://www.hucc-coop.tw/uploads/01%E7%94%A2%E5%93%81%E8%88%87%E7%94%9F%E7%94%A2%E8%80%85/%E7%94%A2%E5%93%81%E5%9C%96%E6%AA%94/%E5%B1%85%E5%AE%B6%E5%A5%BD%E7%89%A9/%E6%97%A5%E7%94%A8%E5%93%81/%E4%B8%8D%E6%BC%82%E7%99%BD%E6%BF%BE%E7%B4%99/%E4%B8%8D%E6%BC%82%E7%99%BD%E6%BF%BE%E7%B4%99%E6%83%85%E5%A2%83%E7%85%A7360x360.jpg" alt="濾紙" class="card-image">
                </div>
                <h3>📄 濾紙 (Filter Paper)</h3>
                <p>用來過濾咖啡粉渣，讓咖啡液更乾淨透亮。使用前可先用熱水潤濕，去除紙張味並溫熱濾杯。</p>
              </div>
            </div>
          </div>

        <!-- ================= 【第三部分：教學模式 (沖泡步驟)】 ================= -->
        <div v-else-if="currentTab === 'tutorial'" key="tutorial" class="tutorial-view">
          
          <!-- 進度條 (Progress Bar) -->
          <div class="progress-bar-container">
            <div class="progress-bar-fill" :style="{ width: progressPercentage + '%' }"></div>
          </div>

          <!-- 教學內容區塊（步驟切換動畫） -->
          <Transition name="fade" mode="out-in">
            <div :key="currentStep" class="step-card">
              <div class="step-badge">Step {{ coffeeSteps[currentStep].id }}</div>
              <h2 class="step-title">{{ coffeeSteps[currentStep].title }}</h2>
              
              <!-- 真實圖片渲染 -->
              <div class="image-container">
                <img :src="coffeeSteps[currentStep].imageUrl" :alt="coffeeSteps[currentStep].title" class="step-image" />
              </div>
              
              <p class="step-description">{{ coffeeSteps[currentStep].description }}</p>
            </div>
          </Transition>

          <!-- 底部控制按鈕 -->
          <div class="navigation-buttons">
            <button 
              class="btn btn-secondary" 
              @click="prevStep" 
              :class="{ invisible: currentStep === 0 }"
            >
              上一步
            </button>
            <button class="btn btn-primary" @click="nextStep">
              {{ currentStep === coffeeSteps.length - 1 ? '前往測驗' : '下一步' }}
            </button>
          </div>

        </div>

        <!-- ================= 【第四部分：測驗模式】 ================= -->
        <div v-else key="quiz" class="quiz-view">
          <h2 class="view-title">☕ 手沖咖啡隨堂測驗</h2>
          
          <Transition name="fade" mode="out-in">
            <!-- 測驗首頁 -->
            <div v-if="!isQuizStarted && !isSubmitted" key="quiz-home" class="quiz-intro-card">
              <h3>準備好挑戰了嗎？ 🎯</h3>
              <p>系統將從題庫隨機抽取 3 題，您只有 <strong>45 秒</strong> 的作答時間！</p>
              <div class="highscore-badge">🏆 歷史最高分：{{ highScore }} 分</div>
              <button class="btn btn-primary submit-btn" @click="startNewQuiz">開始測驗</button>
            </div>

            <!-- 作答區 -->
            <div v-else-if="isQuizStarted && !isSubmitted" key="questions" class="quiz-content">
              <div class="quiz-header">
                <span class="timer" :class="{ 'text-danger': quizTimeLeft <= 10 }">
                  ⏳ 剩餘時間：{{ quizTimeLeft }} 秒
                </span>
              </div>
              <div v-for="(q, index) in quizQuestions" :key="q.id" class="question-card">
                <p class="question-text">Q{{ index + 1 }}. {{ q.question }}</p>
                <div class="options-group">
                  <label 
                    v-for="(opt, optIndex) in q.options" 
                    :key="optIndex" 
                    class="option-label"
                    :class="{ selected: userAnswers[index] === optIndex }"
                  >
                    <input 
                      type="radio" 
                      :name="'question' + index" 
                      :value="optIndex" 
                      v-model="userAnswers[index]"
                    >
                    {{ opt }}
                  </label>
                </div>
              </div>
              
              <button 
                class="btn btn-primary submit-btn" 
                @click="submitQuiz" 
                :disabled="!isAllAnswered"
              >
                提交答案
              </button>
            </div>

            <!-- 結果區 -->
            <div v-else key="results" class="quiz-results">
              <div class="score-board">
                <h3>本次測驗結果：{{ score }} / {{ quizQuestions.length }} 分</h3>
              </div>
              
              <div v-if="score === quizQuestions.length" class="perfect-score">
                🎉 滿分過關！你已經掌握了手沖咖啡的精髓，快去沖一杯吧！
              </div>
              
              <div v-else class="mistakes-review">
                <p>別灰心，讓我們複習一下錯的題目：</p>
                <div v-for="(q, index) in quizQuestions" :key="'res'+q.id">
                  <div v-if="userAnswers[index] !== q.correctAnswer" class="review-card">
                    <p class="review-question">❌ 第 {{ index + 1 }} 題：{{ q.question }}</p>
                    <p class="review-explanation"><strong>解析：</strong>{{ q.explanation }}</p>
                  </div>
                  <div v-else class="review-card correct">
                    <p class="review-question">✅ 第 {{ index + 1 }} 題答對了！</p>
                  </div>
                </div>
              </div>

              <button class="btn btn-primary reset-btn" @click="goToQuizHome">
                返回測驗首頁
              </button>
            </div>
          </Transition>
        </div>
      </Transition>
    </div>
    </main>
  </div>
</template>

<script setup>
import { ref, computed, onMounted, watch } from 'vue'

// ================= 【資料結構設定】 =================

// 教學步驟資料
const coffeeSteps = [
  {
    id: 1,
    title: '準備與磨豆',
    description: '秤取適量的咖啡豆（粉水比建議 1:15）。使用磨豆機將咖啡豆磨至中等粗細，類似二號砂糖的顆粒大小。同時可以先用熱水溫杯與潤濕濾紙，去除紙味。',
    imageUrl: 'https://images.unsplash.com/photo-1559525839-b184a4d698c7?auto=format&fit=crop&w=800&q=80'
  },
  {
    id: 2,
    title: '悶蒸（Blooming）',
    description: '從中心開始緩慢注水，水量約為咖啡粉的 2 倍。這個過程是為了釋放烘焙時產生的二氧化碳，等待約 30 秒讓咖啡粉膨脹（Blooming），為後續均勻萃取做準備。',
    imageUrl: 'https://images.unsplash.com/photo-1497935586351-b67a49e012bf?auto=format&fit=crop&w=800&q=80'
  },
  {
    id: 3,
    title: '分段注水',
    description: '悶蒸結束後，開始由內向外畫圈注水。可以分為兩到三段注水，保持水流穩定，控制水位不要忽高忽低。持續注水直到達到目標的總水量。',
    imageUrl: 'https://images.unsplash.com/photo-1498804103079-a6351b050096?auto=format&fit=crop&w=800&q=80'
  },
  {
    id: 4,
    title: '完成',
    description: '當濾杯中最後的水滴完後，將濾杯移開。輕輕搖晃下壺讓咖啡液混合均勻即可享用。小提示：若咖啡太苦，可能是萃取過度，下次可以加快注水速度或將粉磨粗一些。',
    imageUrl: 'https://images.unsplash.com/photo-1514432324607-a09d9b4aefdd?auto=format&fit=crop&w=800&q=80'
  }
]

// 隨堂測驗題庫 (共 10 題)
const quizPool = [
  {
    id: 1,
    type: 'memory',
    question: '悶蒸（Blooming）通常需要花費多少時間？',
    options: ['10～15 秒', '30～40 秒', '1 分鐘', '2 分鐘'],
    correctAnswer: 1,
    explanation: '悶蒸的黃金時間通常在 30～40 秒左右，讓咖啡粉有充足的時間釋放氣體，準備好被均勻萃取。'
  },
  {
    id: 2,
    type: 'comprehension',
    question: '為什麼悶蒸時咖啡粉會膨脹？',
    options: ['吸收空氣中的水分', '釋放烘焙時產生的二氧化碳', '咖啡脂揮發', '因為水溫太高'],
    correctAnswer: 1,
    explanation: '咖啡豆在烘焙過程中會產生二氧化碳，悶蒸時注水會把氣體逼出，導致咖啡粉表面膨脹起泡。'
  },
  {
    id: 3,
    type: 'application',
    question: '如果最後沖出來的咖啡太苦，下次注水時可以怎麼調整？',
    options: ['水溫調得更高', '咖啡粉磨得更細', '加快注水速度／縮短萃取時間', '增加咖啡粉量'],
    correctAnswer: 2,
    explanation: '咖啡太苦通常是因為「過度萃取」。降低水溫、把粉磨粗一點，或加快萃取速度（縮短時間），都能減少苦味物質的過度溶出。'
  },
  {
    id: 4,
    type: 'memory',
    question: '下列哪種處理法通常會讓咖啡帶有濃郁的熱帶水果香氣與較高的甜度？',
    options: ['水洗法', '日曬法', '蜜處理', '濕剝法'],
    correctAnswer: 1,
    explanation: '日曬法是將咖啡果實直接曝曬乾燥，果肉的甜感與水果香氣更容易滲透進咖啡豆中。'
  },
  {
    id: 5,
    type: 'comprehension',
    question: '淺焙咖啡豆通常具有什麼樣的風味特徵？',
    options: ['濃郁的苦甜巧克力味', '焦糖與堅果香氣', '明亮的果酸與花草香氣', '醇厚度極高且酸度低'],
    correctAnswer: 2,
    explanation: '淺焙最能保留咖啡豆原始的風味，通常帶有明亮的果酸與清新的花果香氣。'
  },
  {
    id: 6,
    type: 'memory',
    question: '手沖咖啡通常建議的黃金「粉水比」大約是多少？',
    options: ['1:5', '1:10', '1:15', '1:20'],
    correctAnswer: 2,
    explanation: '通常建議的粉水比大約落在 1:15 左右（1克咖啡粉配15毫升水），可依個人口味偏好微調。'
  },
  {
    id: 7,
    type: 'comprehension',
    question: '手沖咖啡為何推薦使用「細長鵝頸」的手沖壺？',
    options: ['保溫效果較好', '水流較穩定，容易控制注水角度', '容量比較大', '能自動加熱'],
    correctAnswer: 1,
    explanation: '細長鵝頸設計能幫助沖煮者穩定控制水流大小與注水角度，是手沖的關鍵工具。'
  },
  {
    id: 8,
    type: 'memory',
    question: '手沖咖啡建議將咖啡豆磨成大約什麼樣的粗細度？',
    options: ['極細的麵粉狀', '類似二號砂糖的顆粒', '粗糙的碎石狀', '完全不磨'],
    correctAnswer: 1,
    explanation: '手沖通常建議使用中等粗細，大約類似二號砂糖的顆粒大小，太細容易苦澀，太粗則會萃取不足。'
  },
  {
    id: 9,
    type: 'application',
    question: '使用濾紙前先用熱水潤濕，主要的目的包含下列何者？',
    options: ['去除濾紙味並溫熱濾杯', '讓濾紙變軟', '測試濾杯是否漏水', '消毒殺菌'],
    correctAnswer: 0,
    explanation: '熱水潤濕濾紙可以沖洗掉殘留的紙味，同時預熱濾杯與下壺，避免咖啡液在沖煮過程中快速降溫。'
  },
  {
    id: 10,
    type: 'memory',
    question: '以「濕剝法」處理著名，醇厚度極高並帶有香料與草本植物風味的是哪一個產區？',
    options: ['衣索比亞', '哥倫比亞', '巴西', '印尼'],
    correctAnswer: 3,
    explanation: '印尼咖啡（如曼特寧）以獨特的濕剝法聞名，造就了極高的醇厚度與草本、香料的沈穩風味。'
  }
]

// ================= 【狀態管理】 =================

// 教學區狀態
const currentStep = ref(0)
const progressPercentage = computed(() => {
  // 依照當前步驟計算百分比 (1/4 -> 25%, 4/4 -> 100%)
  return ((currentStep.value + 1) / coffeeSteps.length) * 100
})

// 分頁與測驗狀態
const currentTab = ref('home')
const isSubmitted = ref(false)

// 實用工具區狀態
const coffeePowder = ref(15)
const waterRatio = ref(15)
const isTimerRunning = ref(false)
const timerSeconds = ref(0)
let timerInterval = null

// 測驗區狀態
const isQuizStarted = ref(false)
const quizQuestions = ref([])
const quizTimeLeft = ref(45)
let quizTimer = null
const highScore = ref(0)
const userAnswers = ref([])
const score = ref(0)

// 檢查是否所有題目都已作答
const isAllAnswered = computed(() => {
  return userAnswers.value.every(answer => answer !== null)
})

// ================= 【功能方法】 =================
const formattedTime = computed(() => {
  const m = Math.floor(timerSeconds.value / 60).toString().padStart(2, '0')
  const s = (timerSeconds.value % 60).toString().padStart(2, '0')
  return `${m}:${s}`
})

const toggleTimer = () => {
  if (isTimerRunning.value) {
    clearInterval(timerInterval)
    isTimerRunning.value = false
  } else {
    isTimerRunning.value = true
    timerInterval = setInterval(() => {
      timerSeconds.value++
    }, 1000)
  }
}

const resetTimer = () => {
  clearInterval(timerInterval)
  isTimerRunning.value = false
  timerSeconds.value = 0
}

// 生命週期：讀取最高分
onMounted(() => {
  const savedScore = localStorage.getItem('coffee_quiz_high_score')
  if (savedScore) {
    highScore.value = parseInt(savedScore, 10)
  }
})

// 監聽分頁切換，離開測驗區時自動暫停/清除計時
watch(currentTab, (newTab) => {
  if (newTab !== 'quiz' && isQuizStarted.value && !isSubmitted.value) {
    clearInterval(quizTimer)
    isQuizStarted.value = false
  }
})

const nextStep = () => {
  if (currentStep.value < coffeeSteps.length - 1) {
    currentStep.value++
  } else {
    currentTab.value = 'quiz' // 最後一步切換到測驗分頁
  }
}

const prevStep = () => {
  if (currentStep.value > 0) {
    currentStep.value--
  }
}

const startNewQuiz = () => {
  // 洗牌並抽出 3 題
  const shuffled = [...quizPool].sort(() => 0.5 - Math.random())
  quizQuestions.value = shuffled.slice(0, 3)
  userAnswers.value = Array(3).fill(null)
  
  score.value = 0
  isSubmitted.value = false
  isQuizStarted.value = true
  quizTimeLeft.value = 45
  
  // 開始倒數計時
  if (quizTimer) clearInterval(quizTimer)
  quizTimer = setInterval(() => {
    if (quizTimeLeft.value > 0) {
      quizTimeLeft.value--
    } else {
      submitQuiz() // 時間到自動交卷
    }
  }, 1000)
}

const submitQuiz = () => {
  if (quizTimer) clearInterval(quizTimer)
  
  let currentScore = 0
  userAnswers.value.forEach((answer, index) => {
    if (answer === quizQuestions.value[index].correctAnswer) {
      currentScore++
    }
  })
  score.value = currentScore
  isSubmitted.value = true
  
  if (currentScore > highScore.value) {
    highScore.value = currentScore
    localStorage.setItem('coffee_quiz_high_score', currentScore.toString())
  }
}

const goToQuizHome = () => {
  isQuizStarted.value = false
  isSubmitted.value = false
}
</script>

<style scoped>
/* 
  色彩計畫：
  奶油白背景：#FDFBF7
  拿鐵色（主要按鈕/點綴）：#C08A63
  深焙咖啡色（文字/標題）：#4A3728
  淺米色（卡片背景）：#F4EFE6
*/

.app-wrapper {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #FDFBF7;
  font-family: 'Helvetica Neue', Arial, '微軟正黑體', sans-serif;
  color: #4A3728;
}

/* ================= 頂部導覽列 ================= */
.app-header {
  width: 100%;
  padding: 15px 40px;
  background-color: #ffffff;
  box-shadow: 0 2px 10px rgba(74, 55, 40, 0.05);
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-sizing: border-box;
  position: sticky;
  top: 0;
  z-index: 100;
}
.logo {
  font-size: 1.4rem;
  font-weight: bold;
  color: #4A3728;
  letter-spacing: 1px;
}
.nav-tabs {
  display: flex;
  gap: 10px;
}
.nav-btn {
  background: transparent;
  border: none;
  font-size: 1.05rem;
  font-weight: bold;
  color: #a89f96;
  cursor: pointer;
  padding: 8px 16px;
  border-radius: 20px;
  transition: all 0.3s ease;
}
.nav-btn:hover {
  color: #4A3728;
  background-color: #F4EFE6;
}
.nav-btn.active {
  color: #ffffff;
  background-color: #C08A63;
}

/* ================= 主要內容區 ================= */
.main-content {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 40px 20px;
  box-sizing: border-box;
}

.coffee-app-container {
  background: #ffffff;
  width: 100%;
  max-width: 1200px;
  min-height: 80vh;
  border-radius: 16px;
  box-shadow: 0 10px 30px rgba(74, 55, 40, 0.1);
  overflow: hidden;
  padding: 50px;
}

/* ================= 首頁區 ================= */
.home-view {
  padding: 20px 0;
}
.main-title {
  font-size: 2rem;
  color: #4A3728;
  text-align: center;
  margin-bottom: 20px;
}
.main-desc {
  font-size: 1.1rem;
  line-height: 1.8;
  color: #5a4b41;
  text-align: center;
  margin: 0 auto 35px auto;
  max-width: 800px;
}
.home-action {
  display: flex;
  justify-content: center;
}

/* ================= 共用標題 ================= */
.view-title {
  text-align: center;
  margin-bottom: 25px;
  color: #4A3728;
}

.section-subtitle {
  text-align: center;
  color: #C08A63;
  margin: 30px 0 15px 0;
  font-size: 1.3rem;
}

/* ================= 咖啡豆介紹區 ================= */
.intro-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.intro-card {
  background-color: #FDFBF7;
  border: 1px solid #e8dcc8;
  padding: 20px;
  border-radius: 12px;
  transition: transform 0.2s;
}
.intro-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 4px 12px rgba(74, 55, 40, 0.08);
}
.intro-card:hover .card-image {
  transform: scale(1.05);
}
.intro-card h3 {
  color: #C08A63;
  margin-bottom: 10px;
}
.intro-card p {
  color: #5a4b41;
  line-height: 1.5;
}

.card-image-container {
  height: 180px;
  width: 100%;
  margin-bottom: 15px;
  border-radius: 8px;
  overflow: hidden;
  background-color: #F4EFE6;
}

.card-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

/* ================= 實用工具區 ================= */
.tools-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}
.tool-card {
  background-color: #FDFBF7;
  border: 1px solid #e8dcc8;
  padding: 30px;
  border-radius: 12px;
}
.input-group {
  margin-bottom: 15px;
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.tool-input {
  padding: 10px;
  border: 1px solid #e8dcc8;
  border-radius: 6px;
  font-size: 1.1rem;
  background-color: #ffffff;
}
.result-box {
  margin-top: 20px;
  padding: 15px;
  background-color: #F4EFE6;
  border-radius: 8px;
  text-align: center;
  font-size: 1.1rem;
  color: #4A3728;
}
.timer-display {
  font-size: 3.5rem;
  font-weight: bold;
  text-align: center;
  margin: 20px 0;
  font-variant-numeric: tabular-nums;
  color: #4A3728;
}
.timer-display.running {
  color: #C08A63;
}

/* ================= 教學區：進度條 ================= */
.progress-bar-container {
  height: 8px;
  background-color: #F4EFE6;
  border-radius: 4px;
  margin-bottom: 30px;
  overflow: hidden;
}
.progress-bar-fill {
  height: 100%;
  background-color: #C08A63;
  transition: width 0.6s cubic-bezier(0.25, 0.8, 0.25, 1);
}

/* ================= 教學區：卡片內容 ================= */
.step-badge {
  display: inline-block;
  background-color: #F4EFE6;
  color: #C08A63;
  font-weight: bold;
  padding: 6px 14px;
  border-radius: 20px;
  margin-bottom: 15px;
  font-size: 0.9rem;
}
.step-title {
  font-size: 1.8rem;
  margin-bottom: 20px;
  color: #4A3728;
}
.image-container {
  height: 450px;
  background-color: #F4EFE6;
  border-radius: 12px;
  margin-bottom: 20px;
  overflow: hidden;
  box-shadow: 0 4px 12px rgba(74, 55, 40, 0.08);
}
.step-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
.step-description {
  line-height: 1.6;
  font-size: 1.05rem;
  color: #5a4b41;
  min-height: 80px;
}

/* ================= 按鈕設計 ================= */
.navigation-buttons {
  display: flex;
  justify-content: space-between;
  margin-top: 30px;
}
.invisible {
  visibility: hidden;
}
.btn {
  padding: 12px 24px;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s ease;
}
.btn-primary {
  background-color: #C08A63;
  color: white;
}
.btn-primary:hover:not(:disabled) {
  background-color: #4A3728;
  transform: scale(1.05);
}
.btn-primary:disabled {
  background-color: #d8c5b8;
  cursor: not-allowed;
}
.btn-secondary {
  background-color: #F4EFE6;
  color: #4A3728;
}
.btn-secondary:hover {
  background-color: #e8dcc8;
  transform: scale(1.05);
}

/* ================= 測驗區 ================= */
.quiz-intro-card {
  text-align: center;
  background-color: #FDFBF7;
  border: 1px solid #e8dcc8;
  padding: 40px;
  border-radius: 12px;
  margin-top: 20px;
}
.quiz-intro-card h3 {
  font-size: 1.5rem;
  margin-bottom: 15px;
  color: #4A3728;
}
.highscore-badge {
  display: inline-block;
  margin: 20px 0;
  padding: 10px 20px;
  background-color: #F4EFE6;
  border-radius: 30px;
  font-weight: bold;
  color: #C08A63;
}
.quiz-header {
  display: flex;
  justify-content: flex-end;
  margin-bottom: 15px;
}
.timer {
  font-weight: bold;
  font-size: 1.1rem;
  background: #F4EFE6;
  padding: 6px 12px;
  border-radius: 8px;
}
.text-danger {
  color: #d93025;
  background: #fce8e6;
}
.question-card {
  background-color: #FDFBF7;
  border: 1px solid #e8dcc8;
  padding: 20px;
  border-radius: 12px;
  margin-bottom: 15px;
}
.question-text {
  font-weight: bold;
  margin-bottom: 15px;
  font-size: 1.1rem;
}
.options-group {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 15px;
}
.option-label {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 12px;
  border-radius: 8px;
  background-color: #ffffff;
  border: 2px solid #F4EFE6;
  cursor: pointer;
  transition: all 0.2s ease;
}
.option-label:hover {
  border-color: #C08A63;
}
.option-label.selected {
  background-color: #F4EFE6;
  border-color: #C08A63;
}
.option-label input[type="radio"] {
  accent-color: #C08A63;
  transform: scale(1.2);
}
.submit-btn {
  width: 100%;
  margin-top: 20px;
}

/* ================= 測驗結果區 ================= */
.score-board {
  text-align: center;
  font-size: 1.5rem;
  color: #C08A63;
  margin-bottom: 20px;
}
.perfect-score {
  background-color: #e6f4ea;
  color: #2e7d32;
  padding: 20px;
  border-radius: 12px;
  text-align: center;
  font-weight: bold;
  line-height: 1.5;
}
.mistakes-review {
  margin-top: 15px;
}
.review-card {
  background-color: #fce8e6;
  border-left: 4px solid #d93025;
  padding: 15px;
  margin-bottom: 15px;
  border-radius: 0 8px 8px 0;
}
.review-card.correct {
  background-color: #e6f4ea;
  border-left: 4px solid #2e7d32;
}
.review-question {
  font-weight: bold;
  margin-bottom: 8px;
}
.review-explanation {
  color: #5a4b41;
  font-size: 0.95rem;
  line-height: 1.5;
}
.reset-btn {
  width: 100%;
  margin-top: 20px;
}

/* ================= Vue 過場動畫 (Transition) ================= */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease, transform 0.4s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(10px);
}
</style>
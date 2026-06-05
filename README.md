<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>뮤지컬 넘버 분석 연구소</title>
    <!-- 부드럽고 트렌디한 프리텐다드 폰트 -->
    <link rel="stylesheet" as="style" crossorigin href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.min.css" />
    
    <style>
        /* ==========================================
           1. 상큼한 옐로우 파스텔 그라데이션 테마
           ========================================== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Pretendard', sans-serif;
        }

        body {
            background: linear-gradient(135deg, #fff7dc 0%, #ffebb3 50%, #ffe393 100%);
            background-attachment: fixed;
            color: #5d4b1a;
            padding: 20px 20px 80px 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* ==========================================
           2. 상단 헤더 영역
           ========================================== */
        header {
            width: 100%;
            max-width: 1100px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 5px;
            margin-bottom: 25px;
        }

        .dimigo-logo {
            font-weight: 800;
            letter-spacing: 1px;
            color: #b5912a;
            font-size: 0.95rem;
        }

        .top-right-badge {
            background-color: rgba(255, 255, 255, 0.6);
            color: #947214;
            padding: 5px 14px;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 700;
            box-shadow: 0 2px 5px rgba(0,0,0,0.02);
        }

        /* ==========================================
           3. 메인 배너 및 대시보드 시스템
           ========================================== */
        .main-banner {
            background: rgba(255, 255, 255, 0.55);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.6);
            border-radius: 32px;
            width: 100%;
            max-width: 1100px;
            padding: 45px 35px;
            box-shadow: 0 15px 35px rgba(212, 174, 69, 0.12);
            margin-bottom: 45px;
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .banner-text-zone {
            text-align: center;
        }

        .banner-tag {
            display: inline-block;
            background-color: #ff9f43;
            color: #ffffff;
            font-size: 0.8rem;
            font-weight: 700;
            padding: 5px 14px;
            border-radius: 20px;
            margin-bottom: 15px;
            box-shadow: 0 2px 8px rgba(255, 159, 67, 0.2);
        }

        .main-banner h1 {
            font-size: 2.5rem;
            color: #ffffff;
            font-weight: 900;
            text-shadow: 2px 2px 0px #d4ae45, -1px -1px 0px #d4ae45, 1px -1px 0px #d4ae45, -1px 1px 0px #d4ae45;
            margin-bottom: 12px;
            letter-spacing: -0.5px;
        }

        .banner-subtitle {
            font-size: 0.95rem;
            color: #ffffff;
            background-color: rgba(212, 174, 69, 0.75);
            display: inline-block;
            padding: 4px 16px;
            border-radius: 15px;
            font-weight: 600;
        }

        .dashboard-panel {
            display: flex;
            gap: 20px;
            width: 100%;
        }

        .panel-left {
            flex: 1.2;
            background: linear-gradient(135deg, #ff9f43 0%, #ffbe76 100%);
            border-radius: 20px;
            padding: 24px;
            color: #ffffff;
            display: flex;
            flex-direction: column;
            justify-content: center;
            box-shadow: 0 8px 20px rgba(255, 159, 67, 0.15);
        }

        .panel-left .focus-title {
            font-size: 0.75rem;
            font-weight: 800;
            letter-spacing: 1px;
            opacity: 0.9;
            margin-bottom: 8px;
        }

        .panel-left .focus-main {
            font-size: 1.3rem;
            font-weight: 800;
            line-height: 1.4;
            word-break: keep-all;
        }

        .panel-right {
            flex: 2;
            background: #ffffff;
            border-radius: 20px;
            padding: 24px;
            display: flex;
            flex-direction: column;
            gap: 16px;
            justify-content: center;
            border: 1px solid rgba(212, 174, 69, 0.1);
        }

        .progress-item {
            display: flex;
            flex-direction: column;
            gap: 6px;
        }

        .progress-info {
            display: flex;
            justify-content: space-between;
            font-size: 0.75rem;
            font-weight: 700;
            color: #7a611c;
        }

        .progress-info .label-name {
            display: flex;
            align-items: center;
            gap: 4px;
        }

        .bar-track {
            width: 100%;
            height: 8px;
            background-color: #f5eed3;
            border-radius: 4px;
            overflow: hidden;
        }

        .bar-fill {
            height: 100%;
            background: linear-gradient(90deg, #e1b12c, #ff9f43);
            border-radius: 4px;
        }

        /* ==========================================
           4. 연구 프로세스 영역 레이아웃
           ========================================== */
        .section-title {
            font-size: 1.35rem;
            font-weight: 800;
            color: #7a611c;
            margin-bottom: 25px;
            letter-spacing: 1px;
        }

        .content-container {
            width: 100%;
            max-width: 1100px;
            display: flex;
            flex-direction: column;
            gap: 24px;
        }

        /* 공통 카드 기본 스타일 설정 */
        .study-card {
            background: #ffffff;
            border-radius: 24px;
            text-decoration: none;
            color: inherit;
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 25px rgba(220, 190, 100, 0.1);
            transition: transform 0.25s cubic-bezier(0.175, 0.885, 0.32, 1.275), box-shadow 0.25s ease;
            z-index: 1;
        }

        .study-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(212, 174, 69, 0.22);
        }

        /* 1번 메뉴: 아코디언 상자 스타일 */
        .full-width-accordion {
            width: 100%;
        }

        .accordion-summary {
            padding: 24px 30px; 
            display: flex;
            align-items: center;
            cursor: pointer;
            outline: none;
            list-style: none;
            position: relative;
        }

        .accordion-summary::-webkit-details-marker {
            display: none;
        }

        .accordion-summary::after {
            content: "▼ 클릭하여 15가지 조건 확인하기";
            position: absolute;
            bottom: 12px;
            right: 30px;
            font-size: 0.75rem;
            color: #ff9f43;
            font-weight: 700;
        }

        details[open] .accordion-summary::after {
            content: "▲ 클릭하여 닫기";
        }

        .accordion-info {
            flex: 1;
            padding-right: 120px;
        }

        .accordion-content {
            background-color: #fdfaf0;
            border-top: 1px dashed rgba(225, 177, 44, 0.3);
            padding: 30px;
            border-bottom-left-radius: 24px;
            border-bottom-right-radius: 24px;
        }

        .sub-item-list {
            list-style: none;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        .sub-item-list li button {
            width: 100%;
            text-align: left;
            display: block;
            background: #ffffff;
            padding: 15px 20px;
            border-radius: 14px;
            color: #4a3c15;
            font-weight: 700;
            font-size: 0.9rem;
            border: 1px solid rgba(225, 177, 44, 0.15);
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .sub-item-list li button:hover {
            background-color: #ffbe76;
            color: #ffffff;
            border-color: #ffbe76;
            transform: translateX(5px);
        }

        /* 하단 4개 카드가 정렬될 2x2 그리드 시스템 */
        .card-grid-2x2 {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 24px;
        }

        .grid-card-padding {
            padding: 32px 28px;
            display: flex;
            flex-direction: column;
            height: 100%;
            position: relative;
            z-index: 3;
            transition: color 0.3s ease;
        }

        /* 기본 내부 디자인 요소 */
        .card-badge {
            position: absolute;
            top: 24px;
            right: 28px;
            background-color: #ffbe76;
            color: #ffffff;
            font-size: 0.7rem;
            font-weight: 700;
            padding: 4px 10px;
            border-radius: 10px;
            z-index: 4;
            transition: background-color 0.3s ease, color 0.3s ease;
        }

        .card-icon { font-size: 1.8rem; margin-bottom: 12px; }
        .card-step { font-size: 0.75rem; color: #cca43b; font-weight: 700; margin-bottom: 4px; letter-spacing: 0.5px; transition: color 0.3s ease; }
        .card-title { font-size: 1.15rem; font-weight: 800; color: #4a3c15; margin-bottom: 8px; line-height: 1.35; transition: color 0.3s ease; }
        .card-desc { font-size: 0.85rem; color: #8c805c; line-height: 1.5; font-weight: 400; transition: color 0.3s ease; }

        /* 커서 올렸을 때 배경 사진이 나타나는 멀티 가상 요소 처리 */
        .photo-card::before {
            content: "";
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background-size: cover;
            background-position: center;
            opacity: 0;
            z-index: 1;
            transition: opacity 0.35s ease;
        }

        .photo-card::after {
            content: "";
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.55);
            opacity: 0;
            z-index: 2;
            transition: opacity 0.35s ease;
        }

        /* 개별 이미지 매핑 */
        .bg-suha::before { background-image: url('미디어/레미제라블.jpg'); }
        .bg-eva::before { background-image: url('미디어/eva_2.png'); }
        .bg-les::before { background-image: url('미디어/레미제라블_du.webp'); }
        .bg-saigon::before { background-image: url('미디어/미스사이공_id_re.png'); }

        /* 호버(Hover) 효과 작동 시 */
        .photo-card:hover::before,
        .photo-card:hover::after {
            opacity: 1;
        }

        .photo-card:hover .card-title,
        .photo-card:hover .card-desc,
        .photo-card:hover .card-step {
            color: #ffffff;
        }
        
        .photo-card:hover .card-badge {
            background-color: #ffffff;
            color: #ff9f43;
        }

        /* ==========================================
           5. 팝업창(모달) 스타일 시스템
           ========================================== */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.4);
            backdrop-filter: blur(4px);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.25s ease;
        }

        .modal-overlay.active {
            opacity: 1;
            pointer-events: auto;
        }

        .modal-box {
            background-color: #ffffff;
            width: 90%;
            max-width: 520px;
            border-radius: 24px;
            padding: 35px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
            position: relative;
            transform: translateY(20px);
            transition: transform 0.25s ease;
        }

        .modal-overlay.active .modal-box {
            transform: translateY(0);
        }

        .modal-close-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            background: none;
            border: none;
            font-size: 1.4rem;
            color: #baaf90;
            cursor: pointer;
            font-weight: bold;
        }
        .modal-close-btn:hover { color: #ff9f43; }

        .modal-badge {
            display: inline-block;
            background-color: #ffbe76;
            color: #ffffff;
            font-size: 0.7rem;
            font-weight: 700;
            padding: 3px 9px;
            border-radius: 8px;
            margin-bottom: 12px;
        }

        #modal-title {
            font-size: 1.25rem;
            font-weight: 800;
            color: #3b300e;
            margin-bottom: 14px;
            line-height: 1.4;
            word-break: keep-all;
        }

        #modal-desc {
            font-size: 0.95rem;
            color: #6e623d;
            line-height: 1.65;
            word-break: keep-all;
            white-space: pre-wrap;
        }

        /* 모바일 반응형 처리 */
        @media (max-width: 768px) {
            .dashboard-panel { flex-direction: column; }
            .card-grid-2x2, .sub-item-list { grid-template-columns: 1fr; }
            .accordion-summary { padding: 20px; }
            .accordion-summary::after { position: static; margin-top: 10px; display: block; }
            .accordion-info { padding-right: 0; }
        }
    </style>
</head>
<body>

    <!-- 상단 탭 바 -->
    <header>
        <div class="dimigo-logo">🌻 DIMIGO 1人1PROJECT</div>
        <div class="top-right-badge">3224 전소현</div>
    </header>

    <!-- 메인 대시보드 스크린 섹션 -->
    <section class="main-banner">
        <div class="banner-text-zone">
            <div class="banner-tag">MUSICAL ANALYSIS LAB 🌻</div>
            <h1>뮤지컬 넘버 분석 연구소</h1>
        </div>
        
        <div class="dashboard-panel">
            <div class="panel-left">
                <span class="focus-title">💡 CURRENT FOCUS</span>
                <p class="focus-main">논문을 통한 넘버 분석 방법으로 김수하의 'on my own'분석</p>
            </div>
            
            <div class="panel-right">
                <div class="progress-item">
                    <div class="progress-info">
                        <span class="label-name">🌼 논문 읽기 및 정리</span>
                        <span>100% Complete</span>
                    </div>
                    <div class="bar-track">
                        <div class="bar-fill" style="width: 100%;"></div>
                    </div>
                </div>
                <div class="progress-item">
                    <div class="progress-info">
                        <span class="label-name">✨ 배우만의 발성법 및 연기 분석</span>
                        <span>2 Actors Active</span>
                    </div>
                    <div class="bar-track">
                        <div class="bar-fill" style="width: 50%;"></div>
                    </div>
                </div>
                <div class="progress-item">
                    <div class="progress-info">
                        <span class="label-name">🌱 뮤지컬 넘버 분석</span>
                        <span>2 Pieces Loaded</span>
                    </div>
                    <div class="bar-track">
                        <div class="bar-fill" style="width: 30%;"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <h2 class="section-title">진행중인 연구🧪</h2>

    <!-- 메인 레이아웃 박스 -->
    <div class="content-container">

        <!-- 1. 기본 음악 분석 접근 방법 (15개 항목 확장) -->
        <details class="study-card full-width-accordion">
            <summary class="accordion-summary">
                <div class="card-badge">METHOD</div>
                <div class="accordion-info">
                    <div class="card-icon" style="margin-bottom: 5px;">🌼</div>
                    <div class="card-step">논문분석</div>
                    <div class="card-title" style="margin-bottom: 4px;">기본 음악 분석 접근 방법</div>
                    <div class="card-desc">조 디어와 로코 달 베라의 이상의 전제를 바탕으로 한 다양한 음악 분석의 접근 방법들 중 15개</div>
                </div>
            </summary>
            
            <div class="accordion-content">
                <ul class="sub-item-list">
                    <li><button onclick="openModal('01 음악만을 집중해서 들어라', '가사가 갖고 있는 영향력에서 벗어나서 오로지 멜로디 그리고 반주만 들릴 때까지 집중해서 들어야 한다. 이를 위해 피아노로 반주만 연주한 녹음본과 멜로디만 연주한 녹음본, 그리고 멜로디와 반주를 같이 연주한 녹음본을 준비한다.')">💛 01. 음악만 집중해서 듣기</button></li>
                    <li><button onclick="openModal('02 음악에서 느껴지는 감정과 그 변화에 주의하라', '음악은 노래하는 캐릭터의 내면에서 일어나는 감정을 알 수 있는 척도다. 노래의 느낌이 변했다면 캐릭터의 감정 또한 변한 것이다.')">💛 02. 음악에서 느껴지는 감정변화 주의하기</button></li>
                    <li><button onclick="openModal('03 멜로디의 진행 형태는 캐릭터의 감정을 보여준다', '멜로디란 시간 순서에 따라 음을 높낮이로 배열한 것으로, 이 멜로디에 가사를 얹어서 부르게 된다. 멜로디는 더 높은 음 아니면 더 낮은 음으로 진행하는데, 이 변화의 폭에 주의를 집중하면 캐릭터의 감정에 대한 실마리를 잡을 수 있다.\n악보의 오선지 위에 배열된 음표들을 하나의 선으로 연결해보면 위아래로 물결치는 그래프의 형태를 띠게 되는데, 이 형태는 완만한 언덕 같을 수도, 거친 산봉우리 같을 수도 있다. 이러한 그래프의 시각적 형태는 캐릭터의 감정에 접근할 수 있는 실마리가 된다.')">💛 03. 멜로디의 진행 형태=캐릭터의 감정</button></li>
                    <li><button onclick="openModal('04 템포의 변화에 주의하라', '템포는 음악의 빠르기를 뜻한다. 작곡가는 음악의 빠르기를 통해 수많은 감정들을 표현하고, 우리는 그것을 즉각적으로 받아들인다. 뮤지컬에서도 마찬가지로 캐릭터의 감정은 템포로 표현되고, 또 감정이 변하면 그것은 템포의 변화로 나타난다.')">💛 04. 템포 변화에 주의하기</button></li>
                    <li><button onclick="openModal('05 리듬의 변화는 캐릭터에게 일어나고 있는 감정의 변화를 전달한다', '이러한 리듬의 변화에 예민해지려면 다양한 리듬 형태를 듣는 훈련이 반드시 필요하다. 뮤지컬 작곡가는 왈츠, 폭스트롯, 차차, 탱고, 찰스톤, 랙타임, 스윙, 행진곡, 장송곡 등의 음악이 가지고 있는 독특한 리듬 패턴을 통해 캐릭터의 감정을 전달할 수 있다.')">💛 05. 리듬의 변화=캐릭터 감정의 변화</button></li>
                    <li><button onclick="openModal('06 조(key)는 캐릭터의 감정 상태 그리고 분위기를 표현한다', '예를 들어 장조(major key)의 곡이라면, 마음이 안정되어 있는 상태 혹은 강한 의지를 갖고 있는 상태를 표현할 수 있다. 반대로 단조(minor key)의 곡이라면 긴장이나 슬픔 혹은 마음의 갈등을 표현할 수 있다.')">💛 06. 조(key)=캐릭터의 감정 상태와 분위기</button></li>
                    <li><button onclick="openModal('07 작곡가는 전조(Modulation)를 통해 캐릭터의 다양한 감정 상태를 표현한다', '전조란 노래 한 곡 안에서 조를 올리거나 내리는 음악적 기법을 말하는 것으로, 이러한 변화를 통해 극도의 흥분이나 감동, 또는 점차 가중되는 긴장감이나 해방감 등 다양한 캐릭터의 감정을 표현할 수 있다. 이러한 변화에 민감해질 수 있도록 전조를 사용하고 있는 다양한 음악을 접하고 그 작품에 대해 공부하는 노력이 뮤지컬 배우에게는 필요하다.')">💛 07. 전조를 통한 다양한 감정 상태 표현</button></li>
                    <li><button onclick="openModal('08 긴장감과 해방감(Tensions and releases)을 느껴라', '반주를 들을 때, 어느 음악구간에서 강한 압력이 발생하다가 어느 순간 긴장감이 무너지며 시원하게 발산하는 느낌을 받아 본 적이 있을 것이다. 이렇게 긴장감과 해방감이 느껴지는 이유는 선율이나 화성의 진행 방식 때문이거나 템포나 음조의 변화 때문일 수도 있고, 음악의 구조적인 이유일 수도 있다. 이러한 작곡가의 인위적인 조율에 의해서 긴장감과 해방감이 만들어지고, 이는 캐릭터의 생각과 감정에 접근할 수 있는 또 하나의 실마리가 된다.')">💛 08. 긴장과 해방감을 느끼기</button></li>
                    <li><button onclick="openModal('09 음악의 악센트(Musical accent)를 찾아라', '뮤지컬 음악에서는 캐릭터의 감정 상태나 변화, 신체적 행동 등을 강조하기 위해 음악적으로 강조하는 부분이 있다. 이것을 음악적 악센트라고 한다. 음악적 악센트는 여러 가지 방법으로 표현될 수 있는데, 같은 음이 반복적으로 연주된다든지, 노래 중간에 음악이 멈춘다든지 하는 순간에 이러한 음악적 강조가 발생한다.')">💛 09. 음악의 악센트 찾기</button></li>
                    <li><button onclick="openModal('10 음악의 강약(Musical dynamic)으로 캐릭터의 감정 변화를 표현할 수 있다', '음악의 강약은 조용하다가 시끄러워지거나, 낮은 음에서 갑자기 높은 음으로 도약하거나, 거칠었다가 부드러워지고, 빨라졌다가 느려지거나, 점점 커지거나 점점 작아지는 등의 확연한 대비를 통해서 알 수 있다. 이러한 대비는 작곡가의 의도를 이해하고, 캐릭터의 감정 상태를 파악할 수 있는 중요한 정보가 된다.')">💛 10. 음악의 강약=캐릭터의 감정변화 표현</button></li>
                    <li><button onclick="openModal('11 음악의 어법(Musical idiom)을 파악하라', '이 접근법은 캐릭터의 고향이라든가, 민족, 인종 등 특정 지역의 색채가 드러난 음악 스타일을 사용하고 있는가에 주의하여 음악과 캐릭터의 상관관계를 파악하는데 그 목적이 있다.')">💛 11. 음악의 어법 파악하기</button></li>
                    <li><button onclick="openModal('12 뮤지컬의 음악은 캐릭터의 개성을 드러내기도 한다', '예를 들어, 뮤지컬 <레 미제라블>에 등장하는 좋은 가문 출신의 마리우스의 노래 \'Empty chairs at empty tables\'와 파리 뒷골목을 주름잡는 떼나르디에가 파리의 하수구에서 부르는 \'The sewers\'를 비교해보면, 전혀 다른 두 남자의 차이점이 음악적 기법을 통해 명확하게 드러나고 있다는 것을 알 수 있다.')">💛 음악=캐릭터의 개성</button></li>
                    <li><button onclick="openModal('13 멜로디와 반주의 연관관계를 확인하라', '멜로디와 반주 각각에서 수집한 정보가 서로 어떻게 연관되고 있는지, 서로 어떤 영향을 끼치고 있는지를 확인하는 것이다. 이를 통해 캐릭터에 관한 새로운 사실을 알 수도 있다.')">💛 13. 멜로디와 반주의 연관관계 확인하기</button></li>
                    <li><button onclick="openModal('14 음악과 가사를 재결합하고 비트를 나누어라', '노래는 정서적인 면(음악)과 구체적인 정보(가사)의 결합으로 이루어져 있다. 가사를 통해 이해한 정보와 음악을 통해 수집한 정보를 통합하면, 배우는 이 노래를 부르는 캐릭터의 생각과 감정, 그리고 목적을 명확하게 알 수 있게 된다.\n그리고 캐릭터의 목적을 파악하기 위해서는 노래를 여러 개의 비트로 구분하여 분석해야 한다. 음악에서 비트를 나눌 수 있는 단서들은 멜로디, 템포, 리듬, 조 그리고 반주가 변화하는 지점에서 찾을 수 있다. 이를 가사에서 얻은 정보를 토대로 나눈 비트와 비교해보면 캐릭터의 감정의 변화와 생각의 흐름이 명확해진다.')">💛 14. 음악과 가사의 재결합, 비트 변화하기</button></li>
                    <li><button onclick="openModal('15 비트별 목적을 찾고 그 목적을 이루기 위해 전술적으로 행동하라', '음악과 가사에서 얻은 정보를 바탕으로 신중하게 각 비트의 목적을 선택한다. 배우는 지금 노래하고 있는 비트의 목적만을 생각해야 한다. 다음 비트의 목적을 미리 예상하면 안 된다.\n그러기 위해서는 완전한 몰입이 필요하다. 배우는 그 비트에서 자신이 바라는 이상적인 결과를 상상하고, 자신의 목적을 달성하는데 방해가 되는 장애물에 어떻게 대처할 것인지 전술적인 해법을 찾아야 한다.')">💛 15. 비트별 목적 찾고, 행동하기</button></li>
                <!-- /n이 문단내리기임 -->
                </ul>
            </div>
        </details>

        <!-- 하단 이미지 카드 영역 -->
        <div class="card-grid-2x2">
            <!-- 2. 뮤지컬배우 김수하 분석 -->
            <a href="actor_suha.html" class="study-card photo-card bg-suha">
                <div class="grid-card-padding">
                    <div class="card-badge">ACTOR</div>
                    <div class="card-icon">✨</div>
                    <div class="card-step">영역 II</div>
                    <div class="card-title">뮤지컬 배우 김수하 분석</div>
                    <div class="card-desc">독보적인 감정선과 탄탄한 발성 스타일을 중심으로 한 롤모델 탐구</div>
                </div>
            </a>

            <!-- 3. 뮤지컬배우 eva noblezada 분석 -->
            <a href="actor_eva.html" class="study-card photo-card bg-eva">
                <div class="grid-card-padding">
                    <div class="card-badge">ACTOR</div>
                    <div class="card-icon">👑</div>
                    <div class="card-step">영역 III</div>
                    <div class="card-title">뮤지컬 배우 Eva Noblezada 분석</div>
                    <div class="card-desc">브로드웨이를 사로잡은 폭발적인 성량과 영리한 보컬 딕션 연구</div>
                </div>
            </a>

            <!-- 4. 뮤지컬 레미제라블 넘버 분석 -->
            <a href="les_miserables.html" class="study-card photo-card bg-les">
                <div class="grid-card-padding">
                    <div class="card-badge">NUMBER</div>
                    <div class="card-icon">📖</div>
                    <div class="card-step">영역 IV</div>
                    <div class="card-title">뮤지컬 레미제라블 넘버 분석</div>
                    <div class="card-desc">웅장한 송스루(Song-through) 구조 안에서 전개되는 입체적 넘버 매핑</div>
                </div>
            </a>

            <!-- 5. 뮤지컬 미스 사이공 넘버 분석 -->
            <a href="miss_saigon.html" class="study-card photo-card bg-saigon">
                <div class="grid-card-padding">
                    <div class="card-badge">NUMBER</div>
                    <div class="card-icon">🎙️</div>
                    <div class="card-step">영역 V</div>
                    <div class="card-title">뮤지컬 미스 사이공 넘버 분석</div>
                    <div class="card-desc">클래식과 팝 발성을 넘나드는 고난도 주연 넘버들의 연기적 해석 가이드</div>
                </div>
            </a>
        </div>

    </div>

    <!-- 미니 팝업창(모달) 레이아웃 -->
    <div id="desc-modal" class="modal-overlay" onclick="closeModal()">
        <div class="modal-box" onclick="event.stopPropagation()">
            <button class="modal-close-btn" onclick="closeModal()">×</button>
            <span class="modal-badge">ANALYSIS DETAILS</span>
            <h3 id="modal-title">항목 제목</h3>
            <p id="modal-desc">여기에 간단한 설명이 들어갑니다.</p>
        </div>
    </div>

    <!-- 팝업창 제어용 자바스크립트 -->
    <script>
        const modal = document.getElementById('desc-modal');
        const modalTitle = document.getElementById('modal-title');
        const modalDesc = document.getElementById('modal-desc');

        function openModal(title, text) {
            modalTitle.innerText = title;
            modalDesc.innerText = text;
            modal.classList.add('active');
        }

        function closeModal() {
            modal.classList.remove('active');
        }
    </script>

</body>
</html>

<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <title>세미나 출석체크 예시</title>
  <style>
    .person {
      display: inline-block;
      width: 80px;
      height: 40px;
      line-height: 40px;
      text-align: center;
      margin: 5px;
      background-color: #ccc;
      cursor: pointer;
      user-select: none;
      border-radius: 5px;
    }
    .selected {
      background-color: #ff6b6b;
      color: #fff;
    }
    .info {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>세미나 출석체크</h1>
  <div id="attendeeContainer"></div>
  <div class="info">
    현재 출석 인원: <span id="count">0</span>명
  </div>

  <script>
    // 예: 세미나 참석 예정자 목록
    const attendees = [
      "김철수", "이영희", "박민수", "최가영", "정윤아",
      "John", "Alice", "Bob", "Charlie", "David"
    ];

    const container = document.getElementById('attendeeContainer');
    const countSpan = document.getElementById('count');

    // 출석 대상자 버튼 생성
    attendees.forEach((name) => {
      const div = document.createElement('div');
      div.className = 'person';
      div.textContent = name;

      // 클릭 시 'selected' 토글
      div.addEventListener('click', () => {
        div.classList.toggle('selected');
        updateCount();
      });

      container.appendChild(div);
    });

    // 선택된 출석자 수 갱신
    function updateCount() {
      const selectedPersons = document.querySelectorAll('.person.selected');
      countSpan.textContent = selectedPersons.length;
    }
  </script>
</body>
</html>

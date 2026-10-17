# 26_HC023
# 저비용, 고효율의 AI 기반 맞춤형 상지 재활 훈련 로봇

## 💡 1. 프로젝트 개요

**1-1. 프로젝트 소개**
- 프로젝트 명 : 저비용, 고효율의 AI 기반 맞춤형 상지 재활 훈련 로봇
- 프로젝트 정의 : 정밀 링크 구조의 로봇 하드웨어와 스마트 재활 플랫폼을 결합한 가정용 상지 재활 로봇으로, 환자의 근력 상태에 따라 보조·저항 모드를 선택해 맞춤형 훈련을 하고, 게임 수행도와 근력 변화를 분석한 리포트를 제공하는 시스템

<!-- 대표 사진: docs/images에 올린 뒤 아래 주석을 풀고 경로 수정 -->
<!-- ![대표 이미지](docs/images/main.png) -->

**1-2. 개발 배경 및 필요성**
- **재활 적기 치료의 어려움** : 뇌졸중이나 사고로 상지 기능이 저하된 환자에게 꾸준한 재활은 필수지만, 평균 3개월 이상의 입원 대기로 결정적인 회복 시기를 놓치고 장애가 고착화되는 경우가 많습니다.
- **높은 재활 비용** : 고가의 병원 치료비와 보험의 한계, 장기 치료에 따른 누적 비용이 환자와 보호자에게 큰 부담이 됩니다. 시중에는 저가 수동 기구(11만-29만 원)와 고가 전문 로봇(1.2억-3.5억 원) 사이의 공백이 존재합니다.
- **객관적 데이터의 부재** : 기존 수동형 훈련 기구는 환자가 가하는 힘이나 근육 자극 정도를 정량적으로 측정할 수 없어, 센서 기반의 생체 데이터 수집과 분석이 필요합니다.
- 따라서 거동이 불편한 환자도 가정이나 1차 의료기관에서 중단 없이 재활을 이어갈 수 있는 저비용·고효율 대안이 필요합니다.

**1-3. 프로젝트 특장점**
- **저비용 고효율** : 일반 가정에서도 도입 가능한 가격 경쟁력을 갖추면서, 전문 의료 기기에 상응하는 정밀한 훈련 효율을 목표로 설계
- **데스크탑형 설계** : 일반 책상에 거치해 바로 사용할 수 있는 공간 활용성
- **두 가지 훈련 방식** : 목적에 따라 게임 모드와 자유 모드 중 선택
  - 게임 모드 : 물 채우기, 줄다리기, 미로찾기 3종의 재활 게임으로 목표를 달성하며 훈련
  - 자유 모드 : 게임 없이 원하는 방향으로 자유롭게 반복 훈련
- **개인 맞춤형 훈련 강도** : 로드셀로 감지한 운동 의도 방향은 그대로 두고 움직임 배율만 조절
  - 보조 모드 : 의도한 양보다 더 크게 움직여 적은 힘으로도 수월하게 이동
  - 저항 모드 : 의도한 양보다 더 적게 움직여 더 큰 힘을 들이도록 유도해 근력 강화
- **몰입형 훈련 환경** : 게임 콘텐츠로 반복 훈련의 지루함을 줄이고 자발적 참여 유도
- **데이터 기반 객관적 리포트** : 로드셀·EMG 센서 데이터를 분석해 시각화된 결과 리포트 제공
- **이중 안전장치** : 관절 과회전을 막는 물리적 락(스토퍼)과, 소프트웨어와 무관하게 모터 전원을 끊는 독립 비상정지 회로

**1-4. 주요 기능**
- **정밀 링크 구조 하드웨어** : 알루미늄 프로파일 프레임과 3D 프린팅 부품으로 관절 궤적을 부드럽게 추종하는 링크 구조 구현
- **로드셀 기반 운동 의도 파악** : 손잡이 내부에 십자 배치한 로드셀 4개로 전·후·좌·우 및 대각선 방향과 힘의 크기 판별
- **보조·저항 제어 알고리즘** : 선택된 모드에 따라 모터 구동 배율을 계산하고 PWM으로 듀얼 모터 제어
- **EMG 센서 기반 생체 데이터 수집** : 근활성도 데이터를 실시간 수집
- **재활 분석 리포트** : 최대·평균 힘, 수행 횟수, 운동 시간 등 정량 지표 산출, EMG 선형회귀로 회복 추세(개선/유지/저하) 판정 및 다음 세션 예측
- **재활 게임 콘텐츠** : 첨벙첨벙 물 채우기(X·Z축), 으쌰으쌰 줄다리기(Z축), 어질어질 미로찾기(X·Z축) 3종 + 자유 모드
- **훈련 이력 관리** : 사용자 정보 입력 및 날짜별 훈련 기록 조회
- **안전 기능** : 리미트 스위치 기반 초기 위치 보정, 물리적 락, 독립 비상정지 회로

**1-5. 기대 효과 및 활용 분야**
- 기대 효과
  - 저비용 재활 로봇으로 환자와 보호자의 경제적 부담 완화
  - 가정 내 재활의 연속성을 보장해 재활 골든타임 확보 및 빠른 기능 회복 지원
  - 객관적 훈련 데이터를 의료진과 공유해 가정과 병원을 잇는 진료 연속성 확보
  - 게임 콘텐츠로 심리적 스트레스를 줄이고 재활 의지 고취
- 활용 분야 : 가정 내 맞춤형 재활, 중소규모 요양 병원 및 지역 보건소·복지관, 고령자 상지 근력 유지, 운동선수·연주자 정밀 동작 훈련, 디지털 치료제(DTx) 기반 헬스케어

**1-6. 기술 스택**
- 게임 / UI : Godot Engine 4.x (GDScript)
- 제어 서버 / 데이터 분석 : Qt6 (C++), Python
- 임베디드 제어 : Arduino Mega (C/C++), BTS7960 모터 드라이버, DC 엔코더 모터
- 센서 : 빔형 로드셀 4개 + HX711, EMG(근전도) 센서, 리미트 스위치
- 메인 컨트롤러 : Raspberry Pi 4 (Linux)
- 통신 : UART (Arduino ↔ Raspberry Pi), 로컬 TCP 소켓 + JSON (Qt 서버 ↔ Godot)
- 설계 / 분석 도구 : SolidWorks, 3D 프린팅, MATLAB (로드셀 캘리브레이션)
- 협업 : GitHub, Notion

---

## 💡 2. 팀원 소개

| 🛠️ | 📡 | 🖥️ | 🎮 | 👨‍🏫 |
|:---:|:---:|:---:|:---:|:---:|
| **멘티1** | **멘티2** | **멘티3** | **멘티4** | **멘토** |
| • 기구부 설계<br>• SolidWorks 모델링<br>• 프레임·링크 구조 제작<br>• 안전장치 설계<br>• 전원부·회로 구성 | • 센서부 개발<br>• 로드셀 캘리브레이션<br>• Arduino 모터 제어<br> | • 제어부 개발<br>• Qt 서버 구축<br>• EMG 데이터 처리<br>• 재활 분석 리포트 | • 게임 개발부<br>• Godot 재활 게임 개발<br>• UI/UX 설계<br>• TCP 통신 연동 | • 프로젝트 멘토<br>• 기술 자문 |

---

## 💡 3. 시스템 구성도

**3-1. 서비스 구성도**

<img width="1438" height="952" alt="image" src="https://github.com/user-attachments/assets/e62af546-62d5-4fb0-8e15-b59a969b451d" />


- 사용자가 로봇 손잡이를 잡고 훈련 방식(게임 모드 / 자유 모드)과 훈련 강도(보조 모드 / 저항 모드)를 선택합니다.
  - 보조 모드 : 로드셀 기반 의도 방향보다 더 크게 움직이도록 보조
  - 저항 모드 : 로드셀 기반 의도 방향보다 더 적게 움직이도록 유도
  - 자유 모드 : 게임 없이 반복 훈련
- 모니터의 Godot 게임으로 훈련을 진행하고, EMG 센서로 근력 데이터를 실시간 수집합니다.
- 훈련 후 개인 맞춤형 재활 리포트를 생성하며, 병원 재진료 시 경과 참고 자료로 활용할 수 있습니다.

**3-2. 서비스 흐름도**

<img width="1114" height="1006" alt="image" src="https://github.com/user-attachments/assets/b0ee9fc7-bc87-4627-8d42-7d130deebd29" />


1. 사용자가 GUI에서 로그인한 후 운동 모드(보조 / 저항)를 선택합니다.
2. 라즈베리파이는 선택된 운동 정보를 아두이노 메가로 전달하고 시스템 및 센서를 초기화합니다.
3. 아두이노 메가는 근전도 센서(MyoWare), 로드셀, 엔코더 데이터를 수집해 제어 알고리즘을 수행합니다.
4. 선택된 모드에 따라 모터의 동작 방향과 제어 방식을 결정합니다.
5. 운동 중 센서 데이터를 라즈베리파이로 전송해 GUI에 실시간 표시하고 데이터베이스에 저장합니다.
6. 운동이 끝나면 라즈베리파이가 저장된 데이터를 분석해 운동 결과와 향상도를 계산하고 재활 리포트를 생성합니다.
7. 종료 명령이 없으면 다시 로그인 및 운동 선택 단계로 돌아갑니다.

**3-3. H/W 구성도**

<img width="2118" height="1470" alt="image" src="https://github.com/user-attachments/assets/dde71839-d2d1-4c4a-aaa4-ce8cc5521796" />

| 구성 | 부품 |
|:---:|---|
| 센서부 | EMG 센서(MyoWare), 로드셀 |
| 메인 컨트롤러 | 라즈베리파이 4, 아두이노 메가 |
| 로봇 구동 시스템 | DC 엔코더 모터, 모터 드라이버, 감속기 |
| UI | 모드 선택 및 게임 화면, 맞춤형 분석 리포트 화면 |

**3-4. 메뉴 구성도**

<img width="1610" height="950" alt="image" src="https://github.com/user-attachments/assets/0630afc4-137e-44de-9726-1e5f928ec30c" />


**3-5. 테이블 정의서**

<img width="1572" height="904" alt="image" src="https://github.com/user-attachments/assets/d8e526fb-30f0-434f-9a42-680058372ed1" />

---

## 💡 4. 작품 소개영상

> 🎬 **YouTube 작품 소개영상**
> 저비용, 고효율의 AI 기반 맞춤형 상지 재활 훈련 로봇의 개발 배경과 하드웨어 구성, 보조·저항 모드 훈련, 재활 게임 실행 모습을 소개하는 영상입니다.

[![저비용, 고효율의 AI 기반 맞춤형 상지 재활 훈련 로봇 소개영상](https://img.youtube.com/vi/Dy2TFdKQHPU/maxresdefault.jpg)](https://youtu.be/Dy2TFdKQHPU)

▶️ 썸네일을 클릭하면 유튜브에서 영상이 재생됩니다.

---

## 💡 5. 핵심 소스코드

**5-1. 4방향 로드셀 힘 비교를 통한 방향 판별 (Arduino)**

- 손잡이에 배치한 로드셀 4개의 힘(N)을 비교해 가장 큰 힘과 두 번째로 큰 힘을 찾습니다.
- 가장 큰 힘이 임계값보다 작으면 운동 의도가 없는 `NONE`으로 판단합니다.
- 두 번째 힘도 임계값 이상이고 두 힘의 비율이 기준 이상이면 대각선 방향으로, 아니면 가장 큰 힘의 방향으로 판별합니다.

```cpp
#include "HX711.h"
#include <math.h>

// =====================================================
// 센서 개수
// =====================================================
const int SENSOR_COUNT = 4;

// 센서 번호
const int FRONT_SENSOR = 0;  // LC1
const int LEFT_SENSOR  = 1;  // LC2
const int RIGHT_SENSOR = 2;  // LC3
const int BACK_SENSOR  = 3;  // LC4

// =====================================================
// HX711 핀 설정
// =====================================================
const byte DOUT_PINS[SENSOR_COUNT] = {
  25,  // LC1 앞 DAT
  26,  // LC2 왼쪽 DAT
  27,  // LC3 오른쪽 DAT
  28   // LC4 뒤 DAT
};

const byte SCK_PINS[SENSOR_COUNT] = {
  29,  // LC1 앞 SCK
  30,  // LC2 왼쪽 SCK
  31,  // LC3 오른쪽 SCK
  32   // LC4 뒤 SCK
};

HX711 scale[SENSOR_COUNT];

// =====================================================
// 센서 방향 이름
// =====================================================
const char* DIRECTION_NAME[SENSOR_COUNT] = {
  "FRONT",
  "LEFT",
  "RIGHT",
  "BACK"
};

// =====================================================
// 센서별 보정계수 K
// 단위: raw/g
// =====================================================
const float K_RAW_PER_G[SENSOR_COUNT] = {
  222.5480,  // LC1: Up/Down average
  222.3732,  // LC2: Up/Down average
  224.0414,  // LC3: Up/Down average
  225.4151   // LC4: Up/Down average
};

// =====================================================
// 통신 및 방향 판단 설정
// =====================================================
const unsigned long BAUD_RATE = 115200;

////////////// 값 조절 파라미터1 ////////////////
// 0.02N보다 작으면 힘이 없는 것으로 판단
const float FORCE_THRESHOLD_N = 0.02;


// 센서별 무반응 구간
// LC3 RIGHT만 무부하 오인식을 줄이기 위해 크게 설정
const float SENSOR_DEADBAND_N[SENSOR_COUNT] = {
  0.02,  // LC1 FRONT
  0.02,  // LC2 LEFT
  0.04,  // LC3 RIGHT
  0.25   // LC4 BACK
};


////////////// 값 조절 파라미터2 ////////////////
// 두 번째 힘이 가장 큰 힘의 55% 이상이면 대각선
const float DIAGONAL_RATIO = 0.55;

//////////////// 값 조절 파라미터3 /////////////
// 100ms마다 측정 = 약 10Hz
const unsigned long SEND_INTERVAL_MS = 100;


//////////////// 값 조절 파라미터4 /////////////
// 영점 측정 횟수
const int ZERO_SAMPLE_COUNT = 50;



// 센서별 영점 raw
long zeroRaw[SENSOR_COUNT] = {
  0, 0, 0, 0
};

unsigned long packetNumber = 0;
unsigned long lastSendTime = 0;

// =====================================================
// 모든 HX711 준비 확인
// =====================================================
bool allSensorsReady() {
  for (int sensor = 0;
       sensor < SENSOR_COUNT;
       sensor++) {

    if (!scale[sensor].is_ready()) {
      return false;
    }
  }

  return true;
}

// =====================================================
// 모든 HX711이 준비될 때까지 대기
// =====================================================
bool waitAllSensors(unsigned long timeoutMs) {
  unsigned long startTime = millis();

  while (!allSensorsReady()) {
    if (millis() - startTime >= timeoutMs) {
      return false;
    }

    delay(1);
  }

  return true;
}

// =====================================================
// 센서 4개의 raw값 읽기
// =====================================================
bool readAllRaw(long raw[SENSOR_COUNT]) {
  if (!waitAllSensors(200)) {
    return false;
  }

  for (int sensor = 0;
       sensor < SENSOR_COUNT;
       sensor++) {

    raw[sensor] = scale[sensor].read();
  }

  return true;
}

// =====================================================
// 영점 설정
// 실행 중에는 모든 센서에서 손을 떼야 함
// =====================================================
bool setZero() {
  int64_t sum[SENSOR_COUNT] = {
    0, 0, 0, 0
  };

  long raw[SENSOR_COUNT];

  Serial.println("# ========================================");
  Serial.println("# Do not press any load cell.");
  Serial.println("# Measuring zero...");
  Serial.println("# ========================================");

  // 처음 불안정한 측정값 3개 버리기
  for (int sample = 0; sample < 3; sample++) {
    if (!readAllRaw(raw)) {
      Serial.println("# ERROR: HX711 not ready");
      return false;
    }
  }

  // 센서별 영점 평균
  for (int sample = 0;
       sample < ZERO_SAMPLE_COUNT;
       sample++) {

    if (!readAllRaw(raw)) {
      Serial.println("# ERROR: HX711 not ready");
      return false;
    }

    for (int sensor = 0;
         sensor < SENSOR_COUNT;
         sensor++) {

      sum[sensor] += raw[sensor];
    }
  }

  for (int sensor = 0;
       sensor < SENSOR_COUNT;
       sensor++) {

    zeroRaw[sensor] =
        sum[sensor] / ZERO_SAMPLE_COUNT;

    Serial.print("# ");
    Serial.print(DIRECTION_NAME[sensor]);
    Serial.print(" zeroRaw = ");
    Serial.println(zeroRaw[sensor]);
  }

  Serial.println("# Zero setting complete.");
  Serial.println("# ========================================");

  return true;
}

// =====================================================
// raw값을 힘 N으로 변환
// =====================================================
float calculateForceN(int sensor, long raw) {
  // raw가 증가하거나 감소해도 변화량의 크기 사용
  float rawDifference =
      fabs((float)(raw - zeroRaw[sensor]));

  // raw → g
  float weightG =
      rawDifference / K_RAW_PER_G[sensor];

  // g → N
  float forceN =
      weightG * 0.00980665;

  return forceN;
}

// =====================================================
// 인접한 센서 조합을 대각선으로 변환
// =====================================================
const char* getDiagonalDirection(
  int firstSensor,
  int secondSensor
) {
  // 앞 + 왼쪽
  if ((firstSensor == FRONT_SENSOR &&
       secondSensor == LEFT_SENSOR) ||
      (firstSensor == LEFT_SENSOR &&
       secondSensor == FRONT_SENSOR)) {

    return "FRONT_LEFT";
  }

  // 앞 + 오른쪽
  if ((firstSensor == FRONT_SENSOR &&
       secondSensor == RIGHT_SENSOR) ||
      (firstSensor == RIGHT_SENSOR &&
       secondSensor == FRONT_SENSOR)) {

    return "FRONT_RIGHT";
  }

  // 뒤 + 왼쪽
  if ((firstSensor == BACK_SENSOR &&
       secondSensor == LEFT_SENSOR) ||
      (firstSensor == LEFT_SENSOR &&
       secondSensor == BACK_SENSOR)) {

    return "BACK_LEFT";
  }

  // 뒤 + 오른쪽
  if ((firstSensor == BACK_SENSOR &&
       secondSensor == RIGHT_SENSOR) ||
      (firstSensor == RIGHT_SENSOR &&
       secondSensor == BACK_SENSOR)) {

    return "BACK_RIGHT";
  }

  // 앞+뒤 또는 왼쪽+오른쪽이 동시에 큼
  return "MIXED";
}

// =====================================================
// 방향 판단
// =====================================================
const char* determineDirection(
  const float forceN[SENSOR_COUNT]
) {
  int maxIndex = -1;
  int secondIndex = -1;

  // 가장 큰 힘과 두 번째로 큰 힘 찾기
  for (int sensor = 0;
       sensor < SENSOR_COUNT;
       sensor++) {

    if (maxIndex == -1 ||
        forceN[sensor] > forceN[maxIndex]) {

      secondIndex = maxIndex;
      maxIndex = sensor;
    }
    else if (secondIndex == -1 ||
             forceN[sensor] >
             forceN[secondIndex]) {

      secondIndex = sensor;
    }
  }

  float maxForce = forceN[maxIndex];

  // 모든 힘이 임계값 미만
  if (maxForce < FORCE_THRESHOLD_N) {
    return "NONE";
  }

  if (secondIndex != -1) {
    float secondForce = forceN[secondIndex];

    // 두 번째 힘도 임계값 이상인지 확인
    if (secondForce >= FORCE_THRESHOLD_N) {
      float ratio =
          secondForce / maxForce;

      // 두 힘이 비슷하면 대각선 판단
      if (ratio >= DIAGONAL_RATIO) {
        return getDiagonalDirection(
          maxIndex,
          secondIndex
        );
      }
    }
  }

  // 대각선 조건이 아니면 가장 큰 힘의 방향
  return DIRECTION_NAME[maxIndex];
}

// =====================================================
// Raspberry Pi로 패킷 전송
//
// DATA,번호,시간,
// 앞raw,앞N,
// 왼쪽raw,왼쪽N,
// 오른쪽raw,오른쪽N,
// 뒤raw,뒤N,
// 방향
// =====================================================
void sendPacket(
  const long raw[SENSOR_COUNT],
  const float forceN[SENSOR_COUNT],
  const char* direction
) {
  packetNumber++;

  Serial.print("DATA,");
  Serial.print(packetNumber);
  Serial.print(",");
  Serial.print(millis());

  for (int sensor = 0;
       sensor < SENSOR_COUNT;
       sensor++) {

    Serial.print(",");
    Serial.print(raw[sensor]);

    Serial.print(",");
    Serial.print(forceN[sensor], 4);
  }

  Serial.print(",");
  Serial.println(direction);
}

// =====================================================
// setup
// =====================================================
void setup() {
  Serial.begin(BAUD_RATE);

  // HX711 4개 초기화
  for (int sensor = 0;
       sensor < SENSOR_COUNT;
       sensor++) {

    pinMode(SCK_PINS[sensor], OUTPUT);
    digitalWrite(SCK_PINS[sensor], LOW);

    scale[sensor].begin(
      DOUT_PINS[sensor],
      SCK_PINS[sensor]
    );
  }

  // HX711 안정화
  delay(1500);

  Serial.println();
  Serial.println("# ========================================");
  Serial.println("# Four Load Cell Direction System");
  Serial.println("# LC1 = FRONT");
  Serial.println("# LC2 = LEFT");
  Serial.println("# LC3 = RIGHT");
  Serial.println("# LC4 = BACK");
  Serial.println("# ========================================");

  // HX711 연결 상태 확인
  if (!waitAllSensors(3000)) {
    Serial.println(
      "# ERROR: One or more HX711 modules are not ready."
    );

    Serial.println(
      "# Check DAT, SCK, VCC, VDD and GND."
    );

    while (true) {
      delay(1000);
    }
  }

  // 영점 설정
  if (!setZero()) {
    while (true) {
      delay(1000);
    }
  }

  Serial.println(
    "# Packet: DATA,packet,time_ms,"
    "front_raw,front_N,"
    "left_raw,left_N,"
    "right_raw,right_N,"
    "back_raw,back_N,"
    "direction"
  );

  Serial.println("# Send T to reset zero.");
  Serial.println();

  lastSendTime = millis();
}

// =====================================================
// loop
// =====================================================
void loop() {
  // 시리얼 모니터에 T를 입력하면 영점 재설정
  if (Serial.available() > 0) {
    char command = Serial.read();

    if (command == 'T' ||
        command == 't') {

      setZero();
      lastSendTime = millis();
    }
  }

  unsigned long now = millis();

  // 100ms마다 측정
  if (now - lastSendTime <
      SEND_INTERVAL_MS) {

    return;
  }

  long raw[SENSOR_COUNT];
  float forceN[SENSOR_COUNT];

  // 센서값 읽기
  if (!readAllRaw(raw)) {
    Serial.println("WARN,HX711_NOT_READY");
    return;
  }

  lastSendTime = millis();

  // 힘 계산
  for (int sensor = 0;
       sensor < SENSOR_COUNT;
       sensor++) {

    forceN[sensor] =
        calculateForceN(sensor, raw[sensor]);

    // 센서별 무반응 구간보다 작은 값은 힘이 없는 것으로 처리
    if (forceN[sensor] <
        SENSOR_DEADBAND_N[sensor]) {

      forceN[sensor] = 0.0;
    }
  }

  // 방향 판단
  const char* direction =
      determineDirection(forceN);

  // Raspberry Pi로 전송
  sendPacket(
    raw,
    forceN,
    direction
  );
}


```

**5-2. 라즈베리파이 명령 기반 아두이노 모터 구동 (Arduino)**

- 라즈베리파이에서 시리얼로 받은 명령을 한 줄 단위로 버퍼에 모아 처리합니다.
- `M` 명령이면 두 모터의 PWM 값을 읽어 `applyMotorCommand()`로 모터를 구동하고, 그 외 명령은 관리자 명령으로 처리합니다.

```cpp
// readSerialCommands(), processLine() 코드 붙여넣기
```

**5-3. 라즈베리파이와 아두이노 메가 간의 통신 (Qt / C++)**

- `SerialManager` 클래스가 시리얼 포트 연결, 시작/정지 명령 전송, 데이터 수신을 담당합니다.
- 아두이노에서 받은 패킷을 `,` 기준으로 나누고 `FORCE:`, `ANGLE:` 값을 파싱해 센서 데이터로 갱신합니다.

```cpp
// SerialManager.cpp 핵심 부분 (readData, parsePacket 등) 붙여넣기
```

**5-4. 라즈베리파이 메인 코드 (Qt / C++)**

- 시리얼, 센서 처리, 데이터베이스, 소켓 서버, 리포트 모듈을 초기화하고 서로 연결합니다.
- 게임 클라이언트가 보낸 방향 명령(`up`, `down`, `left`, `right`, `stop`)을 PWM 값으로 바꿔 아두이노로 전달합니다.
- 운동 세션의 시작·종료와 데이터 저장, 재활 리포트 생성을 관리합니다.

```cpp
// main.cpp 핵심 부분 붙여넣기
```

**5-5. 게임 - 서버 TCP 통신 (Godot / GDScript)**

- `TCPManager.gd`는 Autoload 싱글톤으로, Qt 서버(`127.0.0.1:9000`)에 접속해 센서 데이터를 받습니다.
- 수신한 JSON(`direction`, `dx`, `dy`, `force`, `intent`, `mode`)을 파싱해 게임 화면에 반영하고, 모드 변경 요청을 서버로 보냅니다.

```gdscript
# TCPManager.gd 핵심 부분 붙여넣기
```

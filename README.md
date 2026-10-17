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
float rawToForceN(byte sensor, long raw) {
  float deltaRaw = fabs((float)(raw - zeroRaw[sensor]));
  float weightG = deltaRaw / K_RAW_PER_G[sensor];
  return weightG * 0.00980665f;
}

const char* determineDirection(const float forceN[SENSOR_COUNT]) {
  byte maxIndex = 0;
  byte secondIndex = 1;

  if (forceN[secondIndex] > forceN[maxIndex]) {
    byte temp = maxIndex;
    maxIndex = secondIndex;
    secondIndex = temp;
  }

  for (byte i = 2; i < SENSOR_COUNT; i++) {
    if (forceN[i] > forceN[maxIndex]) {
      secondIndex = maxIndex;
      maxIndex = i;
    } else if (forceN[i] > forceN[secondIndex]) {
      secondIndex = i;
    }
  }

  float maxForce = forceN[maxIndex];
  float secondForce = forceN[secondIndex];

  if (maxForce < FORCE_THRESHOLD_N) return "NONE";

  if (secondForce >= FORCE_THRESHOLD_N &&
      secondForce / maxForce >= DIAGONAL_RATIO) {
    return diagonalDirection(maxIndex, secondIndex);
  }

  return DIRECTION_NAMES[maxIndex];
}



```

**5-2. 방향·힘 → 목표 위치 이동 벡터 → IK 호출 (Raspberry Pi / Qt C++)**

- 제어 흐름의 중심으로, 사용자가 힘을 준 **의도**가 로봇의 **이동 목표**로 바뀌는 부분입니다.
- 아두이노에서 받은 방향과 힘 크기를 좌우(LR)·앞뒤(FB) 성분으로 분해합니다.
- 보조 / 저항 / 자유 모드의 차이는 여기서 `modeScale` 배율로 만들어집니다.
- 배율이 적용된 힘을 이동량으로 바꿔 현재 위치에 누적(오픈루프)하고, 목표 위치로 IK를 계산합니다.

```cpp
// 방향 + 힘 크기 → 좌우/앞뒤 성분
int lrSign = 0, fbSign = 0;
directionToAxis(data.direction, lrSign, fbSign);
double magnitude = dominantMagnitude(data);
rawLr = lrSign * magnitude;
rawFb = fbSign * magnitude;

// 모드별 배율 (Assist / Resist / Free)
double lr = rawLr * modeScale;
double fb = rawFb * modeScale;

// 힘 → 목표 위치 이동 벡터
double stepPx = lr * stepGain;
double stepPy = -fb * stepGain;

// 오픈루프 누적
double targetPx = currentPx + stepPx;
double targetPy = currentPy + stepPy;

// IK 계산
double theta1Deg, theta2Deg;
bool ok = computeIK(targetPx, targetPy, theta1Deg, theta2Deg);
```

**5-3. 역기구학(IK) 계산 — computeIK (Raspberry Pi / Qt C++)**

- 직교좌표 목표 위치 `(Px, Py)`를 두 모터(AB, AD)의 관절각으로 바꿔주는 수학적 핵심 함수입니다.
- 로봇 기구(마름모형 4절 링크, L = 225mm)에 종속된 유일한 코드입니다.
- 목표가 최대 도달 범위를 넘으면 같은 방향으로 범위 안까지 줄이고, 최소 거리보다 가까우면 특이점으로 보고 계산하지 않습니다.
- 목표 방향 각도 φ와 링크 벌어짐 각도 β로 두 관절각을 구합니다.

```cpp
bool ExerciseController::computeIK(double px, double py, double &theta1Deg, double &theta2Deg) const
{
    double r = qSqrt(px * px + py * py);

    if (r > kMaxReachMM) {            // 도달 범위 초과 시 스케일 다운
        double scale = kMaxReachMM / r;
        px *= scale; py *= scale;
        r = kMaxReachMM;
    }
    if (r < kMinReachMM)              // 특이점 회피
        return false;

    double phiRad  = qAtan2(py, px);
    double betaRad = qAcos(qBound(-1.0, r / kMaxReachMM, 1.0));

    double phiDeg  = qRadiansToDegrees(phiRad);
    double betaDeg = qRadiansToDegrees(betaRad);

    theta1Deg = -phiDeg - betaDeg;          // AB 모터
    theta2Deg = 180.0 + phiDeg - betaDeg;   // AD 모터
    return true;
}
```

**5-4. 관절각 변화량 → 모터 명령 (Raspberry Pi / Qt C++)**

- 실제로 로봇이 움직이는 출구로, 목표 관절각과 현재 관절각의 차이를 모터 PWM 명령으로 바꿉니다.
- 변화량이 데드밴드보다 작으면 모터를 움직이지 않아 미세한 떨림을 막습니다.
- 변화량 크기로 PWM 세기를, 부호로 회전 방향을 정하고, 모터 장착 방향 보정값(`DirectionSign`)을 곱합니다.
- 현재 위치·각도를 갱신한 뒤 두 모터의 PWM 명령을 아두이노로 보낼 수 있도록 시그널을 발생시킵니다.

```cpp
double deltaTheta1 = theta1Deg - currentTheta1Deg;
double deltaTheta2 = theta2Deg - currentTheta2Deg;

if (qAbs(deltaTheta1) > angleDeadbandDeg) {
    int mag  = angleToPwm(qAbs(deltaTheta1));
    int sign = (deltaTheta1 > 0) ? 1 : -1;
    pwmAB = abDirectionSign * sign * mag;
}
if (qAbs(deltaTheta2) > angleDeadbandDeg) {
    int mag  = angleToPwm(qAbs(deltaTheta2));
    int sign = (deltaTheta2 > 0) ? 1 : -1;
    pwmAD = adDirectionSign * sign * mag;
}

currentPx = targetPx;  currentPy = targetPy;
currentTheta1Deg = theta1Deg;  currentTheta2Deg = theta2Deg;

emit motorCommandReady(pwmAB, pwmAD);
```

**5-5. 게임 ↔ 서버 TCP 통신 (Godot / GDScript)**

- `TCPManager.gd`는 Autoload 싱글톤으로, 게임 어느 화면에서든 같은 연결을 사용합니다.
- 라즈베리파이 Qt 서버(`127.0.0.1:9000`)에 접속하고, 매 프레임 연결 상태를 확인합니다.
- 서버가 줄 단위로 보내는 JSON을 파싱해 방향·이동량·힘·운동 의도·모드(`direction`, `dx`, `dy`, `force`, `intent`, `mode`)를 갱신하고, 각 게임은 이 값으로 캐릭터와 오브젝트를 움직입니다.
- 게임은 모터를 직접 제어하지 않고 세션 시작·종료, 훈련 모드 선택 같은 **요청만** 서버로 보냅니다.
- 서버 연결 전에 보낸 메시지는 대기열에 저장했다가 연결되면 한꺼번에 전송해, 명령이 유실되지 않도록 했습니다.

```gdscript
func _process(delta):
	tcp.poll()
	var status = tcp.get_status()
	if status == StreamPeerTCP.STATUS_CONNECTED and not connected:
		connected = true
		print("서버 연결 성공")
		_flush_pending_messages()
	if status != StreamPeerTCP.STATUS_CONNECTED and connected:
		connected = false
		print("서버 연결 끊김 (상태: ", status, ")")
	if connected and tcp.get_available_bytes() > 0:
		var data = tcp.get_utf8_string(tcp.get_available_bytes())
		for line in data.split("\n"):
			if line.strip_edges() != "":
				var json = JSON.parse_string(line)
				if json:
					current_direction = json.get("direction", "")
					current_dx = json.get("dx", 0.0)
					current_dy = json.get("dy", 0.0)
					current_force = json.get("force", [])
					current_intent = json.get("intent", false)
					current_mode = json.get("mode", "")

func _send_json(data: Dictionary) -> void:
	var json_str = JSON.stringify(data) + "\n"
	if connected:
		tcp.put_data(json_str.to_utf8_buffer())
	else:
		_pending_messages.append(json_str)
		print("서버 미연결 상태 - 메시지 대기열에 저장: ", data.get("command", ""))

func _flush_pending_messages() -> void:
	for msg in _pending_messages:
		tcp.put_data(msg.to_utf8_buffer())
	_pending_messages.clear()

func send_start_session(user_id: String, age: int, gender: String) -> void:
	current_user_id = user_id
	_send_json({
		"command": "start_session",
		"user_id": user_id,
		"age": age,
		"gender": gender
	})

func send_end_session() -> void:
	_send_json({"command": "end_session"})

func send_training_mode(mode: String) -> void:
	_send_json({
		"command": "training_mode",
		"mode": mode
	})
```

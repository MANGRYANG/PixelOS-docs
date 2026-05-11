# PixelOS 개발 문서

> 32비트 x86 환경에서 동작하는 커스텀 OS인 **PixelOS**의 개발 과정, 구조 설계, 구현 기록, 실험 결과를 정리한 문서 저장소입니다.

이 저장소는 PixelOS 본 프로젝트의 코드 저장소가 아니라, 개발 과정에서 작성한 문서와 실험 기록을 관리하기 위한 문서 레포지토리입니다.

### PixelOS 코드 저장소
[![PixelOS Docs](https://img.shields.io/badge/PixelOS-Repository-orange?style=for-the-badge&logo=qemu)](https://github.com/MANGRYANG/PixelOS-docs)

### 문서 저장소
[![PixelOS Docs](https://img.shields.io/badge/PixelOS-Documentation-purple?style=for-the-badge&logo=obsidian)](https://github.com/MANGRYANG/PixelOS-docs)

---

## 프로젝트 개요

PixelOS는 운영체제의 핵심 구성 요소를 직접 구현하면서, 단순한 게임 애플리케이션이 OS 위에서 어떻게 실행되고 OS와 어떤 방식으로 상호작용하는지 관찰하기 위한 커스텀 OS 프로젝트입니다.

이 프로젝트의 핵심 목적은 완성도 높은 범용 운영체제를 만드는 것이 아니라, 다음 흐름을 직접 구현하고 확인하는 데 있습니다.

1. 부트로더에서 커널로 진입
2. 커널 초기화
3. 인터럽트, 타이머, 입력 처리
4. 그래픽 및 윈도우 시스템 구성
5. 태스크와 유저 모드 실행 흐름 구성
6. 시스템 콜을 통한 OS-애플리케이션 인터페이스 구현
7. Pong 게임 실행
8. 시스템 콜 호출량과 렌더링 비용 관측
9. 게임 실행 구조 최적화 실험

---

## 문서화 목표

이 문서 저장소는 단순한 작업 기록이 아니라, PixelOS를 구현하면서 어떤 문제를 만났고, 어떤 방식으로 해결했으며, 그 결과 OS와 게임 사이에서 어떤 실행 흐름이 만들어졌는지를 추적하기 위한 공간입니다.

주요 문서화 대상은 다음과 같습니다.

- 기능 구현 과정
- 커널 구조 변화
- 시스템 콜 추가 과정
- 유저 모드 앱 실행 흐름
- Pong 게임 구현 과정
- OS와 게임 사이의 데이터 교환 방식
- 렌더링 및 입력 처리 관련 실험
- 성능 관측 및 최적화 결과
- 커밋 단위 리뷰

---

## 저장소 구조

```text
PixelOS/
├── Canvas/
│   └── Obsidian Canvas 관련 파일
│
├── Docs/
│   └── 프로젝트 개요 문서
│
├── Images/
│   └── 개발 과정 및 실험 결과 스크린샷
│
├── PixelOS/
│   ├── 000. 초기 부트로더 구현.md
│   ├── 001. 보호 모드 전환 및 커널 로드.md
│   ├── ...
│   ├── 057. Pong 게임 루프에 delta tick 전달 구조 추가.md
│   ├── E01. Batching을 통한 Draw Call 감소 실험.md
│   └── E02. Frame 처리 빈도 조절에 따른 syscall 교환량 감소 실험.md
│
└── Template/
    ├── Docs_Template.md
    ├── Experiment_Template.md
    └── Review_Template.md

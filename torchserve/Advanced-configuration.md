# Advanced configuration(작성중)

---

TorchServe를 사용자 정의하려는 경우 이 문서에 설명된 구성 옵션을
사용하면 됩니다.

TorchServe를 구성하기 위한 우선순위로 나열된 세가지 방법입니다.

1. Environment variables (환경변수)
2. Command line arguments (명령행 아규먼트)
3. Configuration file (구성파일)

예를 들어, 명령행 아규먼트는 환경변수로 덮어 씌어질 수 있고 구성파일은
명령행 아규먼트로 덮어 씌어져 재정의 될 수 있습니다.

## Configure TorchServe listening address and port

TorchServe는 기본적으로 보안인증을 지원하지는 않습니다.
무단 엑세스를 방지하려면, 
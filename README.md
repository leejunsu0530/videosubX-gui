# videosubX-gui
https://www.gradio.app/guides/dynamic-apps-with-render-decorator

https://www.gradio.app/guides/custom-CSS-and-JS 

PySide6 based gui of videosubX
버전관리는 따로 하고, git clone으로 사용하는 등의 방식으로 만들기 위해 메인에서 분리함. 
gradio 데모를 만들고 실제 지원은 pyside로 할 예정.

## TODO
- [ ] gradio + yt-dlp args gui 테스트
- [ ] pwcpp gui 테스트


gui는 pyqt로 하고, 정적인 부분은 qt designer로, 동적인(yt-dlp 옵션 부분 등) 부분은 내가 코드로 직접 구현. 그리고 ui와 백앤드 사이에 
```
Core (yt-dlp, ffmpeg, AI 처리)
↓
Service Layer (옵션 처리, 상태 관리)
↓
UI (Qt)
```
이런 구조로 해야 함. 관련 내용은 노트 참조.

### yt-dlp gui
- [ ] 시작시 yt-dlp 자동 업데이트(설정에서 변경 가능)
- [ ] 리스트, 겔러리 형태로 영상 띄워주는 형태의 관리창
     - [ ] 사용자가 표시할 정보 편집 가능(채널은 채널 썸내일도)
     - [ ] 다운로드할 영상도 이렇게 표시
     - [ ] 과거 다운로드한 영상들 썸내일과 정보 띄워주고 관리
     - [ ] da도 관리. 다운된 파일 읽어서 다운로드 날짜 등도 표시.  
     - [ ] 파이썬식 조건을 걸어서 필터링 가능. yt-dlp 필터로도 가능. 필터링시 전체 체크 누르면 그것들만 포함됨.
     - [ ] 영상별 체크박스 형태의 선택기
     - [ ] 파일탐색기 기능(파일들의 폴더 관리, 엘범 등의 메타데이터 관리 - 일괄 엘범 변경 등)
- [ ] 인자 선택창: 인텔리센스같은 형식 + 리스트로 하나씩 있고 그걸 아래 +버튼 눌러서 추가하는 형태. 인자를 만들고 나면 구문강조된 파이썬 ydl_opts로 바뀌고 추가편집 가능. 이전 옵션 기억 및 저장 가능. outtmpl 미리보기 가능
- [ ] 여러 기능 창들
    - [ ] 챕터 수정용 gui
    - [ ] 다운로드 형식 선택기(개별 영상, 여러 영상, 전체 영상)
    - [ ] 구간 선택기(잘라내는 등)
    - [ ] 챕터 생성기(이건 댓글창을 불러오고, PP를 응용)
    - [ ] ffmpeg 계열 gui(메타데이터 열람 및 수정 등)
    - [ ] 유저가 PP, 필터 등을 만드는 창
  - [ ] 설정창
    - [ ] json/yaml 등과 연결

### 기타
- [ ] setting을 toml로 처리? 이 경우 파일과 gui에서의 연동을 어떻게 하는지 확인

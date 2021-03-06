# Unity GSheet Util Manual

Installation
------------
GSheet 리포지토리를 다운받고 리포지토리의 GSheet 폴더를 유니티 프로젝트의 Assets 폴더 안에 넣습니다

Setting
-------
### 인증 정보 세팅
  * Assets/GSheet 폴더의 GSheetSettings 에셋을 선택합니다
  * Client 정보 세팅
    * Client ID와 Client Secret 키를 세팅합니다 (하단의 Client 세팅법 참고)
  * Access Code 받기
    * Client 정보를 세팅하면 Get Access Code 버튼을 클릭합니다
    * 허용 버튼을 누르고 나오는 키를 복사해 Unity Inspector의 Access code에 입력합니다
    * 오류 메시지 없이 Access Token과 Refresh Token이 새로고침되면 성공
### 자동 생성되는 에셋 위치
  * Script Path : 자동으로 생성되는 스크립트 폴더입니다
  * Editor Script Path : 자동으로 생성되는 에디터 스크립트 폴더입니다
  * Data Asset Path : 자동 생성되는 데이터 에셋 폴더입니다
  * Script Path와 Editor Script Path에 해당하는 경로에 폴더가 없으면 새로 폴더를 생성해줍니다
  * 바꿀 이유가 없으면 그냥 사용하셔도 됩니다

워크시트
-------
### 샘플 워크시트
### 워크시트 포맷
  * 1행에 필드 입력을 입력하고 2행부터 데이터를 입력합니다
  * `string`: 필드 앞에 s를 붙입니다
  * `int`: 필드 앞에 n을 붙입니다
  * `float`: 필드 앞에 f를 붙입니다
### 데이터 스크립트 생성
  * GSheetManager 에셋을 선택합니다
  * Spreadsheet Name과 Worksheet Name을 입력합니다
  * Create data script 버튼을 클릭합니다
  * GSheetSettings에 설정한 Script Path와 Editor Script Path에 각각 스크립트가 생성되면 성공
  * GSheetSettings에 설정한 Path에 해당하는 폴더가 없을 경우 스크립트 생성에 실패합니다. 폴더 경로가 존재하는지 확인해주세요
  * 열만 추가한 겨웅에는 직접 해당 asset을 클릭하고 Download From Google Spread Sheet 버튼을 눌러 추가된 내용을 갱신해야 합니다.
    * 그렇게 하지 않으면 해당 필드값은 0으로 됨
### 데이터 에셋 생성
  * 에셋을 생성하려는 폴더에서 우클릭 → Create → Custom → GSheet → Create {WorkSheetName}Data 클릭
    (예제에서는 Create SampleWorkSheetData)
  * 생성된 에셋의 이름을 적당히 수정하고
  * 에셋을 선택
  * SpreadSheet Name과 WorkSheet Name을 입력
  * Download From Google Spread Sheeet 버튼 클릭
  * 위와 같이 Data가 Inspector에 표시되면 성공
  * 주의사항
    * Inspector 상에서도 데이터를 수정할 수 있도록 되어있지만, Unity에서 수정하더라도 구글 시트에 적용되지는 않습니다.
    * Unity 상에서의 데이터 수정은 테스트 용도로만 사용하고, 실제 데이터 편집은 구글 시트에서 다운받는 식으로 해야 합니다
### 데이터 수정
  * 데이터 값 수정, 데이터에 새로운 행 추가
    * 새로운 필드(열) 추가 없이 행추가와 데이터 수정만 이루어 졌을 경우
    * 데이터 에셋의 Inspector에서 Download 버튼을 누르는 것만으로 데이터 업데이트가 가능합니다
    * Download From Google Spread Sheet 버튼을 클릭하고 에셋 데이터 업데이트 확인
  * 데이터에 새로운 필드(새로운 열) 추가
    * 필드를 추가할 경우 스크립트를 새로 생성해 주어야 합니다
    * GSheetManaer 선택 후, Inspector에서 SpreadSheetName과 WorkSheetName 입력
    * Create Data Script 버튼 클릭
    * 생성되어 있는 데이터 에셋 선택
    * 데이터 내용에 새로운 필드가 추가된 것을 확인
    * Download From Google Spread Sheet 버튼 클릭

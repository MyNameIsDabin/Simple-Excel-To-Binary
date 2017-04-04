# Simple-Excel-To-Binary

![](http://cfile10.uf.tistory.com/image/2757E73457A34E9D1EDC93)

 엑셀파일로 작성한 데이터를 바이너리 파일로 만들어주는 프로그램입니다.
 
![](http://cfile9.uf.tistory.com/image/230CB73C57A2191C1285C5)


 일단 바이너리로 변경할 엑셀파일의 구조는 최소한 위와같이 데이터들이 시작되는 첫번째 행에는 데이터 타입이 기입되어야 합니다.

| String, UTF8, Unicode | 문자열(UTF8 혹은 유니코드)|
|---|---|
| double | 8바이트 실수 데이터 |
| float | 4바이트 실수 데이터 |
| int32 | 4바이트 정수 데이터 |
| int64 | 8바이트 정수 데이터 |
| bool | 1바이트 정수 데이터 |


데이터 타입은 위의 표에 나와있는 5가지를 지원하며 대소를 구분하지 않고 기입하면 됩니다.

※ 문자열 데이터의 경우는 바이너리 파일이 추출될때 문자열의 길이가 2바이트 정수데이터로 먼저 저장된다.


![](http://cfile3.uf.tistory.com/image/210AF13357A21AEE054117) 


프로그램의 상단 탭에는 바이너리로 변환할 데이터의 첫번째 셀의 행과 열을 입력하도록 되어있습니다.

'행'의 기본값이 1이 아니라 2인 이유는 아래와 같은 엑셀파일의 구조를 기준으로 하기 때문입니다.

![](http://cfile6.uf.tistory.com/image/22139E3B57A34EC212CA07)  

 
(행이 '2' 이기 때문에 첫번째 행은 읽지 않습니다.)


![](http://cfile8.uf.tistory.com/image/2516FA3457A21B7915A308)  

 
바이너리 파일의 문자열 인코딩 형식을 결정할 수 있는데 엑셀파일 내에서 데이터타입에  'String' 을 기입한 데이터만 적용됩니다.

예를들어 데이터 타입에 'Unicode' 를 적어놓고 프로그램에서 UTF-8로 설정후 바이너로파일을 추출해도 소용이 없습니다!

반면에 'String'으로 기입하였다면 유니코드로 문자열 데이터가 인코딩됩니다.

참고로 '사용자설정'을 사용한다면 엑셀파일에 기입된 데이터타입을 그대로 사용합니다.

 ---
 
0.4v

- 엑셀파일 불러올때 에러메세지 띄우도록 수정

- 바이너리 파일 맨 앞에 파일의 사이즈정보를 저장하지 않도록 수정

- 빅 엔디안 방식으로 저장하던것을 리틀 엔디안 방식으로 저장하도록 수정

 

0.5v

- Bool 타입 지정할 수 있도록 수정

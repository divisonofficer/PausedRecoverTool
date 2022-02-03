# PausedRecoverTool
Kotlin - Api call 실패하면 쌓아뒀다가 다시 복구하자


Retrofit 으로 Call을 요청했는데, 네트워크 / 서버 문제로 요청이 실패했을 경우, 꼭 이 요청을 다시 보내야할 경우, Call을 Db에 보관했다가 다시 복구하는 방법을 쓸 수 있습니다.






코드만 보세요 코드만...


TryCall.run 으로 실행된 retrofit call은, call 이 실패했을 경우 PausedBody라는 데이터로 전환되어 Db에 보관됩니다.

RecoverTool.run을 이용하면 보관된 call을 복원하여 다시 시행합니다.
RecoverTool.addMethod를 통해 복원된 call을 어디로 할당할지 지정해줘야합니다.
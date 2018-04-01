Git에 대한 이해
===============

###개념정리

-	git의 데이터는 파일 시스템의 Snapshot으로 이해 - 아주 작은 크기로 생성

-	Commit을 하거나 프로젝트의 상태를 저장할 때 마다 데이터 생성

-	작업중인 파일이 달라지지 않은 경우 Git은 새로운 Git파일을 생성하지 않음

###Git의 파일 상태

-	commited : 데이터가 로컬 저장소에 안전하게 저장

-	modified : 수정한 파일을 아직 로컬 저장소에 commit하지 않은 것

-	staged : 현재 수정한 파일을 곧 commit할 것이라고 표시한 상태

###Git의 영역분리

-	Git Directory : Git이 프로젝트의 메타데이터와 객체 데이터베이스를 저장하는 곳(.git)

-	Working Directory : 수정할 파일들이 있는 디렉토리

	-	Tracked : 이미 Snapshot에 포함되어있는 파일  
	-	UnTracked : Tracked파일이 아닌 것

-	Staging Area : Git Directory에 있으며, 단순한 파일이고 곧 commit할 파일에 대한 정보를 저장

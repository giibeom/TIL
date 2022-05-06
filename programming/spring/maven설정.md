### MVN 명령어

(ex. mvn clean)

- clean : maven build 시 생성된 모든 것들을 삭제하는 명령어
- install : 패키징한 파일을 추가적으로 로컬 repository에 배포하는 명령어
- deploy : 패키징한 파일을 원격 저장소에 배포 (nexus 혹은 maven central 저장소)
- compile : 컴파일 수행
- test : 컴파일 수행 후 테스트 클래스 수행
- package : 컴파일된 결과물을 패키지 파일로 생성
    - 컴파일, 테스트, 빌드를 수행하여 패키지 파일을 생성
    - 프로텍트 이름, 버전, 패키징 옵션에 맞게 파일이 생성
    - pom.xml에서 아래와 같이 설정하면 결과 파일은 **gibeom-1.0-SNAPSHOT.war** 로 생성된다.
    
    ```xml
    <artifactId>gibeom</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>war</packaging>
    ```
    

### MVN 옵션

(ex. mvn clean package -Dmaven.test.skip=true)

- -D, --define : 시스템 속성 정의

```bash
clean install package -Dmaven.test.skip=true -Dtarget=develop -DbranchName=Saas
```

pom.xml 파일

```xml
<resource>
	<directory>/src/main/resources-${target}/${branchName}</directory>
</resource>
```

**-Dtarget** == ${target} 값 설정

**-DbranchName** == ${branchName} 값 설정

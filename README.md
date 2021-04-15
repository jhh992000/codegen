## 코드 제너레이터 eclipse 플러그인
* 이 플러그인은 과거 삼성SDS의 anyframe의 개발환경에 있던 코드제너레이터 플러그인입니다.
* 반복적으로 생성하는 파일이나 클래스들을 사용자가 커스터마이징한 템플릿을 이용하여 자동생성해줍니다.
* DB 테이블을 지정하여 해당 테이블에 대응하는 다양한 코드들(CRUD)을 생성할 수 있습니다.
* 사용하기 매우 간단한 구조를 가지고 있어서 제가 SI 프로젝트를 할때 가끔 사용하곤 합니다.
---
### 의존관계가 있는 플러그인
- SQLExplorer

### 커스텀 템플릿을 제작하기 위해 필요한 사전 지식
- Velocity
---

### 템플릿 파일들이 위치한 경로 
> /eclipse/plugins/anyframe.plugins.codegen.templates_1.2.0/wizards
---
#### 커스텀 템플릿 관리 파일
* 커스텀 템플릿을 등록 및 관리는 아래의 위자드 설정파일에 추가 또는 삭제한다.

> /eclipse/plugins/anyframe.plugins.codegen.templates_1.2.0/wizards/wizards.xml

---
### 커스텀 템플릿 추가 예시
```
<?xml version="1.0" encoding="UTF-8"?>

<templates>
	<category name="UserDefinedService">
		<wizards>
			<wizard-def description="커스텀_템플릿명1" template="UserDefinedService/커스텀_템플릿_경로1/커스텀_템플릿_설정_파일1.xml" />
			<wizard-def description="커스텀_템플릿명2" template="UserDefinedService/커스텀_템플릿_경로2/커스텀_템플릿_설정_파일2.xml" />
		</wizards>
	</category>
</templates>
```
---
## 사용방법
1. plugin 을 다운받는다.
```
git clone https://github.com/jhh992000/codegen.git
```
2. eclipse 폴더안에 들어있는 addins와 links 폴더를 eclipse 의 루트 폴더에 붙혀넣는다.
```
//macOS (예시)
/Applications/SpringToolSuite4.app/Contents/Eclipse/addins
/Applications/SpringToolSuite4.app/Contents/Eclipse/links

//windows (예시)
c:/eclipse/addins
c:/eclipse/links
```
3. eclipse를 재시작한다.
4. Windows > Perspective > Open Perspective > Other...
5. SQL Explorer 선택
6. Connections 탭에서 Create New Connection Profile 을 선택하여 DB에 연결한다. (jdbc 드라이버 설정 필요)
7. 추가한 Connection Profile 선택 우클릭 > Connect
8. Database Structure 탭에서 generate할 대상 테이블을 찾는다.
9. 대상테이블을 선택 우클릭 > Connect Codegen DB 를 선택
10. Codegen 탭에서 본인이 작성한 커스텀 템플릿을 선택하고 우클릭 > Open Wizard 선택  
    ( 참고 : workspace내에 활성 프로젝트 1개이상 존재해야함, 없으면 예외 발생함 )
11. 이 후부터는 각 단계를 모두 사용자가 커스터마이징하는 단계가 시작된다.
12. 최종 Finish를 누르면 템플릿에 정의된 파일들이 주르륵 자동생성된다.  
    ( vm 파일들의 velocity 문법에 오류가 있을경우 자동 생성이 중단됨 )
13. 자동 생성된 코드들을 다듬으며 커스터마이징하여 코딩을 마무리한다.
14. 끝.


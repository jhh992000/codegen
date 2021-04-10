## 코드 제너레이터 eclipse 플러그인
* 이 플러그인은 과거 삼성SDS의 anyframe의 개발환경에 있던 코드제너레이터 플러그인입니다.
* 반복적으로 생성하는 파일이나 클래스들을 사용자가 커스터마이징한 코드 템플릿을 이용하여 자동 생성해주는 기능을 가지고 있습니다.
* DB 테이블을 지정하여 해당 테이블에 대응하는 다양한 코드들을 생성할 수 있습니다.
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

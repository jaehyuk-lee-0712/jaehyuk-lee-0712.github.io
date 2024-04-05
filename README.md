## GIT 블로그
https://elese0821.github.io/

## 루비 명령어 모음
1. Jekyll 다운 받기
gem install bundler 
gem install jekyll

2. 틀생성
jekyll new ./

3. 번들 설치
bundle install

4. 로컬서버 실행
bundle exec jekyll serve 

## post
https://github.com/jekyll/jekyll-compose

Jekyll::작성

- Gemfile에 다음 줄을 추가
gem 'jekyll-compose', group: [:jekyll_plugins]
- 실행
bundle

재빌드
jekyll build

새 게시물 작성
```
$ bundle exec jekyll post "My New Post"
# or specify a custom format for the date attribute in the yaml front matter
$ bundle exec jekyll post "My New Post" --timestamp-format "%Y-%m-%d %H:%M:%S %z"
```

편집기에서 새 초안이나 게시물을 자동으로 엽니다.
  jekyll_compose:
    auto_open: true

JEKYLL_EDITOR 환경 변수 설정:

Windows에서 JEKYLL_EDITOR 환경 변수를 설정하려면, 시스템 환경 변수를 편집해야 합니다. 이는 "시스템 속성"에서 "환경 변수"를 클릭하여 할 수 있습니다.
"시스템 변수" 섹션에서 "새로 만들기"를 선택하고, 변수 이름으로 JEKYLL_EDITOR를, 변수 값으로 Atom 편집기의 실행 파일 경로를 입력합니다.
예를 들어, Atom의 기본 설치 경로를 사용하는 경우, 변수 값은 대략 다음과 같을 것입니다: C:\Users\[YourUsername]\AppData\Local\atom\atom.exe


drafts와 posts: 이들은 Jekyll 사이트에서 다루는 두 가지 주요 컨텐츠 유형을 나타냅니다. 'drafts'는 아직 게시되지 않은 초안이며, 'posts'는 게시할 준비가 된 글입니다.

description: 게시물이나 초안에 대한 짧은 설명입니다. 이는 각 게시물의 요약이나 개요로 사용될 수 있습니다.

image: 게시물이나 초안과 연관된 이미지의 경로나 URL을 지정합니다. 이는 게시물의 시각적 요소로 사용될 수 있습니다.

category: 게시물이나 초안이 속하는 카테고리입니다. 이를 통해 비슷한 주제의 게시물을 그룹화할 수 있습니다.

tags: 게시물이나 초안과 관련된 태그입니다. 이는 특정 키워드나 주제에 따라 게시물을 분류하는 데 도움을 줍니다.

published: 게시물이 공개적으로 게시될지 여부를 결정하는 불리언 값입니다. 'false'로 설정하면 게시물이 사이트에 공개적으로 표시되지 않습니다.

sitemap: 이 값이 'false'로 설정되면 해당 게시물이 사이트의 사이트맵에 포함되지 않습니다. 사이트맵은 검색 엔진 최적화(SEO)에 중요한 역할을 합니다.


## skills

`jekyll`
Jekyll은 간단한, 블로그 지향적인 정적 사이트 생성기입니다. 정적 사이트 생성기란 동적 데이터베이스 기반 시스템이 아닌, 텍스트 파일로부터 웹사이트를 생성하는 소프트웨어입니다. Jekyll은 Ruby로 작성되었으며, Markdown, Liquid, HTML & CSS 등을 사용하여 사이트를 생성합니다. 주요 특징과 사용례는 다음과 같습니다:

### 주요 특징
- 간단한 사용법: 복잡한 데이터베이스 설치나 서버 측 소프트웨어 없이 작동합니다.
- 블로그 지원: 블로그 포스팅을 위한 기본 지원이 포함되어 있으며, 글 작성에 Markdown을 사용할 수 있습니다.
- 테마 사용: 다양한 테마를 적용하여 사이트 디자인을 쉽게 변경할 수 있습니다.
GitHub Pages와의 통합: GitHub Pages 서비스와 직접 호환되어, 무료로 호스팅할 수 있습니다.
- 커스텀 플러그인 사용 가능: Ruby로 작성된 플러그인을 통해 기능을 확장할 수 있습니다.
사용례
- 개인 블로그: 개인적인 글쓰기나 프로젝트 소개를 위한 블로그를 생성할 수 있습니다.
- 프로젝트 문서: 소프트웨어 프로젝트의 문서화에 사용되며, Markdown을 사용하여 쉽게 문서를 작성하고 관리할 수 있습니다.
**포트폴리오 웹사이트**: 개인의 작업이나 프로젝트를 소개하기 위한 포트폴리오 사이트를 만드는 데 사용할 수 있습니다.

### 장점
- 속도와 보안: 데이터베이스를 사용하지 않고 정적 파일을 생성하기 때문에, 로딩 속도가 빠르고 보안이 강화됩니다.
- 커스터마이징 용이성: Liquid 템플릿 언어와 다양한 마크업 언어를 사용하여 높은 수준의 사용자 정의가 가능합니다.
- 커뮤니티 지원: 활발한 개발자 커뮤니티가 있어 다양한 플러그인과 테마가 제공됩니다.
### 단점
- 동적 콘텐츠 제한: Jekyll은 주로 정적 콘텐츠 생성에 초점을 맞추고 있어, 실시간 사용자 인터랙션을 필요로 하는 기능 구현에는 제한적일 수 있습니다.
- 초보자의 진입 장벽: Ruby 설치나 명령줄 사용에 익숙하지 않은 사용자에게는 초기 설정이 다소 복잡하게 느껴질 수 있습니다.
Jekyll은 특히 개발자, 기술 작가, 블로거에게 인기 있는 도구로, 간편한 웹사이트 및 블로그 생성을 위한 효율적인 해결책을 제공합니다.



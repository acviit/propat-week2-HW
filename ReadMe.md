1. VCS란 무엇인가?

Version Control System(버전관리 시스템)으로 파일 변화를 시간에 따라 기록했다가 
나중에 특정 시점의 버전을 다시 불러올 수 있는 시스템입니다.

2. DVCS와 VCS의 차이점
VCS(버전관리 시스템)는 로컬 컴퓨터의 간단한 데이터베이스를 사용하여 파일의 변경 정보를 관리합니다 그리고 하나의 로컬 컴퓨터에서 파일을 관리하는 방식으로 동작합니다

DVCS(분산 버전관리 시스템)는 VCS 처럼 단순히 마지막 파일의 마지막 특정 시간에 데이터를 저장한 파일 시스템을 사용하지 않고 저장소를 히스토리와 더불어 통째로 복제하고 서버에 문제가 생길시 이 복제물로 다시 작업을 시작할 수 있다는 차이점이 있습니다.

3. GIT을 이용하여 remote repository를 생성하고 git용 bash 로 새로 initialize한 local repository랑 연결하는 과정을 스크린샷과 함께 각 명령어의 자세한 설명을 작성하시오. 이때 브랜치명은 main으로 합니다.

-1- git Bash를 실행 후 생성한 디렉토리로 이동 
-2- git init(initialize, 초기화) Git 저장소를 초기화
-3- vim(vi IMproved, vi 에디터를 향상시켜 만든 텍스트 편집기) 파일이름을 적은 뒤에 내용 작성
-4- git add .(working directory에 있는 파일중 변경된 모든 파일을 선택 하는 명령어이다), git commit (의미있는 변경 작업들을 저장소에 기록하는 동작)
-5- 로컬 저장소와 원격 저장소 연결하기
git remote(원격 저장소를 관리할 수 있는 명령어) add origin [원격 저장소 URL]
-6- 로컬 저장소의 변경 내용을 원격 저장소에 업로드
git push -u orgin main

4. .gitignore 사용법과 작성방식 및 내용에 대해서 조사를 해 오시오. (이클래스에 있는 Visual Studio 2022 C++ 프로젝트용 ignore도 git에 업로드 해주세요.)

-1- .gitignore란? 
사용자가 git에 등록 되지 않길 원하는 파일 또는 풀더들의 목록을 저장하는 곳
-2- .gitignore 작성법
#주석의역할을 한다
폴더: /폴더명
파일: 파일명.확장자
폴더 안파일 : /폴더명/파일명.확장자
폴더 안 특정 확장자 파일 전부
폴더 하위 모든 특정 확장자 파일 전부
-3- .gitignore 사용법
(git init을 한 폴더에 .gitgnore 라는 이름으로 파일을 하나 생성 한뒤 
그 안에 한줄씩 제외할 파일 혹은 폴더를 작성하면 된다)
ex) 
fileName.md

/fileName.md

foler/my.txt

folder/**/fileName_2.txt

*.txt

!fileName.txt

-4- Visual Studio 2022 C++ 프로젝트용 ignore
## Ignore Visual Studio temporary files, build results, and
## files generated by popular Visual Studio add-ons.
##
## Get latest from https://github.com/github/gitignore/blob/main/VisualStudio.gitignore

# User-specific files
*.rsuser
*.suo
*.user
*.userosscache
*.sln.docstates

# User-specific files (MonoDevelop/Xamarin Studio)
*.userprefs

# Mono auto generated files
mono_crash.*

# Build results
[Dd]ebug/
[Dd]ebugPublic/
[Rr]elease/
[Rr]eleases/
x64/
x86/
[Ww][Ii][Nn]32/
[Aa][Rr][Mm]/
[Aa][Rr][Mm]64/
bld/
[Bb]in/
[Oo]bj/
[Ll]og/
[Ll]ogs/

# Visual Studio 2015/2017 cache/options directory
.vs/
# Uncomment if you have tasks that create the project's static files in wwwroot
#wwwroot/

# Visual Studio 2017 auto generated files
Generated\ Files/

# MSTest test Results
[Tt]est[Rr]esult*/
[Bb]uild[Ll]og.*

# NUnit
*.VisualState.xml
TestResult.xml
nunit-*.xml

# Build Results of an ATL Project
[Dd]ebugPS/
[Rr]eleasePS/
dlldata.c

# Benchmark Results
BenchmarkDotNet.Artifacts/

# .NET Core
project.lock.json
project.fragment.lock.json
artifacts/

# ASP.NET Scaffolding
ScaffoldingReadMe.txt

# StyleCop
StyleCopReport.xml

# Files built by Visual Studio
*_i.c
*_p.c
*_h.h
*.ilk
*.meta
*.obj
*.iobj
*.pch
*.pdb
*.ipdb
*.pgc
*.pgd
*.rsp
*.sbr
*.tlb
*.tli
*.tlh
*.tmp
*.tmp_proj
*_wpftmp.csproj
*.log
*.tlog
*.vspscc
*.vssscc
.builds
*.pidb
*.svclog
*.scc

# Chutzpah Test files
_Chutzpah*

# Visual C++ cache files
ipch/
*.aps
*.ncb
*.opendb
*.opensdf
*.sdf
*.cachefile
*.VC.db
*.VC.VC.opendb

# Visual Studio profiler
*.psess
*.vsp
*.vspx
*.sap

# Visual Studio Trace Files
*.e2e

# TFS 2012 Local Workspace
$tf/

# Guidance Automation Toolkit
*.gpState

# ReSharper is a .NET coding add-in
_ReSharper*/
*.[Rr]e[Ss]harper
*.DotSettings.user

# TeamCity is a build add-in
_TeamCity*

# DotCover is a Code Coverage Tool
*.dotCover

# AxoCover is a Code Coverage Tool
.axoCover/*
!.axoCover/settings.json

# Coverlet is a free, cross platform Code Coverage Tool
coverage*.json
coverage*.xml
coverage*.info

# Visual Studio code coverage results
*.coverage
*.coveragexml

# NCrunch
_NCrunch_*
.*crunch*.local.xml
nCrunchTemp_*

# MightyMoose
*.mm.*
AutoTest.Net/

# Web workbench (sass)
.sass-cache/

# Installshield output folder
[Ee]xpress/

# DocProject is a documentation generator add-in
DocProject/buildhelp/
DocProject/Help/*.HxT
DocProject/Help/*.HxC
DocProject/Help/*.hhc
DocProject/Help/*.hhk
DocProject/Help/*.hhp
DocProject/Help/Html2
DocProject/Help/html

# Click-Once directory
publish/

# Publish Web Output
*.[Pp]ublish.xml
*.azurePubxml
# Note: Comment the next line if you want to checkin your web deploy settings,
# but database connection strings (with potential passwords) will be unencrypted
*.pubxml
*.publishproj

# Microsoft Azure Web App publish settings. Comment the next line if you want to
# checkin your Azure Web App publish settings, but sensitive information contained
# in these scripts will be unencrypted
PublishScripts/

# NuGet Packages
*.nupkg
# NuGet Symbol Packages
*.snupkg
# The packages folder can be ignored because of Package Restore
**/[Pp]ackages/*
# except build/, which is used as an MSBuild target.
!**/[Pp]ackages/build/
# Uncomment if necessary however generally it will be regenerated when needed
#!**/[Pp]ackages/repositories.config
# NuGet v3's project.json files produces more ignorable files
*.nuget.props
*.nuget.targets

# Microsoft Azure Build Output
csx/
*.build.csdef

# Microsoft Azure Emulator
ecf/
rcf/

# Windows Store app package directories and files
AppPackages/
BundleArtifacts/
Package.StoreAssociation.xml
_pkginfo.txt
*.appx
*.appxbundle
*.appxupload

# Visual Studio cache files
# files ending in .cache can be ignored
*.[Cc]ache
# but keep track of directories ending in .cache
!?*.[Cc]ache/

# Others
ClientBin/
~$*
*~
*.dbmdl
*.dbproj.schemaview
*.jfm
*.pfx
*.publishsettings
orleans.codegen.cs

# Including strong name files can present a security risk
# (https://github.com/github/gitignore/pull/2483#issue-259490424)
#*.snk

# Since there are multiple workflows, uncomment next line to ignore bower_components
# (https://github.com/github/gitignore/pull/1529#issuecomment-104372622)
#bower_components/

# RIA/Silverlight projects
Generated_Code/

# Backup & report files from converting an old project file
# to a newer Visual Studio version. Backup files are not needed,
# because we have git ;-)
_UpgradeReport_Files/
Backup*/
UpgradeLog*.XML
UpgradeLog*.htm
ServiceFabricBackup/
*.rptproj.bak

# SQL Server files
*.mdf
*.ldf
*.ndf

# Business Intelligence projects
*.rdl.data
*.bim.layout
*.bim_*.settings
*.rptproj.rsuser
*- [Bb]ackup.rdl
*- [Bb]ackup ([0-9]).rdl
*- [Bb]ackup ([0-9][0-9]).rdl

# Microsoft Fakes
FakesAssemblies/

# GhostDoc plugin setting file
*.GhostDoc.xml

# Node.js Tools for Visual Studio
.ntvs_analysis.dat
node_modules/

# Visual Studio 6 build log
*.plg

# Visual Studio 6 workspace options file
*.opt

# Visual Studio 6 auto-generated workspace file (contains which files were open etc.)
*.vbw

# Visual Studio 6 auto-generated project file (contains which files were open etc.)
*.vbp

# Visual Studio 6 workspace and project file (working project files containing files to include in project)
*.dsw
*.dsp

# Visual Studio 6 technical files
*.ncb
*.aps

# Visual Studio LightSwitch build output
**/*.HTMLClient/GeneratedArtifacts
**/*.DesktopClient/GeneratedArtifacts
**/*.DesktopClient/ModelManifest.xml
**/*.Server/GeneratedArtifacts
**/*.Server/ModelManifest.xml
_Pvt_Extensions

# Paket dependency manager
.paket/paket.exe
paket-files/

# FAKE - F# Make
.fake/

# CodeRush personal settings
.cr/personal

# Python Tools for Visual Studio (PTVS)
__pycache__/
*.pyc

# Cake - Uncomment if you are using it
# tools/**
# !tools/packages.config

# Tabs Studio
*.tss

# Telerik's JustMock configuration file
*.jmconfig

# BizTalk build output
*.btp.cs
*.btm.cs
*.odx.cs
*.xsd.cs

# OpenCover UI analysis results
OpenCover/

# Azure Stream Analytics local run output
ASALocalRun/

# MSBuild Binary and Structured Log
*.binlog

# NVidia Nsight GPU debugger configuration file
*.nvuser

# MFractors (Xamarin productivity tool) working folder
.mfractor/

# Local History for Visual Studio
.localhistory/

# Visual Studio History (VSHistory) files
.vshistory/

# BeatPulse healthcheck temp database
healthchecksdb

# Backup folder for Package Reference Convert tool in Visual Studio 2017
MigrationBackup/

# Ionide (cross platform F# VS Code tools) working folder
.ionide/

# Fody - auto-generated XML schema
FodyWeavers.xsd

# VS Code files for those working on multiple tools
.vscode/*
!.vscode/settings.json
!.vscode/tasks.json
!.vscode/launch.json
!.vscode/extensions.json
*.code-workspace

# Local History for Visual Studio Code
.history/

# Windows Installer files from build outputs
*.cab
*.msi
*.msix
*.msm
*.msp

# JetBrains Rider
*.sln.iml

5. ReadMe.md 파일에 사용된 Mark Down 표기법 에대해서 헤더/목록(숫자)/순서없는목록(ex>*) / 들여쓰기 / 코드블럭 / 수평선 /링크 / 이미지/ 강조 에 대해 사용 방법을 정리해 오시오

-1- Markdown 이란? 
특수기호와 문자를 이용한 매우 간단한 구조의 문법을 사용하여 웹에서도 보다 빠르게 컨텐츠를 작성하고 보다 직관적으로 인식할 수 있는 텍스트 기반의 마크업 언어이다

-2- Markdown의 장점, 단점
장점 : 간결하고 별도의 도구 없이 작성이 가능하고 다양한 형태로 변환이 가능하다
단점 : 표준이 없고 표준이 없어서 도구에 따라서 변환방식이나 생성물이 다르다, 모든HTML 마크업을 대신하지 못한다

-3- Markdown 사용법
Headers: H1~H6순으로 크기가 작어지고문서의 제목, 부제목을 작성할때 사용된다
ex)
[This is a H1
This is a H2
This is a H3
This is a H4
This is a H5
This is a H6]

BlockQuote: 이메일에서 사용하는 > 블록인용문자를 이용하고 안에서는 다른 Markdown 요소를 포함 할 수 있다 
ex)
[ > This is a first blockquote]

list: 순서있는 목록을 작성할 수 있게 하고 이때는 숫자와 점을 사용하고 순서가 없는 목록일 경우에는 글머리 기호인 (*, +, -)를 지원한다
[순서 있는 목록 1, 첫번째, 순서 없는 목록 *빨강, -녹색등]

code: 4개의 공백 또는 하나의 탭으로 들여쓰기를 만나면 변환되기 시작하여 들여쓰지 않은 행을 만날때까지 변환이 계속된다
ex) 한줄 띄어스지 않을 시 인식이 제대로 되지 않는다
[This is a normal paragraph:
    This is a code block.
end code block.]

codeblock: 2가지 방식이 있다
ex)
[1. pre,code 이용방식 
<pre>
<code>
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }

}
</code>
</pre>
[2. 코드블럭코드("") 이용하는 방법
```
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```]

수평선: Markdown 문서를 미리보기로 출력하거나 페이지 나누기 용도로 많이 사용
ex)
[* * *, ***, - - -, ---------------------- 등이 있다]

링크: 외부링크를 넣을 수 있습니다
ex)
참조링크
[```
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```]
외부링크
[사용문법: [Title](link)
적용예: [Google](https://google.com, "google link")]
자동연결
[일반적인 URL 혹은 이메일주소인 경우 적절한 형식으로 링크를 형성한다.

* 외부링크: <http://example.com/>
* 이메일링크: <address@example.com>]

강조: 글씨체를 강조할 수 있습니다
ex)
[*single asterisks*
_single underscores_
**double asterisks**
__double underscores__
~~cancelline~~]

이미지: 이미지를 삽입할 수 있습니다, 사이즈 조절 기능이 없기에 <img width="" height=""></img>을 이용
ex)
[![Alt text](/path/to/img.jpg)
![Alt text](/path/to/img.jpg "Optional title")
<[img width="" height=""></img>]

줄바꿈: 3칸 이상 띄어쓰기를 사용시 줄이 바뀐다
ex)
[* 줄 바꿈을 하기 위해서는 문장 마지막에서 3칸이상을 띄어쓰기해야 한다. 

* 줄 바꿈을 하기 위해서는 문장 마지막에서 3칸이상을 띄어쓰기해야 한다.___\\ 띄어쓰기
]

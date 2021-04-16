C 프로그래밍을 위한 sublimetext 설치 및 세팅
-----
1. http://www.sublimetext.com/ 에서 SublimeText 다운로드 & 설치
2. Sublime Text 실행
3. Tools >> Build System >> New Build System
4. 다음 코드를 copy/paste

        {
        "cmd": ["gcc", "${file}", "-o", "${file_base_name}.exe"],
        "file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
        "working_dir": "${file_path}",
        "selector": "source.c, source.c++",
        "shell": true,
        "variants":
        [
        {
        "name": "Run",
        "cmd": ["gcc", "${file}", "-o", "${file_base_name}.exe", "&&", "start", "cmd", "/k", "${file_path}/${file_base_name}.exe"],
        "shell": true
        }
        ]
        }
  
5. File -> Save

        단, 파일이름 GCC.sublime-build
        저장폴더 .../Sublime Text 3/Packages/User

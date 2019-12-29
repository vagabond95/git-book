---
description: Shell Script 기본 설정
---

# 초기 설정

## 1. 생성

```bash
> touch script.sh
```

## 2. 실행 권한 부여

touch  로 생성된 파일의 초기 권한\(-rw-r--r--\) 은 실행권한이 없으므로 권한 부여

```bash
> chmod +x script.sh
```

## 3. \#!/bin/bash 추가

스크립트 파일 첫번째 line 에 **\#!/bin/bash** 추가

엥? \# 은 주석 아니냐? 혹은 추가해야하는 이유가 궁금하면 [http://forum.falinux.com/zbxe/index.php?document\_srl=541629&mid=lecture\_tip](http://forum.falinux.com/zbxe/index.php?document_srl=541629&mid=lecture_tip)

```bash
> vim script.sh

script.sh
#!/bin/bash
```

## 4. 실행

./\[FILE\_NAME\]

```bash
> ./script.sh
```


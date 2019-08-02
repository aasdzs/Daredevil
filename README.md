# Windows 설치
 * 기본적으로 윈도우에서 실행은 불가능하지만 시그윈(Cygwin), WSL(Windows Subsystem for Linux) 등을 이용하여 설치 및 실행 가능
 * 그러나 성능 면에서 해당 방법으로 컴파일 하는 것은 매우 비효율적임

# Linux(Ubuntu) 설치
 * 설명을 위해 윈도우 10 기능인 WSL 환경에서 설치 및 실행
![우분투 실행 화면](https://github.com/aasdzs/Daredevil/blob/master/captures/01_install_ubuntu.PNG?raw=true)
 * git을 통해 Daredevil 코드를 복사함 (https://github.com/SideChannelMarvels/Daredevil)
![소스복사](https://github.com/aasdzs/Daredevil/blob/master/captures/02_git_clone_daredevil.PNG?raw=true)
   - git 설치안되어있으면 `apt-get install git` 명령어로 설치
   - git 명령어 `git clone https://github.com/SideChannelMarvels/Daredevil.git`
 * compiler with OpenMP support (by default clang) 설치 
   - 명령어 `sudo apt-get install --no-install-recommends clang make libomp-dev`
![컴파일러 설치](https://github.com/aasdzs/Daredevil/blob/master/captures/05_install_daredevil-2.PNG?raw=true)
   - 명령어 오류 시 `sudo apt-get upgrade` 및 `sudo apt-get update` 명령어 입력
![컴파일러 설치 오류](https://github.com/aasdzs/Daredevil/blob/master/captures/05_install_daredevil-1.PNG?raw=true)
![설치 오류 시 대응](https://github.com/aasdzs/Daredevil/blob/master/captures/03_apt-get_upgrade.PNG?raw=true)
![설치 오류 시 대응](https://github.com/aasdzs/Daredevil/blob/master/captures/04_apt-get_update.PNG?raw=true)
   
 * Daredevil 컴파일 및 설치
   - `make` 명령어 입력 후 컴파일 확인 
![컴파일러 설치](https://github.com/aasdzs/Daredevil/blob/master/captures/06_make_daredevil.PNG?raw=true)
   - `sudo make install` 명령어 입력 후 daredevil 파일 생성 확인
![컴파일러 설치](https://github.com/aasdzs/Daredevil/blob/master/captures/07_make_install_daredevil.PNG?raw=true)

* 실제 분석 예제는 추후 작성 예정
---

# Daredevil
*His senses function with superhuman accuracy and sensitivity, giving him abilities far beyond the limits of a sighted person*

Daredevil is a tool to perform (higher-order) correlation power analysis attacks (CPA). 
It allows the user to compute CPA attacks on multiple cores given a specified amount 
of memory. The initial release of Daredevil implements the fastest approaches as 
outlined in the paper

Paul Bottinelli and Joppe W. Bos:  
Computational Aspects of Correlation Power Analysis.  
Journal of Cryptographic Engineering (to appear): http://link.springer.com/article/10.1007/s13389-016-0122-9

See also:  
Cryptology ePrint Archive, Report 2015/260, IACR, 2015.  
http://eprint.iacr.org/2015/260.pdf


## Dependencies

This software only requires a compiler with OpenMP support (by default clang).  
E.g. on a Debian/Ubuntu environment, one can do:

```bash
sudo apt-get install --no-install-recommends clang make libomp-dev
```

## Installation

To compile daredevil simply run:

```bash
make
```

To install it simply run:

```bash
sudo make install
```

You can uninstall it with:

```bash
sudo make uninstall
```

You can also specify the compiler with the CC variable as well as an
installation prefix else than the default /usr/local:

```bash
make CC=g++
sudo make install PREFIX=/usr
```

If you've troubles using clang with OpenMP on your distribution, try
using g++ as explained above.

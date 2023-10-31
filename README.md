# CVE-2021-42342 취약점으로 RCE공격

CVE-2021-42342은 GoAhead 웹서버의 취약점을 나타내는 보안 취약점 식별 번호이다. 
RCE는 원격 코드 실행을 의미하며, 이 취약점은 공격자가 악의적인 코드를 서버에 실핼시킬 수 있는 가능성을 나타낸다.

취약점의 구체적인 내용은 여러가지 방법으로 공격자가 서버에 악의적인 코드를 삽입할 수 있게 한다. 이를 통해 공격자는 서버에 실행 중인 프로그램을 조작하거나, 시스템에 대한 제어를 획득할 수 있다.


# 명령어 입력 순서

    sudo su
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/ccb1b0ff-4e8a-43fc-918d-1db7e8bf770d">

    apt update
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/32624090-b976-4d4c-a11c-eee04fe535cf">

    apt install docker.io
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/93d4889c-2de6-460d-8bd0-40c5a10af5a3">

    apt install docker-compose
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/bee78707-9197-46ff-9618-6813909ac589">

    git clone https://github.com/vulhub/vulhub.git
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/67eb3894-7d4e-405f-be6b-e74cc9863f69">

    cd vulhub
    ls
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/d2d5b5c7-6256-4f8b-99b0-bfd681060ce8">

    cd goahead
    ls
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/79342654-b122-4a25-b034-f050eb75f882">

    cd CVE-2021-42342
    ls
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/1865a3cc-8b05-4a23-96ca-e8acd7877996">

    sudo docker-compose build
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/d78159e8-da99-4308-8501-f5aecb6b4557">

    sudo docker-compose up -d
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/dfaa8f26-37ec-419a-a1e5-1cfda275d207">

    vi poc.c
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/a815f6b1-6352-47f2-9e99-4a985843296f">
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/47a947c0-382a-4519-8fa0-4a980998c58a">

    gcc -s -shared -fPIC ./poc.c -o payload.so
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/6865530d-f8b0-4a54-b46f-4fea67e0f835">

    python3 poc.py http://127.0.0.1:8080/cgi-bin/index payload.so
<img src="https://github.com/hannnnaa/WHS_vulhub/assets/113285516/db1c8279-b001-434f-8347-16f79824b98c">









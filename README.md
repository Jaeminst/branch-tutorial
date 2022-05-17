# branch-tutorial
브랜치 튜토리얼

kimck@KIMCK:~/branch-tutorial$ git status
현재 브랜치 ck
커밋하도록 정하지 않은 변경 사항:
  (무엇을 커밋할지 바꾸려면 "git add <파일>..."을 사용하십시오)
  (작업 디렉토리의 변경을 무시하려면 "git restore <file>..."을 사용하시오)
        수정함:        README.md

커밋할 변경 사항을 추가하지 않았습니다 ("git add" 및/또는 "git commit -a"를
사용하십시오)
kimck@KIMCK:~/branch-tutorial$ git add .
kimck@KIMCK:~/branch-tutorial$ git commit -m 'Docs: readme 수정'
[ck 5985b37] Docs: readme 수정
 1 file changed, 2 insertions(+), 1 deletion(-)
kimck@KIMCK:~/branch-tutorial$ 
kimck@KIMCK:~/branch-tutorial$ git push origin main
ERROR: Permission to Jaeminst/branch-tutorial.git denied to kimminlo.
fatal: 리모트 저장소에서 읽을 수 없습니다

올바른 접근 권한이 있는지, 그리고 저장소가 있는지
확인하십시오.
kimck@KIMCK:~/branch-tutorial$ git push origin ck
ERROR: Permission to Jaeminst/branch-tutorial.git denied to kimminlo.
fatal: 리모트 저장소에서 읽을 수 없습니다

올바른 접근 권한이 있는지, 그리고 저장소가 있는지
확인하십시오.
kimck@KIMCK:~/branch-tutorial$ git push origin ck
오브젝트 나열하는 중: 5, 완료.
오브젝트 개수 세는 중: 100% (5/5), 완료.
오브젝트 쓰는 중: 100% (3/3), 298 바이트 | 298.00 KiB/s, 완료.
Total 3 (delta 0), reused 0 (delta 0)
remote: 
remote: Create a pull request for 'ck' on GitHub by visiting:
remote:      https://github.com/Jaeminst/branch-tutorial/pull/new/ck
remote: 
To github.com:Jaeminst/branch-tutorial.git
 * [new branch]      ck -> ck
kimck@KIMCK:~/branch-tutorial$ git push origin main
Everything up-to-date
kimck@KIMCK:~/branch-tutorial$ git log
commit 5985b378d9c8151fbb7f39f826883b6c54055799 (HEAD -> ck, origin/ck)
Author: kimminlo <kimminlo77@gmail.com>
Date:   Tue May 17 15:45:09 2022 +0900

    Docs: readme 수정

commit bb6db223551ed3e78fa5eb80283d1fa4c6770efb (origin/main, origin/HEAD, main)
Author: Jaeminst <99124279+Jaeminst@users.noreply.github.com>
Date:   Tue May 17 15:32:40 2022 +0900

    Initial commit
kimck@KIMCK:~/branch-tutorial$ git status
현재 브랜치 ck
커밋할 사항 없음, 작업 폴더 깨끗함
kimck@KIMCK:~/branch-tutorial$ git branch
* ck
  main
kimck@KIMCK:~/branch-tutorial$ git add .
kimck@KIMCK:~/branch-tutorial$ git commit -m 'Feat: hello world 콘솔로그 추가'
[ck 281f389] Feat: hello world 콘솔로그 추가
 1 file changed, 3 insertions(+)
 create mode 100644 index.js
kimck@KIMCK:~/branch-tutorial$ git push origin main
Everything up-to-date
kimck@KIMCK:~/branch-tutorial$ 
kimck@KIMCK:~/branch-tutorial$ git push origin ck
오브젝트 나열하는 중: 4, 완료.
오브젝트 개수 세는 중: 100% (4/4), 완료.
Delta compression using up to 4 threads
오브젝트 압축하는 중: 100% (2/2), 완료.
오브젝트 쓰는 중: 100% (3/3), 345 바이트 | 345.00 KiB/s, 완료.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:Jaeminst/branch-tutorial.git
   5985b37..281f389  ck -> ck
kimck@KIMCK:~/branch-tutorial$ git branch main
fatal: 이름이 'main'인 브랜치가 이미 있습니다.
kimck@KIMCK:~/branch-tutorial$ git switch main
'main' 브랜치로 전환합니다
브랜치가 'origin/main'에 맞게 업데이트된 상태입니다.
kimck@KIMCK:~/branch-tutorial$ git branch
  ck
* main
kimck@KIMCK:~/branch-tutorial$ git pull
remote: Enumerating objects: 7, done.
remote: Counting objects: 100% (7/7), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0
오브젝트 묶음 푸는 중: 100% (6/6), 557 바이트 | 557.00 KiB/s, 완료.
github.com:Jaeminst/branch-tutorial URL에서
 * [새로운 브랜치]   develop         -> origin/develop
 * [새로운 브랜치]   feature/jaeyoon -> origin/feature/jaeyoon
이미 업데이트 상태입니다.
kimck@KIMCK:~/branch-tutorial$ git branch
  ck
* main
kimck@KIMCK:~/branch-tutorial$ git switch develop 
'develop' 브랜치가 리모트의 'develop' 브랜치를 ('origin'에서) 따라가도록 설정되었습니다.
새로 만든 'develop' 브랜치로 전환합니다
kimck@KIMCK:~/branch-tutorial$ git branch 
  ck
* develop
  main
kimck@KIMCK:~/branch-tutorial$ git merge origin ck
Merge made by the 'recursive' strategy.
 README.md | 3 ++-
 index.js  | 3 +++
 2 files changed, 5 insertions(+), 1 deletion(-)
 create mode 100644 index.js
kimck@KIMCK:~/branch-tutorial$ git branch
  ck
* develop
  main
kimck@KIMCK:~/branch-tutorial$ git log
commit fdbaa89eea2ff9d540a6f5aa01f2d6afe549adea (HEAD -> develop)
Merge: ef02bba 281f389
Author: kimminlo <kimminlo77@gmail.com>
Date:   Tue May 17 15:57:59 2022 +0900

    Merge branch 'ck' into develop

commit 281f389374b9bcfde0674e4b85ad59113816a04a (origin/ck, ck)
Author: kimminlo <kimminlo77@gmail.com>
Date:   Tue May 17 15:51:45 2022 +0900

    Feat: hello world 콘솔로그 추가

commit 5985b378d9c8151fbb7f39f826883b6c54055799
Author: kimminlo <kimminlo77@gmail.com>
Date:   Tue May 17 15:45:09 2022 +0900

    Docs: readme 수정

kimck@KIMCK:~/branch-tutorial$ l
README.md  index.js  jaemin.txt
kimck@KIMCK:~/branch-tutorial$ git log --oneline -n 5
fdbaa89 (HEAD -> develop) Merge branch 'ck' into develop
281f389 (origin/ck, ck) Feat: hello world 콘솔로그 추가
5985b37 Docs: readme 수정
ef02bba (origin/develop) Feat: jaemin
bb6db22 (origin/main, origin/HEAD, main) Initial commit
kimck@KIMCK:~/branch-tutorial$ git branch
  ck
* develop
  main
kimck@KIMCK:~/branch-tutorial$ git switch ck
'ck' 브랜치로 전환합니다
kimck@KIMCK:~/branch-tutorial$ git branch
* ck
  develop
  main
kimck@KIMCK:~/branch-tutorial$
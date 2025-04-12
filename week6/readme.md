변수 명 에러로 skipping이 일어나서
gitlab-runner/tasks/main.yml의 변수를
 > gitlab_url
 > gitlab_runner_token
로 변경하였습니다.

명령어도 아래와 같이 변경하여 사용해야 합니다.
> ansible-playbook -i development site.yml --extra-vars="gitlab_url=http://192.168.33.44 \
  gitlab_runner_token=<<복사한 값>>"


gitlab에서 CICD 항목이 아닌 Build 항목 내에 Pipeline editor가 존재 
> 참고해서 수행하기!
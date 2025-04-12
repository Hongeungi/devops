변수 명 에러로 skipping이 일어나서
gitlab-runner/tasks/main.yml의 변수를
 > gitlab_url
 > gitlab_runner_token
로 변경하였습니다.

명령어도 아래와 같이 변경하여 사용해야 합니다.
> ansible-playbook -i development site.yml --extra-vars="gitlab_url=http://192.168.33.44 \
  gitlab_runner_token=<<복사한 값>>"
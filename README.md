# docker
dockerfmのフォルダ構成（docker-composeおよびにDockerfileの管理ルール）に従うことで、ファイル管理の簡略化、およびに、DockerHubへのイメージpushプロセスを簡略化する。
フォルダ構成は、以下のようにdockerfm/{docker-compose group}/{docker image}の構成に従うこと。
これによりCircleCI経由で、フォルダ名に従ったイメージがDockerHubに自動プッシュされます。
``` yml
./:
  - .circleci:
    - config.yml（自動生成）
  - dockerfm:
    - README.md
    - pushreadme.py（自動生成）
    - fastapi:
      - README.md
      - docker-compose.yml
      - backend:
        - Dockerfile
        - README.md
      - celery:
        - Dockerfile
        - README.md
    - template:
      - alpine:
        - Dockerfile
        - README.md
        - index.html
    - python37:
      - Dockerfile
      - README.md
      - index.html
    - traefik:
      - README.md
      - docker-compose.yml
```

# Feature
- circleci/config.ymlの生成・更新
- CircleCIでイメージのビルド
- DockerHubへイメージをpush
- DockerHubへイメージのREADMEをpush


# Setup

## install dockerfm
```
pip install -i https://test.pypi.org/simple/ dockerfm
```

## Init project
```
dockerfm init
```

## Generate .circleci/config.yml
CircleCI用のイメージビルド用スクリプトを生成（更新）する。
```
dockerfm ci
```

## Setup CircleCI
CirccleCIで当該プロジェクトをフォローした上で、以下の環境変数を指定する。
- DOCKERHUB_USERNAME
- DOCKERHUB_PASS

## git push
gitリポジトリにpushすると、CircleCI上でCIが実行され、DockerHubにイメージとREADMEがpushされます。

```
git push
```

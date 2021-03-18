# test
    Для запуска контейнера копируем репозиторий :
    
    git clone https://github.com/EmPRio93/test.git

    cd /test

    docker build ./ --label [LABEL] -t [TAG]:[TAG]

    run -d -p 8080:80 [TAG]:[TAG]

    после чего приложение будет отвечать по адресу :
    http://localhost:8080

    Helm chart находится в каталоге test-app, для доставки docker image в k8s был создан docker репозиторий: https://hub.docker.com/r/emprio/emprio-nginx
    Для установки helm чарта в k8s :
    1. git clone https://github.com/EmPRio93/test.git 
    2. cd test/
    3. make changes in test/test-app/values.yaml
    4. helm install test-app test-app/ 

    Для удаления чарта :

    helm delete test-app

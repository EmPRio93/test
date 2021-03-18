# test
1. Реализовать контейнер Docker, который будет слушать порт, при обращении к которому по протоколу HTTP с указанием любого URL (с соблюдением всех спецификаций HTTP) в качестве payload ответа будет возвращаться текст "Hello Kefir!" с заголовком "Content-Type: text/plain"

    Для запуска контейнера копируем репозиторий :
    
    git clone https://github.com/EmPRio93/test.git

    cd /test

    docker build ./ --label [LABEL] -t [TAG]:[TAG]

    run -d -p 8080:80 [TAG]:[TAG]

    после чего приложение будет отвечать по адресу :
    http://localhost:8080

3. (опционально - выполнение будет существенным плюсом) Реализовать Helm-чарт (совместимый с Helm 3), позволяющий запустить уже реализованный на первом шаге контейнер в Kubernetes с доступом извне (наиболее предпочтительным с точки зрения соискателя способом)

    Helm chart находиться в каталоге test-app, для доставки docker image в k8s был создан docker репозиторий: https://hub.docker.com/r/emprio/emprio-nginx
    Для установки helm чарта в k8s :
    1. git clone https://github.com/EmPRio93/test.git 
    2. cd test/
    3. make changes in test/test-app/values.yaml
    4. helm install test-app test-app/ 

    Для удаления чарта :

    helm delete test-app

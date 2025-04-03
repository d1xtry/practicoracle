# practice oracle

#**DOCKER COMPOSE**

1.Скачиваем пакет wget, с помощью команды `sudo yum install wget`.Данная утилита wget в Linux предназначена для скачивания файлов из интернета. 

![image](https://github.com/user-attachments/assets/883cc6a3-9224-47e7-8a13-316eee0bb08e)
![image](https://github.com/user-attachments/assets/3ae11e20-485c-4aa3-bd3b-ebe5407ee6e3)

2.Скачиваем пакет curl, с помощью команды `sudo yum install curl`.Данная утилита curl в Linux предназначена для передачи данных с помощью различных сетевых протоколов.

![image](https://github.com/user-attachments/assets/4a9ef6c4-ce94-413b-a24c-369196de0e93)

3. Далее идет установка docker с помощью `sudo wget -P /etc/yum.repos.d/`

![image](https://github.com/user-attachments/assets/06428378-0a56-4033-b585-83f193fc244e)

4. sudo yum install docker-ce docker-ce-cli containerd.io установка докера.

![image](https://github.com/user-attachments/assets/8f7e9dce-a85e-4618-a2d0-d5284784a99c)
![image](https://github.com/user-attachments/assets/8299da92-55d6-4871-9468-5559fd8a79d2)

5.Команда `sudo systemctl enable docker --now` включает автозапуск Docker и сразу же запускает его

![image](https://github.com/user-attachments/assets/d8c20684-7265-4faf-ada8-e420a95e1829)

6.Эта команда использует утилиту `curl` для выполнения HTTP-запроса к API GitHub, чтобы получить информацию о последнем релизе репозитория Docker Compose, а затем извлекает номер версии этого релиза.

![image](https://github.com/user-attachments/assets/4086e19c-fc3c-4658-8906-2d5677f322bb)

7. `COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)` получаем последнюю версию докера.
   
![image](https://github.com/user-attachments/assets/8e439f1b-2c74-45bf-a189-7e77355d1623)

8. `sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose` загрузка и установка докера (последней версии).

![image](https://github.com/user-attachments/assets/dca434e8-2d58-4bcc-b18d-e2ddffc6d0a5)

9. `sudo chmod +x /usr/bin/docker-compose` с помощью данной команды докер становится исполняемым.

![image](https://github.com/user-attachments/assets/eeacff25-d5c9-425a-8c1a-c7763a02227c)

10. `git clone https://github.com/skl256/grafana_stack_for_docker.git` клонируется репозиторий git.

![image](https://github.com/user-attachments/assets/36369452-5ad6-428f-8f86-86470812e6fc)

11. `cd grafana_stack_for_docker`  смены текущей директории на указанную директорию.

![image](https://github.com/user-attachments/assets/f18d4798-a9af-4c9b-a24f-34f106f71b8b)

12. `sudo docker compose up -d` команда создает и запускает контейнеры в фоновом режиме.

![image](https://github.com/user-attachments/assets/bf58ab35-059b-44aa-85c0-53a31ef32d30)

13. `sudo docker compose stop` остановка контейнеров без удаления. `sudo docker compose down` остановка и удаления контейнеров.

![image](https://github.com/user-attachments/assets/abeb2401-21d1-4543-91e1-c585f19b2b4d)

14. `sudo docker compose ps` мониториг контейнеров.

![image](https://github.com/user-attachments/assets/6b716e63-69a1-41be-ab77-d0c3ed72db71)

15. `sudo vi docker-compose.yaml` открывает docker-compose.yaml в текстовом редакторе.

![image](https://github.com/user-attachments/assets/6689db1d-768e-4c7b-be2e-f909fc94331a)

16. `cd /mnt/common_volume/swarm/grafana/config/` изменение текущей рабочей директории в указанный путь в файловой системе. исправляем targets на exporter:9100.

![image](https://github.com/user-attachments/assets/f33a844f-483b-4131-b2d6-d4ba96bc4ac7)

#**GRAFANA**

1. `localhost:3000/login` вход в графану.

![image](https://github.com/user-attachments/assets/18b3e86a-f8bd-495d-88d3-aa8343e30196)

2. просмотр главного экрана графаны.

![image](https://github.com/user-attachments/assets/ee5d3237-14ae-421c-bae1-d2c643ac33bb)

3. создание дашборда с визуализацией.

![image](https://github.com/user-attachments/assets/c2bac13a-8644-4ce0-9943-cd774029e6a3) ![image](https://github.com/user-attachments/assets/8bd08223-e171-469a-8f64-bcc8475e9ac3)

4. `prometheus`

![image](https://github.com/user-attachments/assets/de553c40-98f4-46d1-ab0d-4b02d62f6218)

5. подключение `prometheus:9090`.

![image](https://github.com/user-attachments/assets/660a2743-4eb7-4f9b-b170-ad1f590b9a6c)

6. успешное сохранение.

![image](https://github.com/user-attachments/assets/2ea6ff2f-6b16-4f41-b4df-3394ded024e3)

7. импорт дашборда 1860 и prometheus.

![image](https://github.com/user-attachments/assets/4e56cc30-7e30-409a-8e78-c542feb6585e) ![image](https://github.com/user-attachments/assets/b85b0c87-2384-4585-90c3-b456ef508ee8)

8. рабочий мониторинг процессов.

![image](https://github.com/user-attachments/assets/6788bf4a-cd5a-460b-905a-bc8b7e1ba8d7)



Victoria Metrics


Запускаю докер с викторией и графаной

![image](https://github.com/user-attachments/assets/b629f28a-1eff-4618-b43a-0d4e41267550)

Создаю новое соединение прометиуса с таким урлом:

![image](https://github.com/user-attachments/assets/8bdf14a2-dc10-420d-a515-edee6e011ed6)
 
Выбираю code и вставляю параметр запроса

![image](https://github.com/user-attachments/assets/3e952bbc-d7bf-4328-975a-50500c9130cc)


 
Прописываю команды в терминал

![image](https://github.com/user-attachments/assets/b75e30b7-0d96-430e-907f-296f64e13fd8)
 
`echo -e "# TYPE OILCOINT_metric1 gauge\nOILCOINT_metric1 0" | curl --data-binary @- http://localhost:8428/api/v1/import/prometheus `

Она формирует и отправляет метрику OILCOINT_metric1 (с типом gauge и значением 0) на локальный сервер Prometheus через POST-запрос.

`curl -G 'http://localhost:8428/api/v1/query' --data-urlencode 'query=OILCOINT_metric1'`

Она запрашивает текущее значение метрики OILCOINT_metric1 с помощью GET-запроса к API Prometheus.

Создаю дэшборд в графане и вставляю OILCOINT_metric1

![image](https://github.com/user-attachments/assets/876f9faa-3b76-4a4e-8184-f339600ca201)

 
И в виктории метрикс
 
![image](https://github.com/user-attachments/assets/d364495b-25de-4084-a702-ae9de602797e)






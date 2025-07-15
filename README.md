# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Кудряшов Андрей`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
sudo -s
....
cd /home/adm1
....
wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.0+ubuntu24.04_all.deb
....
dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb
....
sudo apt update
....
sudo apt install -y zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-nginx-conf zabbix-sql-scripts zabbix-agent2
....
sudo apt install zabbix-agent2-plugin-postgresql
....
sudo nano /etc/zabbix/nginx.conf
раскоментировал listen 8080
....
systemctl restart nginx php8.3-fpm
....
sudo apt install -y postgresql postgresql-contrib
....
sudo -u postgres createuser --pwprompt zabbix
....
sudo -u postgres createdb -O zabbix zabbix
....
zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
....
sudo nano /etc/zabbix/zabbix_server.conf
указал пароль в DBPassword
....
sudo systemctl restart postgresql
....
systemctl restart zabbix-server zabbix-agent2
....
systemctl enable --now zabbix-server zabbix-agent2
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота 1](ссылка на скриншот 1)`
<img width="824" height="431" alt="1" src="https://github.com/user-attachments/assets/aa5010d4-525b-4570-8bc9-4a6f9f6bfe5e" />


---

### Задание 2

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
sudo -s
....
cd /home/adm1
....
wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.0+ubuntu24.04_all.deb
....
dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb
....
sudo apt update
....
sudo apt install zabbix-agent2
....
sudo apt install zabbix-agent2-plugin-postgresql
....
sudo nano /etc/zabbix/zabbix_agent2.conf
поменял порт прослушивания на 10052 и сервер на свой
....
systemctl restart zabbix-agent2
....
systemctl enable zabbix-agent2
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота 2](ссылка на скриншот 2)`

Configuration > Hosts
<img width="918" height="520" alt="2" src="https://github.com/user-attachments/assets/fe9f3c7c-efda-4b6e-b456-573dd8cd22c7" />

zabbix agent лог
<img width="1123" height="902" alt="3" src="https://github.com/user-attachments/assets/2e5eb57c-63a6-4cff-9b19-1b6c3c375ba4" />
<img width="735" height="184" alt="4" src="https://github.com/user-attachments/assets/8cfc5270-543d-4e4d-b7b5-0f79b5d432b7" />

Monitoring > Latest data
<img width="2217" height="1208" alt="5" src="https://github.com/user-attachments/assets/64ce0665-5d37-45bb-a14d-3e1fe7e9b09c" />
<img width="1973" height="1183" alt="6" src="https://github.com/user-attachments/assets/2ac3bf04-878f-4881-8d1a-f44bc1e58bb0" />



---

### Задание 3

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`

Windows Диск C
<img width="2290" height="1065" alt="7" src="https://github.com/user-attachments/assets/40c21077-0bb6-452c-953f-07afbb72a6af" />

Linux Корень
<img width="2269" height="968" alt="8" src="https://github.com/user-attachments/assets/d095af78-15bf-4f97-97ae-d4014117d15b" />


### Задание 4

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`

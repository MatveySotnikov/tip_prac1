# ПР-1 Сотников М. ЭФМО-01-25

**Цель** - развернуть рабочее окружение Go на Windows, создать минимальный HTTP-сервис на net/http, подключить и использовать внешнюю зависимость, собрать и проверить приложение.



## 1. Подготовка окружения и проверка версий

Был загружен и установлен Go версии 1.25.1

<img width="444" height="147" alt="версия Go" src="https://github.com/user-attachments/assets/13c5ee52-8f5f-4956-954d-efeca55f216c" />

Установен Git for Windows

<img width="416" height="170" alt="Git" src="https://github.com/user-attachments/assets/2321ee2a-11ce-4df2-bed7-f8ad61bcbc24" />

###

Инизиализирован модуль 
<img width="984" height="118" alt="инит модуля" src="https://github.com/user-attachments/assets/cd2a7e80-304a-4cea-8b05-fe81ca5cc5d8" />

<img width="715" height="290" alt="модуль в списке файлов" src="https://github.com/user-attachments/assets/10723a07-b357-43ef-8379-ec085fda44e9" />

Добавление пакета для генерации UUID 

<img width="922" height="124" alt="UUID" src="https://github.com/user-attachments/assets/fd4dddc7-acbc-445e-b11b-283b7a29701e" />


## 2. Запуск сервера
<img width="683" height="85" alt="Запуск сервера" src="https://github.com/user-attachments/assets/53d54a01-184a-422c-aa54-313fb89cc0b4" />


## 3. Ответ сервера

### Ответ сервера в бразуре

<img width="1919" height="426" alt="Ответ сервера 1" src="https://github.com/user-attachments/assets/5a3dc3b3-6ccf-418a-ad95-91fb5e98692c" />

### Ответ сервера в PowerShell
<img width="1919" height="850" alt="Ответ сервера PowerShell" src="https://github.com/user-attachments/assets/9e4c4b92-5c36-4186-a2f9-07fcdabb1d6a" />


## 4. Сборка и проверка exe
<img width="926" height="407" alt="сборка .exe" src="https://github.com/user-attachments/assets/008031e1-d1eb-4fb0-8865-40b35e1ab12d" />




## 5. Проверка код-style

Команды отработали без проблем.

<img width="749" height="83" alt="код-стайл" src="https://github.com/user-attachments/assets/735bb18b-5d0f-4d77-af70-c3adf8217088" />

Для проверки была намерена допущена ошибка:

<img width="943" height="145" alt="ошибка_кодстайл" src="https://github.com/user-attachments/assets/c9accb79-e850-4a2c-8425-6720eda1a78b" />



## 6. Добавление ручки для /health
Был подключен пакет "time", создана структура *health*, написан handler:

```
mux.HandleFunc("/health", func(w http.ResponseWriter, r *http.Request) {
		w.Header().Set("Content-Type", "application/json")
		_ = json.NewEncoder(w).Encode(health{
			Status: "ok",
			Time:   time.Now().Format(time.RFC3339),
		})
	})
```

При запросе, сервер выдаёт ожидаемый ответ: 

<img width="481" height="255" alt="/health ответ" src="https://github.com/user-attachments/assets/8a96bb2e-5906-420c-af16-6074cb5b6be3" />

<img width="699" height="87" alt="8081" src="https://github.com/user-attachments/assets/4e30cebc-3e60-476e-be72-1ea29ece0873" />

<img width="664" height="155" alt="8080 clear" src="https://github.com/user-attachments/assets/acb9ba77-1559-4e01-9fd0-3db31267eb97" />





## Дерево проекта
<img width="368" height="231" alt="дерево проекта" src="https://github.com/user-attachments/assets/a287e8ad-2ad9-4c9f-ba90-c7fcb76ce425" />




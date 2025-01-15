### О проекте

Этот проект автоматизации рабочего места специалиста по государственным закупкам (44-ФЗ) является приватным.
Разработка ориентирована на специалистов по государственным закупкам в соответствии с Федеральным законом 44-ФЗ.
Проект нацелен на **автоматизацию ежедневных задач специалистов и формирование сопутствующих документов в форматах `.docx` и `.xls`**, а также улучшить общий процесс управления закупками.
Проект иммеет следующие функциональные возможности:
- **Расчет начальной максимальной цены контракта**
- **Анализ практик премениния постановлений используемых для размещения заказа**
- **Формирование результатов в виде документов в форматах `.docx` и `.xls`**
- **Получение данных о проводимых закупках и отслеживание их в ОДНОМ месте**

Если вам интересно посмотреть на исходный код или получить более подробную информацию о проекте, **я с удовольствием продемонстрирую**, пожалуйста, свяжитесь со мной, если у вас возникнут вопросы или потребуется дополнительная информация.

# Автоматизация рабочего места специалиста по государственным закупкам (44-ФЗ)

Программа разработана с использованием **клиент-серверной архитектуры**, что позволяет эффективно взаимодействовать между различными модулями. 
**Эффективность специалиста** увеличена на **30%** благодаря внедрению автоматизиции и формирования документов.

### Основные компоненты:
- **Серверная часть**: работает на Spring Boot и расположена на **VDS сервере**.
- **Клиентская часть**: представляет собой **Desktop-приложение** с UI, построенным на JavaFX, с использованием **TableView** для отображения и ввода данных.

## Серверная часть:
1. **Авторизация** с использованием **Spring Security**:
    - Конфигурация безопасности осуществляется с помощью `@EnableWebSecurity`, а для хранения паролей используется **BCryptPasswordEncoder**.
    
2. **Database**:
    - Используется **H2** с настройкой таблиц через **JPA** аннотации.
    - Модель пользователя содержит поля для ID, имени, email и пароля.
    
3. **API** для получения и отправки данных:
    - Реализованы методы для получения данных от Users и отправки файлов на клиент.
    
4. **Класс для расчета НМЦК**:
    - Содержит всю логику расчета начальной максимальной цены контракта.
    
5. **Формирование документов**:
    - Использование **Apache POI** для создания документов:
        - `.docx` — для текстовых отчетов.
        - `.xls` — для расчётов с использованием формул Excel.

## Клиентская часть:
1. **Авторизация** через **RestTemplate**:
    - Логика для отправки данных пользователя на сервер и проверки учетных данных.
    
2. **Работа с файлами**:
    - Механизм получения файлов с сервера и сохранения их на локальном устройстве пользователя.
    
3. **Отправка данных для расчета**:
    - Передача введенных данных через **TableView** на сервер для выполнения расчетов.
    
4. **UI на JavaFX**:
    - Использование **TableView** для отображения данных, встроенная валидация полей с визуализацией ошибок (например, строки с некорректными данными подсвечиваются красным).
    
5. **Стилизация интерфейса**:
    - Кастомизация UI с помощью **CSS** и разметка в **FXML** для создания удобного и понятного интерфейса.

## Технологии:
- **JavaFX** — для пользовательского интерфейса.
- **Spring Boot** — серверная часть приложения.
- **H2 Database** — для хранения данных.
- **Hibernate** - для работы с базой данных.
- **Apache POI** — для работы с документами Word и Excel.
- **API** — для обмена данными между клиентом и сервером.
- **Spring Security** — для реализации авторизации и защиты приложения.
- **Word2Vec** - понимание контекста и создание итога.
- **Selenium** - получение данных с веб источников.
- **JUnit** - автоматизация тестирования.

Ниже представлены скриншоты программы и результат работы каждого из компонентов.

**Авторизация**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/LoginPage.jpg)

**Регистрация**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/Handling%20errors%20during%20registration.jpg)

**Ошибка авторизации**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/Error%20notification.jpg)

**Главное меню**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/CalcNMCKMainMenu.PNG)

**Таблица для заполения входных данных**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/TableView.jpg)

**Окно загрузки**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/Download%20window%20(waiting%20for%20response%20from%20server%20with%20files).jpg)

**Результат выполнения расчетов - файл с расширением xls**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/ResultCalcInExel.PNG)

**Раздел автозаполнения полей**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/AutoPurchase.PNG)

**Раздел меню "Анализатор постановлений"**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/Analyzer.PNG)

**Результат выполнения анализатора - файл с расширением doc**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/resultAnalyze.jpg)

**Раздел "Статусы"**:

![Screnshot](https://github.com/IR-gitt/QuickOrder/blob/master/Status.PNG)





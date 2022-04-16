# imc-test

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

### Testing
For testing was used JSON-server (https://www.npmjs.com/package/json-server)
1. install json server
```
npm install -g json-server
```
2. create a 'db.json' file in any directory, with data from test-task (https://github.com/imc-s/frontend-test#readme)
3. start json server from this directory
```
json-server --watch db.json
```

### Task requirements
**Тестовое задание для соискателя на должность frontend-разработчика уровня junior в компании ООО "ИМЦ".**

 **Задача**: разработать веб-приложение, обеспечивающее **динамическое** формирование веб-страницы.
Распарсить, приложенную к заданию, json-конфигурацию и нарисовать на ее основе веб-страницу, содержащую Таблицу и **редактируемую** Форму справа от нее. 
Форма содержит список компонентов, каждый из которых является **конфигурируемым** и ссылается на поле из Таблицы.
При выделении строки в Таблице Форма должна обновляться. 

  Дополнительное (необязательное) задание: написать сервис на node.js, который будет возвращать json-конфигурацию (например, через axios).

  Задание необходимо выполнить на одном из 2 фреймворков - Vue или React. Предпочтительней всего на Vue 3.0 (используемый в проекте, на который подбирается исполнитель). 
Для выполнения желательно не использовать сторонние библиотеки, на подобие Quazar. Сборщик можно использовать Vue Cli. 
При выполнении задания, в первую очередь, оценивается чистота кода. 
Плюсом при выполнении задания будет задействование технологий: TypeScript, Vuex, LocalStorage, Router.

Результаты выполнения задания следует оформить на GitHub.
Дополнительно опишите, как Вы тестировали результат своей работы в README.md - какие используете инструменты и как Вы осуществляете тестирование.

  Расшифровка json-конфигурации:
  ```
ct - тип компонента формы (1 - edit, 2 - select, 3 - checkbox)
cw - ширина компонента в пикселах
gn - порядковый номер компонента на форме
ns - отображаемое имя компонента
rv - ссылка на поле Таблицы
sl - описание справочника select-компонента
```

  Пример json-конфигурации, получаемой с сервера, написан и приложен к заданию.
```
{
  "table": [
    {
      "id": 1,
      "_foreigner": false,
      "_name": "Имя1",
      "_sex": 1
    },
    {
      "id": 2,
      "_foreigner": true,
      "_name": "Имя2",
      "_sex": 2
    },
    {
      "id": 3,
      "_foreigner": true,
      "_name": "Имя3",
      "_sex": 1
    },
    {
      "id": 4,
      "_foreigner": true,
      "_name": "Имя4",
      "_sex": 2
    },
    {
      "id": 5,
      "_foreigner": false,
      "_name": "Имя5",
      "_sex": 2
    },
    {
      "id": 6,
      "_foreigner": false,
      "_name": "Имя6",
      "_sex": 2
    },
    {
      "id": 7,
      "_foreigner": false,
      "_name": "Имя7",
      "_sex": 1
    }
  ],
  "formData": [
    {
      "id": 1,
      "ct": 1,
      "cw": 215,
      "gn": 1,
      "ns": "Имя",
      "rv": "_name"
    },
    {
      "id": 2,
      "ct": 3,
      "cw": 130,
      "gn": 2,
      "ns": "Иностранец",
      "rv": "_foreigner"
    },
    {
      "id": 3,
      "ct": 2,
      "cw": 100,
      "gn": 3,
      "ns": "Пол",
      "rv": "_sex",
      "sl": [
        {
          "id": 1,
          "name": "муж"
        },
        {
          "id": 2,
          "name": "жен"
        }
      ]
    }
  ]
}
```
Пример результата выполнения задания:

 ![гифа](https://user-images.githubusercontent.com/83217262/116071150-992f7580-a69e-11eb-96ae-23ba07d107f8.gif)


Результат выполнения задания следует оформить на github, где в README.md описать способ установки и проверки результата!


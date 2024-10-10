# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)


React домашнее задание 8

Задание
Практика знаний о DevTools, Eslint, написание приложения со списком.

Создание и настройка нового проекта React


Создайте новый проект на React:


Используйте npx create-react-app performance-app для создания нового проекта.


Перейдите в созданную директорию проекта, используя cd performance-app.


Настройка ESLint:


Инициализируйте ESLint в проекте с помощью команды npx eslint --init.


Следуйте инструкциям в консоли для выбора конфигурации ESLint, которая наилучшим образом подходит под ваш стиль работы.


Убедитесь, что в проекте установлены все необходимые зависимости для работы ESLint.


Создание компонентов приложения


Создание компонента для отображения списка элементов (ListItems.js):


Определите функциональный компонент, который будет использовать состояния для управления списком элементов и текущим значением текстового поля:


Используйте хук useState для создания переменных состояния items (массив, хранящий элементы списка) и inputValue (строковое значение текущего ввода пользователя).


Реализуйте функцию addItem, которая добавляет текущее значение inputValue в массив items и очищает inputValue.


Возвращаемый JSX должен включать текстовое поле для ввода, кнопку для добавления элемента в список и элемент <ul> для отображения элементов списка, каждый в своем <li>.


Интеграция компонента в App.js:


Откройте файл src/App.js.


Импортируйте компонент ListItems в этот файл.


Внутри функции App, возвращайте JSX, который содержит компонент ListItems.


Сохраните файл и убедитесь, что приложение запускается без ошибок и новый компонент отображается на странице.


Внедрение намеренной ошибки


Добавление намеренной ошибки в ListItems.js:


В компоненте ListItems, внедрите использование хука useEffect, который будет выполнять некоторую функцию при каждом обновлении списка items (console.log(‘компонент обновлен’)) .


Установите в качестве зависимости useEffect массив items. Это вызовет выполнение функции внутри useEffect при каждом добавлении элемента в список, что намеренно создает избыточные вызовы и потенциальную переработку:


     useEffect(() => {

       console.log("Компонент ListItems обновлен");

     }, [items]);


Этот код будет вызывать логирование в консоль при каждом изменении массива items, что можно наблюдать в консоли браузера при добавлении каждого нового элемента.


Тестирование и анализ производительности


Запустите приложение:


Используйте npm start для запуска приложения в режиме разработки.


Использование React DevTools для анализа производительности:


Откройте React DevTools в браузере.


Начните используя DevTools, взаимодействуйте с приложением (например, добавляя элементы в список).


Обратите внимание на частые перерисовки компонента и логи в консоли, что указывает на наличие излишних обновлений.


Исправление ошибки


Модифицируйте useEffect:


Измените зависимости useEffect таким образом, чтобы он вызывался только один раз при монтировании компонента (исключите список элементов из зависимостей).


Вторичное тестирование производительности


Проведите повторное использование React DevTools.


Убедитесь, что число перерисовок компонента сократилось и сообщения в консоль теперь выводятся только при начальном рендере.


Финализация и проверка кода


Запустите ESLint для анализа исходного кода проекта, чтобы убедиться в отсутствии стилистических и логических ошибок.


Исправьте все выявленные проблемы, следуя рекомендациям ESLint.



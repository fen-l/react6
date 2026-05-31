# Лабораторная работа №6 Многошаговая регистрация

## Meta
Author: Анастасия Лавриеня
Stack: React, TypeScript, Zod

## Описание лабораторной работы

Данная лабораторная работа посвящена разработке многошаговой формы регистрации с использованием React, TypeScript, useReducer и Zod. Цель работы заключается в создании управляемой формы, состоящей из трёх шагов, с централизованным управлением состоянием, валидацией данных и использованием типизированных структур.

В рамках работы реализуется собственный UI Kit, который включает переиспользуемые компоненты интерфейса. Управление состоянием формы осуществляется через useReducer, что позволяет централизованно обрабатывать изменения данных, навигацию между шагами и состояние отправки формы. Валидация данных выполняется с использованием библиотеки Zod, которая также используется как единый источник типов.

## Установка зависимостей

```bash
npm install
npm install zod classnames
```

## Контрольные вопросы

1. В паттерне **Flux** выделяются четыре роли: `Action`, `Dispatcher`, `Store` и `View`. `Action` описывает событие, `Dispatcher` принимает и распределяет действия, `Store` хранит состояние и бизнес-логику, `View` отображает данные и инициирует действия. Центральным узлом, который рассылает уведомления, является `Dispatcher`.

2. Принцип однонаправленного потока данных означает, что данные в приложении движутся только в одном направлении: от `View` к `Action`, затем к `Dispatcher`, далее к `Store` и обратно к `View`. `Store` во `Flux` не может быть изменён напрямую из `View`, все изменения проходят только через `Action` и `Dispatcher`.

3. Три кита **useReducer** это `state`, `action` и `reducer`. **State** представляет текущее состояние, **action** описывает изменение, **reducer** является функцией, которая возвращает новое состояние. Без любого из этих элементов `useReducer` не может работать.

4. **Reducer** в функциональном программировании это чистая функция, которая принимает текущее состояние и `action` и возвращает новое состояние без побочных эффектов. Чистота функции важна для предсказуемости поведения, упрощения тестирования и отсутствия скрытых изменений данных.

5. Функция **dispatch** используется для отправки action в reducer. Она инициирует процесс изменения состояния и является единственным способом обновления `state` при использовании `useReducer`.

6. Типизация **Action** в **TypeScript** ограничивает допустимые значения действий и обеспечивает проверку корректности структуры `action`. Это помогает избежать ошибок при передаче неверных типов или `payload` в `reducer`.

7. Если **reducer** получает неизвестный `action`, он обрабатывает его через ветку `default` и возвращает текущее состояние без изменений. Это защищает приложение от неожиданных изменений состояния.

8. Метод **safeParse** возвращает результат в виде объекта с полем success и не выбрасывает исключение при ошибке. Метод `parse` выбрасывает исключение при невалидных данных. `safeParse` используется в пользовательском интерфейсе, `parse` чаще используется там, где допустимы исключения.

9. Тип на основе **Zod** схемы создаётся с помощью `z.infer<typeof Schema>`. Это позволяет автоматически получать `TypeScript` тип из схемы без ручного описания интерфейсов.

10. Методы **pick** и **partial** используются для создания производных схем. `pick` позволяет выбрать только нужные поля, `partial` делает поля необязательными. Это полезно для многошаговых форм и API, где используются разные подмножества одной модели.

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

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

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

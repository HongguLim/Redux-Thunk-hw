23.01.27 공부


1. getTodos 로직
    1. todoList 컴포넌트에서 dispatch로 getTodos에 action.payload를 보내준다(암것도 없이)
    2. __getTodos가 실행되는데 todos를 선언하고 여기다 axios.get으로 todos를 전부 가져와서 담아준다
    3. thunkAPI.fulfillWithValue로 받아온 todos.data를 extraReducers의 __getTodos.fulfilled의 인자로 넘겨준다
    4. state.todos에 인자로 받아온 payload를 넣어준다
2. addTodos 로직
    1. input 컴포넌트에서 dispatch로 newTodo를 넘겨준다
    2. arg로 넘겨준 payload를 받고 그걸 axios.post로 todos에 넣어준다
    3. 그리고 arg를 thunkAPI.fulfillWithValue(arg)로 넘겨준다
3. __addTodoThunk.fulfilled에서 action.payload로 받아서 그걸 push 로 state.todos에 추가해준다(로컬, 서버 따로관리)
4. deleteTodos 로직
    1. dispatch로 todo.id를 넘겨준다
    2. 위랑 과정 똑같음
    3. __deleteTodoThunk.fulfilled에서 state.todos에서 filter로 하나하나 요소들을 item으로 받아온다음 action.payload로 받아온것과 비교한다. 그중 다른것만 state.todos에 저장 (id가 같은거 하나는 걸러짐)
5. switchTodos 로직
    1. dispatch로 {...todo(구조분해할당), isDone: !todo.isDone}가 담긴 객체인 switchTodo를 넘겨준다 
    2. axios.patch로 해당 id의 객체를 넘겨받은 객체로 바꿔준다
    3. arg를 extraReducers로 넘겨주고 state.todos를 map을 돌려서 id가 같은 객체의 isDone값을 !item.isDone으로 바꿔준다. 나머지 객체는 그냥 리턴해준다.



# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `yarn eject`

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

### `yarn build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)

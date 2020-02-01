### Project Structure

Project Structure are following.

```bash
|
|
|———— actions
|         |
|         |———— types.js
|         |        |
|         |        |—— example
|         |
|         |              const types = {
|         |                USER: {
|         |                   REQUEST_UPDATE: "USER.REQUEST_UPDATE",
|         |                   REQUEST_LOGIN:  "USER.REQUEST_LOGIN",
|         |                   REQUEST_SIGNUP: "USER.REQUEST_SIGNUP",
|         |                 },
|         |                 ARTICLE: {
|         |                   REQUEST_ADD:    "ARTICLE.REQUEST_ADD",
|         |                   REQUEST_UPDATE: "ARTICLE.REQUEST_UPDATE"
|         |                   REQUEST_DELETE: "ARTICLE.REQUEST_DELETE"
|         |                 }
|         |                  ......
|         |              };
|         |              export default types;
|         |
|         |———— userActions.js
|         |———— articleActions.js
|
|———— assets
|         |
|         |———— fonts
|         |———— image
|         |———— .....       
|         
|———— components
|         |
|         |————  App
|         |       |————  App.css
|         |       |————  App.test.js
|         |       |————  App.js
|         |
|         |————  Pages
|         |       |
|         |       |———— UserPage
|         |       |         |
|         |       |         |———— index.js
|         |       |         |         export { default } from "./User";
|         |       |         |
|         |       |         |———— User.js
|         |       |         |———— User.test.js
|         |       |         |———— styled.js (using styled-components)
|         |       |                  import styled from "styled-components";
|         |       |         
|         |       |———— ArticlePage
|         |       |         |
|         |       |         |———— index.js
|         |       |         |         export { default } from "./Article";
|         |       |         |
|         |       |         |———— Article.js
|         |       |         |———— Article.test.js
|         |       |         |———— styled.js (using styled-components)
|         |       |                   import styled from "styled-components";
|         |       |————  .....
|         |
|         |————  Styles
|         |         other styles (css, or scss)
|         |
|         |————  UI (Common UI -)
|                 |
|                 |———— CommonInput
|                 |         |
|                 |         |———— index.js
|                 |         |———— CommonInput.js
|                 |         |———— CommonInput.test.js
|                 |         |———— styled.js
|                 |
|                 |———— CommonButton
|                           |
|                           |———— index.js
|                           |———— CommonButton.js
|                           |———— CommonButton.test.js
|                           |———— styled.js
|
|———— config
|         |
|         |———— development.jsom
|         |———— production.json
|
|———— constants
|         |
|         |———— api_url (backend url)
|         |———— utils.js
|         |———— routes.js
|                    export const DASHBOARD_PAGE = "/dashboard";
|                    export const USER_PAGE = "/user";
|                    export const ARTICLE_PAGE = "/article";
|                    ......
|
|———— reducers
|         |       
|         |———— index.js
|         |          export default combineReducers({
|         |            userReducer,
|         |            articleReducer
|         |          });
|         |
|         |———— userReducer.js
|         |———— articleReducer.js
|
|———— sagas
|         |       
|         |———— index.js
|         |          export default function* rootSaga(getState) {
|         |            yield all([spawn(userSagas)]);
|         |            yield all([spawn(articleSagas)]);
|         |          });
|         |
|         |———— userSagas.js
|         |———— articleSagas.js
|
|———— stores
|         |
|         |———— index.js
|                 import reducers from "../reducers";
|                 import rootSaga from "../sagas";
|
|                 const sagaMiddleware = createSagaMiddleware();
|                 const enhancers = composeWithDevTools(applyMiddleware(sagaMiddleware));
|                 const store = createStore(reducers, enhancers);
|                 sagaMiddleware.run(rootSaga);
|                  
|                 export default store;
|
|———— index.js
|       import App from "./components/App/App";
|       import store from "./stores/index";
|
|       ReactDOM.render(
|         <Provider store={store}>
|           <App history={history} />
|         </Provider>,
|         document.getElementById("root")
|       );
|
|
|
|
|
|
```

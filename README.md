### Project Structure

Project Structure are following.

```bash
|
|
|———— actions
|         |
|         |———— types.js
|                 |
|                 |—— example
|                   const types = {
|                      USER: {
|                      UPDATE: "USER.UPDATE",
|                      REQUEST_LOGIN: "USER.REQUEST_LOGIN",
|                      REQUEST_SIGNUP: "USER.REQUEST_SIGNUP",
|                      },
|                      AUTH: {
|                        OPEN_SIDEBAR: "AUTH.OPEN_SIDEBAR",
|                        CLOSE_SIDEBAR: "AUTH.CLOSE_SIDEBAR",
|                        DOING_AUTH: "AUTH.DOING_AUTH"
|                      }
|                       ......
|                    };
|                    export default types;
|
|
|

```

# React Figma Login

[![npm](https://img.shields.io/npm/v/react-figma-login?logo=npm&cacheSeconds=1800)](https://www.npmjs.com/package/react-figma-login)
[![npm](https://img.shields.io/npm/dt/react-figma-login?cacheSeconds=1800)](https://www.npmjs.com/package/react-figma-login)
[![npm bundle size](https://img.shields.io/bundlephobia/minzip/react-figma-login?cacheSeconds=1800)](https://www.npmjs.com/package/react-figma-login)
[![GitHub issues](https://img.shields.io/github/issues/alexandrtovmach/react-figma-login?cacheSeconds=1800)](https://github.com/alexandrtovmach/react-figma-login/issues)

React component for a simple OAuth login with Figma.

[DEMO HERE](https://alexandrtovmach.github.io/react-figma-login/)

![image](https://user-images.githubusercontent.com/28801003/70469597-ff2f5300-1ad1-11ea-880f-2d604d9ed41b.png)

### 🚀 Get Started

Follow these steps to start using React Figma Login:

1. Installation

```sh
# with npm
npm i react-figma-login

# with yarn
yarn add react-figma-login
```

2. Import and configure component.

```jsx
import React from "react";
import FigmaLogin from "react-figma-login";

export default props => {
  const authHandler = (err, data) => {
    console.log(err, data);
  };

  return (
    <FigmaLogin
      authCallback={authHandler}
      clientId={CLIENT_ID}
      clientSecret={CLIENT_SECRET}
      redirectUri={REDIRECT_URI}
      scope={SCOPE}
    />
  );
};
```

3. Find more info about keys and OAuth apps in [Figma official docs](https://www.figma.com/developers/api#oauth2)

### 📖 API

| Property     | Type                                                       | Default   | Description                                                            |
| ------------ | ---------------------------------------------------------- | --------- | ---------------------------------------------------------------------- |
| authCallback | function                                                   | required  | Callback function which takes two arguments `(error, authData)`        |
| clientId     | string                                                     | required  | Client ID of your OAuth App                                            |
| clientSecret | string                                                     | required  | Client Secret of your OAuth App                                        |
| redirectUri  | string                                                     | required  | Authorization callback URL of your OAuth App                           |
| scope        | string                                                     | required  | Scope that will be requested. For now only `"file_read"` is available. |
| buttonTheme  | enum(`"light"`, `"light_short"`, `"dark"`, `"dark_short"`) | `"light"` | Button style theme that based on Figma styles                         |
| className    | string                                                     | `""`      | Custom class name                                                      |

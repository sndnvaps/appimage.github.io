---
layout: app

permalink: /Comic-Reader/
license: MIT

icons:
  - Comic-Reader/icons/128x128/comic-reader.png

screenshots:
  - Comic-Reader/screenshot.png

authors:
  - name: Pong420
    url: https://github.com/Pong420

links:
  - type: GitHub
    url: Pong420/Comic-Reader
  - type: Download
    url: https://github.com/Pong420/Comic-Reader/releases

desktop:
  Desktop Entry:
    Name: ComicReader
    Comment: 
    Exec: AppRun
    Terminal: false
    Type: Application
    Icon: comic-reader
    StartupWMClass: ComicReader
    X-AppImage-Version: 1.0.1
    Categories: Graphics
    X-AppImage-BuildId: 1Ht6OZSCQPBb9diMDXsMhJuSCvA
  AppImageHub:
    X-AppImage-Signature: no valid OpenPGP data found. the signature could not be verified.
      Please remember that the signature file (.sig or .asc) should be the first file
      given on the command line.
    X-AppImage-Type: 2
    X-AppImage-Architecture: x86_64
    X-AppImage-Payload-License: MIT

electron:
  description: ''
  lint-staged:
    "*.{js,jsx}":
    - cross-env NODE_ENV=development eslint --cache --format=pretty
    - prettier --ignore-path .eslintignore --single-quote --write
    - git add
    "{*.json,.{babelrc,eslintrc,prettierrc}}":
    - prettier --ignore-path .eslintignore --parser json --write
    - git add
    "*.{css,scss}":
    - prettier --ignore-path .eslintignore --single-quote --write
    - git add
    "*.{yml,md}":
    - prettier --ignore-path .eslintignore --single-quote --write
    - git add
  main: "./app/main.prod.js"
  repository:
    type: git
    url: git+https://github.com/Pong420/Comic-Reader
  author:
    name: Pong420
    email: samfunghp@gmail.com
    url: https://pong420.netlify.com/
  license: MIT
  bugs:
    url: https://github.com/Pong420/Comic-Reader/issues
  jest:
    testURL: http://localhost/
    moduleNameMapper:
      "\\.(jpg|jpeg|png|gif|eot|otf|webp|svg|ttf|woff|woff2|mp4|webm|wav|mp3|m4a|aac|oga)$": "<rootDir>/internals/mocks/fileMock.js"
      "\\.(css|less|sass|scss)$": identity-obj-proxy
    moduleFileExtensions:
    - js
    - ts
    - tsx
    - json
    transform:
      "^.+\\.[jt]sx?$": babel-jest
    testRegex: test/.*(spec|test).(ts|tsx|js)$
    setupFiles:
    - "./internals/scripts/CheckBuiltsExist.js"
  dependencies:
    axios: "^0.18.0"
    axios-extensions: "^3.0.5"
    cheerio: "^1.0.0-rc.2"
    chinese-conv: "^1.0.1"
    compression: "^1.7.3"
    cors: "^2.8.5"
    devtron: "^1.4.0"
    electron-debug: "^2.1.0"
    electron-log: "^3.0.1"
    electron-updater: "^4.0.6"
    express: "^4.16.4"
    history: "^4.7.2"
    react: 16.8.3
    react-async: "^4.1.2"
    react-content-loader: "^4.0.1"
    react-desktop: "^0.3.9"
    react-dom: 16.8.3
    react-redux: "^6.0.0"
    react-router: "^4.3.1"
    react-router-dom: "^4.3.1"
    react-use: "^5.5.4"
    react-virtualized: "^9.21.0"
    redux: "^4.0.1"
    redux-thunk: "^2.3.0"
    source-map-support: "^0.5.10"
  devEngines:
    node: ">=7.x"
    npm: ">=4.x"
    yarn: ">=0.21.3"
  browserslist: electron 1.6
---

# personal blog

Committer: @hikari-8

## This repo is working in progress...🏃

## Table of Contents

-   [Personal Blog](#personal-blog)
    -   [Getting Started](#getting-started)
    -   [Installation](#installation)
    -   [Connecting to Expo Project](#connecting-to-expo-project)
    -   [Installation](#installation)
    -   [Running the App](#running-the-app)
-   [Project Structure](#project-structure)
-   [Components Breakdown](#components-breakdown)
-   [Dependencies](#dependencies)
-   [Design Pattern](#design-pattern)
-   [Test](#test)
    -   [Test library, tool](#test-library-tool)
    -   [Test rule](#test-rule)

## Getting Started

To get started with this application, follow the instructions below:

### Installation

1. Clone this repository to your local machine

2. Navigate to the project directory:

    ```bash
    cd blog_client
    ```

3. Install the project dependencies using npm:

    ```bash
    npm install
    ```

### Running the App

Run the **_npm run dev_** command:

```bash
npm run dev
```

## Project Structure

### WIP

The project structure is organized as follows:

```text
└── src/
    ├── __generated__/            #  Generated types and mock data by Orval
    ├── app/                      #  Navigation for App Router
    ├── assets/                   #  Reusable or global assets like images, fonts, etc.
    └─- components/
    |    ├── page/                #  Each pages
    |    ├── *Features/           #  Application's features (begin with Uppercase)
    |    ├── ui/                  #  Globally reusable UI components
    |    └── functional/          #  Globally reusable functional which has no view, only behavior
    ├── contexts/                 #  Globally reusable state
    ├── services/                 #  Application services like API clients
    ├── themes/                   #  Globally reusable themes like color, layouts, etc.
    ├── utils/                    #  Utility/helper functions
    └── stories/                  #  Storybook ui parts and tests
```

＊ src/app の役割は基本的にルーティングのみとする

## Components Breakdown

アプリケーションに存在する Component を以下の 4 種類に分類してディレクトリを分ける

```bash
-   src/components/page
-   src/components/${Feature}
-   src/components/ui
-   src/components/functional
```

src/components/page : 1 つのページを表すコンポーネント

src/components/${Feature} : 何らかのドメインに関心を持つコンポーネント (ドメインごとにディレクトリを切る, ディレクトリ名は他コンポーネントとの差別化のため大文字で始める)

src/components/ui : ドメインに関心がないコンポーネント

src/components/functional : ドメインに関心がなく、view を持たず振る舞いのみを持つコンポーネント

## Dependencies

自分の右側に存在しているコンポーネントを import してよい。  
page 以外は自分の所属する分類軸の参照も可能。
依存関係のチェックは、[eslint-plugin-strict-dependencies](`https://www.npmjs.com/package/eslint-plugin-strict-dependencies`)で静的に行なっている。

```text
functional or ui → models → page
```

## Test

### Test library, tool

-   E2E test : Playwright
-   Unit test : Jest
-   UI test : StoryBook
-   Accessibility test : axe-core, lighthouse

### Test rule

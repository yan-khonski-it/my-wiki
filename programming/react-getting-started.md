# react-getting-started

## UI stack
- React.js: Core framework.
- TypeScript: For added type safety.
- ? Questionable  Material-UI or Ant Design: For pre-designed UI components.
- Axios (Ajax, but better alternative)
- Vite.js (create react app tool is deprecated). It is used to create and build the project.

## Example project
https://github.com/yan-khonski-it/react-rental-app

## React project structure

```java
project-root/
├── public/
│   ├── index.html
│   ├── favicon.ico
│   └── assets/
│       ├── images/
│       ├── fonts/
│       └── static-files/
├── src/
│   ├── components/
│   │   ├── common/       # Reusable components (e.g., Button, Input, Modal)
│   │   ├── layout/       # Layout components (e.g., Header, Footer, Sidebar)
│   │   ├── flats/        # Flat-specific components (e.g., FlatCard, FlatList)
│   │   └── index.js
│   ├── pages/
│   │   ├── HomePage.jsx
│   │   ├── FlatDetailsPage.jsx
│   │   └── SearchPage.jsx
│   ├── services/
│   │   ├── api/
│   │   │   ├── flatsService.js
│   │   │   └── index.js
│   ├── hooks/
│   │   └── useCustomHook.js
│   ├── context/
│   │   └── AppContext.js
│   ├── utils/
│   │   ├── helpers.js
│   │   ├── constants.js
│   │   └── validations.js
│   ├── styles/
│   │   ├── globals.css
│   │   ├── variables.css
│   │   └── components.css
│   ├── App.jsx
│   ├── index.js
│   └── setupTests.js
├── tests/
│   ├── components/
│   │   ├── FlatCard.test.jsx
│   │   └── SearchBar.test.jsx
│   ├── pages/
│   │   ├── HomePage.test.jsx
│   │   └── SearchPage.test.jsx
│   └── integration/
│       ├── SearchFeature.test.js
│       └── Navigation.test.js
├── .env
├── .eslintignore
├── .eslintrc.json
├── .gitignore
├── babel.config.js
├── jest.config.js
├── package.json
├── package-lock.json
└── README.md
```

Explanation of the Structure

#### Top-Level Files and Folders
- public/: Contains static assets and the index.html file.
- src/: Core React application code.
- tests/: Houses all test files for the project.
- Configuration Files: Includes .env (environment variables), .eslintrc.json (linter rules), and jest.config.js (testing setup).

#### src/ Folder
- components/: For reusable and page-specific React components.
- pages/: Contains the main views of your application (Home, Search, Details).
- services/: For API calls and service-related utilities (e.g., fetching flat details from the backend).
- hooks/: Contains custom React hooks.
- context/: Application-wide context providers using React Context API.
- utils/: Common utilities like helper functions and constants.
- styles/: Centralized CSS or SCSS files for global styles and design tokens.

#### tests/ Folder

- Unit Tests: Organized under components/ and pages/.
- Integration Tests: For testing end-to-end flows like searching for a flat or navigating between pages.
This structure is flexible and scalable, supporting your application as it grows while keeping the project maintainable. Let me know if you'd like further customization for specific use cases!


## Prerequesites:
node.js and npm
[how-to-install-nodejs](./how-to-install-nodejs.md)


## Create react app
https://vite.dev/guide/

Choose the name of your project `my-project-name`

```
npm create vite@latest my-project-name
```

Then you will be asked to choose stack (react, typescript, frameworks, etc).

Navigate to the created directory of your project.

Then install dependencies
```
npm install
```

And run dev server
```
npm run dev
```

If you save a file, the server will apply the changes quickly.

## Build application for deployment
```
npm run build
```

It will create static files in the `build` or `dist` directory.

To test the built files
```
npx serve -s build
```
will deploy a dev server where you can see how the static files are deployed.

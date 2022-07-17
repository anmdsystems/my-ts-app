cd ~/projects/some-dep
npm link  # Step 1.
cd ~/projects/my-app
npm link some-dep  # Step 2.

# 👇️ with NPM
npm install react@latest react-dom@latest

# 👇️ ONLY If you use TypeScript
npm install --save-dev @types/react@latest @types/react-dom@latest

# ----------------------------------------------

# 👇️ with YARN
yarn add react@latest react-dom@latest

# 👇️ ONLY If you use TypeScript
yarn add @types/react@latest @types/react-dom@latest --dev

cd apricus-react-lib
npm run rollup
cd ..\my-ts-app\
npm run build

This problem can also come up when you use npm link or an equivalent. In that case, your bundler might “see” two Reacts — one in application folder and one in your library folder. Assuming myapp and mylib are sibling folders, one possible fix is to run npm link ../myapp/node_modules/react from mylib. This should make the library use the application’s React copy.


"test-component-library": "git+https://github.com/anmdsystems/test-component-library.git",
    
"prestart": "npm-link-shared ../sampletest/node_modules . react"
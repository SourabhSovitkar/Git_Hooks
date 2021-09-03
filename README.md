# Git Hooks - Husky
It's good practice in JavaScript projects to utilise ESLint to define the project's coding conventions and prettier to define formatting of code. Quality includes both the chosen coding conventions in addition to the formatting of the code. how to actually enforce the conventions and formatting on a real life project with multiple developers to apply this Husky is a very popular npm package that allows custom scripts to be ran against your repository. Husky works with any project that uses a package.json file. It also works out of the box with SourceTree!

# What are pre-commit checks?
Pre-commit checks run after staging your changes and running git commit and before a commit is completed. 
If the checks fail then the commit is not made and an error shown, while if all checks pass the commit is made as normal.

# Why run pre-commit checks?
Pre-commit checks are commonly used to run linting scripts and tests, allowing each commit to be as clean as possible. 
As the lint-staged docs state, they prevent ‘💩 slipping into your code base!’.

# Install Husky
```bash
npm i husky --save-dev
```

# Active hooks
```bash
npx husky install
```

# Add hook
```bash
npx husky add .husky/commit-msg 'npx --no-install commitlint --edit $1'
# or
npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"'
```

# Create a hook
```bash
1. npx husky add .husky/pre-commit "# pre commit commands"
2. npx husky add .husky/post-commit "# post commit commands"
```

# Commitlint Package
```bash
1. Application specific 
npm install @commitlint/config-conventional @commitlint/cli --dev
2. Global linting 
npm install -g @commitlint/cli @commitlint/config-conventional
```

# Create .commitlintrc.json file to Configure linting 
```bash
echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js
```

# First simple usage test of commlitlint you can do the following 
```bash
1. echo "foo" | ./node_modules/.bin/commitlint
2. echo 'foo' | commitlint
3. npx commitlint --from HEAD~1 --to HEAD --verbose
```

## App Installation
```bash
# Install dependency from package.json
$ npm install
```

## Running the app
```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

### Conventional Commits References
- [Why Use Conventional Commits?](https://www.conventionalcommits.org/en/v1.0.0-beta.2/#why-use-conventional-commits)
- [The Angular Convention](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines)
- [Husky](https://typicode.github.io/husky/#/)
- [Commitlint](https://commitlint.js.org/#/)

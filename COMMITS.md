# Commits Quality

Commits quality is important for the project. 
It helps to understand what was done and why. 
It also helps to find the right commit when you need to revert something.

## Tools Installation

```shell
### install husky
npm install husky --save-dev
npm pkg set scripts.prepare="husky install"
npm run prepare

### install commitlint
npm install @commitlint/config-conventional @commitlint/cli --save-dev
sh -c "npm pkg set commitlint.extends[]='@commitlint/config-conventional'" ### workaround for zsh (problem with [])

### install commitlint hook
npx husky add .husky/commit-msg 'npx --no -- commitlint --edit ${1}'
git add .husky/commit-msg

### install lint-staged
npm install lint-staged --save-dev
npm pkg set scripts.pre-commit="lint-staged"
npm pkg set --json lint-staged1='{"*.{js,jsx,ts,tsx}":"npm run lint:fix"}'

### install lint-staged hook
npx husky add .husky/pre-commit "npx lint-staged"
git add .husky/pre-commit
```
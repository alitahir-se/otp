# otp

## Commit message format

We use [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) for commit messages.
To ensure that the commit messages are formatted correctly, we use [commitlint](https://commitlint.js.org/#/).
It will check the commit messages against the rules defined in [commitlint.config.js](./commitlint.config.js).
Checks are done automatically on every commit made locally and on every pull request.

**IMPORTANT**: To enable commit-lint locally you need to run `npm install` in the root of the project.

There is a [plugin](https://plugins.jetbrains.com/plugin/13389-conventional-commit) for IntelliJ IDEA that can help you with writing commit messages in the correct format.
Or you can use [commitizen](https://commitizen-tools.github.io/commitizen/) to help you write commit messages in the correct format from you terminal.

### Examples

Commit message with description and breaking change footer
```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```
Commit message with ! to draw attention to breaking change
```
feat!: send an email to the customer when a product is shipped
```

Commit message with scope and ! to draw attention to breaking change
```
feat(api)!: send an email to the customer when a product is shipped
```

Commit message with both ! and BREAKING CHANGE footer
```
chore!: drop support for Node 6

BREAKING CHANGE: use JavaScript features not available in Node 6.
```

Commit message with no body
```
docs: correct spelling of CHANGELOG
```

Commit message with scope
```
feat(lang): add Polish language
```
Commit message with multi-paragraph body and multiple footers
```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.
```

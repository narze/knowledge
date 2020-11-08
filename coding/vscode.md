# VSCode

## Create your own VSCode Extension

* Install Node.js with npm or yarn
* Install Yo with generator for VSCode extension `npm install -g yo generator-code` or `yarn global add yo generator-code`
* Create new project `yo code`

![VSCode Extension generator](../.gitbook/assets/image%20%284%29.png)

### Publishing

* Create Azure DevOps account and get a Personal Access Token
* `npm install -g vsce`
* `vsce create publisher [name]`
* `vsce package`
* `vsce publish`

### Testing Extension

End-to-end testing is not doable \(yet\), so that you cannot make clicks or typing commands. To test typing command arguments I use Sinon stub instead.

```text
// This mock clicking "Yes" label when your command runs and open Quick Pick dialog.

let quickPickStub = stub(vscode.window, "showQuickPick")
quickPickStub.resolves({ label: 'Yes' })

await vscode.commands.executeCommand('extension.your.command.name')
```

Try separating the business logic and interaction with VS Code, then the logic can be tested with normal Javascript testing.

## Links

* [https://code.visualstudio.com/api](https://code.visualstudio.com/api)
* [https://code.visualstudio.com/api/get-started/your-first-extension](https://code.visualstudio.com/api/get-started/your-first-extension)
* [https://code.visualstudio.com/api/working-with-extensions/testing-extension](https://code.visualstudio.com/api/working-with-extensions/testing-extension)
* [https://code.visualstudio.com/api/working-with-extensions/publishing-extension](https://code.visualstudio.com/api/working-with-extensions/publishing-extension)
* [https://scotch.io/tutorials/create-your-first-visual-studio-code-extension](https://scotch.io/tutorials/create-your-first-visual-studio-code-extension)
* [https://vscode.rocks/testing/](https://vscode.rocks/testing/)
* [https://github.com/narze/switcheroo](https://github.com/narze/switcheroo) - My first extension
* [From Editor to IDE](https://www.driftingruby.com/episodes/from-editor-to-ide) - Ruby VSCode extensions setup
* [Visual Studio Code | Custom User Snippets](https://medium.com/@jordan.eckowitz/visual-studio-code-custom-user-snippets-26f6ce0c0425)
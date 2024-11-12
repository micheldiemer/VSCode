# Espace de travail Visual Studio Code

- [Espace de travail Visual Studio Code](#espace-de-travail-visual-studio-code)
  - [Concept](#concept)
  - [Dossier .vscode](#dossier-vscode)
  - [Fichier `.vscode/settings.json`](#fichier-vscodesettingsjson)
  - [Fichier `.vscode/extensions.json`](#fichier-vscodeextensionsjson)
  - [Fichier `.vscode/projet.code-workspace`](#fichier-vscodeprojetcode-workspace)
  - [Fichier `.vscode/launch.json`](#fichier-vscodelaunchjson)
  - [Fichier `.vscode/tasks.json`](#fichier-vscodetasksjson)
  - [Source](#source)

## Concept

Un espace de travail permet :

- de configurer des paramètres qui ne s’appliquent qu’a certains dossiers
- créer des tâches de lancement spécific à ce workspace
- sauvegarder et restaurer l’état de l'interface graphique
- activer ou désactiver des extensions.

Un `dossier` (`folder`) est un `espace de travail` (`workspace`). Un `espace de travail` (fichier `.code-workspace`) peut regrouper plusieurs `dossier`.

## Dossier .vscode

Dans votre dossier de projet, créer un sous-dossier `.vscode`

## Fichier `.vscode/settings.json`

Créer un fichier `.vscode/settings.json`. Ce dossier sera publié sur `git`.

Par exemple, pour avoir un éditeur de texte sans aucun formatage automatique et avoir des fichiers Windows sans Unicode :

```json
{
  "editor.detectIndentation": false,
  "editor.formatOnPaste": false,
  "editor.formatOnSave": false,
  "editor.formatOnType": false,
  "editor.insertSpaces": false,
  "editor.tabSize": 4,
  "files.encoding": "windows1252",
  "files.eol": "\r\n",
  "files.trimFinalNewlines": false,
  "files.trimTrailingWhitespace": false,
}
```

## Fichier `.vscode/extensions.json`

Créer un fichier `.vscode/extensions.json`, par exemple pour JavaScript.

Cela vous permettra de lister les extensions recommandées/utiles pour les projet ainsi que les extensions à désactiver.

Cf. [extensions.json](.vscode/extensions.json) pour une configuration basique.

```json
{
  // See https://go.microsoft.com/fwlink/?LinkId=827846 to learn about workspace recommendations.
  // Extension identifier format: ${publisher}.${name}. Example: vscode.csharp

  // List of extensions which should be recommended for users of this workspace.
  "recommendations": [],
  // List of extensions recommended by VS Code that should not be recommended for users of this workspace.
  "unwantedRecommendations": [""]
}
```

## Fichier `.vscode/projet.code-workspace`

Fichier de l’espace de travail. Un espace de travail contient plus d’informations qu’un simple dossier. Un espace de travail peut regrouper plusierus dossiers.

Le nom et l’emplacement du ficher `.code-workspace` sont libres.

```json
{
  "folders": [
    {
      "path": ".."
    }
  ],
  
  "settings": {
  }
}
```

Il est préférable d’ouvrir un espace de travail plutôt qu’un dossier.

## Fichier `.vscode/launch.json`

Permet de définir les possibilités d’exécution et de débogage du code source.  
Cela s’intègre avec le débugger de Visual Studio Code. Une extension founit des commandes et on personnalise cetaines options.  
Valable pour des scripts ou des programmes informatiques.

```json
{
  "version": "2.0.0",
  "configurations": [
  ]
}
```

Cf. [VSCode Debugging](https://code.visualstudio.com/docs/editor/debugging)

## Fichier `.vscode/tasks.json`

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Open in notepad",
      "type": "process",
      "command": "notepad.exe",
      "presentation": {
        "reveal": "always"
      },
      "problemMatcher": [],
      "args": ["${file}"]
    }
  ]
}
```

Cf. [VSCode Tasks](https://code.visualstudio.com/docs/editor/tasks) pour en savoir plus.

## Source

<https://code.visualstudio.com/docs/editor/workspaces>

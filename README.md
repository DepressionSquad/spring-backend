# Git Precommit hooks

<br>

# Spotless Java formatter

### [Spotless Dokumentáció](https://github.com/diffplug/spotless/tree/main)

A Spotless egy Java formatter, hasonló, mint a Prettier a Javascripthez.

build.gradle tartalmazza a Spotless működéséhez szükséges beállításokat, ezért egy `./gradlew spotlessApply` lefuttatása sikeresenek kéne lennie. A parancs után minden `.java` fájlnak formattálódni kellene.

Amennnyiben fejlesztés közben egy fájl mentésekor is szeretnénk használni (format on save), akkor az alábbi extension-t és beállítást kell alkazmaznunk.

## VSCode

### [Spotless Gradle Extension](https://marketplace.visualstudio.com/items?itemName=richardwillis.vscode-spotless-gradle)

### Ctrl + Shift + P -> Open User Settings (JSON):

```json
"[java]": {
  "spotlessGradle.format.enable": true,
  "spotlessGradle.diagnostics.enable": true,
  "editor.defaultFormatter": "richardwillis.vscode-spotless-gradle",
  "editor.codeActionsOnSave": {
    "source.fixAll.spotlessGradle": true
  },
},
```

Ez a sor azt állítja be, hogy valós időben minden fájlmódosításkor automatikusan szkennelje a kódot, és ha kell akkor javaslatot tegyen.

```json
"spotlessGradle.diagnostics.enable": true,
```

Nem kötelező, szerintem számításigényes is lehet.

<br><br>

# PMD Source Code Analyzer

A PMD egy bővíthető, több nyelvet támogató statikus kódelemző eszköz. Olyan gyakori programozási hibákat tár fel, mint például a nem használt változók, az üres try-catch blokkok, a felesleges objektum-létrehozások stb.

Körülbelül mint egy TypeScript Compiler. Azért van, hogy letépje a fejed ha hülyeséget csinálsz.

### [PMD főoldal](https://pmd.github.io/)

### [PMD Dokumentáció](https://docs.pmd-code.org/latest/)

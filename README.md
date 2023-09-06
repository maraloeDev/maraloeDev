<br clear="both">

<h1 align="left">¡¡¡Hola!!!, Mi nombre es Eduardo Martín-Sonseca</h1>

###

<p align="left">Soy estudiante del Gregorio Fernández y actualmente estoy estudiando 2º de Desarrollo de Aplicaciones Multiplataforma.<br><br>En 2021 empece en Valladolid un ciclo formativo grado medio de Sistemas Microinformáticos y Redes,  done aprendi, el montaje de ordenadores, HTML, CSS y un poco de JS, administración de redes y subredes (Packet Tracer, Microsoft Visio...), el manejo de algunos sistemas operativos (Microsoft Windows y Ubuntu),  la creación de servidores, unidades de red, en las practicas de grado medio, estuve en el departamento de informatica de red hospitalaria Recoletas, trabajando en el montaje y transporte de ordenadores de sobremesa, supervisor de redes de un laboratorio con el tutor.<br><br>Me gusto tanto esta rama, que empece un nuevo grado superior de Desarrollo de Aplicaciones Multiplataforma, donde perfeccione los conocimientos dados en SMR de HTML, CSS y JS, adquirí nuevos conocimientos en las bases de datos relacionales (MySQL, MyPHPAdmin....) y en la nuve para la realización de consultas (Oracle Live SQL), en la programación con el lenguaje de Java, y un poco por mi cuenta C# y Kotlin, he trabajado con diferentes IDE's (Apache NetBeans, Eclipse Visual Studio Code, Visual Studio e IntelliJIDEA..., [...].</p>

###

<br clear="both">

<h2 align="left">Estas son las tecnologías que utilizo actualmente:</h2>

###

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="40" alt="html5 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="40" alt="css3 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="40" alt="javascript logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" height="40" alt="typescript logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" height="40" alt="java logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" height="40" alt="mysql logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" height="40" alt="git logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/androidstudio/androidstudio-original.svg" height="40" alt="androidstudio logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" height="40" alt="vscode logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/visualstudio/visualstudio-plain.svg" height="40" alt="visualstudio logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kotlin/kotlin-original.svg" height="40" alt="kotlin logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/swift/swift-original.svg" height="40" alt="swift logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-line.svg" height="40" alt="csharp logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jetbrains/jetbrains-original.svg" height="40" alt="jetbrains logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/slack/slack-original.svg" height="40" alt="slack logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/trello/trello-plain.svg" height="40" alt="trello logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/unity/unity-original.svg" height="40" alt="unity logo"  />
</div>

###

<br clear="both">

<h2 align="left">Contacto:</h2>

###

<div align="left">
  <img src="https://raw.githubusercontent.com/maurodesouza/profile-readme-generator/master/src/assets/icons/social/linkedin/default.svg" width="52" height="40" alt="linkedin logo"  />
  <a href="martinsonsecaeduardo@gmail.com" target="_blank">
    <img src="https://raw.githubusercontent.com/maurodesouza/profile-readme-generator/master/src/assets/icons/social/microsoft-outlook/default.svg" width="52" height="40" alt="microsoft-outlook logo"  />
  </a>
</div>

name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    runs-on: ubuntu-latest

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v2
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v2.6.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

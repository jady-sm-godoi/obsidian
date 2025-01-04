
A primeira versão do Angular foi denominada Angular Js e consistia num framework Javascript. Posteriormente, o Google reformulou o framework utilizando a linguagem de programação Typescript e foi denominado Angular 2.

Angular é um framework com recursos modernos da plataforma da Web para oferecer experiências semelhantes aos aplicativos. Instalação de alto desempenho, offline e sem etapas é uma estrutura de design de aplicativos e plataforma de desenvolvimento para criar aplicativos de página única eficientes e sofisticados.

**Resumo**

Os aplicativos angulares são um _single page web application_ traduzindo "aplicativo de uma página"; ou seja, quando o estado é alterado, a página não é recarregada. Em vez disso, o Document Object Model (DOM) é modificado para alterar seu conteúdo. Angular implementa isso usando um esquema virtual DOM e um detector de mudança de estado, de modo que, quando o estado do aplicativo é alterado, apenas o DOM é modificado para o mínimo necessário para refletir a mudança.

### Para criar um projeto

Tenha o Node instalado na sua máquina. A versão mais recente é melhor para que não falte nada na instalação do Angular.

```bash
node -v
nvm ls
nvm use 20
```

Teremos que instalar o Angular CLI que consiste num conjunto de comandos, bibliotecas e instruções do Angular. O comando abaixo instala o Angular CLI através do NPM do node.

```bash
npm install -g @angular/cli
```

Agora, já podemos criar nosso primeiro projeto com o comando abaixo.

```bash
ng new <project-name>
```

You will be presented with some configuration options for your project. Use the arrow and enter keys to navigate and select which options you desire.

If you don't have any preferences, just hit the enter key to take the default options and continue with the setup.

After you select the configuration options and the CLI runs through the setup, you should see the following message:

```bash
✔ Packages installed successfully.
 Successfully initialized git.
```

At this point, you're now ready to run your project locally!

![[Pasted image 20250104102651.png]]



Vamos agora criar alguns componentes e algumas páginas
Para organizar tudo, as páginas ficarão dentro da pasta **src/app/pages** e os componentes dentro da pasta **src/app/components**. Para isso vamos usar os seguintes comando no terminal:

```bash
ng g component pages/home
ng g component pages/listar
ng g component components/head
```


# POC-5-REACT


# 1. Estrutura de Projeto no Next.js 14+
A estrutura padrão de um projeto Next.js oferece uma organização prática para os arquivos e facilita a navegação entre as rotas. Abaixo estão algumas das pastas principais e seus papéis no desenvolvimento de um projeto organizado:
app/: Introduzida no Next.js 13, essa pasta substitui pages/ para definir o roteamento. Cada subpasta dentro de app/ representa uma rota. Assim, app/about/page.js cria uma rota /about, permitindo uma estruturação fácil e intuitiva.
components/: Destinada a componentes reutilizáveis. Componentes em components/ podem ser usados em várias páginas, contribuindo para a modularização do código.
styles/: Armazena arquivos CSS, tanto globais quanto módulos CSS para estilização isolada de componentes. Geralmente inclui o arquivo global globals.css.
public/: Utilizada para armazenar arquivos estáticos, como imagens e ícones, que podem ser acessados diretamente pelas rotas, por exemplo, /public/logo.png é acessível como /logo.png.
Roteamento Baseado em Pastas: A estrutura app/ permite um roteamento baseado em pastas. Cada pasta cria uma rota correspondente e, dentro dela, é possível definir subpáginas e rotas dinâmicas com parâmetros de rota (ex.: [id].js). Esse modelo otimiza o carregamento das páginas por meio de renderização no servidor (SSR) ou geração estática (SSG) conforme necessário.



# 2. Criação de Componentes Simples (Sem Estado)
Para criar um componente funcional simples, o código pode ser estruturado da seguinte forma:
// components/HelloWorld.js
export default function HelloWorld() {
  return <div>Hello, Next.js 14!</div>;
}

Esse componente pode ser importado e utilizado em qualquer página ou componente que necessite dele. Isso facilita o reaproveitamento de código e a modularização, reduzindo redundâncias no projeto:

import HelloWorld from '../components/HelloWorld';

export default function HomePage() {
  return (
    <div>
      <h1Welcome to my Next.js Project</h1
      <HelloWorld />
    </div>
  );
}






# 3.Estilo CSS (Global e Módulo)
CSS Global: No Next.js, o arquivo styles/globals.css é comumente usado para aplicar estilos que afetem todas as páginas do projeto.

/* styles/globals.css */
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

CSS Modules: Cada componente pode ter um estilo isolado usando CSS Modules, que cria um escopo local para as classes CSS, prevenindo conflitos entre estilos de diferentes componentes. Por exemplo, para o componente HelloWorld, criamos HelloWorld.module.css:

/* styles/HelloWorld.module.css */
.hello {
  color: blue;
  font-size: 1.5em;
}

E aplicamos o estilo dentro do componente assim:

import styles from '../styles/HelloWorld.module.css';

export default function HelloWorld() {
  return <div className={styles.hello}>Hello, Next.js 14 with CSS Modules!</div>;
}

Essa estrutura de CSS Modules permite estilizar componentes de forma encapsulada, evitando conflitos entre os estilos de diferentes partes da aplicação.


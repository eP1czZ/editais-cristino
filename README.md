## 📥 Download & Installation

You can download the latest Windows installer directly from GitHub:

* **[Download Editais Cristino for Windows (Latest .exe)](https://github.com/eP1czZ/editais-cristino/releases/latest/download/Editais-Cristino-Setup-1.3.1.exe)**
* **[View All Releases & Changelogs](https://github.com/eP1czZ/editais-cristino/releases)**

---

### Installation Steps
1. Download the `.exe` file from the link above.
2. Double-click `Editais-Cristino-Setup-1.0.1.exe` to run the installer.
3. Follow the on-screen prompts to complete installation.

# Editais Cristino

Aplicação de Windows para preencher, formatar e exportar os editais de falecimento da Cristino Agência Funerária. O edital é uma folha A4 que se ajusta sozinha ao texto escrito.

## O que faz

- **Preenche o edital** a partir de um formulário: fotografia, nome, idade, tratamento (Dª., Sr., D. ou nenhum), morada, família, funeral, nota adicional, velório, contactos do rodapé e local/data. A pré-visualização atualiza-se em tempo real.
- **Ajuste automático:** se o texto for muito, o conteúdo reduz-se (até 70%) para caber sempre numa página; o rodapé e a data ficam fixos ao fundo.
- **Destaque amarelo opcional** na nota adicional e no velório (cada um com o seu interruptor) e cruz que se pode ocultar.
- **Modelos por localidade** (Vila de Cucujães, Madaíl, São Martinho da Gândara, Santiago de Riba-Ul, São João da Madeira, São Roque, Bustelo). Ao abrir a app e em **Novo**, o nome, a idade, a família e a fotografia ficam em branco e a morada, o funeral e o rodapé vêm do modelo. A app abre com o modelo de Vila de Cucujães.
- **Dia/hora do funeral:** escolhe-se a data e a hora em dois seletores e a app escreve o texto com o **dia da semana certo** (por exemplo, `sábado, 3 de outubro, pelas 15:30 horas`). O texto continua editável à mão e os seletores acompanham-no. Ao abrir a app vem preenchido com o do último processo guardado (ou atualizado) ou, se ainda não houver nenhum, com o dia de hoje **às 15:30** (a hora predefinida). Se apagares a hora, o texto fica `pelas __:__ horas` e a app avisa antes de imprimir ou exportar. Em **Novo** mantém-se o que estiver no campo.
- **Data do rodapé:** também tem um seletor de data; muda só a data do texto (`Vila de Cucujães, 28 de setembro de 2026`) e o local mantém-se. Nos editais novos vem a data de hoje: com um modelo, e também com *Manter os valores actuais*, que só troca a data do rodapé.
- **Processos:** *Guardar* (atualiza o processo aberto, ou cria um novo), *Guardar como* (cria sempre um novo), *Abrir* e apagar. Guarda também a fotografia. Na lista de processos há uma **pesquisa por nome** (sem distinguir maiúsculas nem acentos; várias palavras, por qualquer ordem).
- **Rascunho automático:** enquanto escreves, o formulário é gravado ao fim de 1 segundo de pausa. Se a app fechar sem guardares o processo (falha, PC reiniciado), ao abrir pergunta se queres recuperar o que estavas a escrever. Guardar, abrir um processo ou começar um novo apaga o rascunho.
- **Cópia de segurança:** em *Cópia de segurança*, escolhe uma pasta (por exemplo, dentro do OneDrive). Cada processo que guardas é também copiado para lá, e os que já existem são copiados logo. Se a pasta não estiver acessível, o processo fica guardado no PC e a app avisa que a cópia falhou. *Restaurar…* traz de volta os processos de uma pasta de cópias (num PC novo, por exemplo) sem substituir os que estão mais recentes neste PC. Apagar um processo na app não apaga a cópia, por isso um restauro traz de volta o que foi apagado.
- **Exportar e imprimir:** PDF, PNG e impressão, com a página A4 exatamente como na pré-visualização. Antes de exportar ou imprimir, a app avisa se faltar o nome, a idade ou o dia/hora do funeral (incluindo a hora `__:__` por preencher).
- **Atalhos de teclado:** ver a tabela abaixo.
- **Atualizações automáticas** através do GitHub (ver abaixo).

## Onde ficam os ficheiros

| O quê | Onde |
|---|---|
| PDFs e PNGs exportados | `Documentos\Editais\<ano>\<Nome_do_falecido>.pdf` (a pasta do ano é criada sozinha) |
| Processos guardados (JSON) | `%APPDATA%\Editais Cristino\Processos` |
| Cópias de segurança | `<pasta escolhida>\Editais Cristino - Processos` |
| Rascunho e definições | `%APPDATA%\Editais Cristino\rascunho.json` e `config.json` |

## Atalhos de teclado

| Atalho | O que faz |
|---|---|
| `Ctrl+N` | Novo |
| `Ctrl+O` | Abrir (com a pesquisa pronta a escrever) |
| `Ctrl+S` | Guardar |
| `Ctrl+Shift+S` | Guardar como |
| `Ctrl+P` | Imprimir |
| `Esc` | Fecha a janela aberta |

Fazem o mesmo que os botões, incluindo as confirmações e o aviso antes de imprimir. Com uma janela aberta os atalhos param.

## Instalação

O instalador não tem assinatura digital, por isso o Windows mostra avisos. No SmartScreen, escolhe *Mais informações → Executar mesmo assim*. Com o **Smart App Control** ligado, o Windows bloqueia a instalação e as atualizações; é preciso desligá-lo para instalar.

## Desenvolvimento

Requer [Node.js](https://nodejs.org) 22.12 ou superior.

```bash
npm install
npm start            # abre a app (as atualizações automáticas só funcionam na app instalada)
npm run build:win    # gera o instalador em dist/
```

**Scripts de instalação (npm 12 ou superior):** o npm passou a bloquear os scripts de instalação dos pacotes. O único de que a app precisa é o do `electron`, que descarrega o programa do Electron; já está aprovado em `allowScripts` no `package.json`. O do `electron-winstaller` fica recusado de propósito: só serve para o instalador Squirrel.Windows, e a app usa o NSIS. Se o `npm install` avisar que outro pacote ficou bloqueado, vê a lista com `npm install-scripts ls` e aprova só o que reconheceres com `npm install-scripts approve <pacote>`.

**Erro `Electron failed to install correctly, please delete node_modules/electron and try installing again`:** aparece no `npm start` quando o `npm install` foi feito sem a aprovação do `electron` em `allowScripts` (o npm 12 salta o script sem dar erro). Apagar só `node_modules/electron` e instalar de novo, como a mensagem sugere, não resolve, porque o script volta a ser bloqueado. Confirma que o `package.json` tem `"allowScripts": { "electron": true }`, apaga a pasta `node_modules` e o ficheiro `package-lock.json`, e corre `npm install` outra vez. Se mesmo assim faltar, corre `node node_modules\electron\install.js`, que é o que esse script faz.

**Avisos e vulnerabilidades do `npm install`:** os avisos `deprecated` vêm de bibliotecas internas do Electron, do electron-builder e do electron-updater e não afetam a app. Nas vulnerabilidades do `npm audit`, o que pesa é o Electron (vai dentro da app instalada, apesar de estar listado nas ferramentas) e o electron-updater; o electron-builder só corre no teu PC, ao gerar o instalador. Por isso convém manter o Electron numa versão com suporte (cada versão tem suporte cerca de 6 meses): muda o número em `package.json`, corre `npm install` e testa a impressão, o PDF e o PNG. Não uses `npm audit fix --force`, porque pode instalar versões incompatíveis.

### Estrutura

```
main.js               processo principal: janela, exportação, impressão, processos, atualizações
preload.js            ponte segura entre a interface e o main.js
renderer/
  index.html          estrutura da interface e do edital
  styles.css          estilos (interface e página A4)
  modelos.js          os modelos por localidade
  app.js              lógica da interface
  assets/             cruz.png e logo.jpeg
build/icon.ico        ícone da aplicação e do instalador
```

### Alterar ou acrescentar um modelo

Edita `renderer/modelos.js`: cada entrada de `TEMPLATES` tem `nome`, `localNome`, `morada`, `participa`, `local`, `sepultamento`, `notaAntesVelorio`, `velorio` e `contactos`. O primeiro modelo da lista é o que a app usa ao abrir.

## Publicar uma atualização

A app instalada procura versões novas ao abrir e de 4 em 4 horas, descarrega-as em segundo plano e mostra na barra lateral o botão **Reiniciar e atualizar**. Se não o usares, a atualização instala-se ao fechar a app. Por baixo do título aparece uma linha com o estado da verificação (incluindo erros).

**Configuração (uma só vez)**

1. Repositório **público** `eP1czZ/editais-cristino` no GitHub (é o `owner`/`repo` de `package.json` > `build` > `publish`).
2. Um *Personal Access Token* (classic) com a permissão `repo`: GitHub → *Settings* → *Developer settings* → *Personal access tokens*.
3. `npm install`.

**Sempre que publicares uma versão**

1. Aumenta o `"version"` em `package.json` (por exemplo, `1.1.0` → `1.1.1`). Sem isto as apps instaladas não detetam nada de novo.
2. Define o token no terminal e publica:
   ```bash
   set GH_TOKEN=o_teu_token              # cmd
   $env:GH_TOKEN="o_teu_token"           # PowerShell
   npm run release
   ```
3. No GitHub, abre *Releases*, edita a versão criada (fica como rascunho) e carrega em **Publish release**. As apps só detetam versões publicadas.

**Se o instalador mostrar "Não é possível fechar o Editais Cristino":** o instalador espera que a app antiga feche e, se ela demorar, mostra esta janela. Fecha o `Editais Cristino.exe` no Gestor de Tarefas (separador *Detalhes*) e carrega em **Repetir**. Desde a 1.1.2 a app força o fim do processo 3 segundos depois de começar a fechar, mas a atualização *para* a 1.1.2 ainda usa o fecho da versão antiga, por isso pode aparecer uma vez.

**Se a app instalada não encontrar a atualização:** confirma que a versão está publicada (não é rascunho), que o `"version"` publicado é maior do que o instalado e que `owner`/`repo` estão certos. A instalação de origem tem de ser feita a partir de uma build que já inclua esta configuração.

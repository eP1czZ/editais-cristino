## 📥 Download & Installation

You can download the latest Windows installer directly from GitHub:

* **[Download Editais Cristino for Windows (Latest .exe)](https://github.com/eP1czZ/editais-cristino/releases/latest/download/Editais-Cristino-Setup-1.3.1.exe)**
* **[View All Releases & Changelogs](https://github.com/eP1czZ/editais-cristino/releases)**

---

### Installation Steps
1. Download the `.exe` file from the link above.
2. Double-click `Editais-Cristino-Setup-1.3.1.exe` to run the installer.
3. Follow the on-screen prompts to complete installation.

# Editais Cristino

Aplicação de Windows para preencher, formatar e exportar os editais de falecimento da Cristino Agência Funerária. O edital é uma folha A4 que se ajusta sozinha ao texto escrito.

## O que faz

- **Preenche o edital** a partir de um formulário: fotografia, nome, idade, tratamento (Dª., Sr., D. ou nenhum), morada, família, funeral, nota adicional, velório, contactos do rodapé e local/data. A pré-visualização atualiza-se em tempo real.
- **Fotografia:** escolhe-se com um clique na caixa ou **largando lá o ficheiro**. Ao entrar é reduzida para o lado maior de 1600px (a moldura só precisa de cerca de 700px; uma fotografia de telemóvel de 5MB passa a ocupar cerca de 1MB por processo), sem perder a transparência dos PNG. Os processos antigos, com a fotografia inteira, encolhem quando os guardares outra vez. Se o ficheiro não abrir (as fotografias HEIC do iPhone, por exemplo), a app pede para o converter para JPG. Largar um ficheiro noutro sítio da janela não faz nada.
- **Ajuste automático:** se o texto for muito, a app primeiro reduz o espaço entre os blocos (nome, família e funeral) e só depois, se ainda não couber, reduz o próprio texto (até 70%). A cruz, a fotografia e "Faleceu" têm sempre o mesmo tamanho — nunca encolhem. O rodapé e a data ficam sempre fixos ao fundo.
- **Destaque amarelo opcional** na nota adicional e no velório (cada um com o seu interruptor) e cruz que se pode ocultar.
- **Modelos por localidade** (Vila de Cucujães, Madaíl, São Martinho da Gândara, Santiago de Riba-Ul, São João da Madeira, São Roque, Bustelo). Ao abrir a app e em **Novo**, o nome, a idade, a família e a fotografia ficam em branco e a morada, o funeral e o rodapé vêm do modelo. A app abre com o modelo de Vila de Cucujães.
- **Dia/hora do funeral:** escolhe-se a data e a hora em dois seletores e a app escreve o texto com o **dia da semana certo** (por exemplo, `sábado, 3 de outubro, pelas 15:30 horas`). O texto continua editável à mão e os seletores acompanham-no. Ao abrir a app vem preenchido com o do último processo guardado (ou atualizado) ou, se ainda não houver nenhum, com o dia de hoje **às 15:30** (a hora predefinida). Se apagares a hora, o texto fica `pelas __:__ horas` e a app avisa antes de imprimir ou exportar. Em **Novo** mantém-se o que estiver no campo.
- **Data do rodapé:** também tem um seletor de data; muda só a data do texto (`Vila de Cucujães, 28 de setembro de 2026`) e o local mantém-se. Nos editais novos vem a data de hoje: com um modelo, e também com *Manter os valores actuais*, que só troca a data do rodapé.
- **Processos:** *Guardar* (atualiza o processo aberto, ou cria um novo), *Guardar como* (cria sempre um novo), *Abrir* e apagar. Guarda também a fotografia. Se guardar, abrir ou apagar falhar (disco cheio, pasta protegida, ficheiro em uso…), a app diz o motivo e nada se perde: o edital fica aberto e o rascunho mantém-se. Na lista de processos há uma **pesquisa por nome** (sem distinguir maiúsculas nem acentos; várias palavras, por qualquer ordem).
- **Rascunho automático:** enquanto escreves, o formulário é gravado ao fim de 1 segundo de pausa. Se a app fechar sem guardares o processo (falha, PC reiniciado), ao abrir pergunta se queres recuperar o que estavas a escrever. Guardar, abrir um processo ou começar um novo apaga o rascunho.
- **Cópia de segurança:** em *Cópia de segurança*, escolhe uma pasta (por exemplo, dentro do OneDrive). Cada processo que guardas é também copiado para lá, e os que já existem são copiados logo. Se a pasta não estiver acessível, o processo fica guardado no PC e a app avisa que a cópia falhou. *Restaurar…* traz de volta os processos de uma pasta de cópias (num PC novo, por exemplo) sem substituir os que estão mais recentes neste PC. Apagar um processo na app não apaga a cópia, por isso um restauro traz de volta o que foi apagado.
- **Missas (7.º dia, 30.º dia e aniversário):** o botão *Criar / editar missas…* abre uma janela própria com a participação de missa (A5 na horizontal), já preenchida com o nome, a fotografia e o local do edital. A data vem sugerida a partir da data do rodapé, que é o dia da morte: **+7 dias**, **+30 dias** ou **+1 ano** (a hora vem às 19:00). Tudo se pode alterar, e o local leva a preposição ("na Igreja de…", "no Santuário de…"). Regras: o nome e a fotografia vêm sempre do edital, por isso uma correção no edital chega à missa; cada tipo só fica na ficha se lhe mexeres ou o exportares (só ver um tipo não o guarda); *Concluir* leva as missas para o edital e só ficam gravadas quando guardares o processo; fechar a janela descarta as alterações (pergunta se as houver). Em *Abrir* cada processo mostra apenas quais missas tem ("Missas: 7.º dia, 30.º dia"). *Novo* limpa as missas e *Guardar como* mantém-nas. A janela exporta o PNG da missa.
- **Exportar e imprimir:** PDF, PNG e impressão, com a página A4 exatamente como na pré-visualização. Antes de exportar ou imprimir, a app avisa se faltar o nome, a idade ou o dia/hora do funeral (incluindo a hora `__:__` por preencher).
- **Atalhos de teclado:** ver a tabela abaixo.
- **Atualizações automáticas** através do GitHub (ver abaixo).

## Onde ficam os ficheiros

| O quê | Onde |
|---|---|
| PDFs e PNGs exportados | `Documentos\Editais\<ano>\<Nome_do_falecido>.pdf` (a pasta do ano é criada sozinha) |
| PNG das missas | `Documentos\Editais\<ano>\<Nome_do_falecido>_missa_7_dia.png` (ou `_30_dia`, `_2_aniversario`) |
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

### Estrutura

```
main.js               processo principal: janelas, exportação, impressão, processos, missas, atualizações
preload.js            ponte segura entre a interface e o main.js
renderer/
  index.html          estrutura da interface e do edital
  styles.css          estilos (interface e página A4 do edital)
  comum.js            auxiliares partilhados pelo editor e pela janela da missa (datas, confirmações)
  modelos.js          os modelos por localidade
  app.js              lógica do editor
  missa.html          janela da missa: formulário e pré-visualização
  missa.css           a página da missa (A5), com as medidas do ficheiro Word
  missa.js            desenho da missa, tipos e datas sugeridas
  missa-janela.js     lógica da janela da missa
  assets/             cruz.png e logo.jpeg
build/icon.ico        ícone da aplicação e do instalador
```

**Se o instalador mostrar "Não é possível fechar o Editais Cristino" (numa instalação feita à mão):** o instalador espera que a app antiga feche e, se ela demorar, mostra esta janela. Fecha o `Editais Cristino.exe` no Gestor de Tarefas (separador *Detalhes*) e carrega em **Repetir**. Desde a 1.1.2 a app força o fim do processo 3 segundos depois de começar a fechar, mas a atualização *para* a 1.1.2 ainda usa o fecho da versão antiga, por isso pode aparecer uma vez.

**Erro 404 na linha de estado (`o repositório de atualizações no GitHub não está acessível`):** a app procura as versões no endereço público `https://github.com/<owner>/<repo>/releases.atom`, e o GitHub responde 404 quando o repositório é privado (ou foi apagado ou mudou de nome). Não é problema de token nem de código. Confirma abrindo `https://github.com/<owner>/<repo>/releases` numa janela anónima do browser. Para corrigir, no repositório vai a *Settings → General → Danger Zone → Change visibility → Make public*; a app volta a funcionar na verificação seguinte, sem reinstalar. Se o código tiver de ficar privado, as versões podem ficar noutro repositório público só com os instaladores (muda `repo` em `package.json`), mas as apps já instaladas continuam a apontar para o repositório antigo e têm de ser reinstaladas uma vez. Não ponhas um token dentro da app: quem a tenha consegue extraí-lo.

**Se a app instalada não encontrar a atualização:** confirma que a versão está publicada (não é rascunho), que o `"version"` publicado é maior do que o instalado e que `owner`/`repo` estão certos. A instalação de origem tem de ser feita a partir de uma build que já inclua esta configuração.

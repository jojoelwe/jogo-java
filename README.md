# Forest Guard Simulator

Jogo point-and-click com elementos de combate e terror, desenvolvido em Java. O jogador assume o papel de um guarda florestal investigando o desaparecimento de um jovem chamado Scott Trevor — e descobre que várias outras pessoas já haviam desaparecido na mesma floresta.

> Projeto pessoal desenvolvido durante o Ensino Médio, em um prazo de 4 semanas, sem uso de ferramentas de IA.

## Sobre o jogo
- Sistema de combate por turnos contra criaturas (Siren Head, Cartoon Cat)
- Inventário com armas, itens de cura e buffs
- Eventos de QTE (Quick Time Event) sincronizados com trilha sonora e efeitos sonoros
- Sistema de save baseado em banco de dados SQLite, com múltiplos finais possíveis registrados por personagem
- Interface gráfica feita com Java Swing

## Como jogar

### Criação de personagem
Ao iniciar, você escolhe:
- Nome do personagem
- Arma: Shotgun, Revolver ou Rifle (cada uma com dano e munição diferentes)
- Remédio de cura: Riforcina, Kit de Curativos ou Kit Médico
- Potencializador (buff): Diazepam, Adrenalina ou Bateria de Tranquilizante

### Objetivo
Você é um guarda florestal investigando o desaparecimento de Scott Trevor e de outras pessoas na mesma floresta. Ao longo da história, você enfrenta criaturas e toma decisões que definem qual final você alcança.

### Ações em combate
- **ATIRAR** — usa munição da arma equipada para causar dano
- **CURAR** — usa um item de cura para recuperar vida (quantidade limitada)
- **BUFFAR** — usa um potencializador para aumentar dano/vida temporariamente
- **OLHAR EM VOLTA** — investiga o ambiente; pode revelar uma rota de fuga ou um perigo
- **FUGIR** — tenta escapar do combate (nem sempre funciona)
- **RECARREGAR** — recarrega a arma quando as balas acabam

### Progresso
O botão **"Progresso"**, na tela inicial, mostra uma tabela com o histórico de personagens salvos no banco de dados local, incluindo qual final cada um alcançou.

### Avisos
- O jogo tem elementos de terror, incluindo jumpscares com som alto.
- Há múltiplos finais possíveis, dependendo das suas escolhas durante o combate.

## Tecnologias
- **Java** (Swing para interface gráfica)
- **SQLite** (via JDBC) para persistência dos dados de save
- **Jaco MP3 Player** para reprodução de áudio

## ⚠️ Sobre o build
O jogo carrega imagens e sons diretamente do sistema de arquivos (`new File("src/res/...")`), com caminhos relativos fixos no código. Por isso ele ainda não tem uma versão `.jar` distribuível — a forma de rodar é a partir do código-fonte, pelo Eclipse.

## Como rodar

**Pré-requisitos**
- JDK 8 ou superior instalado
- Eclipse IDE (recomendado — o projeto foi desenvolvido nele)

**Passo a passo**
1. Baixe o arquivo com o código-fonte e os recursos (link na seção Download) e extraia.
2. No Eclipse: **File → New → Java Project**. Desmarque "Use default location", clique em **Browse** e aponte para a pasta extraída (a que contém a pasta `src`). Desmarque também "Create module-info.java file". Clique em **Finish**.
3. Adicione as bibliotecas externas ao Build Path do projeto:
   - Botão direito no projeto → **Build Path → Configure Build Path → Libraries → Add External JARs**
   - Adicione `sqlite-jdbc-3.40.0.0.jar` e `jaco-mp3-player-0.9.3.jar` (ambos incluídos no arquivo baixado, dentro da pasta `src`)
4. Confirme que a estrutura de pastas ficou assim — **os caminhos das imagens e sons estão fixos no código, então essa estrutura precisa ser respeitada**:
```
src/
 ├── jogo/          (arquivos .java)
 ├── res/           (imagens e áudios)
 └── bd_jogin.db    (banco de dados SQLite)
```
5. Rode a classe **Main.java** (botão direito sobre o arquivo → **Run As → Java Application**).

## Download
📦 (https://github.com/jojoelwe/jogo-java/releases/tag/1.0)

## Reportando bugs
Encontrou algum bug ou problema para rodar o jogo? Abra uma [issue](https://github.com/jojoelwe/jogo-java/issues) descrevendo o que aconteceu, em qual parte do jogo, e qual erro apareceu (se houver).

---

*Este é um projeto pessoal e não recebe manutenção ativa no momento.*

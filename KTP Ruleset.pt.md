<!-- ktp-translation
locale: pt
source: KTP Ruleset.md
source-sha256: 5f160e48fdbefb97096fbeefa2edc8357980efc462432cf7ff2f4613adc028e2

Records which revision of the English ruleset this translation was made from.
ktpleague.gg re-checks it on every render and warns readers when it no longer
matches. Whenever KTP Ruleset.md changes, update this translation and refresh
the hash - the workflow in .github/workflows/ opens a tracking issue for it.
-->
# Regras Oficiais da Liga KTP

**Regulamento Competitivo de Day of Defeat 1.3**

[![Version](https://img.shields.io/badge/Version-Season_10_2026-blue)](#)
[![Game](https://img.shields.io/badge/Game-Day%20of%20Defeat%201.3-green)](#)

> **Nota:** Estas regras regem a liga competitiva KTP para o mod Day of Defeat de Half-Life. Elas podem ser atualizadas conforme necessário (ver Regra 1.1). Espera-se que todos os times e jogadores conheçam e cumpram estas regras. O descumprimento pode resultar em penalidades, incluindo suspensões e derrotas por W.O.

---

## Índice

- [1. Regras Gerais, Jogos e Servidores](#1-regras-gerais-jogos-e-servidores)
- [2. Times, Regiões, Home/Away e Regras de Ringer](#2-times-regiões-homeaway-e-regras-de-ringer)
- [3. Trapaça, Penalidades e Contestações](#3-trapaça-penalidades-e-contestações)
- [4. Regras para Jogadores](#4-regras-para-jogadores)
- [5. Regras para Capitães](#5-regras-para-capitães)

---

## 1. Regras Gerais, Jogos e Servidores

> **Resumo da Seção:** Esta seção trata da administração da liga, das definições de termos, dos requisitos de servidor e dos procedimentos gerais de partida.

### 1.1 Alterações nas Regras

A KTP reserva-se o direito de modificar ou atualizar quaisquer regras da liga a qualquer momento, conforme necessário. Isso inclui alterações motivadas por atualizações do jogo, novos lançamentos ou outros fatores considerados necessários para a liga. Qualquer alteração de regra será publicada aqui E anunciada publicamente (via Discord, site etc.). Os times são responsáveis por consultar as regras regularmente (especialmente antes das partidas) para garantir que permaneçam em conformidade. Serão feitos os melhores esforços de boa-fé para garantir que ninguém perca uma alteração de regra.

### 1.2 Penalidades por Violação das Regras

Diante de uma infração às regras listadas aqui ou às regras listadas nas Regras da Comunidade KTP, a liga poderá aplicar penalidades. Dependendo da gravidade, qualquer combinação das seguintes medidas poderá ocorrer:

- Um jogador (ou vários jogadores) pode ser suspenso
- Um único jogo pode ser perdido por W.O.
- Uma partida inteira pode ser declarada derrota por W.O. para o time infrator

### 1.3 Definições: Jogos vs Partidas

| Termo | Definição |
|------|------------|
| **Jogo** | Um único confronto entre dois times em um mapa, composto por dois tempos (os times trocam de lado no intervalo) |
| **Partida** | Pode consistir em múltiplos jogos entre os mesmos times (por exemplo, uma melhor de três pode incluir até três jogos separados, possivelmente em mapas diferentes) |

> **Importante:** As suspensões são normalmente aplicadas em quantidade de **jogos** (ou em período de tempo), e não em partidas inteiras. Essa distinção é fundamental para entender a duração das penalidades.

### 1.4 Requisitos de Jogo Válido

Para que um jogo oficial seja válido, as seguintes condições devem ser atendidas:

- [ ] O mapa correto deve ser jogado (conforme agendado)
- [ ] A config oficial da liga KTP para aquele mapa deve ser usada
- [ ] O jogo deve ocorrer em um servidor aprovado pela KTP

### 1.5 Servidores Aprovados pela KTP

Todas as partidas devem ser jogadas em um servidor aprovado pelos administradores da KTP. Para ser considerado aprovado, um servidor deve atender aos seguintes requisitos:

| Requisito | Descrição |
|-------------|-------------|
| **Servidor dedicado** | Deve ser um servidor dedicado (não listen) |
| **Logging habilitado** | O logging do servidor deve estar configurado para gravar |
| **Requisito de HLTV** | Um proxy de espectador HLTV deve estar em execução com um delay mínimo de 120 segundos para impedir ghosting |
| **Configuração** | O servidor e o HLTV devem estar configurados com os ajustes oficiais da KTP |
| **Aprovação final** | É necessária a aprovação de um administrador antes que o servidor possa ser usado em partidas da KTP |

### 1.6 Acesso de Administradores aos Servidores

Os proprietários de servidores que desejarem sediar partidas da liga devem fornecer aos administradores da KTP acesso completo ao servidor:

- Quaisquer senhas de HLTV
- Senha de rcon (console remoto) do servidor
- Acesso ao painel de controle do servidor
- Acesso FTP aos arquivos/logs do servidor

### 1.7 Procedimento em Caso de Crash do Servidor

#### Crash nos primeiros 5 minutos de um tempo:
O tempo deve ser integralmente reiniciado desde o início (placar 0-0)

#### Crash após os primeiros 5 minutos de um tempo:
- O tempo será reiniciado com o placar e o tempo restante ajustados para os valores existentes no momento do crash
- Arredonde o tempo para cima, até o minuto cheio mais próximo
- O placar precisará ser restaurado manualmente por meio de comandos do servidor
- **Nenhuma substituição de jogador é permitida** durante esse reinício no meio do jogo

> **Notificação obrigatória:** Os times devem informar imediatamente um administrador da liga quando ocorrer um crash/reinício.

> **Nota:** Estes mesmos procedimentos de crash se aplicam durante os períodos de prorrogação. O limite de 5 minutos se aplica a cada tempo de prorrogação de forma independente.

### 1.8 Pausas Técnicas (Período de Teste)

Cada time recebe 5 minutos de tempo de pausa técnica por jogo (tempo regulamentar) para resolver problemas técnicos legítimos. O tempo de pausa regulamentar não utilizado NÃO é transferido para a prorrogação. Cada período de prorrogação oferece 5 minutos novos de tempo de pausa por time. Em séries de melhor de três, cada time recebe 5 minutos por jogo individual.

#### 1.8.a Mecânica das Pausas

O plugin de partida aciona automaticamente uma pausa 30 segundos após a desconexão de qualquer jogador, a menos que o time afetado a cancele digitando `.nodc` (ou `.stopdc`) no chat durante a contagem regressiva. Os times também podem iniciar pausas manuais usando os comandos `.tech`. Por meio do uso do plugin, todas as pausas exigem confirmação do time adversário para serem retiradas, seguida de uma contagem regressiva automática antes que o jogo seja retomado. Os times não têm tempo de pausa descontado enquanto aguardam o time adversário confirmar a retirada da pausa.

#### 1.8.b Problemas Técnicos Válidos

As pausas técnicas são autorizadas apenas para desconexões, crashes do jogo, falhas de hardware e problemas técnicos genuínos semelhantes. Pausas para discussões táticas, para esperar jogadores atrasados ou para atrasos deliberados são proibidas.

#### 1.8.c Exigência de Boa-Fé

Ambos os times devem agir de boa-fé ao usar o sistema de pausa. Os times devem confirmar a retirada da pausa prontamente quando seu problema estiver resolvido. O abuso do sistema de pausa — incluindo pausas táticas, atraso deliberado na confirmação da retirada da pausa ou alegações técnicas falsas — resultará em advertências, suspensão de jogador ou derrota da partida por W.O.

#### 1.8.d Status de Teste

Este sistema de pausa está em avaliação em caráter de **TESTE** e pode ser modificado ou até completamente removido com base no uso pela comunidade, no retorno recebido ou a critério dos administradores. Isso pode acontecer a qualquer momento nesta temporada.

> **Ver também:** Regra 1.7 para os procedimentos em caso de crash do servidor.

### 1.9 Exploits de Mapa e Locais Ilegais

O uso de áreas restritas ou não previstas de um mapa é estritamente proibido:

- Ficar em pé sobre pequenas saliências ou bordas invisíveis que não foram feitas para sustentar jogadores
- "Pixel-walking e pendurar-se" (por exemplo, empoleirar-se na escada em dod_harrington por meio de um exploit)
- Entrar em qualquer área que só seja alcançável usando um pixel walk

As violações podem resultar em suspensão do jogador e/ou perda do jogo ou da partida por W.O.

### 1.10 Jogos Empatados e Prorrogação

Em caso de jogo empatado, a prorrogação deve ser disputada imediatamente para determinar um vencedor.

**Formato da prorrogação:**
- Dois tempos adicionais de **10 minutos cada** (os times trocam de lado para o segundo tempo da prorrogação)
- Se o empate persistir, continue jogando tempos adicionais de prorrogação de 10 minutos até que um vencedor seja definido

> **Penalidade:** Deixar de completar os rounds de prorrogação exigidos resultará no registro de uma derrota para **ambos os times**.

> **Nota:** Em partidas de melhor de três, a prorrogação se aplica a cada mapa individualmente, caso aquele mapa termine empatado. Cada mapa deve produzir um vencedor.

### 1.11 Espectadores

Não são permitidos espectadores não autorizados no servidor de jogo durante partidas oficiais. Os únicos espectadores permitidos são:

- Administradores da KTP
- Transmissores oficiais (por exemplo, proxy HLTV com o delay exigido, ou narradores autorizados pela liga)

### 1.12 Admissão de Times e Elegibilidade para Participação

A KTP reserva-se a discricionariedade única e absoluta de aprovar ou negar a entrada de qualquer time. Os times podem ter a entrada negada ou ser removidos por:

| Motivo | Descrição |
|--------|-------------|
| **Conduta Disruptiva** | Comportamento destinado a provocar conflito, interferir na jogabilidade ou violar as políticas da liga |
| **Falta de Confiabilidade Operacional** | Padrões de W.O., partidas não comparecidas, rotatividade excessiva de roster ou comportamento que atrapalhe o agendamento da liga |

### 1.13 BYEs e Pontuação de W.O.

Um **BYE** é uma semana da temporada regular em que um time não tem partida porque sua divisão possui um
número ímpar de times. Um **W.O.** é uma partida concedida sem que seja jogada.

#### 1.13.a Pontuação de um BYE

Um BYE vale a **média dos placares que os demais times da divisão registraram naquela semana**, no
mapa daquela semana. Cada partida disputada na divisão naquela semana contribui com dois placares — um por time — e
o time em BYE é creditado com a média deles, tanto como pontos marcados quanto como pontos sofridos.

Apenas uma partida jogada contribui com placares para essa média. Uma partida perdida por W.O. ou anulada não tem
placar, portanto não fornece nada: ela recebe a média em vez de fornecê-la. Além disso, um time nunca faz parte
de sua própria média. Nos casos em que uma semana contiver um segundo BYE ou um W.O., a média será extraída das
partidas que aquela divisão realmente jogou.

A média é calculada **por semana**, porque cada semana é jogada em um mapa e os mapas não pontuam
da mesma forma. Ela nunca é calculada ao longo da temporada.

A média é uma fração e é mantida como tal. A classificação a calcula com até quatro casas decimais e a exibe aparada
(um número inteiro não mostra decimais). Ela nunca é arredondada para um número inteiro antes que os critérios de
desempate sejam aplicados, porque o arredondamento de oito placares para pontos inteiros pode reordenar uma divisão.

*Exemplo prático.* A Silver tem nove times, então um fica de fora a cada semana. Na semana 4, em dod_harrington,
os outros oito disputam quatro partidas que terminam em 429-243, 312-300, 500-180 e 260-411. Os oito placares
têm média de 329,375, então o time em BYE é creditado com 329,375 pontos a favor e 329,375 pontos contra.

Creditar a média tanto como pontos marcados quanto como pontos sofridos é deliberado: significa que um BYE
altera o saldo de pontos de um time em exatamente zero. Um BYE **não é um resultado** — não adiciona vitória nem derrota, e não torna as campanhas
comparáveis entre times que disputaram um número diferente de partidas.

#### 1.13.b Pontuação de um W.O.

Uma partida perdida por W.O. é pontuada da mesma forma — a média dos placares que os demais times da divisão
registraram naquela semana — e é creditada **somente ao time que não deu W.O.** O time que deu W.O.
não recebe pontos por aquela partida, nem marcados nem sofridos.

Um time que compareceu a uma partida que seu adversário não jogou está na mesma posição de um time em
BYE: ficou sem adversário, sem culpa própria. O time que causou isso não merece o
mesmo tratamento, e a derrota em sua campanha não é a totalidade da consequência.

Uma partida perdida por W.O. não contribui em nada para a média a partir da qual é pontuada. Ela não tem placar.

Quando ambos os times dão W.O., a partida é **anulada** em vez disso (§1.13.c) — nenhum dos times recebe nada.

#### 1.13.c Quando cada um se torna definitivo

- Um **BYE** é definitivo assim que todas as demais partidas que aquela divisão disputou naquela semana forem pontuadas. Ele
  não espera pelo restante da temporada. Até lá, é provisório e se move a cada resultado.
- Um **W.O.** é pontuado **somente ao fim da temporada regular**, uma vez definido que nenhuma
  partida de reposição será disputada. Até lá, o time que não deu W.O. não recebe crédito algum, de modo que um confronto
  que acabe sendo disputado nunca chegou a carregar um crédito.

Uma partida **anulada** por decisão administrativa não pontua nada para nenhum dos times, não contribui para nenhuma
média e não mantém um BYE ou a temporada em aberto.

### 1.14 Classificação e Critérios de Desempate

A classificação conta **apenas as partidas da temporada regular**. Partidas de playoff nunca afetam a tabela da liga. Uma
partida anulada por decisão administrativa não conta para nenhum dos times — nem vitória, nem derrota, e em nenhum total.

Os times são ordenados por:

1. **Campanha** — mais vitórias, depois menos derrotas.
2. **Confronto direto** — os resultados entre os times que estão igualados na campanha (ver abaixo).
3. **Saldo de pontos** — pontos de round marcados menos pontos de round sofridos ao longo de toda a
   temporada regular.

#### 1.14.a Como o confronto direto é aplicado

- O **grupo empatado** é composto por todos os times da divisão com campanha idêntica. O confronto direto é aplicado
  ao grupo inteiro de uma só vez — ele **não** é uma sequência de comparações par a par. Comparar pares não
  é transitivo: com três ou mais times, produz uma resposta diferente dependendo de qual par for
  comparado primeiro, e pode não produzir resposta alguma.
- O grupo é ordenado por uma **mini-tabela** das partidas que esses times disputaram entre si,
  contando as mesmas partidas que a classificação conta (temporada regular, disputadas ou perdidas por W.O.). Um W.O. é
  um resultado de confronto direto como qualquer outro.
- A mini-tabela é ordenada **somente pela campanha** — mais vitórias na mini-tabela, depois menos derrotas na mini-tabela.
  **O saldo de pontos da mini-tabela deliberadamente não é usado**, em nenhuma etapa. Ver §1.14.c.
- O confronto direto se aplica **somente quando todo time do grupo tiver jogado contra pelo menos um dos outros**.
  Se algum time empatado não tiver jogado contra nenhum deles, o confronto direto é ignorado para o grupo inteiro e o empate
  é resolvido pelo saldo de pontos. Um confronto direto não disputado nunca é tratado como uma campanha de 0-0.
- Times que permanecerem igualados após a mini-tabela caem para o saldo de pontos. A mini-tabela é
  aplicada uma única vez; a regra não recursa para um empate menor dentro do grupo.

#### 1.14.b Exemplo prático

Dois times terminam em 5-2. Um está em +500 no saldo, o outro em +100. O time de +100 venceu a partida
entre eles, então termina à frente — o confronto direto é aplicado antes do saldo. As colunas visíveis
não conseguem mostrar isso sozinhas, e é por isso que a página de classificação marca uma linha assim e nomeia
o resultado que a posicionou.

#### 1.14.b.i Times ainda igualados após todas as três etapas

> Nota de localização: Esta regra está numerada sob o §1.14.b (o exemplo prático), mas se aplica ao §1.14.a e aos critérios
> de desempate em geral, não apenas ao exemplo acima. O identificador e o nível do cabeçalho são deixados inalterados de
> propósito: o site cria âncoras a partir do número da regra, e ambas as decisões espelham essa estrutura linha por linha.

Se dois ou mais times permanecerem exatamente igualados após campanha, confronto direto e saldo de pontos, e a
ordem definir um seed de playoff ou qualquer outra consequência, **um administrador da KTP decide a ordem e a
decisão é registrada publicamente.** Nenhum critério automático adicional é aplicado.

⛔ **A ordem exibida na página de classificação não é autoritativa nesse caso.** O site desempata o
restante com base em um identificador interno puramente para que a tabela não se reorganize entre carregamentos de página.
Isso não tem significado esportivo. Até que um administrador tenha decidido, trate essas linhas como não ordenadas.

#### 1.14.c Por que a mini-tabela ignora o saldo de pontos

Em um empate triplo circular, todo time fica em 1-1 dentro do grupo, então a mini-tabela não separa ninguém
e o empate cai para o saldo de pontos **geral**. Este é precedente consolidado da liga: os empates triplos da
Silver nas Temporadas 4, 5 e 8 foram todos resolvidos dessa forma. Acrescentar uma etapa de saldo na mini-tabela
reverteria aqueles resultados. A etapa está ausente de propósito — não é um descuido a ser
arrumado depois.

### 1.15 Idioma e Traduções

O texto em inglês deste regulamento é a versão oficial e prevalecente. As traduções para outros idiomas são oferecidas apenas como cortesia.

Quando uma tradução e o texto em inglês divergirem — na redação, no significado, ou por erro ou omissão na tradução —, o texto em inglês prevalece. Todas as decisões, penalidades e resoluções de contestação são tomadas com base nas regras em inglês, e nenhuma decisão pode ser apelada sob o argumento de que uma tradução dizia algo diferente.

> **Importante:** Se uma regra traduzida for pouco clara ou parecer conflitar com o inglês, leia a versão em inglês ou pergunte a um administrador da KTP antes de agir com base nela. A leitura equivocada de uma tradução não é defesa para uma violação de regra.

---

## 2. Times, Regiões, Home/Away e Regras de Ringer

> **Resumo da Seção:** Esta seção trata da composição dos times, do agendamento, da seleção de servidor por região, da gestão de roster e das regras para o uso de jogadores substitutos (ringers).

### 2.1 Composição do Time (Internacional vs NA)

| Tipo de Time | Definição |
|-----------|------------|
| **Internacional** | Maioria dos jogadores (4+) sediados fora da América do Norte (UE, SA etc.) |
| **Norte-Americano** | Maioria de jogadores norte-americanos |

### 2.2 Horários Padrão de Agendamento das Partidas

#### 2.2.a Horário Padrão
Domingo às 21h00, horário do Leste (EST).

#### 2.2.b Horário Padrão Internacional
Quando um ou ambos os times tiverem maioria de jogadores da UE a leste de UTC -2, o horário padrão da partida é domingo às 15h00 EST.

> Os horários podem ser ajustados em razão do horário de verão.

### 2.3 Vantagem do Time Home

#### 2.3.a Partidas Padrão
O time listado na tabela de jogos como time **HOME** tem a escolha do uso do servidor para ambos os tempos, bem como a escolha de qual lado (Allies ou Axis) ocupar primeiro.

#### 2.3.b Partidas de Melhor de Três (BO3)
Cada mapa é tratado de forma independente. O time que escolheu um mapa é considerado o time "home" naquele mapa.

### 2.4 Seleção de Servidor por Região

#### 2.4.a NA vs NA — Seleção de Servidor pelo Time Home

Em partidas entre times norte-americanos (sem envolvimento de time Internacional), o time **HOME** seleciona a localização do servidor de jogo entre as seguintes localizações aprovadas pela KTP:

| Localização | Status |
|----------|--------|
| **Chicago** | Disponível |
| **Dallas** | Disponível |
| **Denver** | Disponível |

O time HOME pode propor uma localização alternativa de servidor aprovado pela KTP não listada acima, mas isso fica sujeito à aprovação do capitão do time adversário. Se o capitão adversário não aprovar a localização alternativa, o time HOME deve escolher entre as três localizações padrão listadas acima.

> **Importante:** As partidas nunca podem ser jogadas em servidores não aprovados pela KTP, independentemente de acordo mútuo.

> **Política em Teste:** Esta política de seleção de servidor pelo time home está sendo introduzida em caráter de teste, para avaliar seu impacto no equilíbrio competitivo e na qualidade das partidas. A liga acompanhará o uso e poderá ajustar as localizações disponíveis, retornar à atribuição neutra de servidor ou modificar o processo de seleção com base no retorno da comunidade e nos resultados competitivos.

#### 2.4.b Internacional vs Internacional

Em partidas entre times Internacionais (maioria de jogadores da UE/SA conforme a Regra 2.1), o time **HOME** seleciona a localização do servidor de jogo entre as seguintes localizações aprovadas pela KTP:

| Localização | Status |
|----------|--------|
| **Atlanta** | Disponível |
| **New York** | Disponível |

O time HOME pode propor uma localização alternativa de servidor aprovado pela KTP não listada acima. A localização alternativa exige a aprovação do capitão do time adversário. Se o capitão adversário não aprovar, o time HOME deve escolher entre as localizações padrão listadas acima.

> **Importante:** As partidas nunca podem ser jogadas em servidores não aprovados pela KTP, independentemente de acordo mútuo.

#### 2.4.c NA vs EU — Seleção de Servidor

Em partidas entre um time norte-americano e um time europeu (maioria de jogadores da UE a leste de UTC -2 conforme a Regra 2.1), o time **HOME** seleciona a localização do servidor de jogo entre as seguintes localizações aprovadas pela KTP, com prioridade para New York:

| Localização | Status |
|----------|--------|
| **New York** | Principal |
| **Atlanta** | Somente reserva (se New York estiver indisponível) |

New York deve ser usada sempre que estiver disponível. Atlanta só pode ser escolhida se nenhum servidor de New York estiver disponível no momento do agendamento ou do início da partida. Essas localizações da Costa Leste oferecem uma latência de compromisso razoável para conexões transatlânticas.

O time HOME pode propor uma localização alternativa de servidor aprovado pela KTP não listada acima. A localização alternativa exige a aprovação do capitão do time adversário. Se o capitão adversário não aprovar, o time HOME deverá selecionar uma das localizações padrão listadas acima, respeitando estritamente a ordem de prioridade (New York como primária obrigatória).

> **Importante:** As partidas nunca podem ser jogadas em servidores não aprovados pela KTP, independentemente de acordo mútuo.

#### 2.4.d NA vs SA — Seleção de Servidor

Em partidas entre um time norte-americano e um time sul-americano (maioria de jogadores da SA a oeste de UTC -2), o time **HOME** seleciona a localização do servidor de jogo entre as seguintes localizações aprovadas pela KTP:

| Localização | Status |
|----------|--------|
| **Atlanta** | Disponível |
| **New York** | Disponível |

Essas localizações oferecem uma latência de compromisso razoável para conexões sul-americanas.

O time HOME pode propor uma localização alternativa de servidor aprovado pela KTP não listada acima. A localização alternativa exige a aprovação do capitão do time adversário. Se o capitão adversário não aprovar, o time HOME deve escolher entre as localizações padrão listadas acima.

> **Importante:** As partidas nunca podem ser jogadas em servidores não aprovados pela KTP, independentemente de acordo mútuo.

#### 2.4.e Escolha de Lado em NA vs EU

Quando um time norte-americano joga contra um time europeu (maioria de jogadores da UE a leste de UTC -2 conforme a Regra 2.1), **o time NA sempre escolhe** em qual lado (Allies ou Axis) jogará primeiro, **sobrepondo-se à vantagem do time home definida na Regra 2.3.a**. Isso compensa a vantagem de agendamento que os times da UE recebem do horário padrão de partida mais cedo.

### 2.5 Uso de Jogadores Suspensos

Os times não podem incluir no roster nem escalar indivíduos suspensos pela KTP. As violações resultam em:
- Remoção do time da liga
- Possível suspensão de todos os membros do time
- Suspensão de qualquer pessoa que empreste contas para burlar banimentos

### 2.6 Mudanças de Nome do Time

Um time pode mudar de nome **uma vez** ao longo de uma temporada. Depois de usar essa única mudança de nome, o nome do time fica travado pelo restante da temporada.

### 2.7 Rosters e Travas de Roster

| Regra | Detalhes |
|------|---------|
| **Tamanho máximo do roster** | 10 jogadores |
| **Momento da trava** | Fim do período de registro de times |
| **Após a trava** | Nenhuma alteração de roster, nome do time, aliases dos jogadores ou SteamIDs |
| **Exceção** | Alterações ainda podem ser feitas por decisão administrativa — ver Regra 2.7.a |

#### 2.7.a Solicitação de Alteração de Roster

As alterações de roster são solicitadas no site da liga (ktpleague.gg), nas configurações da sua conta, e não por ticket de suporte.

| Quando | Capitão | Jogador que pede para sair |
|------|---------|------------------------|
| **Registro aberto** | Edita o roster diretamente; os administradores são notificados do que mudou | Registra uma solicitação |
| **Registro fechado, antes da trava** | Registra uma solicitação; a equipe a analisa | Registra uma solicitação |
| **Após a trava** | O formulário do capitão é encerrado — fale com um administrador | Registra uma solicitação |

Um jogador pode pedir para sair de um roster **a qualquer momento, antes ou depois da trava**, pelas configurações da própria conta. É uma solicitação em todos os casos: o jogador permanece no roster até que um administrador atue sobre ela, e uma solicitação que deixaria um time sem capitão não é aplicada até que outro capitão esteja no lugar.

Toda solicitação e toda decisão ficam registradas.

### 2.7.1 Janela de Roster no Meio da Temporada

Uma janela de adição ao roster ocorrerá no meio da temporada, anunciada com pelo menos uma semana de antecedência.

| Divisão | Requisitos |
|----------|--------------|
| **Divisão mais alta** | Adições aprovadas se houver vaga no roster (até 10) |
| **Demais divisões** | Aprovação de administrador necessária (preserva a integridade competitiva) |

### 2.8 Proibição de Contornar Regras por Acordo

Nenhum acordo entre capitães de times pode se sobrepor às regras oficiais ou a suspensões ativas. Tais acordos são inválidos e constituem violação de regra.

### 2.9 Ringers

Um **ringer** é um jogador que não está no seu roster oficial, usado temporariamente para completar o time. O uso de ringers exige a aprovação do capitão do time adversário antes do início da partida.

### 2.10 Mínimos de Roster nas Partidas

| Requisito | Detalhes |
|-------------|---------|
| **Jogadores do roster** | Pelo menos 4 dos 6 jogadores devem ser do roster oficial |
| **Máximo de ringers** | São permitidos até 2 ringers aprovados |

### 2.11 W.O. de Times e Remoção

Times que derem W.O. repetidamente podem ser removidos da liga. Mais de um W.O. em uma temporada pode resultar em remoção, a critério dos administradores.

---

## 3. Trapaça, Penalidades e Contestações

> **Resumo da Seção:** Esta seção descreve o que constitui trapaça, o processo de contestação, os requisitos de evidência e as penalidades por violações.

### 3.1 Autoridade dos Administradores

Os administradores da liga reservam-se o direito de aplicar suspensões, W.O. ou outras penalidades conforme necessário. Todas as decisões visam preservar o jogo limpo e a integridade competitiva.

### 3.2 Investigações e Evidências

Os administradores da KTP podem investigar qualquer jogador ou time por comportamento suspeito, incluindo:
- Solicitar POV demos dos jogadores aleatoriamente e revisar registros do KTPAntiCheat
- Realizar verificações pontuais a qualquer momento

**A falta de fornecimento dos materiais solicitados pode resultar em:**
- Perda do jogo/partida em questão por W.O.
- Suspensão do jogador

### 3.3 Tolerância Zero com Trapaça

Qualquer jogador flagrado trapaceando será suspenso (ou banido) da KTP, e quaisquer resultados de partida influenciados ficam sujeitos a serem revertidos ou declarados W.O.

#### 3.3.a Alcance de um Banimento

Um banimento pode ser aplicado a um jogador e, havendo evidência de burla de banimento, ao hardware usado para burlá-lo. Um banimento se aplica a todos os servidores operados pela KTP.

Quando o hardware é compartilhado — uma máquina de local de evento, uma residência, um computador compartilhado —, um banimento de hardware não deve ser aplicado sem evidência que conecte o jogador específico à burla. Uma pessoa afetada por um banimento de hardware que não tenha participado da burla pode contestá-lo sob a Regra 3.9.a e, em caso de contestação bem-sucedida, deve ser reintegrada.

### 3.4 Definição de Trapaça

Trapaça inclui (mas não se limita a):
- Wallhacks (ver inimigos através de paredes)
- Aimbots (aquisição automática de alvos)
- Modificar ilegalmente arquivos do jogo
- Qualquer programa externo que conceda vantagem injusta
- Multiplicação de input — modos "Snap Tap" / null-cancel SOCD, "Rapid Fire" / Turbo (repetição automática), ou qualquer bind, script ou recurso de dispositivo que produza mais de um input a partir de um único acionamento físico, acelere o disparo ou contorne o stamina (ver Regra 4.6)

### 3.5 Arquivos de Jogo Permitidos e Proibidos

Somente os arquivos padrão do jogo podem ser usados, com estas exceções:

#### Modificações Permitidas:
| Modificação | Status |
|--------------|--------|
| HUD/UI de placar personalizado aprovado | Permitido |
| Modelos HLTV personalizados | Permitido |
| Modificações em ClientScheme.res | Permitido |
| Modificações em TrackerScheme.res | Permitido |
| Mira personalizada (armas que não sejam sniper) | Permitido |
| Mira personalizada para rifle sniper | **NÃO Permitido** |

### 3.6 Regra de Espectador no Jogo (Proibido Espectar Após o Live)

Uma vez que a partida tenha entrado em "live", nenhum jogador tem permissão para usar o modo espectador. **Spec hopping** é considerado trapaça.

**Exceções:**
- Jogador morto no exato momento da captura total do mapa
- Jogador que fica preso na geometria do mapa

### 3.7 Registro de Contestações

As contestações devem ser registradas pelo capitão do time **dentro de 24 horas** do término da partida.

| Fase da Temporada | Limite de Contestações |
|--------------|---------------|
| Temporada regular | 2 contestações de trapaça |
| Pós-temporada (playoffs) | 1 contestação de trapaça |

> **Nota:** Contestações válidas (em que o acusado é considerado culpado) não contam para o seu limite.

### 3.8 Processo de Contestação para Jogadores Acusados

#### 3.8.a Prazo para Envio de Evidências
Os jogadores têm **24 horas a partir da notificação** para enviar:
- POV demos
- Quaisquer outros materiais solicitados

#### 3.8.b Consequências e Investigação
- A falta de fornecimento dos arquivos pode resultar em suspensão e/ou W.O.
- Os administradores podem revisar demos e registros do KTPAntiCheat de partidas anteriores/posteriores
- O jogador pode ficar sujeito a escrutínio adicional em jogos futuros

### 3.9 Registros do KTPAntiCheat

Os registros do KTPAntiCheat são produzidos automaticamente pelo cliente e mantidos pela liga; os jogadores não são obrigados a enviá-los. Em caso de contestação ou verificação aleatória, os jogadores devem fornecer suas POV demos da partida em questão.

Toda sessão é avaliada nos servidores da KTP a partir das evidências enviadas. As sessões podem ser reavaliadas quando os métodos de detecção mudarem, inclusive sessões do início da temporada; uma reavaliação pode alterar um resultado anterior em qualquer direção.

**Retenção:** Os envios de sessão são retidos indefinidamente para revisão de integridade, de modo que uma determinação sempre pode ser reexaminada a partir da evidência original. A telemetria de partida é mantida por **30 dias**; os registros e resultados de sessão são mantidos pela temporada. Uma determinação que se apoie em telemetria só pode ser reexaminada enquanto aquela telemetria ainda estiver retida.

#### 3.9.a Contestação de uma Determinação do KTPAntiCheat

Um jogador pode contestar uma determinação do KTPAntiCheat, inclusive uma determinação de cobertura, notificando um administrador dentro de **14 dias** após ser informado dela. As determinações são reexaminadas a partir da evidência original, onde ela ainda estiver retida (ver Regra 3.9).

Um jogador pode revisar suas próprias sessões enviadas a qualquer momento pelo site da liga KTP (ktpleague.gg), incluindo capturas de tela, arquivos de configuração e inventário de dispositivos, e pode baixar uma cópia própria. Artefatos individuais podem ser retidos e não incluídos nessa cópia quando sua divulgação revelaria como o KTPAntiCheat detecta trapaça. Quando algo for retido, o jogador é informado de que houve material retido, e um administrador que não tenha feito a determinação original explicará o motivo mediante solicitação. O material retido ainda é examinado integralmente quando uma contestação sob esta regra é analisada.

Um administrador que não tenha feito a determinação original analisa a contestação. O resultado é um dos seguintes: determinação mantida, determinação retirada ou determinação modificada. O jogador é informado de qual foi e por quê.

Um resultado automatizado nunca é, por si só, um desfecho final — uma pessoa revisa qualquer determinação antes de uma penalidade ser aplicada.

---

## 4. Regras para Jogadores

> **Resumo da Seção:** Esta seção descreve o registro de jogadores, os requisitos de identidade, as obrigações de gravação, a retenção de arquivos e os comportamentos proibidos.

### 4.1 Registro e Identidade do Jogador

#### 4.1.a Regras da Comunidade e Conduta
Todos os jogadores concordam em cumprir as **Regras da Comunidade KTP** em todos os momentos.

#### 4.1.b Registro de Alias e SteamID
- Um alias no jogo e uma conta Steam por jogador
- Permitido alterar o alias e/ou o SteamID **uma vez** por temporada
- As alterações devem ser comunicadas aos administradores da liga

#### 4.1.c Requisitos de Identidade no Jogo
- Deve usar exatamente o SteamID registrado
- Deve usar a tag do time e o alias registrado do jogador
- Pequenas variações de formatação são permitidas (códigos de cor, abreviações)

#### 4.1.d Verificações de Integridade de Arquivos e de CVAR
Todos os jogadores devem cumprir as verificações de integridade de arquivos, de CVAR e de anticheat. Os jogadores não podem interferir nesses sistemas nem contorná-los.

#### 4.1.e KTPAntiCheat

Todo jogador deve executar a versão atual do **KTPAntiCheat** durante toda a duração de cada partida que disputar. Uma partida está coberta quando a sessão do KTPAntiCheat do jogador está em execução antes do início da partida e permanece em execução até o término dela.

Os jogadores não podem alterar, adulterar ou interferir no cliente, em seus registros de sessão ou em seus envios, e não podem enviar nem fazer com que seja enviado qualquer registro que não seja o seu próprio.

Um jogador cuja partida não esteja coberta fica sujeito ao mesmo tratamento de qualquer outra violação da Seção 4. A falha repetida em cobrir partidas pode ser tratada como burla.

A cobertura é determinada a partir dos próprios registros do KTPAntiCheat. Um jogador pode contestar uma determinação de cobertura sob a Regra 3.9.a.

Falha técnica — um crash, uma desconexão ou uma indisponibilidade do KTPAntiCheat — não é uma violação, desde que o jogador a comunique a um administrador antes da partida seguinte. Os administradores podem aceitar uma partida não coberta a seu critério, quando a causa for evidente.

#### 4.1.f POV Demos e Capturas de Tela

**POV Demos:**
- Grave uma POV demo para cada tempo (duas demos por jogo completo)
- Comece a gravar antes do primeiro round e pare quando o tempo terminar

**Captura de Tela Pré-Jogo:**
- Tire uma captura de tela mostrando pelo menos um modelo de jogador de cada time
- Verifica se os modelos/skins dos jogadores estão corretos

**Capturas de Tela do Placar ao Fim de Cada Tempo:**
- Capture o placar ao fim de cada tempo
- Usadas para verificar o placar e a participação dos jogadores

**Permanecer Até o Fim do Jogo:**
- Não se desconecte até que a partida esteja completamente encerrada
- Se sofrer um crash, reconecte imediatamente

**Demos de Prorrogação:**
- Grave POV demos separadas para cada tempo de prorrogação, seguindo o mesmo procedimento dos tempos regulamentares

#### 4.1.g Comprimento e Formato do Nome do Personagem

Todos os aliases de jogadores, tags de time e nomes completos no jogo devem cumprir os seguintes requisitos técnicos para garantir compatibilidade com a engine do jogo:

**Comprimento Máximo:**
Os aliases de jogadores e as tags de time não podem exceder 30 caracteres visíveis. Os nomes completos no jogo (tag do time + alias do jogador) também não podem exceder 30 caracteres visíveis no total.

**Restrição de Conjunto de Caracteres:**
Somente caracteres ASCII padrão são permitidos. Isso inclui:
- Letras: A-Z, a-z
- Números: 0-9
- Símbolos básicos: ! @ # $ % ^ & * ( ) - _ = + [ ] { } | \ ; : ' " , . < > ? / ~
- Espaços (embora o espaçamento excessivo seja desaconselhado)

**Proibido:**
O seguinte não é permitido em nomes de jogadores ou tags de time:
- Caracteres UTF-8, Unicode ou multibyte (por exemplo, emoji, alfabetos não latinos, símbolos especiais como ™ © ®)
- Caracteres fora da faixa ASCII padrão
- Quaisquer caracteres que possam causar problemas de exibição ou instabilidade da engine

**Aplicação:**
Nomes de jogadores ou tags de time que violem esses requisitos devem ser alterados antes do início da partida.

### 4.2 VODs Não São Substitutos Aceitáveis

Gravações de vídeo ou VODs da Twitch **NÃO** substituem demos nem o KTPAntiCheat. Você ainda deve gravar as demos no jogo e executar o KTPAntiCheat mesmo que esteja transmitindo.

### 4.3 Retenção de Arquivos

Guarde todos os arquivos de partida **durante toda a temporada**:
- POV demos de cada tempo
- Todas as capturas de tela exigidas

> **Nota:** Não há arquivo de anticheat para os jogadores guardarem — os registros do KTPAntiCheat são produzidos e retidos pela liga (ver Regra 3.9).

### 4.4 Boost de Jogadores

O boost é **permitido somente se** a área de destino for alcançável por um único jogador sem boost. Dar boost para acessar áreas com glitch ou não previstas é ilegal.

### 4.5 Comandos de Voz e Sinais

Os comandos de voz devem ser usados apenas para comunicação de time. O uso excessivo para provocar, irritar ou "negar" adversários não é permitido.

### 4.6 Atribuições de Teclas e Recursos de Dispositivo

**Princípio:** um acionamento físico equivale a um input no jogo. Um dispositivo pode alterar *quando* uma única tecla é registrada (seu ponto de acionamento/reset); ele não pode multiplicar uma ação física em vários inputs, repetir automaticamente um input, nem resolver um input por você.

**Permitido:** Rapid Trigger e pontos de acionamento ajustáveis — estes alteram apenas *onde*, no curso de uma tecla, um único pressionamento é registrado. Um pressionamento continua sendo um input, de modo que o jogador segue sendo o limitador de cadência. ("Rapid Trigger" é o termo padrão da indústria — usado por Wooting, Razer, SteelSeries, Corsair etc. — para um ponto de reset dinâmico/contínuo em teclados Hall-effect/analógicos e em switches analógicos de mouse. Rapid Trigger é permitido tanto em teclados quanto em mouses. **Não** é o mesmo que o "Rapid Fire" / "Turbo" de repetição automática proibido abaixo.)

**Proibido:**
- **Uma tecla atribuída a `+attack` deve emitir `+attack` e nada mais.** Atribuir ou criar alias de `+attack` junto com qualquer comando adicional — diretamente, por meio de um alias ou por meio de uma config executada com exec — é proibido.
- Atribuir `+attack` ou `+duck` à roda do mouse (acelera o disparo / contorna as restrições de stamina)
- Modos "Rapid Fire", "Turbo" ou multi-tap de teclado/mouse que emitem inputs repetidos a partir de um único pressionamento
- Binds de "Snap Tap" / tratamento SOCD / null-cancel que soltam automaticamente uma de duas teclas de movimento opostas (**SOCD** é o termo genérico; "Snap Tap" é o nome comercial da Razer)

**Observações:**
- A reatribuição de teclas não é afetada. `+attack` pode ser atribuído a qualquer tecla, e outros comandos podem ter suas próprias teclas. Apenas combiná-los na tecla de disparo é proibido.
- Comandos nativos não são suspeitos por si só. `+lookup`, `+lookdown`, `+left`, `+right` e `centerview` vêm como padrão do Half-Life e aparecem na maioria das configs.
- `+jump` na roda do mouse permanece permitido (bunny-hopping).

### 4.7 Proibição de Scripts Automatizados

Os jogadores não podem usar scripts para automatizar:
- Ataque do jogador
- Movimento do jogador
- Rapid-fire
- Compensação automática de recuo
- Padrões automatizados de pulo ou movimento

### 4.8 Exploração de Movimento/Animação

Os jogadores não podem usar sinais de mão, comandos de voz ou alternâncias de cvar combinados com comandos de movimento para tornar seu modelo de jogador mais difícil de acertar. Qualquer tática que distorça, faça tremer ou desalinhe sua hitbox é ilegal.

### 4.9 Glitches e Exploits

Os seguintes são considerados trapaça:

| Exploit | Descrição |
|---------|-------------|
| **Spawn de Armas** | Gerar armas/munição extras para contornar as limitações de classe |
| **Glitch de Granada** | Duplicar granadas ou contornar as mecânicas normais |
| **Bugs de Mapa** | Atravessar paredes, ficar por baixo/por cima do mapa |
| **Pixel Walking** | Usar pontos de colisão não previstos para posicionamento injusto |
| **Glitch de Parede** | Fazer o modelo do jogador atravessar parcialmente paredes para ver/atirar no outro lado |

> **Princípio geral:** Qualquer exploit que não faça parte de uma jogabilidade justa e prevista é ilegal, mesmo que não esteja explicitamente listado.

---

## 5. Regras para Capitães

> **Resumo da Seção:** Esta seção descreve as responsabilidades e exigências específicas dos capitães de time.

### 5.1 Deveres do Capitão no Jogo

#### 5.1.a Placares Legíveis
Os capitães devem configurar as opções de seu cliente por meio de um client scheme personalizado, de modo que os placares de fim de tempo sejam fáceis de ler nas capturas de tela (alto contraste, fonte clara).

#### 5.1.b Captura de Tela do RCON Status
Os capitães devem tirar uma captura de tela do `rcon status` por jogo para comprovar os SteamIDs dos jogadores.

### 5.2 Comunicação e Disponibilidade

- Os capitães não podem estar banidos do Discord da KTP
- Devem estar acessíveis e responder prontamente às mensagens de agendamento
- Em caso de ausência, devem designar um capitão interino e informar os administradores

### 5.3 Pontualidade nas Partidas e Vitórias por W.O.

| Momento | Ação |
|------|--------|
| **+10 minutos** | Documente e avise um administrador se não houver notícia do time adversário |
| **+15 minutos** | O administrador pode declarar oficialmente o não comparecimento e conceder a vitória por W.O. |

### 5.4 Agendamento Justo

Os capitães devem agendar com integridade:
- Seja proativo na comunicação
- Ofereça múltiplos horários razoáveis
- Responda prontamente
- Guarde registros das comunicações de agendamento

#### 5.4.a Prazo Regulamentar de Agendamento

Todas as partidas da temporada regular devem ser concluídas até a **meia-noite que encerra o
último domingo da temporada regular** (00:00 do Leste do dia seguinte). Uma partida
ainda não disputada ou sem horário confirmado nesse prazo é encaminhada à
equipe de administração junto com todo o seu registro de agendamento — cada horário proposto,
cada resposta e cada lembrete que a liga tentou entregar.

- **Sem W.O. automáticos.** O prazo sinaliza uma partida para revisão administrativa; ele
  nunca decide um resultado. Os administradores decidem sob §1.13 e §3.1, ponderando quem
  propôs horários, quem ficou em silêncio e — como fato distinto — se os
  capitães de um time podiam sequer ser contatados.
- Um time cujos capitães estavam inacessíveis por todos os canais de que a liga dispõe é um
  caso diferente de um time que foi contatado e não respondeu. O
  registro de agendamento mostra qual é qual.

### 5.5 Verificações de Roster e de Ringers

Os capitães devem verificar a elegibilidade dos jogadores antes do início da partida:
- Conferir se os jogadores adversários correspondem aos nomes e SteamIDs do roster
- Verificar se quaisquer ringers foram aprovados

> **Importante:** Uma vez concluída a partida, você não pode contestá-la com base em jogador inelegível se teve a oportunidade de detectá-lo previamente.

### 5.6 Reporte de Placares

Os resultados são reportados na página da partida no site da liga (ktpleague.gg) dentro de **1 hora após o término da partida**. A obrigação de reportar dentro da hora recai sobre o **capitão do time vencedor**; qualquer um dos capitães pode inserir o resultado, e um capitão perdedor que o insira primeiro cumpre essa obrigação.

O reporte é bilateral. Um capitão insere o resultado, o capitão **adversário** o confirma, e o resultado é registrado — e a classificação se move — somente com essa confirmação. Um capitão não pode confirmar o reporte do próprio time.

**Capitão que reporta:**

- [ ] Insira o total final de pontos de cada time na partida
- [ ] Confira o vencedor que o site apresenta de volta a você antes de enviar — um placar invertido é o erro comum, e o outro capitão é a única pessoa que pode detectá-lo

**Capitão adversário:**

- [ ] Confirme o resultado, ou conteste-o com uma justificativa, **dentro de 24 horas** após ser solicitado

Um capitão que discorde de um resultado inserido o contesta em vez de confirmá-lo. Um resultado contestado nunca é registrado; ele vai para a equipe de administração com os relatos de ambos os capitães.

As capturas de tela **não** são enviadas junto com o reporte. Os capitães ainda as tiram (Regra 5.1.a, Regra 5.1.b), as guardam pela temporada (Regra 4.3) e devem apresentá-las mediante solicitação — um resultado contestado é resolvido a partir delas.

> **Nota:** Os resultados de séries de playoff e os W.O. são registrados pelos administradores, e não pelo reporte dos capitães. Envie os placares de playoff a um administrador quando a série terminar.

> **Se o site não conseguir receber o reporte:** publique-o no canal de placares designado do Discord da KTP dentro da mesma hora e avise um administrador. Isso é um recurso alternativo para uma indisponibilidade, não uma segunda via de reporte.

### 5.7 Vetos de Mapa nos Playoffs

Os vetos são realizados apenas para partidas de playoff. Eles ocorrem na sala de veto da página da partida no site da liga (ktpleague.gg): ambos os capitães agem em turnos — banimentos, escolhas e lados iniciais — contra o pool de mapas de playoff publicado. O site decide de quem é a vez e recusa uma jogada ilegal, de modo que não há nada a enviar em nenhum outro lugar.

Os capitães devem concluir o veto **pelo menos 72 horas antes do horário padrão de início da partida do round** (Regra 2.2). O prazo é medido a partir do horário padrão, e não de qualquer horário posterior que os dois capitães acordem entre si.

> **Penalidade:** Se o veto não estiver concluído nesse prazo, os administradores executam as etapas pendentes em nome do time atrasado. Uma etapa realizada dessa forma é marcada como ação da equipe no log de veto da partida, que é público.

A duração da série é definida pelos administradores na partida. A maioria das partidas de playoff é melhor de três; o veto funciona da mesma forma para uma melhor de um ou uma melhor de cinco.

#### 5.7.a Quando um Round se Define Tarde

Uma partida de playoff não tem times até que o round anterior a ela seja decidido. Quando ambos os times se tornam conhecidos **menos de 72 horas antes** do início padrão do round, o prazo de 72 horas não pode ter sido cumprido e não é computado contra nenhum dos times. O veto passa a ser devido **assim que ambos os capitães tiverem tido uma oportunidade razoável de realizá-lo**, e os administradores podem executar as etapas pendentes quando a partida estiver, de outro modo, prestes a ser disputada.

### 5.8 Responsabilidade do Capitão

Os capitães são responsáveis por garantir que os membros do time compreendam e sigam todas as regras. Violações repetidas do time podem resultar em suspensão do capitão por negligência.

---

**Fim do Documento de Regras**

*Última atualização: agosto de 2026*

*Dúvidas? Entre em contato com os administradores da KTP pelo Discord ou pelo site da liga.*

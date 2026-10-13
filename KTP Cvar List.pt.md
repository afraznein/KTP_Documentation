<!-- ktp-translation
locale: pt
source: KTP Cvar List.md
source-sha256: 40fe78834ec1530138f5cd67d9bdb23af61758fb5d549de38015ae272adc25e8

Records which revision of the English cvar list this translation was made from.
ktpleague.gg re-checks it on every render and warns readers when it no longer
matches. Whenever KTP Cvar List.md changes, update this translation and refresh
the hash - the workflow in .github/workflows/ opens a tracking issue for it.
-->
# Requisitos de CVAR da Liga KTP

**Configurações de Variáveis de Cliente do Day of Defeat 1.3**

[![Version](https://img.shields.io/badge/Version-Season%202026-blue)](#)
[![Game](https://img.shields.io/badge/Game-Day%20of%20Defeat%201.3-green)](#)

> Todos os jogadores devem usar estas configurações de CVAR durante as partidas da KTP. Os valores fixos são obrigatórios, salvo quando uma faixa for especificada. O servidor da KTP verifica e aplica estes valores automaticamente.

---

## Índice

- [CVARs de Valor Fixo](#cvars-de-valor-fixo)
  - [Gráficos e Renderização](#gráficos-e-renderização)
  - [Áudio](#áudio)
  - [Movimento e Entrada](#movimento-e-entrada)
  - [Rede e Predição](#rede-e-predição)
  - [HUD e Interface](#hud-e-interface)
- [CVARs Baseados em Faixa](#cvars-baseados-em-faixa)

---

## CVARs de Valor Fixo

Estes CVARs devem estar no valor exato especificado. O servidor corrigirá automaticamente qualquer desvio.

### Gráficos e Renderização

| CVAR | Valor | Descrição |
|------|-------|-------------|
| `gl_clear` | `0` | Quando em 1, torna visíveis as frestas entre as texturas |
| `gl_d3dflip` | `0` | Quando em 1, torna visíveis as frestas entre as texturas |
| `gl_monolights` | `0` | Fonte de luz uniforme, sem sombras (somente OpenGL) |
| `gl_overbright` | `0` | Modo de brilho máximo |
| `gl_picmip` | `0` | Nível de mipmap das texturas. Valores altos reduzem as texturas de parede a blocos de cor sólida; travado em 0 para impedir o abuso de wallhack por contraste. **Não altere.** |
| `r_drawentities` | `1` | Desenho dos modelos de jogador e dos sprites (0=nenhum, 1=normal, 2=sem texturas, 3=hitbox, 4=hitboxes translúcidas) |
| `r_drawviewmodel` | `1` | Ativa ou desativa o desenho do modelo da arma do jogador |
| `r_dynamic` | `1` | Iluminação dinâmica (reflexos de lanterna etc.) |
| `r_fullbright` | `0` | Brilho máximo somente em jogos locais |
| `r_glowshellfreq` | `2.2` | Velocidade de animação do glow shell — padrão do motor do DoD. Usado pelo brilho do portador da bandeira. Aplicado no valor padrão do motor como verificação de integridade (detecta sobrescritas por autoexec). **Não altere.** |
| `r_lightmap` | `0` | Renderização por software: exibe os lightmaps (0-3) |
| `r_traceglow` | `0` | Depuração de traçado do glow shell — padrão do motor do DoD. Aplicado no padrão como verificação de integridade. **Não altere.** |
| `texgamma` | `2` | Nível de gama das texturas |

### Áudio

| CVAR | Valor | Descrição |
|------|-------|-------------|
| `s_show` | `0` | Mostra na tela quais sons estão sendo reproduzidos |

### Movimento e Entrada

| CVAR | Valor | Descrição |
|------|-------|-------------|
| `cl_bobcycle` | `0.8` | Com que frequência a visão do jogador balança ao correr |
| `cl_bobup` | `0.5` | Quantidade de movimento antes de o balanço da visão começar |
| `cl_pitchdown` | `89` | Ângulo máximo para olhar para baixo |
| `cl_pitchup` | `89` | Ângulo máximo para olhar para cima |
| `cl_pitchspeed` | `225` | Velocidade de giro vertical pelo teclado (graus por segundo). Travado no padrão do GoldSrc para impedir scripts de no-recoil baseados em alias. **Não altere.** |
| `cl_yawspeed` | `210` | Velocidade de giro horizontal pelo teclado (graus por segundo). Travado no padrão do GoldSrc. **Não altere.** |
| `cl_anglespeedkey` | `0.67` | Multiplicador aplicado a `cl_pitchspeed`/`cl_yawspeed` enquanto +speed estiver pressionado. Travado no padrão do GoldSrc. **Não altere.** |
| `m_pitch` | `0.022` ou `-0.022` | Multiplicador de sensibilidade do eixo vertical do mouse. **Jogadores com mouse invertido usam `-0.022`** — o negativo é explicitamente aceito, e um valor negativo fora da tolerância é corrigido para `-0.022`, nunca invertido para positivo. Você não precisa abrir mão do eixo vertical invertido para estar em conformidade. |
| `m_side` | `0.8` | Multiplicador de velocidade de deslocamento lateral do mouse. Travado no padrão do GoldSrc. **Não altere.** |

### Rede e Predição

> 📖 Para a explicação completa destas configurações — como funciona a rede do GoldSrc, por que cada valor é o que é, e quando é legítimo desviar — consulte o **[Guia de Netcode da KTP](https://netcode.ktpdod.com/)**.

| CVAR | Valor | Descrição |
|------|-------|-------------|
| `rate` | `100000` | Taxa de transmissão do cliente para o servidor (bytes/seg). **Não altere.** |

#### CVARs de rede ajustáveis pelo jogador (sem fiscalização)

Estes cvars afetam o comportamento do seu próprio cliente. O KTPCvarChecker NÃO os fiscaliza — a escolha é sua. Os padrões estão indicados.

| CVAR | Padrão | Observações |
|------|---------|-------|
| `cl_mousegrab` | `1` | Se o motor confina o cursor do mouse à janela do jogo. Apenas do cliente — o servidor nunca o vê, sem efeito na jogabilidade nem na mira (a mira usa entrada bruta de qualquer forma). Com `1`, o cursor prende nos cantos do monitor e falha ao alternar janelas ou em configurações multimonitor no modo janela. **Recomendado: `0` para jogo em janela ou multimonitor, `1` para tela cheia exclusiva.** (Não é mais fiscalizado desde o KTPCvarChecker 7.30.) |
| `cl_lc` | `1` | Compensação de lag do lado do servidor para os SEUS tiros. Com `0`, o rebobinamento é desativado — você precisa antecipar os alvos por todo o seu ping. **É uma autolimitação, não um exploit.** Alguns jogadores preferem `0` para eliminar a sensação de "tiro atravessando a parede"; a maioria deixa em `1`. **Recomendado: 1.** |
| `cl_lw` | `1` | Predição de armas do lado do cliente. Com `0`, as animações de arma passam a depender do servidor (parece travado com ping fora de LAN). Definir `0` também desativa a compensação de lag (as verificações exigem `lc=1` E `lw=1`). **É uma autolimitação, não um exploit.** **Recomendado: 1.** |
| `cl_fixtimerate` | `7.5` | Com que agressividade o seu cliente corrige o relógio local em direção ao horário do servidor (ms de correção permitidos por quadro). Sem superfície competitiva — a sincronização do relógio acontece de qualquer forma. O padrão é uma causa conhecida de **falhas na animação do modelo de arma** no GoldSrc; se as animações da sua arma engasgarem, reduza-o (em direção a `0`) para deixar o modelo de arma mais fluido. **Recomendado: 7.5, a menos que você veja falhas na arma.** |
| `cl_smoothtime` | `0.1` | Quanto tempo (em segundos) o seu cliente leva para suavizar visualmente as correções de erro de predição do SEU PRÓPRIO movimento (esbarrões de companheiros, recuo, aterrissagens em bordas). Durante a janela de suavização, sua posição renderizada fica atrás da do servidor — uma pequena discrepância de mira. `0.01` distribui a correção ao longo de ~um intervalo de atualização: precisão praticamente instantânea, sem saltos de um único quadro (a convenção antiga da liga). **Recomendado: 0.01. Jogadores com ping alto (100 ms ou mais) podem usar o padrão de 0.1 por conforto — suas correções são maiores e mais frequentes.** |

### HUD e Interface

| CVAR | Valor | Descrição |
|------|-------|-------------|
| `hud_takesshots` | `1` | Salva automaticamente uma captura do placar ao fim de um mapa. Fiscalizado **somente em partidas competitivas** (`.ktp`, `.ktpOT`) — em `.12man`, `.scrim` e `.draft` o servidor não o verifica nem o corrige. |
| `cl_showevents` | `0` | Mostra eventos como o disparo de armas (os eventos estão listados em dod/events/) |

---

## CVARs Baseados em Faixa

Estes CVARs devem estar dentro da faixa especificada. Valores fora da faixa serão corrigidos pelo servidor.

| CVAR | Faixa | Padrão | Descrição |
|------|-------|---------|-------------|
| `lightgamma` | **1.809** - **3.0** | 2.5 | Valor de gama da iluminação. Valores abaixo de 1.809 fazem o DoD travar |
| `cl_bob` | **0** - **0.01** | 0.005 | Quantidade de balanço da visão ao correr |
| `cl_updaterate` | **100** - **120** | - | Atualizações solicitadas ao servidor por segundo. O cliente limita internamente o processamento a **102** — valores de 103 a 120 passam na verificação, mas não fazem nada, então defina exatamente `102`. **Exigido pela KTP.** |
| `cl_cmdrate` | **100** - **1000** | - | Vezes por segundo que o cliente atualiza o servidor. Faixa útil = ≤ o fps do seu cliente; definir acima do seu fps desperdiça banda. v7.25: teto elevado de 500 para 1000 para permitir testar entrada de alta resolução em clientes de 1000 fps. **Exigido pela KTP.** |
| `ex_interp` | **0.01** - **0.05** | - | Tempo de interpolação entre atualizações. **Defina 0.01** em uma conexão limpa. Aumente APENAS por perda de pacotes ou jitter na sua própria conexão (verifique `net_graph 1`): 0.02 atravessa um único pacote perdido; 0.02-0.03 para rotas com jitter crônico; 0.03-0.05 apenas para rotas de latência genuinamente alta, que é o motivo de o teto ser 0.05 e não menos. O ping sozinho — o seu ou o dos seus adversários — não é um motivo: a latência atrasa o fluxo de forma uniforme e a compensação de lag leva isso em conta (o servidor rebobina por ping + interp, portanto um interp maior custa tempo de reação, não registro de acertos). **Exigido pela KTP.** |
| `fps_max` | **60** - **750** | - | Quadros por segundo máximos. **Defina 100.5**, e não um 100 exato: um 100 exato pode ficar um fio abaixo de 100 e perder um quadro de vez em quando, o que deixa o tiro com sensação de engasgo, e 100.5 dá ao limitador folga para manter um 100 estável. **Exigido pela KTP.** |

---

## Referência Rápida

### Configurações Recomendadas (Copiar/Colar)

```
rate 100000          // travado pelo servidor — qualquer outro valor é corrigido automaticamente
cl_updaterate 102    // o verdadeiro máximo do cliente (o cliente limita internamente em 102)
cl_cmdrate 101       // iguale ao seu fps_max — não dá para enviar mais pacotes do que quadros
ex_interp 0.01       // um intervalo de atualização de folga; você vê os inimigos o mais perto possível da posição real
fps_max 100.5        // um 100 estável (um 100 exato pode cair abaixo e parecer engasgado); use a taxa de atualização do seu monitor (144/240) se for maior
cl_lc 1              // compensação de lag para os seus tiros — 0 significa antecipar por todo o seu ping
cl_lw 1              // predição de armas do cliente — 0 também desativa a compensação de lag
cl_fixtimerate 7.5   // velocidade de sincronização do relógio do cliente (padrão) — reduza em direção a 0 apenas se as animações de arma falharem
cl_smoothtime 0.01   // correção de erro de predição quase instantânea — o padrão de 0.1 é a opção confortável para ping alto
```

Se você usar um limite de quadros maior que 100.5, aumente o `cl_cmdrate` para acompanhá-lo (por exemplo, `fps_max 240` → `cl_cmdrate 250`).

O raciocínio completo por trás de cada valor, além de solução de problemas: **[Guia de Netcode da KTP](https://netcode.ktpdod.com/)**.

### Verifique Suas Configurações

Para conferir seus valores atuais de CVAR dentro do jogo, abra o console (`~`) e digite o nome do CVAR sem nenhum valor:

```
] cl_updaterate
"cl_updaterate" is "101"
```

---

## Observações Importantes

1. **Aplicação automática**: O servidor da KTP verifica e corrige automaticamente os CVARs fora de conformidade
2. **cl_filterstuffcmd**: Deve estar em `0` para que o servidor possa corrigir seus CVARs
3. **Gravação**: Estas configurações não afetam sua capacidade de gravar demos nem de executar o KTPAntiCheat
4. **Desempenho**: Se você tiver problemas de desempenho, fale com um administrador da KTP antes de alterar qualquer CVAR travado

---

*Última atualização: setembro de 2026 — auditado valor por valor contra `ktp_cvar.sma` no KTPCvarChecker **7.39**. Cada cvar fiscalizado desta página foi comparado com `gs_calvalues[]` / `gs_altvalues[]` no código-fonte. Removidos em 2026-09-12: `fastsprites`, `gl_nobind`, `gl_nocolors`, `gl_playermip` e `r_luminance`. O Day of Defeat não possui essas configurações, portanto o servidor nunca conseguiu verificá-las e ninguém jamais foi corrigido por elas; removê-las não muda nada para os jogadores. Mudança de recomendação em 2026-09-11: `fps_max` 100 → **100.5** (é uma mudança de recomendação, não de fiscalização; o 7.39 a aceita dentro da faixa de 60-750). Correções recentes de fiscalização refletidas aqui: **7.39** teto do `cl_bob` 0.011 → 0.01; **7.38** piso do `ex_interp` 0.009 → 0.01, com a correção que o servidor envia agora extraída da própria string do limite, de modo que ele não pode mais instruir um valor que em seguida rejeita; o teto do `ex_interp` é **0.05**, e não 0.03. Dois comportamentos que esta página nunca havia declarado agora estão escritos: o `m_pitch` aceita `-0.022` para o eixo vertical invertido, e o `hud_takesshots` é fiscalizado somente em partidas competitivas. Atualização anterior de julho de 2026 (referência rápida revisada contra a configuração da frota em produção + KTPCvarChecker 7.30: recomendação de `cl_updaterate` corrigida de 101 → 102 [verdadeiro teto do cliente], contexto adicionado para cada configuração, orientação de `cl_lc`/`cl_lw`/`cl_fixtimerate`/`cl_smoothtime` acrescentada à seção ajustável pelo jogador. Atualização anterior de abril de 2026: a v7.26 corrigiu o valor de fiscalização do `r_glowshellfreq` de 0 → 2.2 para coincidir com o padrão do motor do DoD — clientes com o padrão natural estavam sendo expulsos sob a fiscalização anterior de 0 da v7.24; aquele raciocínio do "0" não bloqueava de fato atacantes com ESP e quebrava a renderização do brilho do portador da bandeira. A v7.25 removeu cl_lc e cl_lw da fiscalização após uma auditoria do código do motor confirmar comportamento de mera autolimitação; elevou o teto do cl_cmdrate de 500 para 1000 para testes de clientes com fps alto. A v7.24 havia adicionado 7 cvars: cl_pitchspeed / cl_yawspeed / cl_anglespeedkey / m_side para defesa de giro pelo teclado, gl_picmip / r_glowshellfreq / r_traceglow para defesa contra exploits visuais — a fiscalização do gl_picmip segue ativa como defesa contra o wallhack por picmip.)*

*Dúvidas? Fale com os administradores da KTP pelo Discord ou pelo site da liga.*

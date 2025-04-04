
# Glossário do Podcast Vinteum.org - Optech Recap #347 (V2) 📚

Olá, pessoal! Tudo bem? 😊

Esse é um glossário que montei com base no episódio do podcast da [Vinteum.org](https://vinteum.org), o *Optech Recap #347 (V2)*. 
Aqui, reuni os termos que achei mais complicados ou novos pra mim, com explicações simples e exemplos pra ajudar a entender melhor o universo do Bitcoin e da Lightning Network. 
Se você também ouviu o podcast e ficou com alguma dúvida, espero que isso te ajude! 🚀

                                                                                                                                                                                                           
                                                      ##############  ++++++++++                      @@@@                  @@@                                                                                                                          
                                                      ##############  ++++++++++                      @@@@                  @@@                                                                                                                          
                                                      ##############  ++++++++++                                            @@@                                                                                                                          
                                                      ##############   +++++++++        @@@@     @@@@ @@@@ @@@@@@@@@@@@@  @@@@@@@@@@   @@@@@@@@@    @@@     @@@@ @@@@@@@@@@@@@@@@@@@                                                                     
                                                             #######    ++++++++        @@@@     @@@  @@@@ @@@@@@@@@@@@@@ @@@@@@@@@@  @@@@@@@@@@@@  @@@     @@@@ @@@@@@@@@@@@@@@@@@@                                                                     
                                                             #######    ++++++++         @@@    @@@@  @@@@ @@@@@     @@@@   @@@      @@@      @@@@  @@@     @@@@ @@@@    @@@@    @@@                                                                     
                                                             #######    ++++++++         @@@@   @@@   @@@@ @@@@       @@@@  @@@      @@@@@@@@@@@@@  @@@     @@@@ @@@@    @@@@    @@@                                                                     
                                                             #######    ++++++++          @@@@ @@@@   @@@@ @@@@       @@@@  @@@      @@@@@@@@@@@@@  @@@     @@@@ @@@@    @@@@    @@@                                                                     
                                                             ############*******          @@@@@@@@    @@@@ @@@@       @@@@  @@@@@@@@ @@@@@   @@@@@  @@@@@@@@@@@@ @@@@    @@@@    @@@                                                                     
                                                             #######%%%%%%%%%%%#           @@@@@@@    @@@@ @@@@       @@@@  @@@@@@@@@  @@@@@@@@@@   @@@@@@@@@@@@ @@@@    @@@@    @@@                                                                     
                                                             #####%%%%%%%%%%%%%#                                                                                                                                                                         
                                                             ###%%%%%%%%%%%%%%%#                                                                                                                                                                         

                                                                                                                                                                                                                                              
---

## Glossário de Termos

### Ótimo de Pareto
No Bitcoin, é quando os recursos (taxas, capacidade de transação, largura de banda da rede) são distribuídos de um jeito que não dá pra melhorar a situação de alguém (um minerador, usuário ou nó) sem prejudicar outro.  
**Exemplo:** Na Lightning Network, um equilíbrio ótimo de Pareto acontece quando os canais estão bem balanceados, maximizando a eficiência de roteamento sem sobrecarregar nenhum nó.

### HTLC (Hash Time-Locked Contract)
Um contrato inteligente no Bitcoin que usa dois mecanismos: um "hash lock" (exige um segredo criptográfico, chamado preimage) e um "time lock" (um prazo pra executar). É muito usado na Lightning Network pra pagamentos condicionais e em atomic swaps.  
**Exemplo:** Garante que o receptor prove que recebeu o pagamento, ou o dinheiro volta pro remetente depois do prazo.

### Equilíbrio de Nash
Um conceito da teoria dos jogos que se aplica ao Bitcoin. É quando todos os participantes (mineradores, usuários, nós) chegam num ponto em que ninguém quer mudar sua estratégia sozinho, porque já tá no melhor cenário possível.  
**Exemplo:** Mineradores seguem o protocolo do Bitcoin porque minerar honestamente dá mais lucro, se todo mundo também seguir as regras.

### HTLC in Flight
Um HTLC ativo na Lightning Network que tá "no ar", ou seja, em trânsito entre os nós, ainda não foi resolvido (nem pago, nem expirado).  
**Exemplo:** Um pagamento pendente que pode travar a liquidez dos canais enquanto não é finalizado.

### RoboSats
Uma plataforma P2P (peer-to-peer) descentralizada pra trocar Bitcoin usando a Lightning Network e HTLCs. Foca em privacidade e segurança, sem intermediários.  
**Exemplo:** Você pode negociar Bitcoin anonimamente, com trocas seguras e sem depender de uma corretora centralizada.

### Channel Jamming
Um ataque na Lightning Network onde alguém mal-intencionado ocupa a capacidade de um canal com HTLCs pendentes, bloqueando ele pra impedir outros pagamentos.  
**Exemplo:** Um atacante pode travar um canal importante, dificultando transações de outros usuários.

### Upfront Fees Hold
Taxas cobradas adiantado na Lightning Network pra desencorajar ataques como o channel jamming. O remetente paga uma taxa inicial que fica retida até o pagamento ser concluído ou falhar.  
**Exemplo:** Isso incentiva que os usuários sejam honestos, porque eles perdem a taxa se tentarem um ataque.

### Routing Node
Um nó na Lightning Network que encaminha pagamentos entre outros nós, usando HTLCs pra garantir que o dinheiro chegue ao destino.  
**Exemplo:** Esses nós cobram taxas de roteamento e precisam ter liquidez suficiente nos canais pra funcionar bem.

### Settlement HTLC
O processo de finalizar um HTLC na Lightning Network. Pode ser concluído (o receptor fornece o preimage e pega os fundos) ou expirar (os fundos voltam pro remetente).  
**Exemplo:** Quando um pagamento é finalizado, os saldos dos canais são atualizados.

### Happy Path (Caminho Feliz)
Um termo usado pra descrever o fluxo ideal de um processo, sem erros ou problemas. No Bitcoin, é quando tudo funciona como esperado.  
**Exemplo:** Na Lightning Network, um "happy path" é um pagamento via HTLC que é roteado direitinho, o receptor fornece o preimage, e os saldos dos canais são atualizados sem falhas. 
O oposto é o "unhappy path", como um HTLC expirando ou um ataque como channel jamming.

### Escrow
Um mecanismo de custódia no Bitcoin onde os fundos ficam bloqueados num contrato (como um HTLC) e só são liberados quando certas condições são cumpridas.  
**Exemplo:** O projeto [Satoshi Escrow](https://devpost.com/software/satoshi-escrow) usa isso pra trocas seguras.

### Signet
Uma rede de teste personalizável pro Bitcoin, diferente da testnet3. É feita pra desenvolvedores testarem mudanças no protocolo num ambiente controlado, com blocos assinados por uma entidade confiável.  
**Exemplo:** Útil pra testar novas funcionalidades do Bitcoin sem arriscar dinheiro real.

### Blockstorms
Na testnet3, é quando blocos são minerados quase ao mesmo tempo, causando divisões temporárias (forks) na cadeia.  
**Exemplo:** Isso acontece por causa da baixa dificuldade e alta variabilidade nas redes de teste.

### Timework
Acho que foi um erro de digitação pra "timelock". No Bitcoin, "timelock" é um mecanismo que bloqueia fundos até um tempo ou altura de bloco específico.  
**Exemplo:** É essencial em HTLCs pra garantir que o pagamento tenha um prazo pra ser concluído.

### PSBT Transactions (Partially Signed Bitcoin Transactions)
Transações parcialmente assinadas, definidas no BIP-174. Permitem que várias partes colaborem pra assinar uma transação Bitcoin antes de finalizá-la.  
**Exemplo:** Muito usado em carteiras de hardware e cenários de autocustódia.

### ZeroMQ (libzmq)
Uma biblioteca usada pra criar uma interface de notificação no Bitcoin Core. Permite que apps externas recebam notificações sobre eventos, como novos blocos ou transações.  
**Exemplo:** Um desenvolvedor pode usar ZeroMQ pra monitorar transações em tempo real.

### Libre Relay
Um software ou iniciativa de código aberto pra retransmitir transações Bitcoin entre os nós da rede, sem depender de servidores centralizados.  
**Exemplo:** Ajuda a propagar transações pro mempool dos mineradores, com foco em privacidade e resistência à censura.

---

## Considerações Finais
Esse glossário foi feito com base no que ouvi no podcast da Vinteum.org, e as explicações são o meu entendimento dos termos. Se você tiver dúvidas ou quiser adicionar mais palavras, é só falar! 😄

Feito com gosto por Dannilobr🐼  pra comunidade Bitcoin de 🔺 BH e região. 🚀 🇧🇷

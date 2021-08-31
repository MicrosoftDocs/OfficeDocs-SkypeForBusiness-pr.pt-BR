---
title: Painel de Saúde para Roteamento Direto
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como usar o Painel de Saúde para monitorar a conexão entre o Controlador de Borda de Sessão e o Roteamento Direto.
ms.openlocfilehash: 4927f6473e74a6fc14add9105022fc8efbade260
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728210"
---
# <a name="health-dashboard-for-direct-routing"></a>Painel de Saúde para Roteamento Direto

O Painel de Saúde para Roteamento Direto permite monitorar a conexão entre o Controlador de Borda de Sessão (SBC) e a interface de Roteamento Direto.  Com o Painel de Saúde, você pode monitorar informações sobre seu SBC, o serviço de telefonia e os parâmetros de rede entre seu SBC e a interface de Roteamento Direto. Essas informações podem ajudá-lo a identificar problemas, incluindo o motivo das chamadas não a atender. Por exemplo, o SBC pode parar de enviar chamadas se um certificado no SBC tiver expirado ou se houver problemas de rede. Consulte as [funções de administrador](using-admin-roles.md) para saber quem tem acesso ao painel de saúde.

O Painel de Saúde monitora dois níveis de informações:

- Saúde geral dos SBCs conectados
- Informações detalhadas sobre os SBCs conectados

Você pode exibir o Painel de Saúde no Microsoft Teams e Skype for Business Admin Center.

## <a name="overall-health"></a>Saúde geral

O Painel de Saúde fornece as seguintes informações relacionadas à saúde geral dos SBCs conectados:

 ![Mostra estatísticas do Painel de Saúde.](media/direct-routing-dashboard-stats1.png)

- **Resumo de Roteamento** Direto - Mostra o número total de SBCs registrados no sistema. O registro significa que o administrador do locatário adicionou um SBC usando o comando New-CsOnlinePSTNGateway de locatário. Se o SBC foi adicionado ao PowerShell, mas nunca conectado, o Painel de Saúde o mostrará em um status não acessível.

- **SBC** - O FQDN do SBC emparelhado.

- Taxa de Eficácia de Rede **(NER)** - O NER mede a capacidade de uma rede de fornecer chamadas medindo o número de chamadas enviadas versus o número de chamadas entregues a um destinatário.  

   O NER mede a capacidade das redes de fornecer chamadas para o terminal de extremidade distante, excluindo ações do usuário resultando em rejeições de chamadas.  Se o destinatário rejeitou uma chamada ou enviou a chamada para a caixa postal, a chamada é contada como uma entrega bem-sucedida. Isso significa que uma mensagem de resposta, um sinal de ocupado ou um toque sem resposta são chamadas consideradas bem-sucedidas.
  
   Por exemplo, suponha que Roteamento Direto enviou uma chamada para o SBC e o SBC retorna o código SIP "Tempo limite do servidor 504 - O servidor tentou acessar outro servidor na tentativa de processar a solicitação e não recebeu uma resposta de prompt". Essa resposta indica que há um problema no lado SBC, e isso diminuirá o NER no Painel de Saúde para este SBC.
  
   Como a ação que você toma pode depender do número de chamadas afetadas, o Painel de Saúde mostra quantas chamadas foram analisadas para calcular um parâmetro. Se o número de chamadas for menor que 100, o NER poderá ser bastante baixo, mas ainda assim ser normal.

   A fórmula usada para calcular o NER é:

   NER = 100 x (Chamadas atendidas + User Busy + Ring no Answer + Terminal Reject Seizures)/Total de chamadas

- **Duração média da** chamada - Informações sobre a duração média da chamada podem ajudá-lo a monitorar a qualidade das chamadas. A duração média de uma chamada PSTN de 1:1 é de quatro a cinco minutos.  No entanto, para cada empresa, essa média pode ser diferente.  A Microsoft recomenda estabelecer uma linha de base para a duração média da chamada para sua empresa. Se esse parâmetro ficar significativamente abaixo da linha de base, ele pode indicar que seus usuários estão com problemas de qualidade ou confiabilidade de chamada e estão desligando antes do normal. Se você começar a ver duração de chamada média extremamente baixa, por exemplo, 15 segundos, os chamadores podem estar desligando porque seu serviço não está executando de forma confiável.

   Como a ação que você toma pode depender do número de chamadas afetadas, o Painel de Saúde mostra quantas chamadas foram analisadas para calcular um parâmetro.

- **Status de conectividade TLS** - A conectividade TLS (Transport Layer Security) mostra o status das conexões TLS entre o Roteamento Direto e o SBC. O Painel de Saúde também analisa a data de expiração do certificado e avisa se um certificado está definido para expirar dentro de 30 dias para que os administradores possam renovar o certificado antes que o serviço seja interrompido.

   Ao clicar na mensagem Aviso, você pode ver uma descrição detalhada do problema em uma janela pop-up à direita e recomendações sobre como corrigir o problema.

- **Status das opções SIP** – Por padrão, o SBC envia mensagens de opções a cada minuto. Essa configuração pode variar para diferentes fornecedores SBC. O Roteamento Direto avisa se as opções SIP não são enviadas ou não estão configuradas. Para obter mais informações sobre monitoramento de opções SIP e condições em que um SBC pode ser marcado como não funcional, consulte [Monitor and troubleshoot Direct Routing](direct-routing-monitor-and-troubleshoot.md).

- **Status de opções SIP detalhados** - Além de mostrar que há um problema com o fluxo de opções SIP, o Painel de Saúde também fornece descrições detalhadas dos erros. Você pode acessar a descrição clicando na mensagem "Aviso". Uma janela pop-up à direita mostrará a descrição detalhada do erro.

   Os valores possíveis para mensagens de status de opções SIP são os seguinte:

    - Ativo – O SBC está ativo-- o serviço de Roteamento Direto da Microsoft vê as opções fluindo em um intervalo regular.

    - Aviso, sem opções SIP - O Controlador de Borda de Sessão existe no banco de dados (seu administrador o criou usando o comando New-CsOnlinePSTNGateway). Ele é configurado para enviar opções SIP, mas o serviço de Roteamento Direto nunca viu as opções SIP voltando desse SBC.

    - Aviso: As mensagens SIP não estão configuradas - O monitoramento de tronco usando opções SIP não está ligado. O Sistema de Chamada da Microsoft usa opções SIP e monitoramento de handshake TLS (Transport Layer Security) para detectar a saúde dos Controladores de Borda de Sessão (SBCs) conectados no nível do aplicativo. Você terá problemas se esse tronco puder ser atingido no nível da rede (por ping), mas o certificado expirou ou a pilha SIP não funcionará. Para ajudar a identificar esses problemas mais cedo, a Microsoft recomenda habilenciar o envio de opções SIP. Verifique a documentação do fabricante SBC para configurar o envio de opções SIP.

- **Capacidade de** chamadas simultâneas - Você pode especificar o limite de chamadas simultâneas que um SBC pode manipular usando o comando New ou Set-CsOnlinePSTNGateway com o parâmetro -MaxConcurrentSessions. Este parâmetro calcula quantas chamadas foram enviadas ou recebidas pelo Roteamento Direto usando um SBC específico e compara-as com o conjunto de limites. Observação: se o SBC também tratar chamadas para PBXs diferentes, esse número não mostrará as chamadas simultâneas reais.

## <a name="detailed-information-for-each-sbc"></a>Informações detalhadas para cada SBC

Você também pode exibir as informações detalhadas de um SBC específico, conforme mostrado na captura de tela a seguir:

![Detalhes do SBC do painel de saúde.](media/direct-routing-dashboard-SBC-detail1.png)

A exibição detalhada mostra os seguintes parâmetros adicionais:

- **Status de conectividade TLS** – essa é a mesma métrica da página "Saúde Geral";

- **Último status de conectividade TLS** – mostra a hora em que o SBC fez uma conexão TLS com o serviço de Roteamento Direto;

- **Status das opções SIP** – a mesma métrica da página "Saúde Geral".

- **Opções SIP verificadas pela última** vez – hora em que as opções SIP foram recebidas da última vez.

- **Status SBC** – status geral do SBC, com base em todos os parâmetros monitorados.

- **Chamada simultânea**- mostra quantas chamadas simultâneas o SBC lidou. Essas informações são úteis para prever o número de canais simultâneos necessários e ver a tendência. Você pode deslizar os dados por número de dias e direção de chamada (fluxos de entrada/saída/Todos).

- **Parâmetros de rede** - Todos os parâmetros de rede são medidos da interface roteamento direto para o Controlador de Borda de Sessão. Para obter informações sobre os valores recomendados, consulte Prepare your [organization's network for Microsoft Teams](./prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.

   - Tremido – É a medida milissegunda de variação no tempo de atraso de propagação da rede calculada entre dois pontos de extremidade usando RTCP (O Protocolo de Controle RTP).

   - Perda de pacotes – é uma medida de pacote que falhou ao chegar; ele é calculado entre dois pontos de extremidade.

   - Latência - (Também conhecido como tempo de viagem de ida e volta) é o tempo necessário para que um sinal seja enviado mais o tempo necessário para o reconhecimento desse sinal ser recebido. Esse atraso de tempo consiste nos tempos de propagação entre os dois pontos de um sinal.

   Você pode deslizar os dados por número de dias e direção de chamada (fluxos de entrada/saída/Todos).

**Taxa de eficácia da rede** - Esse é o mesmo parâmetro que aparece no painel Saúde Geral, mas com a opção de fatiar os dados por séries de tempo ou direção de chamada.
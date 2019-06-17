---
title: Painel de integridade para roteamento direto
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Saiba como usar o painel de integridade para monitorar a conexão entre o controlador de borda de sessão e o roteamento direto.
ms.openlocfilehash: 352b23f320a4e2adaa9819952a6e489791294630
ms.sourcegitcommit: 1a768e470a9509139eeb24034def12630acb7914
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2019
ms.locfileid: "34920264"
---
# <a name="health-dashboard-for-direct-routing"></a>Painel de integridade para roteamento direto

O painel de integridade para roteamento direto permite monitorar a conexão entre o controlador de borda de sessão (SBC) e a interface de roteamento direto.  Com o painel de integridade, você pode monitorar informações sobre seu SBC, o serviço de telefonia e os parâmetros de rede entre seu SBC e a interface de roteamento direto. Essas informações podem ajudá-lo a identificar problemas, incluindo o motivo para as chamadas descartadas. Por exemplo, o SBC pode parar de enviar chamadas se um certificado no SBC tiver expirado ou se houver problemas de rede.  

O painel de integridade monitora dois níveis de informações:

- Integridade geral do SBCs conectado
- Informações detalhadas sobre o SBCs conectado

Você pode exibir o painel de integridade no centro de administração do Microsoft Teams e do Skype for Business.


## <a name="overall-health"></a>Integridade geral

O painel de integridade fornece as seguintes informações relacionadas à integridade geral do SBCs conectado:

 ![Mostra as estatísticas do painel de integridade](media/direct-routing-dashboard-stats1.png)

- **Resumo de roteamento direto** -mostra o número total de SBCS registrados no sistema. Registro significa que o administrador do locatário adicionou um SBC usando o comando New-CsOnlinePSTNGateway. Se o SBC foi adicionado no PowerShell, mas nunca conectado, o painel de integridade mostra o status de integridade.

- **SBC** – o FQDN do SBC emparelhado.

- **Taxa de eficácia da rede (Ner)** – o Ner mede a capacidade de uma rede de entregar chamadas, medindo o número de chamadas enviadas versus o número de chamadas entregues a um destinatário.  

   O NER mede a capacidade das redes de entregar chamadas para o terminal distante--excluindo ações do usuário que resultam em rejeições de chamadas.  Se o destinatário rejeitou uma chamada ou enviou a chamada para o correio de voz, a chamada será contada como uma entrega bem-sucedida. Isso significa que uma mensagem de resposta, um sinal de ocupado ou um toque sem resposta são considerados chamadas bem-sucedidas. 
  
   Por exemplo, suponha que o roteamento direto enviou uma chamada para o SBC e o SBC retorne o código SIP "504 tempo limite do servidor-o servidor tentou acessar outro servidor para tentar processar a solicitação e não recebeu uma resposta de prompt". Essa resposta indica que há um problema no lado do SBC, e isso diminuirá o NER no painel de integridade para este SBC. 
  
   Como a ação que você pode ter pode depender do número de chamadas afetadas, o painel de integridade mostra quantas chamadas foram analisadas para calcular um parâmetro. Se o número de chamadas for menor do que 100, o NER pode estar muito baixo, mas ainda é normal. 

   A fórmula usada para calcuate NER é:

   NER = chamadas atendidas + usuário ocupado + toque em nenhuma resposta + capturas de rejeição de terminal x 100

 
- **Duração média da chamada** -informações sobre a média da duração das chamadas podem ajudá-lo a monitorar a qualidade das chamadas. A duração média de uma chamada PSTN 1:1 é de quatro a cinco minutos.  No entanto, para cada empresa, essa média pode ser diferente.  A Microsoft recomenda estabelecer uma linha de base para a média da duração da chamada da sua empresa. Se esse parâmetro ficar significativamente abaixo da linha de base, isso pode indicar que os usuários estão com problemas com a qualidade da chamada ou a confiabilidade e estão desligados antes do normal. Se você começar a ver a duração média de chamadas médias médias, por exemplo, 15 segundos, os chamadores podem estar sendo soltos porque o seu serviço não está funcionando de maneira confiável. 

   Como a ação que você pode ter pode depender do número de chamadas afetadas, o painel de integridade mostra quantas chamadas foram analisadas para calcular um parâmetro.

- **Status da conectividade TLS** – a conectividade do TLS (Transport Layer Security) mostra o status das conexões TLS entre roteamento direto e SBC. O painel de integridade também analisa a data de expiração do certificado e avisa se um certificado está configurado para expirar dentro de 30 dias para que os administradores possam renovar o certificado antes que o serviço seja interrompido.

   Ao clicar na mensagem de aviso, você pode ver uma descrição detalhada do problema em uma janela pop-up à direita e recomendações sobre como corrigir o problema.

- **Status das opções SIP** – por padrão, o SBC envia as mensagens de opções a cada minuto. Essa configuração pode variar para fornecedores de SBC diferentes. O roteamento direto avisa se as opções de SIP não são enviadas ou não são configuradas. Para obter mais informações sobre monitoramento de opções SIP e condições quando um SBC pode ser marcado como não funcional, consulte [monitorar e solucionar problemas de roteamento direto](direct-routing-monitor-and-troubleshoot.md).

- **Status de opções do SIP detalhadas** -além de mostrar que há um problema com o fluxo de opções do SIP, o painel de integridade também fornece descrições detalhadas dos erros. Você pode acessar a descrição clicando na mensagem "aviso". Uma janela pop-up à direita mostrará a descrição detalhada do erro.

   Os valores possíveis para mensagens de status de opções SIP são os seguintes:

    - Ativo – o SBC está ativo--o serviço de roteamento direto da Microsoft vê as opções que fluem em um intervalo regular.

    - Aviso: nenhuma opção SIP-o controlador de borda da sessão existe no banco de dados (seu administrador o criou usando o comando New-CsOnlinePSTNGateway). Ele está configurado para enviar opções de SIP, mas o serviço de roteamento direto nunca viu as opções de SIP que chegam deste SBC.

    - Aviso: as mensagens SIP não são configuradas – o monitoramento de tronco usando as opções do SIP não está ativado. O sistema de chamadas da Microsoft usa opções SIP e monitoramento de handshake de Transport Layer Security (TLS) para detectar a integridade dos controladores de borda de sessão conectados (SBCs) no nível do aplicativo. Você terá problemas se esse tronco puder ser alcançado no nível da rede (por ping), mas o certificado expirou ou a pilha SIP não funciona. Para ajudar a identificar esses problemas com antecedência, a Microsoft recomenda habilitar as opções de envio de SIP. Verifique a documentação do fabricante do SBC para configurar o envio de opções SIP. 

- **Capacidade de chamadas simultâneas** – você pode especificar o limite de chamadas simultâneas que um SBC pode manipular usando o comando New-ou Set-CsOnlinePSTNGateway com o parâmetro-MaxConcurrentSessions. Esse parâmetro calcula quantas chamadas foram enviadas ou recebidas pelo roteamento direto usando um SBC específico e a compara com o limite definido. Observação: se o SBC também manipular chamadas para PBXs diferentes, esse número não mostrará as chamadas simultâneas reais.


## <a name="detailed-information-for-each-sbc"></a>Informações detalhadas para cada SBC

Você também pode exibir as informações detalhadas de um SBC específico, conforme mostrado na captura de tela a seguir:

![Detalhes de SBC do painel de integridade](media/direct-routing-dashboard-SBC-detail1.png)


O modo de exibição detalhado mostra os seguintes parâmetros adicionais:

- **Status de conectividade de TLS** – é a mesma métrica que na página "integridade geral";

- **Conectividade TLS último status** – mostra a hora em que o SBC fez uma conexão TLS para o serviço de roteamento direto;

- **Status das opções SIP** – a mesma métrica da página "integridade geral".

- **Opções de SIP última verificação** – hora em que as opções de SIP foram recebidas na última vez.

- **Status do SBC** – status geral do SBC com base em todos os parâmetros monitorados.

- **Chamada simultânea**-mostra quantas chamadas simultâneas o SBC tratouu. Essas informações são úteis para prever o número de canais simultâneos que você precisa e veja a tendência. Você pode deslizar os dados por número de dias e direção de chamada (entrada/saída/todos os fluxos).

- **Parâmetros de rede** – todos os parâmetros de rede são medidos da interface de roteamento direto para o controlador de borda de sessão. Para obter informações sobre os valores recomendados, consulte [preparar a rede da sua organização para o Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/prepare-network)e verificar os valores recomendados de borda do cliente para o Microsoft Edge.

   - Tremulação – é a medida de milissegundos da variação no tempo de atraso de propagação de rede calculado entre dois pontos de extremidade usando RTCP (o protocolo de controle RTP).

   - Perda de pacotes – é uma medida do pacote que falhou ao chegar; Ele é calculado entre dois pontos de extremidade.

   - Latancy-(também conhecido como tempo de viagem de ida e volta) é o período de tempo que leva para o envio de um sinal mais o tempo necessário para que a confirmação daquele sinal seja recebida. Esse atraso de tempo consiste nos tempos de propagação entre os dois pontos de um sinal.

   Você pode deslizar os dados por número de dias e direção de chamada (entrada/saída/todos os fluxos).

**Taxa de eficácia da rede** -é o mesmo parâmetro que aparece no painel de integridade geral, mas com a opção de dividir os dados por série temporal ou direção de chamada.





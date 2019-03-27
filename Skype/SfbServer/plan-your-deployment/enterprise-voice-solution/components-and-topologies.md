---
title: Componentes e topologias para chamar o controle de admissão no Skype para negócios
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planejamento do CAC (controle de admissão de chamadas) se você tiver uma rede MPLS, um tronco SIP ou um gateway PSTN de terceiros ou PBX. Aplica-se à Skype para o Business Server Enterprise Voice.
ms.openlocfilehash: 7022ade98dbd614023a4faaea283b939fa658e73
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872835"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a>Componentes e topologias para chamar o controle de admissão no Skype para negócios

Planejamento do CAC (controle de admissão de chamadas) se você tiver uma rede MPLS, um tronco SIP ou um gateway PSTN de terceiros ou PBX. Aplica-se à Skype para o Business Server Enterprise Voice.

Os tópicos desta seção oferecem informações sobre considerações especiais para implantar o serviço de controle de admissão de chamadas (CAC) em vários tipos de topologias de rede.

## <a name="call-admission-control-on-an-mpls-network"></a>Controle de admissão de chamadas em uma rede MPLS

Em uma rede de Comutação de Rótulo Multiprotocolo (MPLS), todos os sites são conectados por uma malha completa. Isto é, todos os sites são conectados diretamente à nuvem MPLS, e cada site é provisionado com a largura de banda a ser usada em um link WAN para a nuvem MPLS. Não existe hub de rede nem local central para controlar o roteamento IP. A figura abaixo mostra uma rede simples baseada na tecnologia MPLS.

**Exemplo de rede MPLS**

![CAC com MPLS](../../media/CAC_MPLS_1.jpg)

Para implantar um controle de admissão de chamada (CAC) em uma rede MPLS, é preciso criar uma região de rede para representar a nuvem MPLS, bem como criar um site de rede para representar cada site de satélite MPLS. A figura a seguir ilustra como a região de rede e os sites de rede devem ser configurados para representar a rede MPLS de exemplo na figura anterior. Os limites gerais da largura de banda e os limites de sessão da largura de banda têm base na capacidade do link WAN a partir de cada site de rede até a região de rede que representa a nuvem MPLS.

**Região de rede e sites de rede para uma rede MPLS**

![Controle de admissão de chamadas (CAC) com diagrama MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a>Controle de admissão de chamada em um tronco SIP

Para implantar o controle de admissão de chamadas em um tronco SIP, crie um local de rede para representar o ITSP (provedor de serviço de telefonia da Internet). Para aplicar valores de política de largura de banda no tronco SIP, crie uma política entre locais entre o local de rede na sua empresa e o local de rede criado para representar o ITSP.

A figura a seguir mostra um exemplo de implantação do CAC em um tronco SIP.

**Configuração do CAC em um tronco SIP**

![Diagrama do tronco de SIP do controle de admissão de chamada](../../media/CAC_SIP_trunk_1.jpg)

Para configurar o CAC em um tronco SIP, você terá que executar as seguintes tarefas durante a implantação do CAC:

1. Crie um site de rede para representar o ITSP. Associe o site de rede a uma região de rede apropriada e aloque a largura de banda de zero para áudio e vídeo para este site de rede. Para obter detalhes, consulte [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) na documentação de implantação.

    > [!NOTE]
    > Para o ITSP, essa configuração de site de rede não funciona. Os valores da política de largura de banda são, na verdade, aplicados na etapa 2.

2. Crie um link entre sites para o tronco SIP usando os valores de parâmetro relevantes para o site criado na etapa 1. Por exemplo, use o nome do site de rede na sua empresa como o valor do parâmetro NetworkSiteID1 e o site de rede ITSP como o valor do parâmetro NetworkSiteID2. Para obter detalhes, consulte [criar políticas de entre sites de rede no Skype para Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) na documentação de implantação e [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).

3. Obter o endereço IP da Session Border Controller (SCB) ponto de terminação de mídia do seu ITSP. Adicione o endereço IP com uma máscara de sub-rede de 32 para o site de rede que representa o ITSP. Para obter detalhes, consulte  [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a>Controle de admissão de chamada com um gateway PSTN ou PBX de terceiros

Este tópico descreve exemplos de como o controle de admissão de chamadas (CAC) pode ser implantado no link entre a interface de gateway do servidor de mediação e um gateway PSTN (rede) telefônica comutada pública de terceiros ou privada Central de comutação telefônica (PBX).

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>Caso 1: CAC entre o Servidor de Mediação e um gateway PSTN

CAC pode ser implantado em WAN link da interface de gateway do servidor de mediação para um gateway de PBX ou PSTN de terceiros.

**Caso 1: CAC entre o Servidor de Mediação e um gateway PSTN**

![Caso 1: CAC entre o Gateway PSTN do servidor de mediação](../../media/CAC_gateways_1.jpg)

Neste exemplo, o CAC é aplicado entre o servidor de mediação e um gateway PSTN. Se um Skype para o usuário de negócios do cliente no Site de rede 1 faz uma chamada PSTN por meio do gateway PSTN no Site de rede 2, a mídia flui através do link WAN. Portanto, duas verificações CAC são executadas para cada sessão PSTN:

- Entre o Skype para o aplicativo cliente de negócios e o servidor de mediação

- Entre o servidor de mediação e o gateway PSTN

Isto funciona para as chamadas PSTN de entrada para um cliente no Local de Rede 1 e para chamadas PSTN de saída provenientes de um aplicativo cliente no Local de Rede 1.

> [!NOTE]
> Certifique-se de que a sub-rede do IP ao qual o gateway PSTN pertence está configurada e associada ao Local de Rede 2.

> [!NOTE]
> Certifique-se de que a sub-rede do IP que ambas as interfaces do servidor de mediação pertencem está configurada e associada ao local de rede 1.

> [!NOTE]
> Para obter detalhes, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>Caso 2: CAC entre o servidor de mediação e um PBX de terceiros com ponto de terminação de mídia

Esta configuração é similar ao Caso 1. Em ambos os casos, o servidor de mediação sabe qual dispositivo finaliza a mídia no final oposto do link de WAN e o endereço IP do gateway PSTN ou PBX com o ponto de terminação de mídia (MTP) está configurado no servidor de mediação como o próximo salto.

**Caso 2: CAC entre o Servidor de Mediação e um PBX de terceiros com MTP**

![Caso 2: CAC entre o PBX do servidor de mediação com MTP](../../media/CAC_gateways_2.jpg)

Neste exemplo, o CAC é aplicado entre o servidor de mediação e o PBX/MTP. Se um Skype para o usuário de cliente empresarial no Site de rede 1 faz uma chamada PSTN por meio do PBX/MTP localizado no Site de rede 2, a mídia flui através do link WAN. Portanto, para cada sessão PSTN duas verificações CAC são executadas:

- Entre o Skype para o aplicativo cliente de negócios e o servidor de mediação

- Entre o servidor de mediação e o PBX/MTP

Isto funciona para ambas, chamadas PSTN de entrada para um cliente no Local de Rede 1 e chamadas PSTN de saída provenientes de um cliente no Local de Rede 1.

> [!NOTE]
> Certifique-se de que a sub-rede do IP à qual o MTP pertence está configurada e associada ao Local de Rede 2.

> [!NOTE]
> Certifique-se de que a sub-rede do IP que ambas as interfaces do servidor de mediação pertencem está configurada e associada ao local de rede 1.

> [!NOTE]
> Para obter detalhes, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>Caso 3: CAC entre o servidor de mediação e um PBX de terceiros sem um ponto de terminação de mídia

O Caso 3 é um ligeiramente diferente dos dois primeiros. Se não houver nenhuma MTP ao PBX de terceiros, para uma sessão de saída a solicitação para o PBX de terceiros o servidor de mediação não sabe qual mídia será terminada em que o limite de PBX. Nesse caso, a mídia flui diretamente entre o servidor de mediação e o dispositivo de ponto de extremidade de terceiros.

**Caso 3: CAC entre o Servidor de Mediação e um PBX de terceiros sem MTP**

![Caso 3: CAC entre o PBX do servidor de mediação sem MTP](../../media/CAC_gateways_3.jpg)

Neste exemplo, se um Skype para o usuário de negócios do cliente no Site de rede 1 faz uma chamada para um usuário através do PBX, o servidor de mediação é capaz de realizar as verificações CAC apenas nos trecho proxy entre (Skype para o aplicativo cliente de negócios) e o servidor de mediação. Como o servidor de mediação não têm informações sobre o dispositivo de ponto de extremidade enquanto a sessão é solicitada, verificações CAC não podem ser executadas na WAN link (entre o servidor de mediação e o ponto de extremidade de terceiros) antes do estabelecimento da chamada. No entanto, depois que a sessão for estabelecida, o servidor de mediação facilita na contabilidade para a largura de banda usada no tronco.

Para chamadas originadas do ponto de extremidade de terceiros, as informações sobre esse dispositivo de ponto de extremidade estão disponíveis no momento da solicitação de sessão e seleção CAC pode ser executada em ambos os lados do servidor de mediação.

> [!NOTE]
> Certifique-se de que a sub-rede do IP à qual os dispositivos de ponto de extremidade pertencem está configurada e associada ao Local de Rede 2.

> [!NOTE]
> Certifique-se de que a sub-rede do IP que ambas as interfaces do servidor de mediação pertencem está configurada e associada ao local de rede 1.

> [!NOTE]
> Para obter detalhes, consulte [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).



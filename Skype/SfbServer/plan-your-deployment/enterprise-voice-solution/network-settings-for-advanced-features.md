---
title: Configurações de rede para os recursos de Enterprise Voice avançados no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Saiba mais sobre regiões de rede, sites de rede e sub-redes IP. Todos eles devem ser configurados para implantar Plan for media bypass em Skype for Business, Plan for call admission control in Skype for Business Server) ou Plan for emergency services in Skype for Business Server in Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 50e076cd4be0e0c98b6319a7d0b4ce1a848689cd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861088"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server"></a>Configurações de rede para os recursos de Enterprise Voice avançados no Skype for Business Server

Saiba mais sobre regiões de rede, sites de rede e sub-redes IP. Todos eles devem ser configurados para implantar o [Plan for media bypass no Skype for Business](media-bypass.md), Planejar o controle de admissão de chamada no [Skype for Business Server](call-admission-control.md)ou Planejar serviços de emergência no [Skype for Business Server](emergency-services.md) em Skype for Business Server Enterprise Voice.

Skype for Business Server tem três recursos avançados de Enterprise Voice: Planejar o controle de admissão de chamada no [Skype for Business Server,](call-admission-control.md)Planejar serviços de emergência no [Skype for Business Server](emergency-services.md)e Planejar mídia [ bypass em Skype for Business](media-bypass.md). Esses recursos compartilham determinados requisitos de configuração para regiões de rede, sites de rede e associação de cada sub-rede na topologia Skype for Business Server com um site de rede.

Este tópico fornece uma visão geral dos requisitos de configuração que são comuns a todos os três desses recursos Enterprise Voice avançados.

## <a name="network-regions"></a>Regiões de Rede

Uma região de rede é um hub de rede ou backbone de rede usada somente na configuração do serviço de controle de admissão de chamadas (CAC),  E9-1-1 e bypass de mídia.

> [!NOTE]
> As regiões de rede não são as mesmas Skype for Business Server de conferência discada, que são necessárias para associar números de acesso de conferência discada a um ou mais planos de discagem Skype for Business Server discagem. Para obter detalhes sobre regiões de conferência discadas, consulte [Planning for Dial-In Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-dial-in-conferencing-requirements).

Skype for Business Server O CAC exige que todas as regiões de rede tenham um site central associado, que gerencie o tráfego de mídia dentro da região (ou seja, toma decisões com base nas políticas que você configurou, em relação a se uma sessão de áudio ou vídeo em tempo real pode ou não ser estabelecida). Skype for Business Server locais centrais não representam locais geográficos, mas sim grupos lógicos de servidores configurados como um pool ou um conjunto de pools.

Para configurar uma região de rede, você  pode usar a guia Regiões na seção Configuração de Rede do Painel de Controle Skype for Business Server ou executar os cmdlets **New-CsNetworkRegion** ou **Set-CsNetworkRegion** Skype for Business Server Management Shell.  Para obter instruções, consulte [Deploy network regions, sites and subnets in Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) in the Deployment documentation, or refer to the Skype for Business Server Management Shell documentation.

As mesmas definições de região de rede são compartilhadas por todos os três recursos Enterprise Voice avançados. Se você já criou áreas de rede para um recurso, não será necessário criar novas regiões de rede para outros recursos. No entanto, pode ser necessário modificar uma definição de região de rede existente para aplicar as configurações específicas do recurso. Por exemplo, se você criou áreas de rede para E9-1-1 (que não requer um site central associado) e posteriormente implantou o serviço de controle de admissão de chamadas, é necessário modificar cada uma das definições de região de rede para especificar um site central.

Para associar um site central Skype for Business Server a uma região de rede, especifique o nome do site central, usando a seção Configuração de Rede do Painel de Controle do Skype for Business Server ou executando os cmdlets **New-CsNetworkRegion** ou **Set-CsNetworkRegion.**  Para obter instruções, consulte [Deploy network regions, sites and subnets in Skype for Business](../../deploy/deploy-enterprise-voice/deploy-network.md) in the Deployment documentation, or refer to the Skype for Business Server Management Shell documentation.

## <a name="network-sites"></a>Sites de Rede

Um site de rede representa uma localização geográfica, como um escritório principal, filiais ou regionais. Cada site de rede deve ser associado a uma região específica de rede.

> [!NOTE]
> Os sites de rede são usados apenas pelos recursos Enterprise Voice avançados. Eles não são os mesmos que os sites de filial que você configura em sua topologia Skype for Business Server de dados.

Para configurar um site de rede e associá-lo a uma região de rede, você pode usar a seção Configuração de Rede do Painel de Controle do Skype for Business Server ou executar os cmdlets do Shell de Gerenciamento do Skype for Business Server **New-CsNetworkSite** ou **Set-CsNetworkSite.**  Para obter detalhes, [consulte Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site) na documentação de Implantação ou consulte a documentação Skype for Business Server Shell de Gerenciamento.

## <a name="identify-ip-subnets"></a>Identificar Subredes IP

Para cada site de rede, você precisará trabalhar com seu administrador de rede para determinar quais subredes IP são atribuídas a cada site de rede. Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho fica muito mais simples.

No exemplo, o site de Nova York na região da América do Norte pode ser atribuído às seguintes sub-redes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suponha que Bob, que geralmente trabalha em Detroit, viaja para o escritório de Nova York para treinamento. Quando ele liga o computador e se conecta à rede, seu computador terá um endereço IP em um dos quatro intervalos alocados para Nova York, por exemplo 172.29.80.103.

> [!CAUTION]
> As subredes IP especificadas durante a configuração de rede no servidor devem corresponder ao formato oferecido por computadores clientes para poder ser usado adequadamente pelo bypass de mídia. Um Skype for Business cliente pega seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada. Ao determinar o ID de bypass associado com cada cliente, o Registrador irá comprar a lista de subredes IP associadas com cada local de rede na subrede oferecida pelo cliente para uma correspondência exata. Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais. (Se você implantar o controle de admissão de chamada, mas não o bypass de mídia, o controle de admissão de chamada funcionará corretamente, mesmo se você configurar sub-redes virtuais.) Por exemplo, se um cliente Skype for Business entrar em um computador com um endereço IP 172.29.81.57 com uma máscara de sub-rede IP de 255.255.255.0, ele solicitará a ID de bypass associada à sub-rede 172.29.81.0. Se a subrede é definida como 172.29.0.0/16, embora o cliente pertença à subrede virtual, o Registrador não irá considerar uma correspondência porque ele está procurando especificamente pela subrede 172.29.81.0. Portanto, é importante que o administrador insira sub-redes exatamente como fornecida pelos clientes Skype for Business (que são provisionadas com sub-redes durante a configuração de rede, de forma estática ou por DHCP (Dynamic Host Configuration Protocol).)

## <a name="associating-subnets-with-network-sites"></a>Associando Subredes aos Locais de Rede

Cada subrede na rede corporativa deve ser associado um site de rede (ou seja, cada sub-rede deve ser associado a uma localização geográfica). Essa associação de sub-redes permite que os recursos de Enterprise Voice avançados localizem geograficamente os pontos de extremidade. Por exemplo, localizar os pontos de extremidade permite que CAC regule o fluxo de áudio e dados de vídeo em tempo real indo e voltando do local de rede.

Para associar sub-redes a sites de  rede, você pode usar a seção Configuração de Rede do Painel de Controle Skype for Business Server ou pode usar o Shell de Gerenciamento Skype for Business Server. Para obter instruções, [consulte Associar uma sub-rede a um site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site) de rede na documentação de Implantação ou consulte a documentação do Shell de Gerenciamento Skype for Business Server Gerenciamento.

## <a name="see-also"></a>Confira também

[Planejar o controle de admissão de chamada Skype for Business Server](call-admission-control.md)

[Planejar serviços de emergência no Skype for Business Server](emergency-services.md)

[Planejar o bypass de mídia Skype for Business](media-bypass.md)
---
title: Configurações de rede para recursos avançados do Enterprise Voice no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
description: Aprender sobre regiões de rede, sites de rede e sub-redes IP. Todos eles devem ser configurados para implantar o plano de bypass de mídia no Skype para negócios 2015, planeje o controle de admissão de chamada no Skype para Business Server 2015), ou plano para serviços de emergência no Skype para 2015 do servidor de negócios no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: e76c88df482dfd5e58d6c0e11449eb6f6242b796
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504093"
---
# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-skype-for-business-server-2015"></a>Configurações de rede para recursos avançados do Enterprise Voice no Skype for Business Server 2015
 
Aprender sobre regiões de rede, sites de rede e sub-redes IP. Todos esses devem ser configurados para implantar o [plano para a mídia ignorar no Skype para negócios 2015](media-bypass.md), [Planejar o controle de admissão de chamada no Skype para Business Server 2015](call-admission-control.md)), ou a [planejar os serviços de emergências no Skype para Business Server 2015](emergency-services.md) no Skype para Business Server Enterprise Voice.
  
Skype para Business Server tem três recursos avançados do Enterprise Voice: [Planejar o controle de admissão de chamada no Skype para Business Server 2015](call-admission-control.md)), [planejar os serviços de emergência Skype para Business Server 2015](emergency-services.md)e bypass [plano para a mídia no Skype para Negócios 2015](media-bypass.md). Esses recursos compartilham determinados requisitos de configuração de regiões de rede, sites de rede e associação de cada sub-rede no Skype para a topologia de servidor de negócios com um site de rede. 
  
Este tópico fornece uma visão geral dos requisitos de configuração que são comuns a todos os três desses recursos do Enterprise Voice avançados.
  
## <a name="network-regions"></a>Regiões de Rede

Uma região de rede é um hub de rede ou backbone de rede usada somente na configuração do serviço de controle de admissão de chamadas (CAC),  E9-1-1 e bypass de mídia.
  
> [!NOTE]
> Regiões de rede não são iguais Skype para regiões de conferência discada Business Server, que são necessárias para associar números de acesso de conferência discada um ou mais Skype para planos de discagem Business Server. Para obter detalhes sobre regiões de conferência discada, consulte [Planning for Dial-In Conferencing](http://technet.microsoft.com/library/9aff949e-3dac-481a-be46-a180c72e8066.aspx). 
  
CAC exige que cada região de rede tenha um Skype associado para o site central Business Server, que gerencia o tráfego de mídia com a região (ou seja, faz decisões com base em políticas que você configurou, relacionadas ou não um áudio em tempo real ou sessão de vídeo pode ser estabelecido). Skype para sites de central de Business Server não representam localizações geográficas, mas sim lógicos grupos de servidores que estão configurados como um pool ou um conjunto de pools. 
  
Para configurar uma região de rede, use a guia **regiões** na seção **Configuração de rede** do Skype para painel de controle do Business Server ou executar o **New-CsNetworkRegion** ou **Set-CsNetworkRegion** Skype para negócios Cmdlets do Shell de gerenciamento de servidor. Para obter instruções, consulte [Deploy regiões de rede, sites e sub-redes em Skype para negócios 2015](../../deploy/deploy-enterprise-voice/deploy-network.md) na documentação de implantação ou consulte o Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.
  
As mesmas definições de região de rede são compartilhadas por todos os três recursos avançados do Enterprise Voice. Se você já criou áreas de rede para um recurso, não será necessário criar novas regiões de rede para outros recursos. No entanto, pode ser necessário modificar uma definição de região de rede existente para aplicar as configurações específicas do recurso. Por exemplo, se você criou áreas de rede para E9-1-1 (que não requer um site central associado) e posteriormente implantou o serviço de controle de admissão de chamadas, é necessário modificar cada uma das definições de região de rede para especificar um site central.
  
Para associar um Skype para o site central de Business Server uma região de rede, especifique o nome do site central, usando-se a seção **Configuração de rede** do Skype para painel de controle do Business Server, ou executando o **New-CsNetworkRegion** ou os cmdlets **Set-CsNetworkRegion** . Para obter instruções, consulte [Deploy regiões de rede, sites e sub-redes em Skype para negócios 2015](../../deploy/deploy-enterprise-voice/deploy-network.md) na documentação de implantação ou consulte o Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.
  
## <a name="network-sites"></a>Sites de rede

Um site de rede representa uma localização geográfica, como um escritório principal, filiais ou regionais. Cada site de rede deve ser associado a uma região específica de rede.
  
> [!NOTE]
> Sites de rede são usadas somente pelos recursos avançados do Enterprise Voice. Eles não são os mesmos sites de filial que você configurar no seu Skype para a topologia de servidor de negócios. 
  
Para configurar um site de rede e associá-lo a uma região de rede, você pode usar a seção de **Configuração de rede** do Skype para painel de controle do Business Server, ou execute o Skype para Business Server Management Shell **New-CsNetworkSite** ou ** Set-CsNetworkSite** cmdlets. Para obter detalhes, consulte [Create or Modify um Site de rede](http://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx) na documentação de implantação ou consulte o Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.
  
## <a name="identify-ip-subnets"></a>Identifique as subredes IP

Para cada site de rede, você precisará trabalhar com seu administrador de rede para determinar quais subredes IP são atribuídas a cada site de rede. Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho fica muito mais simples.
  
No exemplo, o site de Nova York na região da América do Norte pode ser atribuído às seguintes sub-redes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suponha que Bob, que geralmente trabalha em Detroit, viaja para o escritório de Nova York para treinamento. Quando ele liga o computador e se conecta à rede, seu computador terá um endereço IP em um dos quatro intervalos alocados para Nova York, por exemplo 172.29.80.103.
  
> [!CAUTION]
> As subredes IP especificadas durante a configuração de rede no servidor devem corresponder ao formato oferecido por computadores clientes para poder ser usado adequadamente pelo bypass de mídia. Um Skype para o cliente de negócios leva seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada. Ao determinar o ID de bypass associado com cada cliente, o Registrador irá comparar a lista de subredes IP associadas com cada local de rede na subrede oferecida pelo cliente para uma correspondência exata. Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais. (Se implantar o controle de admissão de chamada, mas o bypass de mídia não, o controle de admissão de chamada funcionará corretamente, mesmo se você configurar o virtuais sub-redes.) Por exemplo, se um Skype para o cliente de negócios faz logon em um computador com um endereço IP de 172.29.81.57 com uma máscara de sub-rede do IP de 255.255.255.0, ele solicitará o ID de desvio que está associado à sub-rede 172.29.81.0. Se a sub-rede for definida como 172.29.0.0/16, embora o cliente pertença à sub-rede virtual, o Registrador Avançado não considerará isso uma correspondência porque ele está procurando especificamente pela sub-rede 172.29.81.0. Portanto, é importante que o administrador insere sub-redes exatamente como fornecidos pela Skype para clientes corporativos (que são provisionados com sub-redes durante a configuração de rede, estática ou pelo Dynamic Host Configuration Protocol (DHCP).) 
  
## <a name="associating-subnets-with-network-sites"></a>Associando Subredes aos Locais de Rede

Cada subrede na rede corporativa deve ser associado um site de rede (ou seja, cada sub-rede deve ser associada a uma localização geográfica). Essa associação de sub-redes habilita os recursos avançados do Enterprise Voice localizar os pontos de extremidade geograficamente. Por exemplo, localizar os pontos de extremidade permite que o CAC regule o fluxo de áudio e dados de vídeo em tempo real indo e voltando do local de rede.
  
Para associar sub-redes a sites de rede, você poderá usar a seção **Configuração de rede** do Skype para painel de controle do Business Server, ou você pode usar o Skype do Shell de gerenciamento do servidor de negócios. Para obter instruções, consulte [associar uma sub-rede a um Site de rede](http://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx) na documentação de implantação ou consulte o Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.
  
## <a name="see-also"></a>Consulte também

[Planejar o controle de admissão de chamada no Skype for Business Server 2015](call-admission-control.md)
  
[Planejamento de serviços de emergência no Skype para Business Server 2015](emergency-services.md)
  
[Planejar o bypass de mídia no Skype para negócios 2015](media-bypass.md)
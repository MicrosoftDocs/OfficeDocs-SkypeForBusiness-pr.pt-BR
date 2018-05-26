---
title: Adicionar colocações de servidor de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Para uma implantação do Enterprise Edition, A / o serviço de conferência V é colocado no pool Front-End. Você também pode colocar o servidor de mediação no pool de Front-End, ou você pode implantá-lo como um servidor autônomo. A / o serviço de conferência de V é sempre colocado se conferência estiver habilitada.
ms.openlocfilehash: 0bbe69bdddd0fd9317e33a8f3d5a90be089c4374
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2018
---
# <a name="add-front-end-server-collocations"></a>Adicionar colocações de servidor de Front-End
 
Para uma implantação do Enterprise Edition, A / o serviço de conferência V é colocado no pool Front-End. Você também pode colocar o servidor de mediação no pool de Front-End, ou você pode implantá-lo como um servidor autônomo. A / o serviço de conferência de V é sempre colocado se conferência estiver habilitada.
  
> [!NOTE]
> Um A / serviço V Conferencing é necessário se a **conferência** foi selecionado na página **Selecionar recursos** . Um pool de Front End do Enterprise Edition usa um colocado uma / serviço V Conferencing. Se não tiver sido conferência selecionada, o colocar uma / serviço V Conferencing não estará disponível.
  
Você pode colocar a função de servidor de mediação em um servidor Standard Edition Front End ou um pool de Front End do Enterprise Edition. Se você implantar conexões diretas SIP para um gateway PSTN (rede) qualificado telefônica comutada pública que suporta bypass de mídia e balanceamento de carga de sistema de nome de domínio (DNS), não é necessário um pool do servidor de mediação autônomo. Um pool de servidor de mediação autônomo não é necessário porque o gateways qualificados são capazes de DNS com carga balanceada para um pool de servidores de mediação e eles podem receber tráfego de qualquer servidor de mediação em um pool. Também recomendamos que você colocar o servidor de mediação em um pool de Front-End quando você tiver implantado o IP-PBXs ou se conectar a de um Internet Server provedor de telefonia borda controlador sessão (SBC), desde que qualquer uma das seguintes condições forem atendida:
  
- O IP-PBX ou SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear tráfego uniformemente para todos os servidores de mediação no pool.
    
- O IP-PBX ou SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear tráfego uniformemente para todos os servidores de mediação no pool.
    
Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se o pool de Front-End, onde você deseja colocar o servidor de mediação pode manipular a carga. Se seu ambiente não pode atender a esses requisitos, você deve implantar um pool do servidor de mediação autônomo.
  
Em geral, a colocação do servidor de mediação não é recomendável se sua organização tem requisitos de escalabilidade e alta disponibilidade. Para obter detalhes sobre colocando essas funções de servidor em um pool de Front-End em uma implantação do Enterprise Edition, consulte [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) na documentação de implantação. Para obter detalhes sobre A / recurso de conferência V e componentes, consulte [Planning for Conferencing](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) na documentação de planejamento. Para obter detalhes sobre os recursos do Enterprise Voice e componentes, incluindo o servidor de mediação, consulte [Plan for Enterprise Voice no Skype para Business Server 2015](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) na documentação de planejamento.
  


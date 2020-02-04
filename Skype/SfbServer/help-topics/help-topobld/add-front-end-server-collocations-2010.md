---
title: Adicionar Colocações de Servidor Front End 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Para uma implantação Enterprise Edition, você pode colocar o serviço de conferência A/V, o servidor de mediação ou ambos no pool de front-ends ou pode implantar cada um deles como servidores autônomos. Para uma implantação do servidor Standard Edition, o serviço de conferência A/V sempre será posicionado se a conferência estiver habilitada.
ms.openlocfilehash: 371643491438b7f1711c2a023f1b8a6d7a39525c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685144"
---
# <a name="add-front-end-server-collocations-2010"></a>Adicionar Colocações de Servidor Front End 2010

Para uma implantação Enterprise Edition, você pode colocar o serviço de conferência A/V, o servidor de mediação ou ambos no pool de front-ends ou pode implantar cada um deles como servidores autônomos. Para uma implantação do servidor Standard Edition, o serviço de conferência A/V sempre será posicionado se a conferência estiver habilitada.

> [!NOTE]
> Um serviço de conferência A/V será necessário se a **conferência** tiver sido selecionada na página **selecionar recursos** . Um pool de front-end do Enterprise Edition pode usar um serviço de conferência A/V posicionado ou um pool autônomo de conferência A/V. Se a conferência não for selecionada, o serviço de conferência a/V em colocar não estará disponível.

Você pode colocar a função de servidor de mediação em um servidor front-end do Standard Edition ou pool de front-end do Enterprise Edition. Se você implantar conexões SIP diretas em um gateway PSTN (rede telefônica pública comutada) que ofereça suporte ao bypass de mídia e ao balanceamento de carga do sistema de nomes de domínio (DNS), um pool autônomo do servidor de mediação não será necessário. Um pool autônomo do servidor de mediação não é necessário porque gateways qualificados são capazes de balanceamento de carga de DNS para um pool de servidores de mediação e podem receber tráfego de qualquer servidor de mediação em um pool. Também recomendamos que você colocar o servidor de mediação em um pool de front-end quando tiver implantado PBXs de IP ou conectar-se a um controlador de borda de sessão (SBC) do provedor de servidor de telefonia pela Internet, contanto que qualquer uma das seguintes condições seja atendida:

- O IP-PBX ou o SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear o tráfego uniformemente para todos os servidores de mediação no pool.

- O IP-PBX ou o SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear o tráfego uniformemente para todos os servidores de mediação no pool.

Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se o pool de front-ends em que você deseja colocar o servidor de mediação pode manipular a carga. Se o seu ambiente não puder atender a esses requisitos, você deve implantar um pool autônomo do servidor de mediação.

Em geral, não é recomendável a colocação do servidor de conferência A/V ou do servidor de mediação se a sua organização tiver detalhes de requirementsFor de alta disponibilidade e escalabilidade sobre como posicionar essas funções de servidor em um pool de front-ends em uma implantação do Enterprise Edition, consulte [definir e configurar um pool de front-end](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) na documentação de implantação. Para obter detalhes sobre o recurso de conferência A/V e componentes, consulte [planejando a conferência](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) na documentação de planejamento. Para obter detalhes sobre os recursos e componentes do Enterprise Voice, incluindo o servidor de mediação, consulte [planejar o Enterprise Voice no Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) na documentação de planejamento.



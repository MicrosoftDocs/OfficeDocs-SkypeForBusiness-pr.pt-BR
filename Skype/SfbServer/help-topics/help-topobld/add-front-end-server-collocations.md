---
title: Adicionar Colocações de Servidor Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Para uma implantação Enterprise Edition, o serviço de conferência A/V está posicionado no pool de front-ends. Você também pode colocar o servidor de mediação no pool de front-end ou pode implantá-lo como um servidor autônomo. O serviço de conferência A/V sempre será posicionado se a conferência estiver habilitada.
ms.openlocfilehash: 0f6b3307d73f87af10140ecf594f8e662cfdd369
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820823"
---
# <a name="add-front-end-server-collocations"></a>Adicionar Colocações de Servidor Front End

Para uma implantação Enterprise Edition, o serviço de conferência A/V está posicionado no pool de front-ends. Você também pode colocar o servidor de mediação no pool de front-end ou pode implantá-lo como um servidor autônomo. O serviço de conferência A/V sempre será posicionado se a conferência estiver habilitada.

> [!NOTE]
> Um serviço de conferência A/V será necessário se a **conferência** tiver sido selecionada na página **selecionar recursos** . Um pool de front-end do Enterprise Edition usa um serviço de conferência A/V posicionado. Se a conferência não for selecionada, o serviço de conferência a/V em colocar não estará disponível.

Você pode colocar a função de servidor de mediação em um servidor front-end do Standard Edition ou pool de front-end do Enterprise Edition. Se você implantar conexões SIP diretas em um gateway PSTN (rede telefônica pública comutada) que ofereça suporte ao bypass de mídia e ao balanceamento de carga do sistema de nomes de domínio (DNS), um pool autônomo do servidor de mediação não será necessário. Um pool autônomo do servidor de mediação não é necessário porque gateways qualificados são capazes de balanceamento de carga de DNS para um pool de servidores de mediação e podem receber tráfego de qualquer servidor de mediação em um pool. Também recomendamos que você colocar o servidor de mediação em um pool de front-end quando tiver implantado PBXs de IP ou conectar-se a um controlador de borda de sessão (SBC) do provedor de servidor de telefonia pela Internet, contanto que qualquer uma das seguintes condições seja atendida:

- O IP-PBX ou o SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear o tráfego uniformemente para todos os servidores de mediação no pool.

- O IP-PBX ou o SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear o tráfego uniformemente para todos os servidores de mediação no pool.

Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se o pool de front-ends em que você deseja colocar o servidor de mediação pode manipular a carga. Se o seu ambiente não puder atender a esses requisitos, você deve implantar um pool autônomo do servidor de mediação.

Em geral, a colocação do servidor de mediação não é recomendada se a sua organização tiver requisitos de alta disponibilidade e escalabilidade. Para obter detalhes sobre como posicionar essas funções de servidor em um pool de front-end em uma implantação do Enterprise Edition, consulte [definir e configurar um pool de front-end](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) na documentação de implantação. Para obter detalhes sobre o recurso de conferência A/V e componentes, consulte [planejando a conferência](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) na documentação de planejamento. Para obter detalhes sobre os recursos e componentes do Enterprise Voice, incluindo o servidor de mediação, consulte [planejar o Enterprise Voice no Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) na documentação de planejamento.



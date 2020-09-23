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
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Para uma implantação Enterprise Edition, o serviço de conferência A/V é colocado no pool de front-ends. Você também pode colocar o servidor de mediação no pool de front-ends ou pode implantá-lo como um servidor autônomo. O serviço de conferência A/V é sempre colocado se a conferência estiver habilitada.
ms.openlocfilehash: 015570d42482b0e4f34e6679bab27aa2c40f2f88
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216502"
---
# <a name="add-front-end-server-collocations"></a>Adicionar Colocações de Servidor Front End

Para uma implantação Enterprise Edition, o serviço de conferência A/V é colocado no pool de front-ends. Você também pode colocar o servidor de mediação no pool de front-ends ou pode implantá-lo como um servidor autônomo. O serviço de conferência A/V é sempre colocado se a conferência estiver habilitada.

> [!NOTE]
> Um serviço de Conferência A/V é exigido se **Conferência** foi selecionada na página **Selecionar recursos**. Um pool de front-ends Enterprise Edition usa um serviço de conferência A/V colocado. Se a Conferência não tiver sido selecionada, o serviço Posicionar Conferência A/V não estará disponível.

É possível posicionar a função de Servidor de Mediação em um pool de Servidores Front-End Server Standard Edition ou um pool de Front-End Enterprise Edition. Se você implantar conexões SIP Direto com um gateway PSTN (rede telefônica pública comutada) qualificado que suporta bypass de mídia e balanceamento de carga DNS (Domain Name System), um pool de Servidores de Mediação autônomo não será necessário. Um pool de Servidores de Mediação autônomo não é necessário, pois os gateways qualificados são capazes de balanceamento de carga DNS para um pool de Servidores de Mediação e podem receber tráfego de qualquer Servidor de Mediação em um pool. Também recomendamos que você coloque o servidor de mediação em um pool de front-ends quando tiver implantado IP-PBXs ou se conectar ao SBC (controlador de borda da sessão) de um provedor de servidor de telefonia da Internet, contanto que qualquer uma das seguintes condições sejam atendidas:

- O IP-PBX ou SBC é configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode encaminhar tráfego uniformemente a todos os Servidores de Mediação no pool.

- O IP-PBX ou SBC é configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode encaminhar tráfego uniformemente a todos os Servidores de Mediação no pool.

Você pode usar a ferramenta de planejamento do Microsoft Lync Server 2013 para avaliar se o pool de front-ends onde você deseja colocar o servidor de mediação pode lidar com a carga. Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.

Em geral, a colocação do servidor de mediação não é recomendada se sua organização tem requisitos de alta disponibilidade e escalabilidade. Para maiores detalhes sobre como colocar estas funções de servidor em um pool de Front-Ends em uma implantação Enterprise Edition, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) na documentação de Implantação. Para maiores detalhes sobre o recurso e os componentes de Conferência A/V, consulte [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) na documentação de Planejamento. Para obter detalhes sobre os recursos e componentes do Enterprise Voice, incluindo o servidor de mediação, consulte [Plan for Enterprise Voice in Skype for Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) na documentação de planejamento.



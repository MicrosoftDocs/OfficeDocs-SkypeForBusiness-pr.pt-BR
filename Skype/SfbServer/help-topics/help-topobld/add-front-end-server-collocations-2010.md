---
title: Adicionar Colocações de Servidor Front End 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Para uma implantação Enterprise Edition, você pode colocar tanto o serviço de Conferência A/V quanto o Servidor de Mediação, ou ambos, no pool de Front-Ends, ou você pode implantar cada um como servidores autônomos. Em uma implantação do servidor Standard Edition, o serviço de Conferência A/V é sempre colocado quando a conferência está habilitada.
ms.openlocfilehash: 1cd253c9415027eb36affe11dcd58832d6c07e8c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824101"
---
# <a name="add-front-end-server-collocations-2010"></a>Adicionar Colocações de Servidor Front-end 2010

Para uma implantação Enterprise Edition, você pode colocar tanto o serviço de Conferência A/V quanto o Servidor de Mediação, ou ambos, no pool de Front-Ends, ou você pode implantar cada um como servidores autônomos. Em uma implantação do servidor Standard Edition, o serviço de Conferência A/V é sempre colocado quando a conferência está habilitada.

> [!NOTE]
> Um serviço de Conferência A/V é exigido se **Conferência** foi selecionada na página **Selecionar recursos**. Um pool de Front-Ends Enterprise Edition pode utilizar um serviço de Conferência A/V colocado ou um pool de Conferência A/V autônomo. Caso Conferência não tenha sido selecionada, o serviço de Conferência A/V colocada não estará disponível.

É possível posicionar a função de Servidor de Mediação em um pool de Servidores Front-End Server Standard Edition ou um pool de Front-End Enterprise Edition. Se você implantar conexões SIP Direto com um gateway PSTN (rede telefônica pública comutada) qualificado que suporta bypass de mídia e balanceamento de carga DNS (Domain Name System), um pool de Servidores de Mediação autônomo não será necessário. Um pool de Servidores de Mediação autônomo não é necessário, pois os gateways qualificados são capazes de balanceamento de carga DNS para um pool de Servidores de Mediação e podem receber tráfego de qualquer Servidor de Mediação em um pool. Também recomendamos que você collocate o Servidor de Mediação em um pool de Front-End quando tiver implantado o IP-PBXs ou se conectar a um SBC (Controlador de Borda de Sessão) do Provedor de Telefonia da Internet, desde que qualquer uma das seguintes condições seja atendida:

- O IP-PBX ou SBC é configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode encaminhar tráfego uniformemente a todos os Servidores de Mediação no pool.

- O IP-PBX ou SBC é configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode encaminhar tráfego uniformemente a todos os Servidores de Mediação no pool.

Você pode usar a Ferramenta de Planejamento do Microsoft Lync Server 2013 para avaliar se o pool de Front-End onde você deseja colocar o Servidor de Mediação pode lidar com a carga. Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.

Em geral, a colocação do Servidor de Conferência A/V ou do Servidor de Mediação não é recomendada se sua organização tiver requisitos de alta disponibilidade e escalabilidadePara obter detalhes sobre como coloca-los em um pool de Front-End em uma implantação do Enterprise Edition, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation. Para maiores detalhes sobre o recurso e os componentes de Conferência A/V, consulte [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) na documentação de Planejamento. Para obter detalhes sobre os recursos e componentes do Enterprise Voice, incluindo o Servidor de Mediação, consulte [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) na documentação planejamento.



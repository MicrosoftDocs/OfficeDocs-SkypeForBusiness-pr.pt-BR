---
title: Adicionar Colocações de Servidor Front End 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Para uma implantação do Enterprise Edition, é possível colocar qualquer A / V Conferencing serviço, o servidor de mediação ou ambos em um pool Front-End, ou você podem implantar cada um deles como servidores autônomos. Para uma implantação de servidor do Standard Edition, A / o serviço de conferência de V é sempre colocado se conferência estiver habilitada.
ms.openlocfilehash: 1c2aab2f32a81724b8da649956e10e9a9ee5ae12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903807"
---
# <a name="add-front-end-server-collocations-2010"></a>Adicionar Colocações de Servidor Front End 2010

Para uma implantação do Enterprise Edition, é possível colocar qualquer A / V Conferencing serviço, o servidor de mediação ou ambos em um pool Front-End, ou você podem implantar cada um deles como servidores autônomos. Para uma implantação de servidor do Standard Edition, A / o serviço de conferência de V é sempre colocado se conferência estiver habilitada.

> [!NOTE]
> Um A / serviço V Conferencing é necessário se a **conferência** foi selecionado na página **Selecionar recursos** . Um pool de Front End do Enterprise Edition pode usar um colocado uma / autônomo ou serviço de conferência V / pool de conferência V. Se não tiver sido conferência selecionada, o colocar uma / serviço V Conferencing não estará disponível.

Você pode colocar a função de servidor de mediação em um servidor Standard Edition Front End ou um pool de Front End do Enterprise Edition. Se você implantar conexões diretas SIP para um gateway PSTN (rede) qualificado telefônica comutada pública que suporta bypass de mídia e balanceamento de carga de sistema de nome de domínio (DNS), não é necessário um pool do servidor de mediação autônomo. Um pool de servidor de mediação autônomo não é necessário porque o gateways qualificados são capazes de DNS com carga balanceada para um pool de servidores de mediação e eles podem receber tráfego de qualquer servidor de mediação em um pool. Também recomendamos que você colocar o servidor de mediação em um pool de Front-End quando você tiver implantado o IP-PBXs ou se conectar a de um Internet Server provedor de telefonia borda controlador sessão (SBC), desde que qualquer uma das seguintes condições forem atendida:

- O IP-PBX ou SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear tráfego uniformemente para todos os servidores de mediação no pool.

- O IP-PBX ou SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear tráfego uniformemente para todos os servidores de mediação no pool.

Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se o pool de Front-End, onde você deseja colocar o servidor de mediação pode manipular a carga. Se seu ambiente não pode atender a esses requisitos, você deve implantar um pool do servidor de mediação autônomo.

Em geral, colocação da / V Conferencing Server ou servidor de mediação não é recomendado, se sua organização tem alta disponibilidade e escalabilidade requirementsFor detalhes sobre colocando essas funções de servidor em um pool de Front-End em uma versão Enterprise Edition implantação, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) na documentação de implantação. Para obter detalhes sobre A / recurso de conferência V e componentes, consulte [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) na documentação de planejamento. Para obter detalhes sobre os recursos do Enterprise Voice e componentes, incluindo o servidor de mediação, consulte [Plan for Enterprise Voice no Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) na documentação de planejamento.



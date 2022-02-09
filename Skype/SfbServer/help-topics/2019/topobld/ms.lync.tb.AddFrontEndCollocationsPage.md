---
title: Adicionar Colocações de Servidor Front-end
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: Para uma Edição Enterprise, o serviço de Conferência A/V é alocado no pool de Front-End. Você também pode colocar o Servidor de Mediação no pool de Front-End ou implantá-lo como um servidor autônomo. O serviço de Conferência A/V sempre será alocado se a conferência estiver habilitada.
ms.openlocfilehash: 7f7a2e6f6a7b11e378a9ab42ad045a9bcd7343bc
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397119"
---
# <a name="add-front-end-server-collocations"></a>Adicionar Colocações de Servidor Front-end

Para uma Edição Enterprise, o serviço de Conferência A/V é alocado no pool de Front-End. Você também pode colocar o Servidor de Mediação no pool de Front-End ou implantá-lo como um servidor autônomo. O serviço de Conferência A/V sempre será alocado se a conferência estiver habilitada.

> [!NOTE]
> Um serviço de Conferência A/V é exigido se **Conferência** foi selecionada na página **Selecionar recursos**. Um Edição Enterprise de front-end usa um serviço de Conferência A/V alocado. Se a Conferência não tiver sido selecionada, o serviço Posicionar Conferência A/V não estará disponível.

É possível posicionar a função de Servidor de Mediação em um pool de Servidores Front-End Server Standard Edition ou um pool de Front-End Enterprise Edition. Se você implantar conexões SIP Direto com um gateway PSTN (rede telefônica pública comutada) qualificado que suporta bypass de mídia e balanceamento de carga DNS (Domain Name System), um pool de Servidores de Mediação autônomo não será necessário. Um pool de Servidores de Mediação autônomo não é necessário, pois os gateways qualificados são capazes de balanceamento de carga DNS para um pool de Servidores de Mediação e podem receber tráfego de qualquer Servidor de Mediação em um pool. Também recomendamos que você cole o Servidor de Mediação em um pool de Front-End quando tiver implantado o IP-PBXs ou se conectar a um Controlador de Borda de Sessão do Provedor de Telefonia da Internet (SBC), desde que qualquer uma das seguintes condições seja atendida:

- O IP-PBX ou SBC é configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode encaminhar tráfego uniformemente a todos os Servidores de Mediação no pool.

- O IP-PBX ou SBC é configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode encaminhar tráfego uniformemente a todos os Servidores de Mediação no pool.

Você pode usar a Ferramenta de Planejamento para avaliar se o pool de Front-End onde deseja colocar o Servidor de Mediação pode manipular a carga. Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.

Em geral, a localização do Servidor de Mediação não é recomendada se sua organização tiver requisitos de alta disponibilidade e escalabilidade. Para maiores detalhes sobre como colocar estas funções de servidor em um pool de Front-Ends em uma implantação Enterprise Edition, consulte [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) na documentação de Implantação. Para maiores detalhes sobre o recurso e os componentes de Conferência A/V, consulte [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) na documentação de Planejamento. Para obter detalhes sobre Enterprise Voice e componentes, incluindo o Servidor de Mediação, consulte [Plan for Enterprise Voice in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) na documentação planejamento.
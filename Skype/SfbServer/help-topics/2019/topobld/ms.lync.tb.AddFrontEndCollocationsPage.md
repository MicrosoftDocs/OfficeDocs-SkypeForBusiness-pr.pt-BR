---
title: Adicionar Colocações de Servidor Front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: Para uma implantação do Enterprise Edition, o serviço de Conferência A/V é alocado no pool de Front-End. Você também pode colocar o Servidor de Mediação no pool de Front-End ou implantá-lo como um servidor autônomo. O serviço de Conferência A/V sempre será alocado se a conferência estiver habilitada.
ms.openlocfilehash: 8dd984f52740d38689ec123cc51e5cdb2901f440
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811721"
---
# <a name="add-front-end-server-collocations"></a>Adicionar Colocações de Servidor Front-end

Para uma implantação do Enterprise Edition, o serviço de Conferência A/V é alocado no pool de Front-End. Você também pode colocar o Servidor de Mediação no pool de Front-End ou implantá-lo como um servidor autônomo. O serviço de Conferência A/V sempre será alocado se a conferência estiver habilitada.

> [!NOTE]
> Um serviço de Conferência A/V é exigido se **Conferência** foi selecionada na página **Selecionar recursos**. Um pool de Front-End Enterprise Edition usa um serviço de Conferência A/V. Se a Conferência não tiver sido selecionada, o serviço Posicionar Conferência A/V não estará disponível.

É possível posicionar a função de Servidor de Mediação em um pool de Servidores Front-End Server Standard Edition ou um pool de Front-End Enterprise Edition. Se você implantar conexões SIP Direto com um gateway PSTN (rede telefônica pública comutada) qualificado que suporta bypass de mídia e balanceamento de carga DNS (Domain Name System), um pool de Servidores de Mediação autônomo não será necessário. Um pool de Servidores de Mediação autônomo não é necessário, pois os gateways qualificados são capazes de balanceamento de carga DNS para um pool de Servidores de Mediação e podem receber tráfego de qualquer Servidor de Mediação em um pool. Também recomendamos que você collocate o Servidor de Mediação em um pool de Front-End quando tiver implantado o IP-PBXs ou se conectar a um SBC (Controlador de Borda de Sessão) do Provedor de Telefonia da Internet, desde que qualquer uma das seguintes condições seja atendida:

- O IP-PBX ou SBC é configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode encaminhar tráfego uniformemente a todos os Servidores de Mediação no pool.

- O IP-PBX ou SBC é configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode encaminhar tráfego uniformemente a todos os Servidores de Mediação no pool.

Você pode usar a Ferramenta de Planejamento para avaliar se o pool de Front-End onde você deseja colocar o Servidor de Mediação pode lidar com a carga. Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.

Em geral, a localização do Servidor de Mediação não é recomendada se sua organização tiver requisitos de alta disponibilidade e escalabilidade. Para maiores detalhes sobre como colocar estas funções de servidor em um pool de Front-Ends em uma implantação Enterprise Edition, consulte [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) na documentação de Implantação. Para maiores detalhes sobre o recurso e os componentes de Conferência A/V, consulte [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) na documentação de Planejamento. Para obter detalhes sobre os recursos e componentes do Enterprise Voice, incluindo o Servidor de Mediação, consulte [Plan for Enterprise Voice in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) na documentação planejamento.



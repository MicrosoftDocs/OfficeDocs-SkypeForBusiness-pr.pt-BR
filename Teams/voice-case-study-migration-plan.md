---
title: Estudo de caso de voz do Teams Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudo de caso de voz do Teams para corporação multi-nacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093721"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Estudo de caso contoso: Plano de atualização do Teams

Na decisão de migrar do Skype for Business para o Teams, a Contoso quis oferecer uma experiência de transição fácil para os usuários finais. Em vez de alternar todos para o Teams ao mesmo tempo, eles decidiram configurar a conectividade híbrida e usar o método de recursos sobrepostos para mover os usuários para o Teams. Isso permitia que os usuários do Teams e do Skype for Business locais compartilhavam presença e se comunicavam. À medida que os usuários entraram no piloto do Sistema de Telefonia, eles foram movidos para o modo Somente do Teams.

Para entender os conceitos fundamentais sobre atualização, métodos e modos, a Contoso leu os seguintes artigos:

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Estratégias de atualização para administradores de IT](upgrade-to-teams-on-prem-implement.md) 
- [Diretrizes de migração e interoperabilidade](migration-interop-guidance-for-teams-with-skype.md)
 
A Contoso também participou da sessão Ignite 2019 Projetando seu caminho do [Skype for Business para o Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Contoso aprendeu sobre:

- Conceitos fundamentais, como interoperabilidade, federação e comportamento de atualização 

- Modos de coexistência e gerenciamento com base no TeamsUpgradePolicy 

- Experiência do usuário final para: 

  - Chat e Chamada 

  - Agendamento de reuniões 

  - Disponibilidade da funcionalidade de colaboração em clientes do Teams 

Para planejar e configurar a conectividade híbrida, a primeira etapa para [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) mover seu ambiente local para a nuvem, a Contoso leu Planejar conectividade híbrida e [Configurar](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) conectividade híbrida para entender como: 

  - Configure seu serviço de ambiente local para federar com o Office 365. 

  - Configurar seu ambiente local para confiar no Office 365 e habilitar o espaço de endereço SIP compartilhado com o Office 365 

  - Habilita o espaço de endereço SIP compartilhado em seu locatário do Office 365.

  - Use o modo Ilhas durante o piloto técnico.

  - Alternar usuários para o modo TeamsOnly quando o usuário for habilitado para o Sistema de Telefonia. O modo TeamsOnly é necessário para Plano de Chamadas e Roteamento Direto.
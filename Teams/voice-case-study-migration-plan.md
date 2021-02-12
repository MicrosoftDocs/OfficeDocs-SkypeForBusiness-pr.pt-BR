---
title: Estudo de caso do Teams voice Contoso
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
description: Estudo de caso de voz do Teams para corporação multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785942"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Estudo de caso da Contoso: plano de atualização do Teams

Na decisão de migrar do Skype for Business para o Teams, a Contoso queria fornecer uma experiência de transição fácil para os usuários finais. Em vez de mudar todos para o Teams ao mesmo tempo, eles decidiram configurar a conectividade híbrida e usar o método de sobreposição de recursos para mover os usuários para o Teams. Isso permitia que os usuários do Teams e do Skype for Business locais compartilhavam presença e se comunicam. Conforme os usuários entraram no piloto do Sistema telefônico, eles foram movidos para o modo Somente equipes.

Para entender conceitos fundamentais sobre atualização, métodos e modos, a Contoso leu os seguintes artigos:

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Atualização do Skype for Business para o Teams](upgrade-to-teams-on-prem-overview.md) 
- [Diretrizes de migração e interoperabilidade](migration-interop-guidance-for-teams-with-skype.md)
 
A Contoso também participou da sessão Ignite 2019, projetando seu caminho do [Skype for Business para o Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) A Contoso aprendeu sobre:

- Conceitos fundamentais, como interoperabilidade, federação e comportamento de atualização 

- Modos de coexistência e gerenciamento com base no TeamsUpgradePolicy 

- Experiência do usuário final para: 

  - Chat e Chamada 

  - Agendamento de reunião 

  - Disponibilidade da funcionalidade de colaboração em clientes do Teams 

Para planejar e configurar a conectividade híbrida, o primeiro passo para [](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) mover seu ambiente [](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) local para a nuvem, a Contoso leu Plano de conectividade híbrida e Configurar a conectividade híbrida para entender como: 

  - Configure o serviço de ambiente local para se federar com o Office 365. 

  - Configurar o ambiente local para confiar no Office 365 e habilitar o espaço de endereço SIP compartilhado com o Office 365 

  - Habilitar o espaço de endereço SIP compartilhado no locatário do Office 365.

  - Use o modo Ilhas durante o piloto técnico.

  - Alternar usuários para o modo TeamsOnly assim que o usuário está habilitado para o Sistema de Telefonia. O modo TeamsOnly é necessário para o Plano de Chamada e o Roteamento Direto. 

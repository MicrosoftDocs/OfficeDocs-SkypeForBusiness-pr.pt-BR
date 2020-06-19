---
title: Estudo de caso da Contoso Voice Teams
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
description: Estudo de caso de voz do teams para Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785942"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Estudo de caso da Contoso: plano de atualização do teams

Na decisão de migrar do Skype for Business para o Teams, a contoso queria oferecer uma experiência de transição fácil para os usuários finais. Em vez de alternar entre todas as equipes ao mesmo tempo, elas decidiram configurar a conectividade híbrida e usar o método de recursos sobrepostos para mover usuários para o Teams. Isso permitia aos usuários do Teams e do Skype for Business no local para compartilhar a presença e se comunicar. Conforme os usuários digitam o piloto do sistema telefônico, eles foram movidos para o modo somente para equipes.

Para entender os conceitos fundamentais sobre a atualização, os métodos e os modos, a contoso leu os seguintes artigos:

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Atualização do Skype for Business para o Teams](upgrade-to-teams-on-prem-overview.md) 
- [Orientação de migração e interoperabilidade](migration-interop-guidance-for-teams-with-skype.md)
 
A contoso também participou da sessão do Ignite 2019 [que está criando seu caminho do Skype for Business para o Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions). A contoso aprendeu sobre:

- Conceitos fundamentais, como interoperabilidade, agrupamento e comportamento de atualização 

- Modos de coexistência e gerenciamento baseados no TeamsUpgradePolicy 

- Experiência do usuário final para: 

  - Chat e chamadas 

  - Agendamento de reunião 

  - Disponibilidade da funcionalidade de colaboração em clientes do teams 

Para planejar e configurar a conectividade híbrida, o primeiro passo para mover o ambiente local para a nuvem, a contoso leu o plano de leitura [híbrido](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) e [Configurar a conectividade híbrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) para compreender como: 

  - Configurar o serviço de ambiente local para federação com o Office 365. 

  - Configurar o ambiente local para confiar no Office 365 e habilitar o espaço de endereço SIP compartilhado com o Office 365 

  - Habilite o espaço de endereço SIP compartilhado em seu locatário do Office 365.

  - Use o modo de ilhas durante o piloto técnico.

  - Alternar usuários para o modo TeamsOnly quando o usuário estiver habilitado para o sistema telefônico. O modo TeamsOnly é necessário para o plano de chamadas e o roteamento direto. 

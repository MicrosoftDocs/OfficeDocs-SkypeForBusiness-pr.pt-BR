---
title: Solucionar problemas de acesso de convidado no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Obtenha ajuda para solucionar problemas e corrigir problemas de acesso de convidado no Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837631"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Solucionar problemas de acesso de convidado no Microsoft Teams
======================================================

> [!IMPORTANT]
> Talvez seja necessário aguardar até 24 horas para que as alterações entrem em vigor. 


- Para verificar os problemas de suporte atuais com o acesso de convidado no Teams, vá para solução de problemas do Microsoft [Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Para ver se conhecemos o problema, confira os [problemas conhecidos do Microsoft Teams](Known-issues.md).
- Convidados são usuários de fora da sua organização. Se alguém estiver dentro da sua organização (incluindo seus funcionários, prestadores de site ou agentes Onsite), eles não poderão ser adicionados como convidados. O mesmo se aplica às suas afiliadas.
- Saiba mais sobre os futuros recursos de acesso de convidado novos ou atualizados no [roteiro do teams](https://aka.ms/teamsroadmap).
- Diga-nos o que você deseja no [UserVoice do teams](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Se seus convidados estiverem vendo erros de licença

O acesso de convidado em equipes usa o Azure Active Directory (Azure AD) Business to Business (B2B) e seu modelo de licenciamento. O acesso de convidados está incluído em todas as inscrições do Office 365 Business Premium, Office 365 Enterprise e Office 365 Education. Não é necessária nenhuma licença adicional do Office 365.

Se você estiver vendo erros de licenciamento, leia a [orientação de licenciamento B2B do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para determinar os requisitos de licenciamento para atender às suas necessidades de acesso de convidado em sua organização.


- As licenças de convidado são contadas em relação à organização que convida. Considere isso quando você calcular o número de licenças necessárias.
- As licenças são contadas em relação à sua organização se os convidados convidados vierem de outro locatário do Office 365 ou estiverem usando seus endereços de email pessoais.

## <a name="support-for-b2b-user-types"></a>Suporte para tipos de usuário B2B
Atualmente o Microsoft Teams tem suporte apenas para tipos de estado 1 e estado 2 de usuários convidados [, conforme definido pelo Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Tópicos relacionados

[Acesso de convidados ao Teams](guest-access.md)



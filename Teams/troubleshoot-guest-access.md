---
title: Solucionar problemas com o acesso de convidados no Microsoft Teams
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
description: Obtenha ajuda para solucionar e corrigir problemas de acesso de convidados no Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837631"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Solucionar problemas com o acesso de convidados no Microsoft Teams
======================================================

> [!IMPORTANT]
> Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor. 


- Para verificar se há problemas de suporte atuais relacionados ao acesso de convidados no Teams, vá para [Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).
- Para verificar se sabemos da existência seu problema, consulte [Problemas conhecidos do Microsoft Teams](Known-issues.md).
- Convidados são usuários fora da sua organização. Se alguém estiver dentro da sua organização (incluindo seus funcionários, contratados no local ou agentes no local), essa pessoa não poderá ser adicionada como convidado. O mesmo se aplica aos seus afiliados.
- Descubra os próximos recursos novos ou atualizados de acesso de convidados no [Roteiro do Teams](https://aka.ms/teamsroadmap).
- Diga-nos o que você deseja no [Teams UserVoice](https://aka.ms/TeamsUserVoice).

## <a name="if-your-guests-are-seeing-license-errors"></a>Se seus convidados estiverem vendo erros de licença

O acesso de convidado no Teams usa o Business to Business (B2B) do Azure Active Directory (Azure AD) e seu modelo de licenciamento. O acesso de convidados está incluído em todas as inscrições do Office 365 Business Premium, Office 365 Enterprise e Office 365 Education. Não é necessária nenhuma licença adicional do Office 365.

Se você estiver vendo erros de licenciamento, leia as [orientações de licenciamento B2B do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) para determinar os requisitos de licenciamento que atendem às suas necessidades de acesso de convidado em sua organização.


- As licenças de convidado são contadas na organização que envia os convites. Considere isso ao calcular o número de licenças necessárias.
- As licenças são contadas na sua organização, independentemente de os convidados serem de outro locatário do Office 365 ou estarem usando seus endereços de email pessoais.

## <a name="support-for-b2b-user-types"></a>Suporte para tipos de usuário B2B
Atualmente, o Teams tem suporte apenas para os tipos de usuários Convidados dos tipos Estado 1 e Estado 2, [conforme definido pelo Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Tópicos relacionados

[Acesso de convidados ao Teams](guest-access.md)



---
title: Solucionar problemas com o acesso de convidados no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0468d0d3d1cc7a8d1c17699e28c1449e1f7800c8
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948677"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>Solucionar problemas com o acesso de convidados no Microsoft Teams

- Para ver se sabemos sobre seu problema, confira [Suporte Teams em sua organização.](/MicrosoftTeams/troubleshoot/teams-welcome)
- Para verificar se há problemas de suporte atuais relacionados ao acesso de convidados no Teams, vá para [Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/).
- Os convidados são pessoas fora de sua organização. Se alguém estiver dentro da sua organização (incluindo seus funcionários, contratados no local ou agentes no local), essa pessoa não poderá ser adicionada como convidado. O mesmo se aplica aos seus afiliados.
- Descubra os próximos recursos novos ou atualizados de acesso de convidados no [Roteiro do Teams](https://aka.ms/teamsroadmap).
- Diga-nos o que você deseja no [Teams UserVoice](https://aka.ms/TeamsUserVoice).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>Se seus convidados estiverem vendo erros de licença

O acesso de convidado no Teams usa o Business to Business (B2B) do Azure Active Directory (Azure AD) e seu modelo de licenciamento. O acesso de convidados está incluído em todas as assinaturas do Microsoft 365 Business Standard, do Office 365 Enterprise e do Office 365 Education. Não é necessária nenhuma licença adicional do Microsoft 365 ou Office 365.

> [!NOTE]
> Teams deve ser habilitado no locatário da casa de um convidado para que os convidados sejam capazes de entrar e usar o Teams como convidado em outro locatário (recurso).

Se você estiver vendo erros de licenciamento, leia o modelo de cobrança para Identidades Externas do [Azure AD](/azure/active-directory/external-identities/external-identities-pricing) para determinar os requisitos de licenciamento para atender às suas necessidades de acesso de convidados em sua organização.

- As licenças de convidado são contadas na organização que envia os convites. Considere isso ao calcular o número de licenças necessárias.
- As licenças são contadas em sua organização se os convidados vêm de outra organização Microsoft 365 ou se estão usando seus endereços de email pessoais.

## <a name="support-for-b2b-user-types"></a>Suporte para tipos de usuário B2B

Atualmente, o Teams tem suporte apenas para os tipos de usuários Convidados dos tipos Estado 1 e Estado 2, [conforme definido pelo Azure B2B](/azure/active-directory/b2b/user-properties).

## <a name="related-topics"></a>Tópicos relacionados

[Acesso de convidados ao Teams](guest-access.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
---
title: Atualize para o Teams a partir de uma implantação local do Skype for Business-Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578394"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Atualize o Skype for Business para o Teams &mdash; para administradores de ti

## <a name="overview"></a>Visão geral

Ao fazer a atualização do Skype for Business para o Teams, algumas organizações exigem uma distribuição progressiva planejada e gerenciada pelos departamentos de ti. Os artigos nesta seção se aplicam principalmente aos administradores de ti em grandes organizações. Essas organizações são geralmente locais, mas também podem ser organizações do Skype for Business online. Antes de ler estes artigos, lembre-se de ler introdução [à atualização do seu Teams](upgrade-start-here.md) e [sobre a estrutura de atualização](upgrade-framework.md).


Os artigos a seguir o orientarão durante o processo de atualização de sua organização: 

- [Métodos de atualização](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Ferramentas para gerenciar a atualização](upgrade-to-teams-on-prem-tools.md)
- [Considerações adicionais sobre organizações com o Skype for Business no local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar sua atualização](upgrade-to-teams-on-prem-implement.md)
- [Considerações sobre PSTN (rede telefônica pública comutada)](upgrade-to-teams-on-prem-pstn-considerations.md)

Além disso, os seguintes artigos descrevem conceitos importantes de atualização e comportamentos de coexistência:

- [Coexistência de Teams e Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência-referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>Estes artigos usam os termos Skype for Business Online, Skype for Business Server local e Skype for Business. O último termo refere-se às versões online e local.

Antes de começar, lembre-se de que um usuário que foi migrado para o Microsoft Teams não usa mais um cliente Skype for Business, exceto para ingressar em uma reunião hospedada no Skype for Business.  Todos os chats e chamadas recebidos chegam ao cliente do Teams do usuário, independentemente do remetente usar o Teams ou o Skype for Business. Qualquer reunião nova organizada pelo usuário migrado será agendada como reuniões do teams. Se o usuário tentar usar o cliente Skype for Business, a iniciação de chats e chamadas será bloqueada.  No entanto, o usuário pode (e deve) ainda usar o cliente Skype for Business para ingressar em reuniões do Skype for Business às quais eles são convidados. (Os clientes Skype for Business mais antigos que foram enviados antes do 2017 não obedecem ao TeamsUpgradePolicy. Verifique se você está usando o mais recente cliente Skype for Business.
 
Você gerencia a transição do seu usuário para o Microsoft Teams usando o conceito de [Mode](migration-interop-guidance-for-teams-with-skype.md), que é uma propriedade de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Um usuário que foi migrado para o Teams, conforme descrito acima, está no modo "TeamsOnly".  Para uma organização que esteja migrando para o Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly.

>[!NOTE]
>Os usuários que têm uma conta local do Skype for Business não podem ser TeamsOnly. Embora esses usuários possam [usar o Microsoft Teams no modo ilhas](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), isso não fornece o conjunto completo de funcionalidades do teams que está disponível no modo TeamsOnly. Para fazer esses usuários TeamsOnly, eles devem ser movidos para a nuvem usando `Move-CsUser` as ferramentas locais do Skype for Business Server.

Okey. Vamos começar.  A primeira etapa é entender os [métodos de atualização disponíveis para você](upgrade-to-teams-on-prem-upgrade-methods.md).







   

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


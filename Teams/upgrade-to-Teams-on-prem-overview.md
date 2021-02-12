---
title: Atualizar para o Teams a partir de uma implantação local do Skype for Business – Microsoft Teams
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
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Atualizar do Skype for Business para o Teams &mdash; para administradores de IT

## <a name="overview"></a>Visão Geral

Ao atualizar do Skype for Business para o Teams, algumas organizações exigem uma adoção progressiva que seja planejada e gerenciada por seus departamentos de TE. Os artigos desta seção se aplicam principalmente a administradores de IT em grandes organizações. Essas organizações geralmente são locais, mas também podem ser grandes organizações do Skype for Business Online. Antes de ler estes artigos, não deixe de ler ["Começar](upgrade-start-here.md) a trabalhar com a atualização do [Teams" e "Sobre a estrutura de atualização".](upgrade-framework.md)


Os artigos a seguir orientarão você durante o processo de atualização para sua organização: 

- [Métodos de atualização](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Ferramentas para gerenciar sua atualização](upgrade-to-teams-on-prem-tools.md)
- [Considerações adicionais para organizações com o Skype for Business local](upgrade-to-teams-on-prem-considerations.md)
- [Implementar sua atualização](upgrade-to-teams-on-prem-implement.md)
- [Considerações sobre A Rede Telefônica Pública Comutado (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

Além disso, os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:

- [Coexistência do Teams e do Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>Estes artigos usam os termos Skype for Business Online, Skype for Business Server local e Skype for Business. O último termo refere-se às versões online e local.

Antes de começar, esteja ciente de que um usuário que foi migrado para o Teams não usa mais um cliente Skype for Business, exceto para ingressar em uma reunião hospedada no Skype for Business.  Todos os chats e chamadas recebidos chegam ao cliente do Teams do usuário, independentemente do remetente usar o Teams ou o Skype for Business. Todas as novas reuniões organizadas pelo usuário migrado serão agendadas como reuniões do Teams. Se o usuário tentar usar o cliente Skype for Business, o início de chats e chamadas será bloqueado.  No entanto, o usuário ainda pode (e deve) usar o cliente Skype for Business para ingressar em reuniões do Skype for Business para as que ele for convidado. (Clientes mais antigos do Skype for Business que foram enviados antes de 2017 não fazem respeito ao TeamsUpgradePolicy. Certifique-se de que você está usando o cliente Skype for Business mais recente.)
 
Você gerencia a transição do usuário para o Teams usando o conceito de [modo,](migration-interop-guidance-for-teams-with-skype.md)que é uma propriedade do [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) Um usuário que tenha sido migrado para o Teams conforme descrito acima está no modo "TeamsOnly".  Para uma organização que esteja migrando para o Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly.

>[!NOTE]
>Os usuários que têm uma conta local do Skype for Business não podem ser o TeamsOnly. Embora esses usuários possam usar o [Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)no modo Ilhas, isso não fornece o conjunto completo de funcionalidades do Teams disponíveis no modo TeamsOnly. Para tornar esses usuários do TeamsOnly, eles devem ser movidos para a nuvem usando as ferramentas locais do `Move-CsUser` Skype for Business Server.

Okey. Vamos começar.  A primeira etapa é entender os [métodos de atualização disponíveis para você.](upgrade-to-teams-on-prem-upgrade-methods.md)







   

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


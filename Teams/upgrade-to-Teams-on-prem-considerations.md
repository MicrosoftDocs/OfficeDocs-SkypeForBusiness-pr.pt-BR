---
title: Atualizar para o Teams a partir de uma implantação local do Skype for Business – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533588"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a>Considerações de atualização para organizações com o Skype for Business Server local &mdash; para administradores de IT

Este artigo descreve considerações adicionais para organizações com o Skype for Business Server local. Este artigo é o quarto de vários que descrevem conceitos de atualização e implementação para administradores de IT.  

- [Visão geral](upgrade-to-teams-on-prem-overview.md)
- [Métodos de atualização](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Ferramentas para gerenciar sua atualização](upgrade-to-teams-on-prem-tools.md)
- **Considerações adicionais para organizações com o Skype for Business local** (este artigo)
- [Implementando sua atualização](upgrade-to-teams-on-prem-implement.md)
- [Considerações sobre A Rede Telefônica Pública Comutado (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

Além disso, os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:

- [Coexistência do Teams e do Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md)
- [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considerações para organizações com o Skype for Business Server local

- Configurar o Skype for Business híbrido é um pré-requisito para migrar para o modo TeamsOnly. Embora seja possível usar o Teams no modo Ilhas sem híbrido, a transição para o modo TeamsOnly não poderá ser feita até que o usuário seja movido do Skype for Business local para o Skype for Business Online (usando [o Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) Para obter mais informações, consulte [Configurar conectividade híbrida.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- Se sua organização tiver o Skype for Business Server e você não tiver configurado a conectividade híbrida, mas ainda quiser usar o Teams, para administrar a funcionalidade do Teams, use uma conta administrativa que tenha um domínio .onmicrosoft.com. 

- Os usuários do Teams que têm uma conta do Skype for Business local (ou seja, eles ainda não foram movidos para a nuvem usando o Move-CsUser) não podem interoperar com nenhum usuário do Skype for Business, nem podem federar com usuários externos. Essa funcionalidade só estará disponível quando os usuários são movidos para a nuvem (no modo Ilhas ou como usuários do TeamsOnly). 

- Se você tiver usuários com contas do Skype for Business no local, não poderá atribuir o modo TeamsOnly no nível do locatário. Primeiro, você deve mover todos os usuários com contas locais do Skype for Business para a nuvem usando e desabilitar a migração híbrida para concluir a migração `Move-CsUser` [para a nuvem.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` não funcionará no nível do locatário se um registro DNS de descoberta lyncdiscover for detectado que aponta para um local diferente do Office 365.

- Você deve garantir que seus usuários sejam sincronizados corretamente no Azure AD com os atributos corretos do Skype for Business. Esses atributos são todos prefixos com "msRTCSIP-". Se os usuários não estiverem sincronizados corretamente com o Azure AD, as ferramentas de gerenciamento no Teams não poderão gerenciar esses usuários. (Por exemplo, você não poderá atribuir políticas do Teams a usuários locais, a menos que esteja sincronizando esses atributos corretamente.) Para obter mais informações, consulte [Configurar o Azure AD Connect para Teams e o Skype for Business.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- Para criar um novo usuário do TeamsOnly ou do Skype for Business Online em uma organização híbrida, primeiro você deve habilitar o usuário no *Skype for Business Server* local e, em seguida, mover o usuário local para a nuvem usando o Move-CsUser.  Criar o usuário local primeiro garante que outros usuários restantes do Skype for Business local sejam capazes de roteá-lo para o usuário recém-criado. Depois que todos os usuários são movidos online, não é mais necessário habilitar os usuários no local.

- Quando um usuário é movido do local para a nuvem, as reuniões organizadas por esse usuário são migradas para o Skype for Business Online ou o Teams, dependendo se a opção -MoveToTeams está especificada ou não.

- Se quiser exibir notificações no cliente Skype for Business para usuários locais, use o TeamsUpgradePolicy no toolset local. Somente o parâmetro NotifySfbUsers é relevante para usuários locais.  Os usuários locais recebem seu modo das instâncias online do TeamsUpgradePolicy. Veja as anotações [em Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 

>[!NOTE]
> Todos os novos locatários criados após 3 de setembro de 2019 são criados como locatários do TeamsOnly, a menos que a organização já tenha uma implantação local do Skype for Business Server. A Microsoft usa registros DNS para identificar organizações locais do Skype for Business Server. Se sua organização tiver o Skype for Business Server local sem entradas dns públicas, você precisará ligar para o Suporte da Microsoft para que seu novo locatário seja downgrade. 













## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)


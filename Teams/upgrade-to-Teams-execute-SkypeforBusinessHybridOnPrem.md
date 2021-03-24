---
title: Atualizar o Skype for Business local para o Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Saiba como atualizar sua organização para o Microsoft Teams a partir de uma implantação local do Skype for Business.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b35a757ecd70fbf2926e668bef86cb21e51d8b8e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093781"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Atualizar do Skype for Business local para o Teams

![Atualizar diagrama de jornada, enfatizando Implantação e Implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme se você concluiu as seguintes atividades:

-   [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
-   [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
-   [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparou seu ambiente](./upgrade-prepare-environment.md)
-   [Preparou sua organização](./upgrade-prepare-organization.md)
-   [Conduzido um piloto](./pilot-essentials.md)

Se você implantou o Skype for Business Server ou o Microsoft Lync no local e sua organização deseja atualizar para o Teams, siga as diretrizes neste artigo. Você precisa configurar a conectividade híbrida com sua organização do Microsoft 365 ou do Office 365 e determinar os requisitos de coexistência se estiver movendo seus usuários para o Teams em fases.

Antes de começar, os profissionais de TI e administradores devem revisar as considerações importantes para organizações com o [Skype for Business Server local](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) mais adiante neste artigo.

> [!IMPORTANT]
> O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams. Lembre-se de que uma atualização bem-sucedida alinha a preparação técnica e do usuário, portanto, certifique-se de aproveitar as diretrizes aqui enquanto você navega sua jornada para o Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Etapa 1: Configurar conectividade híbrida 

O principal pré-requisito para atualizar seus usuários locais para o Teams é configurar a conectividade híbrida para sua implantação local do Skype for Business Server. 

Comece lendo [Plano de conectividade híbrida](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) e siga as tarefas descritas em Configurar conectividade [híbrida](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Etapa 2: Definir o modo de coexistência de transição (opcional)

A coexistência e a interoperabilidade entre clientes e usuários do Skype for Business e do Teams são definidas pelos modos de Atualização do Teams.  Por padrão, as organizações estão no modo Ilhas, o que permite que os usuários usem os clientes do Teams e do Skype for Business lado a lado.

Para uma organização mudar para o Teams, o modo TeamsOnly é o destino final para cada usuário, embora nem todos os usuários precisem ser atribuídos ao TeamsOnly (ou a qualquer outro modo) ao mesmo tempo.

Antes de os usuários chegarem ao modo TeamsOnly, as organizações podem, opcionalmente, usar qualquer um dos modos de coexistência do Skype for Business para garantir uma comunicação previsível entre usuários que estão no modo TeamsOnly e usuários que ainda não estão.  O objetivo dos modos de coexistência do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) é fornecer uma experiência simples e previsível para os usuários finais à medida que as organizações migram do Skype for Business para o Teams. 

Quando um usuário está em qualquer um dos modos skype for Business, todos os chats de entrada e chamadas são roteados para o cliente skype for Business do usuário. Para evitar confusão do usuário final e garantir o roteamento adequado, a funcionalidade de chamada e chat no cliente do Teams é desabilitada quando um usuário está em qualquer um dos modos skype for Business. Da mesma forma, o agendamento de reuniões no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab e explicitamente habilitados quando um usuário está no modo SfBWithTeamsCollabAndMeetings.

Dependendo dos requisitos, você pode atribuir o modo de coexistência apropriado com base no caminho de atualização escolhido pela sua organização. Para obter mais informações, consulte Diretrizes de migração e [interoperabilidade](migration-interop-guidance-for-teams-with-skype.md) para organizações que usam o Teams em conjunto com o Skype for Business e Definindo suas configurações de [coexistência e atualização.](./setting-your-coexistence-and-upgrade-settings.md)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Etapa 3: Mover usuários do Skype for Business local para o Teams Somente

Em última análise, você vai querer mover seus usuários para o modo TeamsOnly. Isso pode envolver uma ou duas etapas, dependendo do ambiente local.  

Para obter mais informações, consulte [Move users between on-premises and the cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and Move users from [on-premises to Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Etapa 4: Desabilitar o híbrido para concluir sua migração para a nuvem

Depois de ter movido todos os usuários do local para a nuvem, você pode desmantelar a implantação local do Skype for Business. Para obter mais informações, consulte [Desabilitar a migração híbrida para concluir a migração para a nuvem](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).


## <a name="phone-system-and-pstn-connectivity-options"></a>Opções de conectividade do Sistema de Telefonia e PSTN

O Sistema de Telefonia com o Teams é suportado depois que o usuário está no modo TeamsOnly. (Se o usuário estiver no modo Ilhas, o Sistema de Telefonia só será suportado com o Skype for Business.) 

### <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

Ao considerar as opções de conectividade PSTN (Rede Telefônica Pública Comucionada), há dois cenários possíveis ao mudar do Skype for Business local para o modo TeamsOnly:

- Um usuário no Skype for Business local com Enterprise Voice, que estará mudando para online e usando um plano de Chamadas da Microsoft. Migrar esse usuário para o Teams requer mover a conta local do Skype for Business do usuário para a nuvem e coordenar essa movimentação com A) a porta do número de telefone desse usuário para um Plano de Chamadas da Microsoft ou B) atribuindo um novo número de assinante de regiões disponíveis.  Para obter mais informações, [consulte From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Um usuário no Skype for Business local com Enterprise Voice, que estará mudando para online e mantendo a conectividade PSTN local. Migrar esse usuário para o Teams requer mover a conta local do Skype for Business do usuário para a nuvem e coordenar essa movimentação com a migração do usuário para Roteamento Direto. Para obter mais informações, [consulte From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considerações importantes para organizações com o Skype for Business Server local

- Os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:
    - [Coexistência do Teams e do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md)
    - [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)

- Configurar o Skype for Business híbrido é um pré-requisito para migrar para o modo TeamsOnly. Embora seja possível usar o Teams no modo Ilhas sem híbrido, a transição para o modo TeamsOnly não pode ser feita até que o usuário seja movido do Skype for Business local para o Skype for Business Online (usando [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)). Para obter mais informações, consulte [Configure hybrid connectivity](/skypeforbusiness/hybrid/configure-hybrid-connectivity).

- Se sua organização tiver o Skype for Business Server e você não tiver configurado a conectividade híbrida, mas ainda quiser usar o Teams, para administrar a funcionalidade do Teams, você deve usar uma conta administrativa que tenha um domínio .onmicrosoft.com. 

- Os usuários do Teams que têm uma conta do Skype for Business local (ou seja, eles ainda não foram movidos para a nuvem usando Move-CsUser) não podem interoperar com nenhum usuário do Skype for Business, nem podem federar com usuários externos. Essa funcionalidade só estará disponível quando os usuários são movidos para a nuvem (no modo Ilhas ou como usuários do TeamsOnly). 

- Se você tiver usuários com contas do Skype for Business no local, não poderá atribuir o modo TeamsOnly no nível do locatário. Primeiro, você deve mover todos os usuários com contas locais do Skype for Business para a nuvem usando e desabilitar a migração híbrida para concluir a migração `Move-CsUser` [para a nuvem.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` não funcionará no nível do locatário se um registro DNS de descoberta lyncdiscover for detectado que aponta para um local diferente do Office 365.

- Você deve garantir que seus usuários estejam sincronizados corretamente no Azure AD com os atributos corretos do Skype for Business. Esses atributos são todos prefixos com "msRTCSIP-". Se os usuários não estiverem sincronizados corretamente com o Azure AD, as ferramentas de gerenciamento no Teams não poderão gerenciar esses usuários. (Por exemplo, você não poderá atribuir políticas do Teams a usuários locais, a menos que esteja sincronizando corretamente esses atributos.) Para obter mais informações, [consulte Configure Azure AD Connect for Teams and Skype for Business](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Para criar um novo usuário do TeamsOnly ou do Skype for Business Online em uma organização híbrida, primeiro você deve habilitar o usuário no *Skype for Business Server* local e, em seguida, mover o usuário do local para a nuvem usando Move-CsUser.  A criação do usuário no local primeiro garante que outros usuários locais restantes do Skype for Business sejam capazes de roteá-lo para o usuário recém-criado. Depois que todos os usuários foram movidos online, não é mais necessário habilitar os usuários no local.

- Quando um usuário é movido do local para a nuvem, as reuniões organizadas por esse usuário são migradas para o Skype for Business Online ou o Teams, dependendo se a opção -MoveToTeams está especificada ou não.

- Se quiser exibir notificações no cliente Skype for Business para usuários locais, use TeamsUpgradePolicy no toolset local. Somente o parâmetro NotifySfbUsers é relevante para usuários locais.  Os usuários locais recebem seu modo das instâncias online do TeamsUpgradePolicy. Consulte as anotações [em Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Todos os novos locatários criados após 3 de setembro de 2019 são criados como locatários do TeamsOnly, a menos que a organização já tenha uma implantação local do Skype for Business Server. A Microsoft usa registros DNS para identificar organizações locais do Skype for Business Server. Se sua organização tiver o Skype for Business Server local sem entradas DNS públicas, você precisará chamar o Suporte da Microsoft para ter seu novo locatário rebaixado. 

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
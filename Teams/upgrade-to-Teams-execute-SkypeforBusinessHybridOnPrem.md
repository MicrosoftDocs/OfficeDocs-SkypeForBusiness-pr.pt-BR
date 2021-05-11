---
title: Atualizar Skype for Business local para Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Saiba como atualizar sua organização para Microsoft Teams de uma implantação Skype for Business local.
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
ms.openlocfilehash: d323760d4187730b0ae83d45021df44230a982cd
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306045"
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

Se você tiver implantado o Skype for Business Server ou o Microsoft Lync no local e sua organização quiser atualizar para o Teams, siga as diretrizes neste artigo. Você precisa configurar a conectividade híbrida com sua organização Microsoft 365 ou Office 365 e determinar os requisitos de coexistência se estiver movendo seus usuários para Teams em fases.

Antes de começar, os profissionais de [](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) TI e os administradores devem revisar as considerações importantes para as organizações com Skype for Business Server locais mais adiante neste artigo.

> [!IMPORTANT]
> O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams. Lembre-se de que uma atualização bem-sucedida alinha a preparação técnica e do usuário, portanto, certifique-se de aproveitar as diretrizes aqui enquanto você navega sua jornada até Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Etapa 1: Configurar conectividade híbrida 

O principal pré-requisito para atualizar seus usuários locais para Teams é configurar a conectividade híbrida para sua implantação Skype for Business Server local. 

Comece lendo [Plano de conectividade híbrida](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) e siga as tarefas descritas em Configurar conectividade [híbrida](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Etapa 2: Definir o modo de coexistência de transição (opcional)

A coexistência e a interoperabilidade entre Skype for Business e Teams clientes e usuários são definidas Teams modos de atualização.  Por padrão, as organizações estão no modo Ilhas, o que permite que os usuários usem clientes Teams e Skype for Business lado a lado.

Para uma organização mudar para Teams, o modo TeamsOnly é o destino final para cada usuário, embora nem todos os usuários precisem ser atribuídos ao TeamsOnly (ou a qualquer outro modo) ao mesmo tempo.

Antes de os usuários chegarem ao modo TeamsOnly, as organizações podem, opcionalmente, usar qualquer um dos modos de coexistência do Skype for Business para garantir uma comunicação previsível entre usuários que estão no modo TeamsOnly e usuários que ainda não estão.  O objetivo dos modos de coexistência do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) é fornecer uma experiência simples e previsível para os usuários finais à medida que as organizações migram de Skype for Business para Teams. 

Quando um usuário está em qualquer um dos modos Skype for Business, todos os chats de entrada e chamadas são roteados para o cliente Skype for Business usuário. Para evitar confusão do usuário final e garantir o roteamento adequado, a funcionalidade de chamada e de chat no cliente Teams é desabilitada quando um usuário está em qualquer um dos modos Skype for Business de usuário. Da mesma forma, o agendamento de reunião no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab e explicitamente habilitados quando um usuário está no modo SfBWithTeamsCollabAndMeetings.

Dependendo dos requisitos, você pode atribuir o modo de coexistência apropriado com base no caminho de atualização escolhido pela sua organização. Para obter mais informações, consulte Diretrizes de migração e [interoperabilidade](migration-interop-guidance-for-teams-with-skype.md) para organizações que usam Teams em conjunto com Skype for Business e Definindo suas configurações de [coexistência e atualização.](./setting-your-coexistence-and-upgrade-settings.md)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Etapa 3: Mover usuários de Skype for Business local para Teams Somente

Em última análise, você vai querer mover seus usuários para o modo TeamsOnly. Isso pode envolver uma ou duas etapas, dependendo do ambiente local.  

Para obter mais informações, consulte [Move users between on-premises and the cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and Move users from [on-premises to Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Etapa 4: Desabilitar o híbrido para concluir sua migração para a nuvem

Depois de ter movido todos os usuários do local para a nuvem, você pode desmantelar a implantação local Skype for Business local. Para obter mais informações, consulte [Desabilitar a migração híbrida para concluir a migração para a nuvem](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).


## <a name="phone-system-and-pstn-connectivity-options"></a>Sistema de Telefonia e opções de conectividade PSTN

Sistema de Telefonia com Teams é suportado depois que o usuário está no modo TeamsOnly. (Se o usuário estiver no modo Ilhas, Sistema de Telefonia só será suportado com Skype for Business.) 

### <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

Ao considerar as opções de conectividade PSTN (Rede Telefônica Pública Comutado), há dois cenários possíveis ao mudar do Skype for Business local para o modo TeamsOnly:

- Um usuário em Skype for Business local com Enterprise Voice, que estará mudando para online e usando um plano de Chamada da Microsoft. Migrar esse usuário para Teams requer mover a conta de Skype for Business local do usuário para a nuvem e coordenar essa movimentação com A) a porta do número de telefone desse usuário para um Plano de Chamadas da Microsoft ou B) atribuindo um novo número de assinante de regiões disponíveis.  Para obter mais informações, consulte From Skype for Business Server local, with [Enterprise Voice, to Microsoft Calling Plan](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Um usuário em Skype for Business local com Enterprise Voice, que estará mudando para online e mantendo a conectividade PSTN local. Migrar esse usuário para Teams requer mover a conta de Skype for Business local do usuário para a nuvem e coordenar essa movimentação com a migração do usuário para Roteamento Direto. Para obter mais informações, [consulte From Skype for Business Server local, with Enterprise Voice, to Direct Routing](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considerações importantes para organizações com Skype for Business Server locais

- Os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:
    - [Coexistência de Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [Modos de coexistência - Referência](migration-interop-guidance-for-teams-with-skype.md)
    - [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)

- Configurar o Skype for Business híbrido é um pré-requisito para migrar para o modo TeamsOnly. Embora seja possível que os usuários locais Skype for Business Server usem o Teams no modo ilhas sem híbrido, a transição para o modo TeamsOnly não pode ser feita sem mover o usuário para a nuvem usando [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud), para o qual a conectividade híbrida é necessária. Para obter mais informações, consulte [Configure hybrid connectivity](/skypeforbusiness/hybrid/configure-hybrid-connectivity). Além disso, a próxima aposentadoria do Skype for Business Online não alterará esse requisito. Para que as organizações mudem de Skype for Business Server para Teams, elas ainda devem configurar e configurar híbridos usando o mesmo conjunto de ferramentas, exatamente como antes *da reforma*.

- Para mover um usuário local para a nuvem, use nas ferramentas `Move-CsUser` de administração locais. No momento, se essa opção não for especificada, os usuários transirem da sua residência no Skype for Business Server local para o Skype for Business Online, seu modo permanecerá inalterado e as reuniões organizadas no Skype for Business Server serão migradas para o Skype for Business Online. Devido à próxima aposentadoria do Skype for Business Online, em breve não será mais necessário especificar a opção para mover os usuários diretamente do local para o `-MoveToTeams` `Move-CsUser` TeamsOnly.  Após a reforma, ao mover um usuário do local para a nuvem com , os usuários serão atribuídos automaticamente ao modo TeamsOnly e suas reuniões do local serão automaticamente convertidas em reuniões Teams, como se o , independentemente de a opção ser `Move-CsUser` `-MoveToTeams switch had been specified` realmente especificada. Esperamos lançar essa funcionalidade antes da aposentadoria real de 31 de julho de 2021.

- Se sua organização tiver Skype for Business Server e você não tiver configurado a conectividade híbrida, mas ainda quiser usar o Teams, para administrar uma funcionalidade Teams, você deve usar uma conta administrativa que tenha um domínio .onmicrosoft.com. Sem conectividade híbrida, as ferramentas administrativas não reconhecerão seus domínios locais. 

- Teams usuários que têm uma conta Skype for Business local (ou seja, eles ainda não foram movidos para a nuvem usando Move-CsUser) não podem interoperar com nenhum usuário Skype for Business, nem podem federar com usuários externos. Essa funcionalidade só estará disponível quando os usuários são movidos para a nuvem e são usuários do TeamsOnly. 

- Se você tiver usuários com contas Skype for Business local ou se ainda tiver um registro DNS de descoberta lyncdiscover para uma implantação local, não será possível atribuir o modo TeamsOnly no nível de locatário. Primeiro, você deve mover todos os usuários com contas Skype for Business locais para a nuvem usando e, em seguida, seguir as etapas descritas em Desabilitar a migração híbrida para concluir a migração para a nuvem que inclui a remoção de entradas `Move-CsUser` DNS. [](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`não funcionará no nível do locatário se um registro DNS de descoberta lyncdiscover for detectado que aponta para um local diferente de Office 365.

- Você deve garantir que seus usuários estejam sincronizados corretamente no Azure AD com os atributos Skype for Business corretos. Esses atributos são todos prefixos com "msRTCSIP-". Se os usuários não estiverem sincronizados corretamente com o Azure AD, as ferramentas de gerenciamento no Teams não poderão gerenciar esses usuários. (Por exemplo, você não poderá atribuir políticas de Teams a usuários locais, a menos que esteja sincronizando corretamente esses atributos.) Para obter mais informações, [consulte Configure Azure AD Conexão for Teams and Skype for Business](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Para criar um novo usuário do TeamsOnly ou Skype for Business Online em uma organização híbrida, primeiro você deve habilitar o usuário no Skype for Business Server local e, em seguida, mover o usuário do local para a nuvem usando Move-CsUser.  A criação do usuário no local primeiro garante que qualquer outro usuário local restante Skype for Business os usuários poderão roteá-lo para o usuário recém-criado. Depois que todos os usuários foram movidos online, não é mais necessário habilitar os usuários no local.

- Se quiser exibir notificações no cliente Skype for Business para usuários locais, use TeamsUpgradePolicy no toolset local. Somente o parâmetro NotifySfbUsers é relevante para usuários locais.  Os usuários locais recebem seu modo das instâncias online do TeamsUpgradePolicy. Consulte as anotações [em Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Todos os novos locatários criados após 3 de setembro de 2019 são criados como locatários do TeamsOnly, a menos que a organização já tenha uma implantação local de Skype for Business Server. A Microsoft usa registros DNS para identificar organizações Skype for Business Server locais. Se a sua organização tiver uma Skype for Business Server local sem entradas DNS públicas, você precisará chamar o Suporte da Microsoft para que seu novo locatário seja rebaixado. 

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

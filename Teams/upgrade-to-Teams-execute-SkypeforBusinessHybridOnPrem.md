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
ms.localizationpriority: medium
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
ms.openlocfilehash: c4b233978b9f9edf0aabbdfb8f9b24ff55a234cc
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681362"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Atualizar do Skype for Business local para o Teams

![Diagrama de jornada de atualização, enfatizando a implantação e a implementação.](media/upgrade-banner-deployment.png "Estágios do percurso de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação do seu percurso de atualização. Antes de continuar, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](./upgrade-prepare-environment.md)
- [Preparou sua organização](./upgrade-prepare-organization.md)
- [Conduz um piloto](./pilot-essentials.md)

Se você implantou o Skype for Business Server ou o Microsoft Lync Server local e sua organização deseja atualizar para o Teams, siga as diretrizes neste artigo. Você deve configurar a conectividade híbrida com sua Microsoft 365, conforme descrito em Planejar conectividade híbrida entre Skype for Business Server [e Teams](/skypeforbusiness/hybrid/plan-hybrid-connectivity).

Antes de começar, você também deve examinar considerações importantes para organizações [com Skype for Business Server locais](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) mais adiante neste artigo.

> [!IMPORTANT]
> Skype for Business Online foi desativado em 31 de julho de 2021. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams. Lembre-se de que uma atualização bem-sucedida alinha a preparação técnica e do usuário, portanto, lembre-se de aproveitar essas diretrizes à medida que você navega sua jornada até Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Etapa 1: Configurar a conectividade híbrida

O principal pré-requisito para atualizar seus usuários locais para o Teams é configurar a conectividade híbrida para sua implantação Skype for Business Server local.

Comece lendo Plano [de conectividade híbrida](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) e siga as tarefas descritas em [Configurar conectividade híbrida](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Etapa 2: Definir o modo de coexistência de transição (opcional)

Coexistência e interoperabilidade entre Skype for Business e Teams e usuários são [definidos por modos de coexistência](migration-interop-guidance-for-teams-with-skype.md). As organizações híbridas estão por padrão no modo Ilhas. O modo Ilhas permite que os usuários usem clientes Teams e Skype for Business lado a lado. As organizações podem, opcionalmente, usar outros modos de coexistência para fornecer uma experiência previsível para os usuários finais à medida que as organizações fazem a transição de Skype for Business para Teams. Seja qual for o modo que uma organização usa para seus usuários locais, quando esses usuários são movidos do local para a nuvem, eles se tornam TeamsOnly (e não podem ter nenhum outro modo).  Desde que os usuários ainda estejam usando Skype for Business Server, eles podem ser atribuídos a qualquer modo diferente do TeamsOnly. Se necessário, os usuários do TeamsOnly podem ser movidos de volta para o local, o que resultaria no recebimento da política global do locatário do TeamsUpgradePolicy.

Quando um usuário está em qualquer um dos modos Skype for Business, todos os chats e chamadas de entrada são roteados para o cliente Skype for Business usuário. Para evitar confusão do usuário final e garantir o roteamento adequado, a funcionalidade de chamada e chat no cliente Teams está desabilitada para um usuário que recebe qualquer um dos modos *de Skype for Business.* O agendamento de reunião no Teams é desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab e habilitados quando um usuário está no modo SfBWithTeamsCollabAndMeetings.

Dependendo de seus requisitos, você pode atribuir o modo de coexistência apropriado com base no caminho de atualização escolhido pela sua organização. Para obter mais informações, consulte as diretrizes de [migração e interoperabilidade](migration-interop-guidance-for-teams-with-skype.md) para organizações que usam Teams em conjunto com o Skype for Business e definindo suas [configurações de coexistência e atualização](./setting-your-coexistence-and-upgrade-settings.md).

## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Etapa 3: Mover usuários Skype for Business local para Teams somente

Recentemente, a Microsoft simplificou o processo para mover usuários para o TeamsOnly. Esse processo agora é uma única etapa, independentemente da versão do Skype for Business Server ou do Lync Server 2013 que você está usando. Para obter mais informações, consulte [Mover](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) usuários entre o local e a nuvem e Mover usuários do local para o [Teams](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>Etapa 4: Concluir a migração para a nuvem desabilitando a migração híbrida e desativando as configurações Skype for Business

Depois de migrar todos os usuários do local para a nuvem, você poderá desativar a implantação Skype for Business local. Para obter mais informações, [consulte Desativar seu](/skypeforbusiness/hybrid/decommission-on-prem-overview) ambiente de Skype for Business local.

## <a name="phone-system-and-pstn-connectivity-options"></a>Sistema de Telefonia e opções de conectividade PSTN

Sistema de Telefonia com Teams é compatível depois que o usuário está no modo TeamsOnly. (Se o usuário estiver no modo Ilhas, Sistema de Telefonia só será compatível com Skype for Business.)

### <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

Ao considerar as opções de conectividade PSTN (Rede Telefônica Pública Comulitada), há dois cenários possíveis ao migrar do Skype for Business local para o modo TeamsOnly:

- Um usuário em Skype for Business local com o Enterprise Voice, que será migrado para online e usando um plano de Chamada da Microsoft. Migrar esse usuário para o Teams requer mover a conta do Skype for Business local do usuário para a nuvem e coordenar essa movimentação com A) a porta do número de telefone desse usuário para um Plano de Chamada da Microsoft ou B) atribuindo um novo número de assinante de regiões disponíveis.  Para obter mais informações, [consulte Do Skype for Business Server local, com o Enterprise Voice, para o Plano de Chamadas da Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Um usuário Skype for Business local com o Enterprise Voice, que será movido para online e manterá a conectividade PSTN local. Migrar esse usuário para Teams requer mover a conta de Skype for Business local do usuário para a nuvem e coordenar essa movimentação com a migração do usuário para o Roteamento Direto. Para obter mais informações, [consulte Skype for Business Server local, com Enterprise Voice, para Roteamento Direto](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).

## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Considerações importantes para organizações com Skype for Business Server locais

- A configuração Skype for Business híbrido é um pré-requisito para migrar para o modo TeamsOnly. É possível que os usuários locais Skype for Business Server usem Teams no modo Ilhas sem híbrido. No entanto, a transição para o modo TeamsOnly não pode ser feita sem mover o usuário para a nuvem usando [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud), para o qual a conectividade híbrida é necessária. Para obter mais informações, consulte [Configurar conectividade híbrida](/skypeforbusiness/hybrid/configure-hybrid-connectivity). A próxima desativação do Skype for Business Online não alterará esse requisito. Para que as organizações mudem de Skype for Business Server para Teams, elas ainda devem configurar e configurar o híbrido usando o mesmo conjunto de ferramentas, exatamente como antes *da desativação*.

- Para mover um usuário local para a nuvem, use `Move-CsUser` as ferramentas de administração local. Você não precisa mais especificar a opção `-MoveToTeams` para mover os usuários diretamente do local para o TeamsOnly. Os usuários recebem automaticamente o modo TeamsOnly e suas reuniões locais são convertidas automaticamente em Teams reuniões`-MoveToTeams`, independentemente de a opção ser especificada.

- Se sua organização tiver Skype for Business Server e você não tiver configurado a conectividade híbrida, mas ainda quiser usar o Teams, para administrar a funcionalidade do Teams, use uma conta administrativa que tenha um domínio .onmicrosoft.com. Sem conectividade híbrida, as ferramentas administrativas não reconhecerão seus domínios locais.

- Teams usuários que têm uma conta do Skype for Business local (ou seja, eles ainda não foram movidos para a nuvem usando Move-CsUser) não podem interoperar com nenhum usuário do Skype for Business, nem podem federar com usuários externos. Essa funcionalidade só estará disponível quando os usuários forem movidos para a nuvem e forem usuários do TeamsOnly.

- Se você tiver usuários com contas Skype for Business locais ou se ainda tiver um registro DNS de descoberta lyncdiscover para uma implantação local, não poderá atribuir o modo TeamsOnly no nível do locatário. Primeiro, você deve mover todos os usuários com contas Skype for Business locais para a nuvem usando `Move-CsUser`. Em seguida, siga as etapas descritas em [Desabilitar híbrido para concluir a migração](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid) para a nuvem, que inclui a remoção de entradas DNS. `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`não funcionará no nível do locatário se for detectado um registro DNS de descoberta lyncdiscover que aponte para um local diferente de Office 365.

- Você deve garantir que os usuários sejam sincronizados corretamente no Azure AD com os atributos Skype for Business corretos. Esses atributos são todos prefixos com "msRTCSIP-". Se os usuários não forem sincronizados corretamente com Azure AD, as ferramentas de gerenciamento no Teams não poderão gerenciar esses usuários. (Por exemplo, você não poderá atribuir políticas de Teams a usuários locais, a menos que esteja sincronizando corretamente esses atributos.) Para obter mais informações, [consulte Configurar Azure AD Conexão para Teams e Skype for Business](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Para criar um novo TeamsOnly em uma organização híbrida, primeiro você deve habilitar o usuário no *Skype for Business Server* local e, em seguida, mover o usuário do local para a nuvem usando Move-CsUser.  Criar o usuário local primeiro garante que qualquer outro usuário local restante Skype for Business possa rotear para o usuário recém-criado. Depois *que* todos os usuários tiverem sido movidos online, não será mais necessário primeiro habilitar os usuários no local.

- Se você quiser exibir notificações no cliente Skype for Business para usuários locais, deverá usar o TeamsUpgradePolicy no conjunto de ferramentas local. Somente o parâmetro NotifySfbUsers é relevante para usuários locais.  Os usuários locais recebem o modo das instâncias online do TeamsUpgradePolicy. Consulte as anotações [em Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

> [!NOTE]
> Todos os novos locatários criados após 3 de setembro de 2019 são criados como locatários do TeamsOnly, a menos que a organização já tenha uma implantação local de Skype for Business Server. A Microsoft usa registros DNS para identificar as organizações Skype for Business Server locais. Para obter mais informações, consulte [as implicações de DNS para organizações locais que se tornam híbridas](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid).

- Os artigos a seguir descrevem conceitos importantes de atualização e comportamentos de coexistência:
  - [Coexistência de Teams e Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
  - [Modos de coexistência – Referência](migration-interop-guidance-for-teams-with-skype.md)
  - [Experiência e conformidade do cliente do Teams a modos de coexistência](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>Links relacionados

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Configurar a conectividade híbrida entre Skype for Business Server e Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover os usuários entre um ambiente local e a nuvem](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Usando o Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

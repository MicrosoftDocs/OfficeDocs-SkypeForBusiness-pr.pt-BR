---
title: Planejar a governança em equipes - Teams da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Saiba mais sobre como planejar a implementação de recursos de governança em equipes.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 048b9dd09e9309c4aaaf1af3b92d7e24f280d088
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883248"
---
# <a name="plan-for-governance-in-teams"></a>Plano de governança em equipes

As equipes fornece um rico conjunto de ferramentas para implementar qualquer recursos de governança, sua organização pode exigir. Este artigo o orienta profissionais de TI para fazer as direita perguntas para determinar os requisitos de governança e como atendê-las. 

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Criação de grupo e da equipe, de nomeação, classificação e acesso de convidado

Sua organização pode exigir que você implemente estrito controles em como equipes devem ser nomeadas e classificadas, se os convidados podem ser adicionados como membros da equipe e quem pode criar equipes. Você pode configurar cada uma dessas áreas usando o Windows Azure Active Directory (AD Azure). 

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Pontos de decisão|<ul><li>Sua organização requer uma convenção de nomenclatura específica para equipes?</li><li>Criadores de equipe preciso a capacidade de atribuir classificações específicas da organização para equipes?</li><li>Você precisa restringir a capacidade de adicionar convidados às equipes em uma base por equipe?</li><li>Sua organização requer limitar quem pode criar equipes?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Próximos passos|<ul><li>Documente os requisitos da sua organização para a criação de equipe, de nomeação, classificação e acesso de convidado.</li><li>Você planeja implementar esses requisitos como parte da sua distribuição de equipes.</li><li>Se comunicar e publicar suas políticas para informar os usuários de equipes do comportamento que eles podem esperar.</li></ul>|

> [!TIP]
Use a tabela a seguir para capturar requisitos da sua organização.
|Recurso |Detalhes |Premium do Azure AD <br> é necessária uma licença |Decisão |
|---------|---------|---------|---------|
|Diretiva de nomeação de equipe | Use personalizada, baseada no prefixo-sufixo palavras de bloqueado. |P1 |TBD |
|Classificação de equipe |Atribua classificações de equipes. |P1 |TBD |
|Acesso de convidado da equipe |Permitir ou impedir que os convidados sendo adicionado às equipes. |Não |TBD |
|Criação de equipes |Limite de criação de equipe aos administradores. |Não |TBD|
|Criação de equipes |Limite de criação de equipe para membros do grupo de segurança. |P1 |TBD|

> [!NOTE]
> Para ajudá-lo a planejar com antecedência, [Saiba mais sobre como definir essas políticas e quais licenças exigem](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).

> [!NOTE]
> Limitando a criação de grupo e da equipe pode reduzir a produtividade dos usuários, porque muitos serviços do Office 365 exigem que os grupos seja criado para o serviço de função. Para obter informações adicionais, navegue até e expanda [por que controlar quem cria grupos do Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Informações adicionais

Depois que você determinou seus requisitos, você pode implementá-las usando os controles do Windows Azure AD. Para obter orientações técnicas sobre como implementar essas configurações, consulte:

-   [Cmdlets do Windows azure Active Directory para definir as configurações de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

-   [Impor uma diretiva de nomeação para Office 365 grupos no Active Directory do Windows Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).

-   [Diretiva de nomenclatura de grupos do office 365](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).


## <a name="group-and-team-expiration-retention-and-archiving"></a>Expiração de grupo e da equipe, retenção e arquivamento

A organização poderá ter requisitos adicionais para a configuração de diretivas de expiração, retenção, e arquivamento às equipes e às equipes de dados. Você pode configurar diretivas de expiração de grupo para gerenciar automaticamente o ciclo de vida das diretivas de grupo e de retenção para preservar ou excluir informações conforme necessário, e você pode arquivar as equipes (defini-las para o modo somente leitura) para preservar a um modo de exibição no momento de uma equipe que não é mais ativo.

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Sua organização requer a especificação de uma data de validade para equipes?</li><li>Sua organização exija dados específicos políticas de retenção a ser aplicada às equipes?</li><li>Sua organização espera exigir a capacidade de arquivar equipes inativas para preservar o conteúdo em um estado somente leitura?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>Próximos passos|<ul><li>Requisitos da sua organização para expiração de equipe, retenção de dados e arquivamento de documentos.</li><li>Você planeja implementar esses requisitos como parte de sua distribuição de equipes.</li><li>Se comunicar e publicar suas políticas para informar os usuários de equipes do comportamento que eles podem esperar.</li></ul>|

> [!TIP]
Use a tabela a seguir para capturar requisitos da sua organização.
|Recurso |Detalhes |Premium do Azure AD <br>é necessária uma licença |Decisão |
|---------|---------|---------|---------|
|Política de expiração |Gerencie o ciclo de vida dos grupos do Office 365, definindo uma política de expiração. |P1 |TBD|
|Política de retenção |Reter ou excluir dados (mensagens de canal de equipes e arquivos de canal) por um período de tempo específico, definindo políticas de retenção para equipes na Central de segurança e conformidade. **Observação**: usar esse recurso exige licenciamento do Office 365 Enterprise E3 ou acima. |Não |TBD |
|Arquivamento e restauração |Arquive uma equipe quando ele não está mais ativo, mas deseja mantê-la para referência ou reativá-lo no futuro. |Não |TBD |

> [!Note]
> Expiração de grupo é um recurso do Windows Azure AD Premium. Para que este recurso esteja disponível, seu inquilino deve ter uma assinatura para o Windows Azure AD Premium e licenças para o administrador que configura as configurações e os membros dos grupos afetados.

#### <a name="additional-information"></a>Informações adicionais

Para obter orientações técnicas sobre como implementar essas configurações, consulte:

-   [Configurar a expiração de grupos do Office 365](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

-   [Configurar políticas de retenção de equipes](security-compliance-overview.md#retention-policies).

-   [Arquivo morto ou restauração uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).


## <a name="teams-feature-management"></a>Gerenciamento de recurso de equipes

Outro aspecto importante da governança e gerenciamento do ciclo de vida para equipes é a capacidade de controlar quais recursos os usuários terão acesso ao. Você pode gerenciar mensagens, reuniões e chamar recursos, no nível de locatário do Office 365 ou por usuário. 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Sua organização requer limitar os recursos de equipes para seu locatário todo?</li><li>Sua organização exigir a limitar os recursos de equipes para usuários específicos?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>Próximos passos|<ul><li>Requisitos da sua organização para limitar os recursos de equipes no nível de usuário e de locatário do documento.</li><li>Você planeja implementar seus requisitos específicos como parte de sua distribuição de equipes.</li><li>Se comunicar e publicar suas políticas para informar os usuários de equipes do comportamento que eles podem esperar.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Áreas de foco de gerenciamento de recursos de equipes

As equipes fornece recursos granulares para controlar mensagens, reuniões, chamada e live recursos de eventos e mais algumas, por meio de políticas. Diferentes políticas podem ser aplicadas a todos os usuários, por padrão, ou por usuário conforme exigido pela sua organização. 

Para obter listas detalhadas de todas as configurações, incluindo orientações técnicas sobre como implementá-las para sua organização, consulte os seguintes artigos:

-   [Gerenciar recursos de Teams da Microsoft em sua organização do Office 365](enable-features-office-365.md)
-   [Gerenciar equipes durante a transição para o novo Teams da Microsoft e Skype para Business Admin Center](manage-teams-skypeforbusiness-admin-center.md)
-   [Gerenciar políticas de reunião em equipes](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a>Segurança e conformidade

As equipes foi criada com a segurança avançada e recursos de conformidade do Office 365 e oferece suporte a auditoria e relatórios, pesquisa de conteúdo de conformidade, descoberta eletrônica, retenção Legal e políticas de retenção. 

> [!Important]
> Se sua organização tiver requisitos de segurança e conformidade, analise o conteúdo de detalhadas fornecido sobre este tópico no artigo de [Visão geral de segurança e conformidade no equipes da Microsoft](security-compliance-overview.md).

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
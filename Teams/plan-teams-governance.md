---
title: Planejar a governança em equipes ‒ Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Neste artigo, você aprenderá sobre como planejar a implementação de recursos de governança no Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ab70daffa91b534f15b032cd0c137efe89abb438
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117809"
---
# <a name="plan-for-governance-in-teams"></a>Plano de governança no Teams

O Teams fornece um conjunto rico de ferramentas para implementar todos os recursos de governança que sua organização possa exigir. Este artigo orienta os profissionais de IT a fazer as perguntas certas para determinar seus requisitos de governança e como atender a eles. 

> [!Tip] 
> Assista à sessão a seguir para saber mais sobre Governança no Microsoft Teams: [Governança, gerenciamento e ciclo de vida no Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Criação de grupo e equipe, nomenis, classificação e acesso de convidados

Sua organização pode exigir que você implemente controles estritos sobre como as equipes são nomeadas e classificadas, se os convidados podem ser adicionados como membros da equipe e quem pode criar equipes. Você pode configurar essas áreas usando o Azure Active Directory (Azure AD) e rótulos de sensibilidade. 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Pontos de decisão|<ul><li>Sua organização exige uma convenção de nomenisção específica para equipes?</li><li>Os criadores de equipe precisam da capacidade de atribuir classificações específicas da organização às equipes?</li><li>Você precisa restringir a capacidade de adicionar convidados às equipes por equipe?</li><li>Sua organização exige limitação de quem pode criar equipes?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente os requisitos da sua organização para criação, nomenisão, classificação e acesso de convidados da sua organização.</li><li>Planeje implementar esses requisitos como parte da implantação do Teams.</li><li>Comunique e publique suas políticas para informar os usuários do Teams sobre o comportamento que eles podem esperar.</li></ul>|

> [!NOTE]
> Para ajudá-lo a planejar o futuro, [saiba mais sobre como definir essas políticas e quais licenças elas exigem](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).
> 
> [!NOTE]
> Limitar a criação de grupo e equipe pode reduzir a produtividade dos usuários, pois muitos serviços do Microsoft 365 e do Office 365 exigem que os grupos sejam criados para que o serviço funcione. Para obter informações adicionais, navegue até e expanda Por que o controle que cria grupos do [Microsoft 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Informações adicionais

Depois de determinar seus requisitos, você pode implementá-los usando controles do Azure AD. Para obter orientações técnicas sobre como implementar essas configurações, consulte:

- [Cmdlets do Azure Active Directory para configurar configurações de grupo](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Impor uma política de nomenização para grupos do Microsoft 365 no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Política de nomenis do Microsoft 365 Groups](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Usar rótulos de sensibilidade para proteger conteúdo no Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Opções de fim do ciclo de vida para grupos, equipes e Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Expiração, retenção e arquivamento de grupo e equipe

Sua organização pode ter requisitos adicionais para definir políticas de expiração, retenção e arquivamento de equipes e dados de equipes (mensagens de canal e arquivos de canal). Você pode configurar políticas de expiração de grupo para gerenciar automaticamente o ciclo de vida do grupo e políticas de retenção para preservar ou excluir informações conforme necessário, e você pode arquivar as equipes (defini-las como modo somente leitura) para preservar um modo de exibição point-in-time de uma equipe que não está mais ativa. Observe que as equipes arquivadas continuam com a política de expiração aplicada e podem ser excluídas, a menos que sejam excluídas ou renovadas.

|-          |-           |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Sua organização exige a especificação de uma data de expiração para as equipes?</li><li>Sua organização exige que políticas de retenção de dados específicas sejam aplicadas às equipes?</li><li>Sua organização espera exigir a capacidade de arquivar equipes inativas para preservar o conteúdo em um estado somente leitura?</li></ul>|
| ![Um ícone representando os próximos passos](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Documente os requisitos da sua organização para expiração de equipe, retenção de dados e arquivamento.</li><li>Planeje implementar esses requisitos como parte da implantação do Teams.</li><li>Comunique e publique suas políticas para informar os usuários do Teams sobre o comportamento que eles podem esperar.</li></ul>|

> [!TIP]
> Use a tabela a seguir para capturar os requisitos da sua organização.

|Recursos |Detalhes |Licença do Azure AD Premium necessária |Decisão |
|---------|---------|---------|---------|
|Política de expiração |Gerencie o ciclo de vida dos grupos do Microsoft 365 definindo uma política de expiração. |P1 |TBD|
|Política de retenção |Reter ou excluir dados para um período de tempo específico definindo políticas de retenção para o Teams no centro de conformidade & segurança. **Observação**: o uso desse recurso requer licenciamento do Microsoft 365 ou Office 365 Enterprise E3 ou superior. |Não |TBD |
|Arquivar e restaurar |Arquivar uma equipe quando ela não estiver mais ativa, mas você deseja mantê-la por perto para referência ou reativar no futuro. |Não |TBD |

> [!Note]
> A expiração de grupo é um recurso do Azure AD Premium. Para que esse recurso seja disponibilizado, o locatário deve ter uma assinatura do Azure AD Premium e licenças para o administrador que configura as configurações e os membros dos grupos afetados.

#### <a name="additional-information"></a>Informações adicionais

Para obter orientações técnicas sobre como implementar essas configurações, consulte:

- [Configurar a expiração de grupos do Microsoft 365](/azure/active-directory/users-groups-roles/groups-lifecycle).

- [Configurar políticas de retenção do Teams.](retention-policies.md)

- [Arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).

## <a name="group-and-team-membership-management"></a>Gerenciamento de associação de grupo e equipe

Gerenciar consistentemente membros de grupos com base em projeto ou restritos são necessários para equipes que exigem integração rápida e offboard ou usuários e convidados. Sua organização também pode precisar garantir que todos os membros atuais tenham a justificativa de negócios para estar em uma equipe. Gerenciar membros pode ser difícil porque os proprietários de equipe podem sair e os usuários geralmente não deixam grupos por conta própria quando um projeto termina ou quando eles alteram funções. A melhor maneira de gerenciar a associação de grupo que permite aos usuários obter acesso quando necessário, mas garantir que o grupo não tenha um risco de acesso inadequado é por meio de dois processos distrital: gerenciamento de direitos e revisões de acesso.

[O gerenciamento de](/azure/active-directory/governance/entitlement-management-overview) direitos permite que você delegar a alguém, como um gerente de projeto, colete todos os recursos necessários, incluindo associações de equipes, em um único pacote. Eles também podem definir quem pode fazer solicitações: usuários em seu locatário ou de outras organizações conectadas. O gerente do projeto receberá solicitações de acesso em seus emails e aprovará ou negará solicitações no portal MyAccess. Os administradores podem configurar as condições de acesso para incluir uma data de expiração ou período quando o usuário ou convidado será removido da equipe, a menos que o acesso seja renovado. Os administradores também podem configurar os grupos associados às equipes para participar de avaliações de acesso. Para [análises de acesso,](/azure/active-directory/governance/access-reviews-overview)os proprietários do grupo receberão lembretes regulares para revisar os membros de uma equipe. As avaliações do Access incluem recomendações, o que torna mais fácil para os proprietários do grupo passar pelo processo regular de atestado.

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Pontos de decisão | Sua organização exige um processo consistente para gerenciar a associação de uma ou mais equipes? <br> Sua organização exige que os proprietários, ou os próprios membros, justifiquem sua associação contínua a uma ou mais equipes regularmente? <br> Sua organização exige aprovação para usuários e convidados solicitarem acesso a recursos, incluindo equipes, grupos, sites do SharePoint e aplicativos? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Próximas etapas? | Documente os requisitos de suas organizações para cada equipe ou equipes específicas para o vencimento da associação.<br>Planeje como sua organização pode agrupar equipes, grupos, sites do SharePoint e aplicativos em pacotes de acesso.<br>Planeje quais pessoas, como o gerente do solicitante, um gerente de projeto, um patrocinador de uma organização conectada ou um agente de segurança em sua organização precisarão aprovar ou negar solicitações de acesso. |

> [!TIP]
> Use a tabela a seguir para capturar os requisitos da sua organização.

| Recursos | Detalhes | Licença do Azure AD Premium necessária | Decisão |
|:-|:-|:-|:-|
| Avaliações do Access | Avaliações de acesso à instalação para recertificar a associação de equipes específicas no intervalo regular | P2 | TBD |
| Gerenciamento de direitos | Pacote de acesso de instalação para permitir que usuários e convidados solicitem acesso às equipes | P2 | TBD |

> [!NOTE]
> Para ajudá-lo a planejar o futuro, [saiba mais sobre quais licenças elas exigem](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="additional-information"></a>Informações adicionais

Para obter orientações técnicas sobre como implementar essas configurações, consulte:

- [Gerenciamento de direitos](/azure/active-directory/governance/entitlement-management-overview)
- [Avaliações do Access](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Gerenciamento de recursos do Teams

Outro aspecto importante do gerenciamento de governança e ciclo de vida do Teams é a capacidade de controlar quais recursos seus usuários terão acesso. Você pode gerenciar recursos de mensagens, reuniões e chamada, no nível da organização do Microsoft 365 ou office 365 ou por usuário.


|-        |-        |
|---------|---------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Sua organização exige a limitação de recursos do Teams para todo o locatário?</li><li>Sua organização exige a limitação de recursos do Teams para usuários específicos?</li></ul>|
| ![Um ícone representando os próximos passos](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Documente os requisitos da sua organização para limitar os recursos do Teams no nível do locatário e do usuário.</li><li>Planeje implementar seus requisitos específicos como parte da implantação do Teams.</li><li>Comunique e publique suas políticas para informar os usuários do Teams sobre o comportamento que eles podem esperar.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Áreas de foco de gerenciamento de recursos do Teams

O Teams fornece recursos granulares para controlar recursos de mensagens, reuniões, chamada e eventos ao vivo e muito mais, por meio de políticas. Políticas diferentes podem ser aplicadas a todos os usuários por padrão ou por usuário, conforme exigido pela sua organização. 

Para obter listas detalhadas de todas as configurações, incluindo orientações técnicas sobre como implementá-las para sua organização, consulte os seguintes artigos:

- [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)
- [Gerenciar equipes durante a transição para o novo centro de administração do Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Canais privados no Microsoft Teams](private-channels.md)
- [Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md)
- [Gerenciar políticas de mensagens no Teams](messaging-policies-in-teams.md)
- [Gerenciar seus aplicativos no centro de administração do Microsoft Teams](manage-apps.md)

Além disso, você pode configurar a moderação para um canal e dar recursos de moderador a determinados usuários para que eles possam controlar quem pode criar postagens de canal e responder a eles. Confira [Configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md) para obter mais informações.

## <a name="security-and-compliance"></a>Segurança e conformidade

O Teams é criado com base nos recursos avançados de segurança e conformidade do Microsoft 365 e do Office 365 e oferece suporte a auditoria e relatórios, pesquisa de conteúdo de conformidade, descoberta por e-discovery, Retenção Legal e políticas de retenção.

> [!Important]
> Se sua organização tiver requisitos de conformidade e segurança, revise o conteúdo aprofundado fornecido sobre este tópico no artigo Visão geral da segurança e [conformidade no Microsoft Teams](security-compliance-overview.md).

## <a name="related-topics"></a>Tópicos relacionados

[Início rápido de governança para Teams](teams-adoption-governance-quick-start.md)

[Diretrizes de licenciamento do Microsoft 365 para conformidade & segurança](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
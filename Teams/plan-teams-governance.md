---
title: Planejar a governança em equipes ‒ Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Neste artigo, você aprenderá sobre como planejar a implementação de recursos de gestão no Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2180c819491b3067225ada993aec60ec052bc69f
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416906"
---
# <a name="plan-for-governance-in-teams"></a>Plano de governança no Teams

O Teams fornece um conjunto abrangente de ferramentas para implementar todos os recursos de gestão que sua organização possa exigir. Este artigo orienta os profissionais de EQUIPE a fazer as perguntas corretas para determinar seus requisitos de gestão e como encontrá-los. 

> [!Tip] 
> Assista à sessão a seguir para saber mais sobre Governança no Microsoft Teams: [Governança, gerenciamento e ciclo de vida no Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Criação, nomeação, classificação e acesso de convidado a grupos e equipes

Sua organização pode exigir que você implemente controles estritos sobre como as equipes são nomeadas e classificadas, se os convidados podem ser adicionados como membros da equipe e quem pode criar equipes. Você pode configurar essas áreas usando o Azure Active Directory (Azure AD) e rótulos de sensibilidade. 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Pontos de decisão|<ul><li>Sua organização exige uma convenção específica de nomenmenu para equipes?</li><li>Os criadores de equipe precisam da capacidade de atribuir classificações específicas da organização às equipes?</li><li>Você precisa restringir a capacidade de adicionar convidados às equipes por equipe?</li><li>Sua organização exige limitar quem pode criar equipes?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documente os requisitos da sua organização para criar, nomear, classificar e acessar convidados da equipe.</li><li>Planeje implementar esses requisitos como parte da implantação do Teams.</li><li>Comunique e publique suas políticas para informar os usuários do Teams sobre o comportamento que eles podem esperar.</li></ul>|

> [!TIP]
> Use a tabela a seguir para capturar os requisitos da sua organização.

|Recursos |Detalhes |Azure AD Premium <br> licença necessária |Decisão |
|---------|---------|---------|---------|
|Política de nomeação de equipe | Use palavras bloqueadas personalizadas baseadas em prefixo e sufixo. |P1 |Tbd |
|Classificação da equipe |Atribua classificações às equipes. |P1 |Tbd |
|Acesso de convidado da equipe |Permitir ou impedir que os convidados seja adicionado às equipes. |Não |Tbd |
|Criação de equipes |Limite a criação de equipe aos administradores. |Não |Tbd|
|Criação de equipes |Limite a criação de equipe aos membros do grupo de segurança. |P1 |Tbd|
|Rótulos de sensibilidade|Configurar privacidade e compartilhamento de convidados|Não|Tbd|

> [!NOTE]
> Para ajudá-lo a planejar com antecedência, saiba mais sobre [como definir essas políticas e quais licenças elas exigem.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)
> 
> [!NOTE]
> Limitar a criação de grupo e equipe pode reduzir a produtividade dos usuários, pois muitos serviços do Microsoft 365 e do Office 365 exigem que os grupos sejam criados para que o serviço funcione. Para obter informações adicionais, navegue até e expanda Por que controlar quem cria Grupos do [Microsoft 365.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)


#### <a name="additional-information"></a>Informações adicionais

Depois de determinar seus requisitos, você pode implementá-los usando controles do Azure AD. Para obter orientações técnicas sobre como implementar essas configurações, consulte:

- [Cmdlets do Azure Active Directory para configurar configurações de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Impor uma política de nomenurização para grupos do Microsoft 365 no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Política de nomeação de Grupos do Microsoft 365](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [Usar rótulos de sensibilidade para proteger conteúdo no Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [Opções de fim do ciclo de vida para grupos, equipes e Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>Expiração, retenção e arquivamento de grupos e equipes

Sua organização pode ter requisitos adicionais para definir políticas de expiração, retenção e arquivamento de dados de equipes e equipes (mensagens de canal e arquivos de canal). Você pode configurar políticas de expiração de grupo para gerenciar automaticamente o ciclo de vida do grupo e as políticas de retenção para preservar ou excluir informações conforme necessário, e você pode arquivar equipes (configurá-las para o modo somente leitura) para preservar um modo de exibição point-in-time de uma equipe que não está mais ativa. Observe que as equipes arquivadas continuam com a política de expiração aplicada e podem ser excluídas, a menos que sejam excluídas ou renovadas.

|           |            |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Sua organização exige a especificação de uma data de validade para as equipes?</li><li>Sua organização exige que políticas específicas de retenção de dados sejam aplicadas às equipes?</li><li>Sua organização espera exigir a capacidade de arquivar equipes inativas para preservar o conteúdo em um estado somente leitura?</li></ul>|
| ![Um ícone representando os próximos passos](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Documente os requisitos da sua organização para expiração da equipe, retenção de dados e arquivamento.</li><li>Planeje implementar esses requisitos como parte da implantação do Teams.</li><li>Comunique e publique suas políticas para informar os usuários do Teams sobre o comportamento que eles podem esperar.</li></ul>|

> [!TIP]
> Use a tabela a seguir para capturar os requisitos da sua organização.

|Recursos |Detalhes |Licença do Azure AD Premium necessária |Decisão |
|---------|---------|---------|---------|
|Política de expiração |Gerencie o ciclo de vida dos grupos do Microsoft 365 definindo uma política de expiração. |P1 |Tbd|
|Política de retenção |Mantenha ou exclua dados por um período específico definindo políticas de retenção para o Teams no centro de conformidade & segurança. **Observação:** usar esse recurso requer licenciamento do Microsoft 365 ou do Office 365 Enterprise E3 ou superior. |Não |Tbd |
|Arquivar e restaurar |Arquive uma equipe quando ela não estiver mais ativa, mas você quiser mantê-la para referência ou reativar no futuro. |Não |Tbd |

> [!Note]
> A expiração de grupo é um recurso premium do Azure AD. Para que esse recurso seja disponibilizado, o locatário deve ter uma assinatura do Azure AD Premium e licenças para o administrador que configura as configurações e os membros dos grupos afetados.

#### <a name="additional-information"></a>Informações adicionais

Para obter orientações técnicas sobre como implementar essas configurações, consulte:

- [Configurar a expiração de grupos do Microsoft 365.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

- [Configurar políticas de retenção do Teams.](retention-policies.md)

- [Arquivar ou restaurar uma equipe.](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>Gerenciamento de associação de grupo e equipe

O gerenciamento consistente de membros de grupos restritos ou baseados em projeto são necessários para equipes que exigem integração rápida e desabordo ou usuários e convidados. Sua organização também pode precisar garantir que todos os membros atuais tenham a justificativa comercial para estar em uma equipe. Gerenciar membros pode ser difícil porque os proprietários da equipe podem sair e os usuários geralmente não saem de grupos por conta própria quando um projeto termina ou quando alteram funções. A melhor maneira de gerenciar a associação a um grupo que permite aos usuários obter acesso quando necessário, mas garantir que o grupo não tenha um risco de acesso inadequado é por meio de dois processos districiais: gerenciamento de direitos e revisões de acesso.

[O gerenciamento de](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) direitos permite que você delegar a alguém, como um gerente de projeto, colete todos os recursos necessários, incluindo associações de equipes, em um único pacote. Eles também podem definir quem pode fazer solicitações: usuários em seu locatário ou de outras organizações conectadas. O gerente de projeto receberá solicitações de acesso em seu email e aprovará ou negará solicitações no portal MyAccess. Os administradores podem configurar as condições de acesso para incluir uma data de vencimento ou um período em que o usuário ou convidado será removido da equipe, a menos que o acesso seja renovado. Os administradores também podem configurar os grupos associados às equipes para participar das avaliações de acesso. Para [as avaliações de acesso,](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)os proprietários do grupo receberão lembretes regulares para revisar os membros de uma equipe. As avaliações do Access incluem recomendações, o que torna mais fácil para os proprietários de grupos passar pelo processo regular de atestação.

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | Pontos de decisão | Sua organização exige um processo consistente para gerenciar a associação de uma ou mais equipes? <br> Sua organização exige que os proprietários, ou os próprios membros, justifiquem a continuação da associação de uma ou mais equipes regularmente? <br> Sua organização exige aprovação para que usuários e convidados solicitem acesso a recursos, incluindo equipes, grupos, sites do SharePoint e aplicativos? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| Próximas etapas? | Documente os requisitos de suas organizações para cada equipe ou equipes específicas para a associação expirar.<br>Planeje como sua organização pode agrupar equipes, grupos, sites do SharePoint e aplicativos em pacotes de acesso.<br>Planeje quais pessoas, como o gerente do solicitante, um gerente de projeto, um patrocinador de uma organização conectada ou um agente de segurança em sua organização precisarão aprovar ou negar solicitações de acesso. |

> [!TIP]
> Use a tabela a seguir para capturar os requisitos da sua organização.

| Recursos | Detalhes | Licença do Azure AD Premium necessária | Decisão |
|:-|:-|:-|:-|
| Avaliações do Access | Configuração de avaliações de acesso para recertificar a associação de equipes específicas no intervalo regular | P2 | Tbd |
| Gerenciamento de direitos | Pacote de acesso de configuração para permitir que usuários e convidados solicitem acesso às equipes | P2 | Tbd |

> [!NOTE]
> Para ajudá-lo a planejar com [antecedência, saiba mais sobre quais licenças elas exigem.](https://azure.microsoft.com/pricing/details/active-directory/)

### <a name="additional-information"></a>Informações adicionais

Para obter orientações técnicas sobre como implementar essas configurações, consulte:

- [Gerenciamento de direitos](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Avaliações do Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Gerenciamento de recursos do Teams

Outro aspecto importante do gerenciamento de governança e ciclo de vida do Teams é a capacidade de controlar a quais recursos seus usuários terão acesso. Você pode gerenciar recursos de mensagens, reuniões e chamada, no nível da organização do Microsoft 365 ou do Office 365 ou por usuário.


|         |         |
|---------|---------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Sua organização exige a limitação de recursos do Teams para todo o locatário?</li><li>Sua organização exige a limitação de recursos do Teams para usuários específicos?</li></ul>|
| ![Um ícone representando os próximos passos](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Documente os requisitos da sua organização para limitar os recursos do Teams no nível do locatário e do usuário.</li><li>Planeje implementar seus requisitos específicos como parte da implantação do Teams.</li><li>Comunique e publique suas políticas para informar os usuários do Teams sobre o comportamento que eles podem esperar.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Áreas de foco de gerenciamento de recursos do Teams

O Teams fornece recursos granulares para controlar mensagens, reuniões, chamada e recursos de eventos ao vivo e muito mais, por meio de políticas. Diferentes políticas podem ser aplicadas a todos os usuários por padrão ou por usuário, conforme exigido pela sua organização. 

Para obter listas detalhadas de todas as configurações, incluindo orientações técnicas sobre como implementá-las para sua organização, consulte os seguintes artigos:

- [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)
- [Gerenciar equipes durante a transição para o novo centro de administração do Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Canais privados no Microsoft Teams](private-channels.md)
- [Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md)
- [Gerenciar políticas de mensagens no Teams](messaging-policies-in-teams.md)
- [Gerenciar seus aplicativos no Centro de administração do Microsoft Teams](manage-apps.md)

Além disso, você pode configurar a moderação de um canal e dar recursos de moderador a determinados usuários para que eles possam controlar quem pode criar postagens de canal e respondá-los. Consulte [Configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md) para obter mais informações.

## <a name="security-and-compliance"></a>Segurança e conformidade

O Teams é integrado aos recursos avançados de segurança e conformidade do Microsoft 365 e do Office 365 e oferece suporte a auditoria e relatórios, pesquisa de conteúdo de conformidade, descoberta e descoberta, Retenção Legal e políticas de retenção.

> [!Important]
> Se sua organização tiver requisitos de segurança e conformidade, revise o conteúdo aprofundado fornecido sobre este tópico no artigo Visão geral de segurança e [conformidade no Microsoft Teams.](security-compliance-overview.md)

## <a name="related-topics"></a>Tópicos relacionados

[Início rápido de governança para Teams](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->

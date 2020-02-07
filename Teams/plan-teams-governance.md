---
title: Planejar a governança em equipes ‒ Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Saiba mais sobre como planejar a implementação de recursos de governança no Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: afd990c0a49b1f61bb5be717cc3bf2ad7bc70935
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836183"
---
# <a name="plan-for-governance-in-teams"></a>Plano de governança no Teams

O Microsoft Teams oferece um rico conjunto de ferramentas para implementar qualquer recurso de governança que sua organização possa exigir. Este artigo orienta os profissionais de ti a fazer as perguntas certas a fim de determinar seus requisitos de governança e como atendê-los. 

> [!Tip] 
> Assista à sessão a seguir para saber mais sobre o controle no Microsoft Teams: [governança, gerenciamento e ciclo de vida no Microsoft Teams](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>Criação, classificação e acesso de convidados em grupo e equipe

Sua organização pode exigir que você implemente controles estritos sobre como as equipes são nomeadas e classificadas, se convidados podem ser adicionados como membros da equipe e quem pode criar equipes. Você pode configurar cada uma dessas áreas usando o Active Directory do Azure (Azure AD). 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |Pontos de decisão|<ul><li>Sua organização requer uma Convenção de nomenclatura específica para o Teams?</li><li>Os criadores de equipe precisam ter a capacidade de atribuir classificações específicas da organização ao Teams?</li><li>Você precisa restringir a capacidade de adicionar convidados ao Teams por cada equipe?</li><li>Sua organização requer a limitação de quem pode criar equipes?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|Próximas etapas|<ul><li>Documentar os requisitos da sua organização para acesso de criação, nomenclatura, classificação e convidado de equipe.</li><li>Planeje a implementação desses requisitos como parte de sua distribuição do teams.</li><li>Comunique e Publique suas políticas para informar aos usuários da equipe o comportamento que elas podem esperar.</li></ul>|

> [!TIP]
> Use a tabela a seguir para capturar os requisitos da sua organização.

|Potencial |Detalhes |Azure AD Premium <br> licença necessária |Decidiu |
|---------|---------|---------|---------|
|Política de nomenclatura de equipe | Use palavras bloqueadas personalizadas baseadas em sufixo de prefixo. |P1 |A ser determinado |
|Classificação da equipe |Atribuir classificações ao Teams. |P1 |A ser determinado |
|Acesso de convidado da equipe |Permitir ou impedir que convidados sejam adicionados ao Teams. |Não |A ser determinado |
|Criação de equipes |Limitar a criação de equipes aos administradores. |Não |A ser determinado|
|Criação de equipes |Limitar a criação de equipes a membros do grupo de segurança. |P1 |A ser determinado|

> [!NOTE]
> Para ajudá-lo a planejar com antecedência, [saiba mais sobre como definir essas políticas e quais são as licenças necessárias](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).
> 
> [!NOTE]
> Limitar a criação de grupo e equipe pode reduzir a produtividade dos usuários, pois muitos serviços do Office 365 exigem que os grupos sejam criados para o serviço funcionar. Para obter informações adicionais, navegue até e expanda [por que controlar quem cria grupos do Office 365](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).


#### <a name="additional-information"></a>Informações adicionais

Depois de determinar suas necessidades, você poderá implementá-las usando controles do Azure AD. Para obter orientação técnica sobre como implementar essas configurações, consulte:

- [Cmdlets do Azure Active Directory para definir configurações de grupo](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

- [Impor uma política de nomenclatura para grupos do Office 365 no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).

- [Política de nomenclatura de grupos do Office 365](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).


## <a name="group-and-team-expiration-retention-and-archiving"></a>Expiração de grupo e de equipe, retenção e arquivamento

Sua organização pode ter requisitos adicionais para a configuração de políticas para expiração, retenção e arquivamento de equipes e dados de equipes (mensagens de canal e arquivos de canal). Você pode configurar políticas de expiração de grupo para gerenciar automaticamente o ciclo de vida das políticas de grupo e retenção para preservar ou excluir as informações conforme necessário, e você pode arquivar equipes (definidas como modo somente leitura) para preservar uma exibição point-in-time de uma equipe Não está mais ativo.

|           |            |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Sua organização requer a especificação de uma data de expiração para o Teams?</li><li>Sua organização requer políticas específicas de retenção de dados serem aplicadas ao Teams?</li><li>Sua organização espera exigir a capacidade de arquivar equipes inativas para preservar o conteúdo em um estado somente leitura?</li></ul>|
| ![Um ícone representando os próximos passos](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Documentar os requisitos da sua organização para expiração da equipe, retenção de dados e arquivamento.</li><li>Planeje a implementação desses requisitos como parte da distribuição de suas equipes.</li><li>Comunique e Publique suas políticas para informar aos usuários da equipe o comportamento que elas podem esperar.</li></ul>|

> [!TIP]
> Use a tabela a seguir para capturar os requisitos da sua organização.

|Potencial |Detalhes |É necessária uma licença do Azure AD Premium |Decidiu |
|---------|---------|---------|---------|
|Política de expiração |Gerenciar o ciclo de vida dos grupos do Office 365 definindo uma política de expiração. |P1 |A ser determinado|
|Política de retenção |Manter ou excluir dados de um período de tempo específico definindo as políticas de retenção para equipes no centro de conformidade do & de segurança. **Observação**: o uso deste recurso requer licenciamento do Office 365 Enterprise E3 ou superior. |Não |A ser determinado |
|Arquivar e restaurar |Arquive uma equipe quando ela não estiver mais ativa, mas você quiser mantê-la para referência ou reativar no futuro. |Não |A ser determinado |

> [!Note]
> A expiração do grupo é um recurso do Azure AD Premium. Para que esse recurso esteja disponível, seu locatário deve ter uma assinatura do Azure AD Premium e licenças para o administrador que define as configurações e os membros dos grupos afetados.

#### <a name="additional-information"></a>Informações adicionais

Para obter orientação técnica sobre como implementar essas configurações, consulte:

- [Configurar o vencimento dos grupos do Office 365](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).

- [Configurar as políticas de retenção do teams](retention-policies.md).

- [Arquivar ou restaurar uma equipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).


## <a name="teams-feature-management"></a>Gerenciamento de recursos do teams

Outro aspecto importante do gerenciamento de controle e ciclo de vida para equipes é a capacidade de controlar a quais recursos seus usuários terão acesso. Você pode gerenciar recursos de mensagens, reuniões e chamadas, seja no nível do locatário do Office 365 ou por usuário. 


|         |         |
|---------|---------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Sua organização requer a limitação de recursos de equipes para o seu locatário inteiro?</li><li>Sua organização requer a limitação de recursos de equipes para usuários específicos?</li></ul>|
| ![Um ícone representando os próximos passos](media/audio_conferencing_image9.png)<br/>Próximas etapas|<ul><li>Documentar os requisitos da sua organização para limitar os recursos da equipe no nível do locatário e do usuário.</li><li>Planeje a implementação de seus requisitos específicos como parte da distribuição de suas equipes.</li><li>Comunique e Publique suas políticas para informar aos usuários da equipe o comportamento que elas podem esperar.</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Áreas de foco do gerenciamento de recursos do teams

O Teams oferece recursos granulares para o controle de mensagens, reuniões, chamadas e recursos de eventos dinâmicos e muito mais, por meio de políticas. Políticas diferentes podem ser aplicadas a todos os usuários por padrão ou por usuário, conforme a necessidade da sua organização. 

Para obter listas detalhadas de todas as configurações, incluindo orientações técnicas sobre como implementá-las para sua organização, consulte os seguintes artigos:

- [Gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md)
- [Gerenciar equipes durante a transição para o novo centro de administração do Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md)
- [Gerenciar políticas de mensagens no Teams](messaging-policies-in-teams.md)

Além disso, você pode configurar a moderação de um canal e dar recursos do moderador a certos usuários para que eles possam controlar quem pode criar postagens de canal e respondê-las. Consulte [configurar e gerenciar a moderação de canal no Microsoft Teams](manage-channel-moderation-in-teams.md) para obter mais informações.

## <a name="security-and-compliance"></a>Segurança e conformidade

O Teams foi desenvolvido sobre os recursos avançados de segurança e conformidade do Office 365 e é compatível com auditoria e relatórios, pesquisa de conteúdo de conformidade, descoberta eletrônica, controle legal e políticas de retenção. 

> [!Important]
> Se sua organização tiver requisitos de conformidade e segurança, examine o conteúdo detalhado fornecido sobre este tópico na [visão geral de segurança e conformidade no Microsoft Teams](security-compliance-overview.md).

## <a name="related-topics"></a>Tópicos relacionados

[Início rápido de governança para Teams](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->

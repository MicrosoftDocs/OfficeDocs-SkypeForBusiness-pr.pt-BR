---
title: Criar uma equipe englobando toda a organização no Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e gerenciar uma equipe de toda a organização no Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6bb614de33f532dcf26d7522969911c46331297a
ms.sourcegitcommit: 0278cfe7d5ec53e83df4d9c8b9afb0f425cbb9d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2019
ms.locfileid: "34802642"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Criar uma equipe englobando toda a organização no Microsoft Teams

As equipes de toda a organização fornecem uma maneira automática para todos em uma organização de pequeno e médio porte fazer parte de uma única equipe para colaboração.
 
Com as equipes de toda a organização, os administradores globais podem criar facilmente uma equipe pública que recebe cada usuário da organização e mantém a participação atualizada com o Active Directory, pois os usuários entram e saem da organização. Somente administradores globais podem criar equipes de toda a organização e, atualmente, uma equipe de toda a organização está limitada a organizações com no máximo 5.000 usuários. Também há um limite de cinco equipes de toda a organização por locatário.  Se esses requisitos forem atendidos, os administradores globais verão **toda a organização** como uma opção quando selecionarem **criar uma equipe do zero** ao criar uma equipe. 

![Captura de tela da opção de toda a organização para criar uma equipe de toda a organização] (media/create-org-wide-team.png "Captura de tela da opção de toda a organização para criar uma equipe de toda a organização")

Quando uma equipe de toda a organização é criada, todos os administradores globais são adicionados como proprietários da equipe e todos os usuários ativos são adicionados como membros da equipe. Os usuários não licenciados também são adicionados à equipe. Na primeira vez que um usuário não licenciado entrar no Microsoft Teams, ele receberá uma licença de avaliação de nuvem comercial do Microsoft Teams. Para saber mais sobre a licença de avaliação, confira [gerenciar a oferta de avaliação de nuvem comercial do teams](iw-trial-teams.md). Os usuários que estão desabilitados para equipes, usuários convidados e a maioria das salas não são adicionados à equipe. 

Como o diretório de sua organização é atualizado para incluir novos usuários ativos ou se os usuários não funcionarem mais em sua empresa e a licença do teams estiver desativada, as alterações serão sincronizadas automaticamente e os usuários serão adicionados ou removidos da equipe. Os membros da equipe não podem sair de uma equipe de toda a organização. Como proprietário da equipe, você pode adicionar ou remover usuários manualmente, se necessário.

> [!NOTE]
> - Se você não vir a opção de **toda** a organização ao criar uma equipe e se for um administrador global, o recurso ainda poderá ser implantado ou sua organização poderá ter mais do que o limite de tamanho atual de membros do 5.000. Estamos tentando aumentar esse limite no futuro.
> - As salas que não fazem parte de uma lista de salas, equipamento e contas de recursos podem ser adicionadas ou sincronizadas com a equipe de toda a organização. Os proprietários da equipe podem remover facilmente essas contas da equipe.

## <a name="best-practices"></a>Práticas recomendadas
Para aproveitar ao máximo sua equipe de toda a organização, recomendamos que os proprietários da equipe façam o seguinte.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Permitir que apenas proprietários de equipe publiquem no canal geral
Reduza o ruído do canal ao fazer com que apenas proprietários de equipes sejam postados ao canal geral. Vá para a equipe e clique em **̇ ̇ ̇ mais opções** > **Gerenciar equipe**. Na guia **configurações** , clique em **permissões de membro** > selecionar **somente proprietários podem publicar mensagens**.
### <a name="turn-off-team-and-team-name-mentions"></a>Desativar @team e @ [nome da equipe] menção
 Reduza @mentions para mantê-los sobrecarregando toda a organização. Vá para a equipe e clique em **̇ ̇ ̇ mais opções** > **Gerenciar equipe**. Na guia **configurações** , clique em <strong>@mentions</strong> > desativar **mostrar membros a opção para @team ou @ [nome da equipe]**. 
### <a name="automatically-favorite-important-channels"></a>Canais importantes favoritos automaticamente
 Canais importantes favoritos para garantir que todos em sua organização se envolvam em conversas específicas. Para saber mais, confira [canais de favoritos automáticos para toda a equipe](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="remove-accounts-that-might-not-belong"></a>Remover contas que não podem pertencer
Embora os membros não possam sair de uma equipe de toda a organização, como proprietário da equipe, você pode gerenciar a escala da equipe removendo contas que não pertencem. Certifique-se de usar o Microsoft Teams para remover usuários da sua equipe de toda a organização.  Se você usar outra maneira de remover um usuário, como o centro de administração do Microsoft 365 ou de um grupo no Outlook, o usuário poderá ser adicionado novamente à equipe da organização. 

## <a name="faq"></a>Perguntas frequentes

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Existe uma maneira de criar uma equipe de toda a organização que não use o cliente do teams? 

Os administradores globais só podem criar uma equipe de toda a organização usando o cliente do teams. Se a sua organização limita a criação de equipes usando o PowerShell, a solução alternativa recomendada é adicionar seus administradores globais ao grupo de segurança de usuários que podem criar uma equipe. Para obter mais informações, confira [Gerenciar quem pode criar Grupos do Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups). 

Se isso não for uma opção, você pode criar uma equipe pública usando o PowerShell e adicionar um administrador global como o proprietário da equipe. Em seguida, faça com que o administrador global clique em **̇ ̇ ̇ mais opções** ao lado do nome da equipe, clique em **Editar equipe**e, em seguida, altere a privacidade para **toda a organização-todas em sua organização serão automaticamente adicionadas**. Observe que somente os proprietários da equipe podem acessar a opção **Editar equipe** e somente administradores globais podem ver a opção de **toda a organização** .

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>Existe uma maneira de converter uma equipe existente em uma equipe de toda a organização?

Os administradores globais podem converter uma equipe existente em uma equipe de edição de toda a organização no cliente do teams.
Vá para o nome da equipe, clique em **̇ ̇ ̇ mais opções** > **Editar equipe**.

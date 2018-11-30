---
title: Criar uma equipe englobando toda a organização no Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.date: 09/27/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e gerenciar uma equipe de toda a organização em equipes.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cefcf6cb4d1710935e6448e4babd7a284165e767
ms.sourcegitcommit: f7b706f8ac9647ba854ae3457018d3007edf6f6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2018
ms.locfileid: "26993414"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Criar uma equipe englobando toda a organização no Microsoft Teams

As equipes de toda a organização fornecem uma maneira automática para todas as pessoas em um pequeno a organização de médio porte uma parte de uma única equipe para colaboração. 
 
Com as equipes de toda a organização, os administradores globais podem criar facilmente uma equipe pública que extrai em todos os usuários na organização e mantém a associação atualizado com o Active Directory como a participação de usuários e saem da organização. Somente os administradores globais podem criar equipes de toda a organização e atualmente uma equipe de toda a organização está limitada a organizações com usuários não ultrapassa 2.500. Se esses requisitos são atendidos, administradores globais verá **toda a organização** como uma opção de **privacidade** , ao criar uma equipe.

![Captura de tela da opção toda a organização para criar uma equipe de toda a organização] (media/create-org-wide-team.png "Captura de tela da opção toda a organização para criar uma equipe de toda a organização")

> [!NOTE]
> Se você não vir a opção de **toda a organização** durante a criação de uma equipe e estiver um administrador global, o recurso ainda pode ser aplicação ou sua organização pode ter mais do que o limite de tamanho atual de 2.500 membros. Que queremos para aumentar esse limite no futuro.

Quando uma equipe de toda a organização é criada, todos os administradores globais são adicionados como proprietários de equipe e todos os usuários ativos são adicionados como membros da equipe. Os usuários que estão desabilitados para equipes, os usuários convidados e a maioria das salas não são adicionados para a equipe. Conforme o diretório da sua organização foi atualizado para incluir os novos usuários ativos ou se os usuários não funcionam mais na sua empresa e licença suas equipes estiver desabilitada, as alterações são automaticamente sincronizadas e os usuários forem adicionados ou removidos da equipe. Os membros da equipe não podem deixar uma equipe de toda a organização. Como um proprietário de equipe, manualmente é possível adicionar ou remover usuários, se necessário.

> [!NOTE]
> Salas que não fazem parte das contas de lista, equipamento e recurso sala podem ser adicionadas ou sincronizadas para a equipe de toda a organização. Os proprietários de equipe facilmente podem remover essas contas da equipe.

## <a name="best-practices"></a>Práticas recomendadas
Para obter o máximo da sua equipe de toda a organização, é recomendável que os proprietários de equipe faça o seguinte.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Permitir que somente os proprietários de equipe postar no canal gerais
Reduza o ruído de canal estabelecendo somente equipe postagem de proprietários no canal geral. Vá para a equipe e clique em **mais opções (…)**  >  **Gerenciar equipe**. Na guia **configurações** , clique em **permissões de membro** > selecione **somente proprietários podem postar mensagens**.
### <a name="turn-off-team-and-team-name-mentions"></a>Desativar @team e @ menções [nome da equipe]
 Reduza @mentions para mantê-los da sobrecarga de toda a organização. Vá para a equipe e clique em **mais opções (…)**  >  **Gerenciar equipe**. Na guia **configurações** , clique em **@mentions** > desativar **Mostrar membros a opção de @team ou @[nome da equipe]**. 
### <a name="automatically-favorite-important-channels"></a>Canais de importantes automaticamente Favoritos
 Canais favoritos importantes para garantir que todos em sua organização participa de conversas específicas. Para saber mais, consulte [canais de Autofavorito a equipe inteira](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="remove-accounts-that-might-not-belong"></a>Remover contas que não podem pertencer a
Embora membros não é possível deixar uma equipe de toda a organização, como um proprietário de equipe, você pode gerenciar a lista de participação da equipe, removendo contas que não pertencem. Verifique se que você usar equipes para remover usuários da sua equipe de toda a organização.  Se você usar outra maneira de remover um usuário, como o Centro de administração do Microsoft 365 ou de um grupo no Outlook, o usuário pode ser adicionado novamente para a equipe de toda a organização. 

## <a name="faq"></a>Perguntas Freqüentes

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Há uma maneira de criar uma equipe de toda a organização diferente usando o cliente de equipes? 

Os administradores globais só podem criar uma equipe de toda a organização usando o cliente de equipes. Se sua organização limita as equipes de criação usando o PowerShell, a solução recomendada é adicionar seus administradores globais ao grupo de usuários que pode criar uma equipe de segurança. Para obter mais informações, confira [Gerenciar quem pode criar Grupos do Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups). 

Se isso não for uma opção, você pode criar uma equipe pública usando o PowerShell e adicionar um administrador global como o proprietário de equipe. Em seguida, peça para o administrador global clicar **… Mais opções** ao lado do nome da equipe, clique em **Editar equipe**e altere a privacidade para **toda a organização - todos em sua organização serão automaticamente adicionadas**. Observe que apenas os proprietários de equipe podem acessar a opção de **Editar equipe** e administradores globais só podem visualizar a opção de **toda a organização** .

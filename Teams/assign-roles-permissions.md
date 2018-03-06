---
title: "Atribuir funções e permissões no Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: "Saiba como atribuir funções e permissões de proprietários membros de equipe no Microsoft Teams, inclusive permissões para criar equipes."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0919d588cedf654a515f47f16fafb70cdc923f16
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a>Atribuir funções e permissões no Microsoft Teams
===============================================

No Microsoft Teams, existem duas funções: **Proprietário** e **Membro**. Por padrão, a um usuário que cria uma nova equipe, é atribuído o status de Proprietário. Se uma equipe for criada a partir de um Grupo existente do Office 365, as permissões são herdadas.

A tabela abaixo mostra as diferenças de permissão entre um proprietário e um membro:

|  |Proprietário da equipe  |Membro da equipe  |
|---------|---------|---------|
|**Criar equipe**     |Sim        |Não         |
|**Sair da equipe**     |Sim         |Sim         |
|**Editar nome/descrição da equipe**      |Sim         |Não         |
|**Excluir equipe**      |Sim         |Não         |
|**Adicionar canal**      |Sim         |Sim*         |
|**Editar nome/descrição do canal**      |Sim         |Sim*         |
|**Excluir canal**      |Sim         |Sim*         |
|**Adicionar membros**      |Sim**         |Não         |
|**Adicionar guias**      |Sim         |Sim*         |
|**Adicionar conectores**      |Sim         |Sim*         |
|**Adicionar bots**      |Sim         |Sim*         |
\* Esses itens podem ser desativados por um proprietário em nível de equipe, e nesse caso os membros não teriam acesso para tal.

\*\*Após adicionar um membro a uma equipe, o Proprietário também pode promover um Membro para o status de Proprietário. Também é possível para um Proprietário rebaixar seu próprio status para o status de Membro.



> [!NOTE]
> Os Proprietários também podem fazer com que outros membros se tornem proprietários na opção Visualizar equipes. Uma equipe pode ter até 100 proprietários. É recomendável ter pelo menos alguns proprietários para gerenciar o Teams, isso também evitará grupos órfãos, caso o único proprietário saia da organização. Para obter mais informações sobre grupos órfãos, consulte [Atribuir novo proprietário a um grupo órfão](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).


<a name="permissions-to-create-teams"></a>Permissões para criar equipes
---------------------------

Por padrão, todos os usuários com uma caixa de correio no Exchange Online têm permissões para criar grupos do Office 365 e, portanto, um time no Microsoft Teams. Você pode ter um controle mais rígido e restringir a criação de novas equipes e, assim, a criação de novos grupos do Office 365 ao delegar direitos de criação e gerenciamento de grupos a um conjunto de usuários.

Se a sua organização tiver interesse em proceder dessa forma, as instruções abaixo descrevem as tarefas necessárias para tal.

1.  Identifique ou crie um grupo de segurança (SG) de usuários que tenham permissões atribuídas para criar grupos do Office 365.

    a.  **Ação:** Estabeleça um grupo de segurança no Office 365 para que você possa incluir os usuários que podem criar grupos do Office 365.

    b.  Para obter mais informações, consulte [Criar, editar ou excluir um grupo de segurança no centro de administração do Office 365](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb).

2.  Verifique se o controle na empresa para que usuários criem grupos está habilitado.

    a.  **Ação:** Execute o seguinte script no PowerShell e verifique se o parâmetro UsersPermissiontoCreateGroupsEnabled está definido como **True.**

    ```
    Connect-MsolService

    Get-MsolCompanyInformation
    ```

    b.  Se não estiver como true, execute o cmdlet Set-MsolCompanySettings **para defini-lo como True**.
Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True

    c. Para obter mais informações, consulte: [Gerenciar criação de grupos do Office 365](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings).

3.  Configurar as configurações de Grupo do Office 365 para permitir que apenas grupos de segurança identificados tenham permissões para criar grupos

    a.  **Ação:** Crie um objeto de configuração de grupos que contenha as configurações de grupo que receberão permissões atribuídas para a criação de grupos. 

    ```
    Connect-AzureAD

    $Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b

    $Setting = $template.CreateDirectorySetting()

    $setting["EnableGroupCreation"] = "false"

    $setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"

    New-AzureADDirectorySetting -DirectorySetting $settings
    ```

    b. Para obter mais informações, consulte: [Gerenciar criação de grupos do Office 365](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3).


||||
|---------|---------|---------|
| ![Ícone de ponto de decisão.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |Ponto de decisão         |Todos os usuários do Microsoft Teams terão permissão para criar equipes (recomendado)?         |
| ![Ícone de próximos passos.](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |Próximos passos         |Modifique as permissões padrão para quem pode criar grupos do Office 365, caso precise limitar as pessoas que podem criar equipes         |

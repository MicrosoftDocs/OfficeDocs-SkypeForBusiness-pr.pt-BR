---
title: Arquivar ou excluir uma equipe no Microsoft Teams
manager: serdars
ms.author: mikeplum
author: MikePlumleyMSFT
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Neste artigo, você aprenderá sobre como arquivar ou excluir permanentemente uma equipe no Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9178bb793f25d9c052041432c20af4be8fb4033
ms.sourcegitcommit: 57616ad45eaa8be7f78dd0126d324c8777c5a367
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68792780"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a>Arquivar ou excluir uma equipe no Microsoft Teams

Com o tempo, uma equipe criada no Microsoft Teams pode não ser usada ou você pode querer arquivar ou excluir uma equipe no final de um projeto. Se você for um administrador do Microsoft Teams, siga as etapas neste artigo para arquivar ou excluir uma equipe que não é mais necessária. (Se você for proprietário de uma equipe, também poderá [arquivar uma equipe](https://support.microsoft.com/office/dc161cfd-b328-440f-974b-5da5bd98b5a7).)

Ao arquivar uma equipe, todas as atividades da equipe cessarão. O arquivamento de uma equipe também arquiva canais privados na equipe e em seus conjuntos de sites associados.  No entanto, você ainda pode adicionar ou remover membros e atualizar funções, além de poder exibir todas as atividades da equipe em canais, arquivos e chats padrão e privados.

Quando você exclui uma equipe, a atividade de equipe em canais padrão e privado (e coleções de sites associadas), arquivos e chats também são excluídos.

> [!IMPORTANT]
> As equipes arquivadas podem ser reativadas, mas você não pode restaurar diretamente uma equipe que foi excluída. Primeiro, considere arquivar a equipe e adiar a exclusão até ter certeza de que não precisa mais da equipe.

## <a name="archive-a-team"></a>Arquivar uma equipe

Siga estas etapas para arquivar uma equipe. Você deve ser um administrador de serviço do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](./using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. No centro de administração, selecione **Teams**.
2. Selecione uma equipe clicando no nome da equipe.
3. Selecione **Arquivar**. A seguinte mensagem será exibida.

    ![Captura de tela da mensagem de arquivo do Teams.](media/teams-archive-message.png)

4. Para impedir que as pessoas editem o conteúdo no site do SharePoint e na guia Wiki associada à equipe, selecione **Fazer somente leitura do site do SharePoint para membros da equipe**. (Os proprietários do Teams ainda poderão editar esse conteúdo.)
5. Selecione **Arquivar** para arquivar a equipe. O status da equipe será alterado para **Arquivo**, ele estará temporariamente disponível dentro de **equipes ocultas localizadas** na parte inferior da lista de equipes, e um pequeno ícone que representa o estado arquivado será adicionado ao lado dele. Depois de removido das **equipes ocultas** , ele estará disponível na exibição **Gerenciar equipes** em **Arquivo**. Para exibir e pesquisar o conteúdo da equipe arquivada, selecione seu nome na lista **Arquivada** .

## <a name="make-an-archived-team-active"></a>Reativar uma equipe arquivada

Siga estas etapas para reativar a equipe arquivada.

1. No centro de administração, selecione **Teams**.
2. Selecione uma equipe clicando no nome da equipe.
3. Selecione **Restaurar**. O status da equipe será alterado para **Ativo**. Observe que ele não será movido de volta para dentro de **suas equipes** automaticamente.

## <a name="delete-a-team"></a>Excluir uma equipe

Se a equipe não for necessária no futuro, você pode excluí-la, em vez de arquivá-la. Siga estas etapas para excluir uma equipe.

1. No centro de administração, selecione **Teams**.
2. Selecione uma equipe clicando no nome da equipe.
3. Selecione **Excluir**. Será exibida uma mensagem de confirmação.
4. Selecione **Excluir** para excluir a equipe permanentemente.

## <a name="restore-a-deleted-team"></a>Restaurar uma equipe excluída

Siga estas etapas para restaurar uma equipe excluída restaurando o grupo microsoft 365 associado à equipe. Restaurar o grupo microsoft 365 para uma equipe restaura o conteúdo da equipe, incluindo guias, canais padrão e canais privados e suas coleções de sites associadas.

Por padrão, um grupo do Microsoft 365 excluído é mantido por 30 dias. Esse período de 30 dias é chamado de "exclusão temporária" porque você pode restaurar o grupo. Para saber mais, confira [Restaurar um grupo excluído](/microsoft-365/admin/create-groups/restore-deleted-group).

### <a name="install-the-azureadpreview-module"></a>Instalar o módulo AzureADPreview

1. Abra o Windows PowerShell como um administrador.
2. Se você tiver uma versão anterior do módulo AzureADPreview instalada ou o módulo AzureAD instalado, desinstale-a executando uma das seguintes opções:

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```

3. Instale a versão mais recente do módulo AzureADPreview executando o seguinte:

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a>Restaurar o grupo excluído do Microsoft 365

1. Conecte-se ao Azure AD executando o seguinte:

    ```PowerShell
    Connect-AzureAD
    ```

    Quando solicitado, entre usando sua conta de administrador e senha.

1. Execute o seguinte para exibir uma lista de todos os grupos do Microsoft 365 excluídos que ainda estão dentro do período de retenção de 30 dias. Use o parâmetro **-All $True** se você tiver muitos grupos.

    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```

1. Localize o grupo que você deseja restaurar e, em seguida, anote o `Id`.
1. Execute o seguinte para restaurar o grupo, onde `[Id]` está a ID do grupo.

    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```

1. Execute o seguinte para verificar se o grupo foi restaurado com êxito, onde `[Id]` está a ID do grupo.

    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    Pode levar até 24 horas para o processo de restauração ser concluído, após o qual a equipe e o conteúdo associado a ela, incluindo as guias e os canais, serão exibidos no Teams.

## <a name="related-topics"></a>Tópicos relacionados

- [Arquivar ou restaurar uma equipe](https://support.microsoft.com/office/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)


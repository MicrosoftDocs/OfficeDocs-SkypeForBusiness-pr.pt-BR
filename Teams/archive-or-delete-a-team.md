---
title: Arquivar ou excluir uma equipe no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Saiba como arquivar ou excluir permanentemente uma equipe.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e367fe85f1af35391fa00b4a416b6e796383d962
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826399"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Arquivar ou excluir uma equipe no Microsoft Teams
===========================================

Com o tempo, uma equipe criada no Microsoft Teams pode ficar fora do uso ou talvez você queira arquivar ou excluir uma equipe no final de um projeto. Se você for um administrador do Microsoft Teams, siga as etapas deste artigo para arquivar ou excluir uma equipe que não é mais necessária.

Quando você arquiva uma equipe, todas as atividades da equipe são interrompidas. O arquivamento de uma equipe também arquiva canais privados na equipe e nos conjuntos de sites associados.  No entanto, você ainda pode adicionar ou remover membros e atualizar funções e ainda pode exibir todas as atividades da equipe em canais padrão e privados, arquivos e chats.

Quando você exclui uma equipe, a atividade de equipe em canais padrão e privados (e conjuntos de sites associados), arquivos e chats também é excluída.

> [!IMPORTANT]
> As equipes arquivadas podem ser reativadas, mas você não pode restaurar diretamente uma equipe que tenha sido excluída. Considere o arquivamento da equipe primeiro e adie a exclusão até ter certeza de que você não precisa mais da equipe.

## <a name="archive-a-team"></a>Arquivar uma equipe

Siga estas etapas para arquivar uma equipe.

1. No centro de administração do Microsoft Teams, selecione **equipes**.
2. Selecione uma equipe clicando no nome da equipe.
3. Selecione **arquivo morto**. A seguinte mensagem será exibida.

    ![Captura de tela da mensagem de arquivo do teams](media/teams-archive-message.png)

4. Se você quiser tornar o site do SharePoint para a equipe somente leitura, marque a caixa de seleção.
5. Selecione **arquivo morto** para arquivar a equipe. O status da equipe será alterado para **arquivo morto**.

## <a name="make-an-archived-team-active"></a>Ativar uma equipe arquivada

Siga estas etapas para fazer com que uma equipe arquivada seja ativa novamente.

1. No centro de administração do Microsoft Teams, selecione **equipes**.
2. Selecione uma equipe clicando no nome da equipe.
3. Selecione não **arquivar**. O status da equipe será alterado para **ativo**.

## <a name="delete-a-team"></a>Excluir uma equipe

Se a equipe não for necessária no futuro, você poderá excluí-la em vez de arquivá-la. Siga estas etapas para excluir uma equipe.

1.  No centro de administração do Microsoft Teams, selecione **equipes**.
2.  Selecione uma equipe clicando no nome da equipe.
3.  Selecione **excluir**. Uma mensagem de confirmação será exibida.
4.  Selecione **excluir** para excluir permanentemente a equipe.

## <a name="restore-a-deleted-team"></a>Restaurar uma equipe excluída

Siga estas etapas para restaurar uma equipe excluída restaurando o grupo do Office 365 associado à equipe. Restaurar o grupo do Office 365 para uma equipe, restaura o conteúdo da equipe, incluindo guias, canais padrão e canais privados e seus conjuntos de sites associados.

Por padrão, um grupo do Office 365 excluído é mantido por 30 dias. Este período de 30 dias é chamado de "exclusão reversível" porque você pode restaurar o grupo. Para saber mais, confira [restaurar um grupo do Office 365 excluído](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).

### <a name="install-the-azureadpreview-module"></a>Instalar o módulo AzureADPreview

1. Abra o Windows PowerShell como administrador.
2. Se você tiver uma versão anterior do módulo AzureADPreview instalada ou o módulo AzureAD instalado, desinstale-o executando um dos seguintes procedimentos:

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

### <a name="restore-the-deleted-office-365-group"></a>Restaurar o grupo do Office 365 excluído

1. Conecte-se ao Azure AD executando o seguinte:
    ```PowerShell
    Connect-AzureAD
    ```
    Quando for solicitado, entre usando sua conta de administrador e senha.  
2. Execute o seguinte para exibir uma lista de todos os grupos do Office 365 excluídos de maneira flexível que ainda estão dentro do período de retenção de 30 dias. Use o parâmetro **-All $true** se você tiver muitos grupos.
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. Localize o grupo que você deseja restaurar e tome nota da identificação.
4. Execute o seguinte para restaurar o grupo em que [ID] é a ID do grupo.
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Execute o seguinte para verificar se o grupo foi restaurado com êxito, em que [ID] é a ID do grupo.
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    Pode levar até 24 horas para que o processo de restauração seja concluído, após o qual a equipe e o conteúdo associado à equipe, incluindo guias e canais, são exibidos no Teams.

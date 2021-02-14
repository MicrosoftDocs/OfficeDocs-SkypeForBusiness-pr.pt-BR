---
title: Controle de acesso baseado em função com o serviço Microsoft Teams Room Premium
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre o controle de acesso baseado em função com o serviço gerenciado salas do Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: d673a20b122af876d95bac9d11a1db0433a396e4
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662596"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Controle de acesso baseado em função com o serviço gerenciado salas do Microsoft Teams

O RBAC (controle de acesso baseado em função) no serviço gerenciado salas do Microsoft Teams ajuda você a gerenciar o acesso do usuário aos dados de recursos de sala em sua organização. Ao atribuir funções aos usuários do portal de serviço, você pode limitar o que eles podem ver e alterar. Cada função tem um conjunto de permissões que determinam quais usuários com essa função podem acessar e alterar em sua organização.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões:

- Administrador Global por meio do Azure Active Directory (Azure AD)
- Administrador de Serviços Gerenciados por meio do portal de serviço gerenciado salas do Microsoft Teams

## <a name="what-is-a-role"></a>O que é uma função?

Uma função define o conjunto de permissões concedidas aos usuários atribuídos a essa função. Por enquanto, o serviço gerenciado salas do Microsoft Teams tem três funções: Administrador de Serviços Gerenciados, Cliente de **Site** e Técnico **do Site.** Eles abrangem alguns cenários comuns para os usuários em sua organização que podem estar envolvidos no gerenciamento de suas salas.

Para ver as funções, na navegação à esquerda do portal de serviço gerenciado salas do Microsoft Teams, vá para Funções e selecione qualquer uma das funções para ver as propriedades, permissões e atribuições da função.  

- **Propriedades:** o nome, o tipo de função e a descrição
- **Permissões:** Lista os recursos e o nível de permissões aos quais a função tem acesso.
- **Atribuições:** uma lista de atribuições de função que definem quais usuários têm as permissões configuradas sobre o escopo de contas de recursos de sala. Uma função pode ter várias atribuições e um usuário pode estar em várias atribuições.

## <a name="built-in-roles"></a>Funções integrados

Você pode atribuir funções internas a grupos ou usuários sem mais configuração. Lembre-se de que você não pode excluir ou editar o nome, a descrição, o tipo ou as permissões de uma função integrado.

- **Administrador de Serviços Gerenciados:** tem acesso total ao portal de serviços do Microsoft Teams Room Premium.
- **Site Lead:** organiza salas, tem acesso a relatórios e pode gerenciar tíquetes. Não é possível redefinir a chave de registro ou fazer alterações na configuração do serviço.  
- **Site Tech:** gerencia tíquetes para salas específicas. Não tem permissões para modificar o serviço ou organizar salas no serviço.

A tabela a seguir resume o que cada função pode fazer.

|Recursos |Permissão |Administrador de Serviços Gerenciados  |Site Lead  |Site Tech  |
|---------|---------|---------|---------|---------|
|Quartos     |Exibir        |&#10004;           |&#10004;           |&#10004;  |
|    |Modificar         |&#10004;           |&#10004;           |&#10004; |
|    |Tecla Redefinir         |&#10004;           |         ||
|    |Tecla de download         |&#10004;           |&#10004;          |&#10004; |
|    |Desemocar         |&#10004;           |&#10004;           |&#10004; |
|Gerenciamento de grupo   |Criar         |&#10004;           |           ||
|    |Exibir       |&#10004;          |&#10004;           ||
|    |Modificar         |&#10004;           |           ||
|Atualizar o gerenciamento de anel    |Criar         |&#10004;           |           ||
|    |Exibir         |&#10004;           |           ||
|    |Modificar         |&#10004;           |           ||
|Relatórios   |Exibir        |&#10004;           |&#10004;           ||
|Gerenciamento de tíquetes   |Criar incidentes com o cliente         |&#10004;           |&#10004;           |&#10004;  |
|    |Exibir         |&#10004;           |&#10004;           |&#10004;  |
|    |Atualizar         |&#10004;           |&#10004;           |&#10004;  |
|Configurações de serviço gerenciado de Salas do Microsoft Teams    |Exibir         |&#10004;           |         ||
|    |Modificar        |&#10004;           |         ||
|Gerenciamento de função    |Exibir         |&#10004;           |         ||
|    |Modificar         |&#10004;           |         ||

## <a name="assign-a-role"></a>Atribuir uma função

Para atribuir funções, você deve ser um Administrador Global ou Administrador de Serviços Gerenciados.

1. Na navegação à esquerda do portal de serviço gerenciado salas do Microsoft Teams, vá para **Funções de**  >  **Configurações.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Captura de tela da página de controle do Access mostrando funções":::

2. Selecione a função que você deseja atribuir.
3. No painel de função, selecione **Adicionar**  >  **Tarefas.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Captura de tela da opção Adicionar para adicionar uma função.":::

4. Na página **Configurações Gerais,** em **Propriedades de Atribuição,** insira um nome para essa tarefa. A descrição é opcional. Escolha **Próximo.**
5. Na  página Membros,  na caixa Pesquisar usuário ou grupo de segurança, insira o nome de um usuário ou grupo de segurança em seu locatário para o qual você deseja dar permissões e conclua a seleção. Escolha **Próximo.** 
6. Na página **Escopo,**  na caixa Pesquisar sala ou grupo de sala, digite o nome de uma sala ou grupo de sala que o usuário terá permissão para gerenciar. Escolha **Próximo.**
7. Na página **Concluir,** revise os detalhes da tarefa. Se você estiver satisfeito com a configuração, escolha **Adicionar atribuição.** Se você quiser editar uma seção, use o **botão** Anterior ou selecione a etapa na navegação à esquerda.  

## <a name="related-topics"></a>Tópicos relacionados

- [Serviço gerenciado de Salas do Microsoft Teams](microsoft-teams-rooms-premium.md)

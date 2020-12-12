---
title: Controle de acesso baseado em função com o serviço de sala Premium do Microsoft Teams
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
description: Saiba mais sobre o controle de acesso baseado em função com o serviço gerenciado de salas do Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: d673a20b122af876d95bac9d11a1db0433a396e4
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662596"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Controle de acesso baseado em função com o serviço gerenciado de salas do Microsoft Teams

O controle de acesso baseado em função (RBAC) no serviço gerenciado de salas do Microsoft Teams ajuda você a gerenciar o acesso de usuários a dados de recursos de sala em sua organização. Atribuindo funções aos usuários do portal do serviço, você pode limitar o que eles podem ver e alterar. Cada função tem um conjunto de permissões que determina quais usuários com essa função podem acessar e alterar dentro da sua organização.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões:

- Administrador global por meio do Active Directory do Azure (Azure AD)
- Administrador de serviço gerenciado por meio do portal de serviço gerenciado de salas do Microsoft Teams

## <a name="what-is-a-role"></a>O que é uma função?

Uma função define o conjunto de permissões concedidos aos usuários atribuídos a essa função. Por enquanto, o serviço gerenciado de salas do Microsoft Teams tem três funções internas: **administrador de serviço gerenciado**, **líder do site** e técnico de **site**. Elas abordam alguns cenários comuns para os usuários de sua organização que possam estar envolvidos no gerenciamento de salas.

Para ver as funções, no painel de navegação esquerdo do portal de serviço gerenciado de salas do Microsoft Teams, vá para **funções** e selecione qualquer uma das funções para ver as propriedades, as permissões e as atribuições da função.  

- **Propriedades**: o nome, o tipo de função e a descrição
- **Permissões**: lista recursos e nível de permissões aos quais a função tem acesso.
- **Atribuições**: uma lista de atribuições de função que definem quais usuários têm as permissões configuradas sobre o escopo das contas de recursos da sala. Uma função pode ter várias atribuições, e um usuário pode estar em várias tarefas.

## <a name="built-in-roles"></a>Funções internas

Você pode atribuir funções internas a grupos ou usuários sem configuração adicional. Lembre-se de que não é possível excluir ou editar o nome, a descrição, o tipo ou as permissões de uma função interna.

- **Administrador de serviço gerenciado**: tem acesso completo ao portal de serviços premium do Microsoft Teams.
- **Leads de site**: organiza as salas, tem acesso a relatórios e pode gerenciar ingressos. Não é possível redefinir a chave de registro ou fazer alterações na configuração do serviço.  
- **Site técnico**: gerencia ingressos para salas específicas. Não tem permissões para modificar o serviço ou organizar salas no serviço.

A tabela a seguir resume o que cada função pode fazer.

|Recursos |Permissão |Administrador de serviços gerenciados  |Cliente potencial do site  |Site Tech  |
|---------|---------|---------|---------|---------|
|Salas     |Exibir        |&#10004;           |&#10004;           |&#10004;  |
|    |Editar         |&#10004;           |&#10004;           |&#10004; |
|    |Redefinir chave         |&#10004;           |         ||
|    |Chave de download         |&#10004;           |&#10004;          |&#10004; |
|    |Cancelarem         |&#10004;           |&#10004;           |&#10004; |
|Gerenciamento de grupo   |Criar         |&#10004;           |           ||
|    |Exibir       |&#10004;          |&#10004;           ||
|    |Editar         |&#10004;           |           ||
|Atualizar gerenciamento de anel    |Criar         |&#10004;           |           ||
|    |Exibir         |&#10004;           |           ||
|    |Editar         |&#10004;           |           ||
|Gerente   |Exibir        |&#10004;           |&#10004;           ||
|Gerenciamento de tíquetes   |Criar incidente do cliente         |&#10004;           |&#10004;           |&#10004;  |
|    |Exibir         |&#10004;           |&#10004;           |&#10004;  |
|    |Atualizar         |&#10004;           |&#10004;           |&#10004;  |
|Configurações de serviço gerenciado de salas do Microsoft Teams    |Exibir         |&#10004;           |         ||
|    |Editar        |&#10004;           |         ||
|Gerenciamento de funções    |Exibir         |&#10004;           |         ||
|    |Editar         |&#10004;           |         ||

## <a name="assign-a-role"></a>Atribuir uma função

Para atribuir funções, você deve ser um administrador global ou administrador de serviço gerenciado.

1. Na navegação à esquerda do portal de serviço gerenciado de salas do Microsoft Teams , vá para  >  **funções** configurações.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Captura de tela da página de controle de acesso mostrando funções":::

2. Selecione a função que você deseja atribuir.
3. No painel função, selecione Adicionar **tarefas**  >  .

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Captura de tela da opção Adicionar para adicionar uma função.":::

4. Na página **configurações gerais** , em **Propriedades da atribuição**, insira um nome para essa tarefa. A descrição é opcional. Escolha **Avançar.**
5. Na página **Membros** , na caixa **Pesquisar usuário ou grupo de segurança** , insira o nome de um usuário ou grupo de segurança no locatário ao qual você deseja conceder permissões e, em seguida, conclua a seleção. Escolha **Avançar**. 
6. Na página **escopo** , na caixa de **grupo Pesquisar sala ou sala** , digite o nome de um grupo de salas ou salas que o usuário poderá gerenciar. Escolha **Avançar**.
7. Na página **concluir** , examine os detalhes da tarefa. Se estiver satisfeito com a configuração, escolha **Adicionar tarefa**. Se você quiser editar uma seção, use o botão **anterior** ou selecione a etapa na navegação à esquerda.  

## <a name="related-topics"></a>Tópicos relacionados

- [Serviço gerenciado de salas do Microsoft Teams](microsoft-teams-rooms-premium.md)

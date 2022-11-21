---
title: Controle de acesso baseado em função no Microsoft Teams Pro Management Portal
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre o controle de acesso baseado em função no Portal de Gerenciamento de Salas Microsoft Teams Pro.
f1keywords: ''
ms.openlocfilehash: 2cc62699cb4f59c3f80726f18bc80323557f966f
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046874"
---
# <a name="role-based-access-control-in-the-microsoft-teams-pro-management-portal"></a>Controle de acesso baseado em função no Microsoft Teams Pro Management Portal

O RBAC (controle de acesso baseado em função) no portal de Gerenciamento de Salas Microsoft Teams Pro ajuda você a gerenciar o acesso do usuário aos dados de recursos de sala em sua organização. Ao atribuir funções aos usuários do portal, você pode limitar o que eles podem ver e alterar. Cada função tem um conjunto de permissões que determinam quais usuários com essa função podem acessar e alterar em sua organização.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões:

- Administrador global por meio do Azure Active Directory (Azure AD)
- Administrador de Serviço Gerenciado por meio do portal de Gerenciamento de Salas Microsoft Teams Pro

## <a name="what-is-a-role"></a>O que é uma função?

Uma função define o conjunto de permissões concedidas aos usuários atribuídos a essa função. Por enquanto, o portal Salas Microsoft Teams Pro Management tem três funções internas: **Administrador de Serviço Gerenciado**, **Site Lead** e **Site Tech**. Eles abordam alguns cenários comuns para usuários em sua organização que podem estar envolvidos no gerenciamento de seus quartos.

Para ver funções, na navegação à esquerda do portal de Gerenciamento de Salas Microsoft Teams Pro, acesse **Funções** e selecione qualquer uma das funções para ver as propriedades, permissões e atribuições da função.  

- **Propriedades**: o nome, o tipo de função e a descrição
- **Permissões**: lista recursos e o nível de permissões aos quais a função tem acesso.
- **Atribuições**: uma lista de atribuições de função definindo quais usuários têm as permissões configuradas no escopo de contas de recursos de sala. Uma função pode ter várias atribuições e um usuário pode estar em várias atribuições.

## <a name="built-in-roles"></a>Funções internas

Você pode atribuir funções internas a grupos ou usuários sem configuração adicional. Tenha em mente que você não pode excluir ou editar o nome, a descrição, o tipo ou as permissões de uma função interna.

- **Administrador de Serviço Gerenciado**: tem acesso completo ao portal do Microsoft Teams Room Pro Management.
- **Site Lead**: organiza salas, tem acesso a relatórios e pode gerenciar tíquetes. Não é possível redefinir a chave de registro nem fazer alterações nas configurações de serviço.  
- **Site Tech**: gerencia tíquetes para salas específicas. Não tem permissões para modificar configurações de serviço ou organizar salas.

A tabela a seguir resume o que cada função pode fazer.

|Recursos |Permissão |Administrador de Serviço Gerenciado  |Site Lead  |Site Tech  |
|---------|---------|---------|---------|---------|
|Quartos     |Exibir        |&#10004;           |&#10004;           |&#10004;  |
|    |Modificar         |&#10004;           |&#10004;           |&#10004; |
|    |Redefinir chave         |&#10004;           |         ||
|    |Baixar chave         |&#10004;           |&#10004;          |&#10004; |
|    |Unenroll         |&#10004;           |&#10004;           |&#10004; |
|Gerenciamento de grupo   |Criar         |&#10004;           |           ||
|    |Exibir       |&#10004;          |&#10004;           ||
|    |Modificar         |&#10004;           |           ||
|Atualizar o gerenciamento de anel    |Criar         |&#10004;           |           ||
|    |Exibir         |&#10004;           |           ||
|    |Modificar         |&#10004;           |           ||
|Relatórios   |Exibir        |&#10004;           |&#10004;           ||
|Gerenciamento de tíquetes   |Criar incidente do cliente         |&#10004;           |&#10004;           |&#10004;  |
|    |Exibir         |&#10004;           |&#10004;           |&#10004;  |
|    |Atualizar         |&#10004;           |&#10004;           |&#10004;  |
|configurações do serviço de gerenciamento de Salas Microsoft Teams Pro    |Exibir         |&#10004;           |         ||
|    |Modificar        |&#10004;           |         ||
|Gerenciamento de funções    |Exibir         |&#10004;           |         ||
|    |Modificar         |&#10004;           |         ||

## <a name="create-a-custom-role"></a>Criar uma função personalizada

Se as funções internas não atenderem às suas necessidades organizacionais, você poderá criar uma função e configurar suas permissões conforme desejado. Para criar uma função, você deve ser um administrador global ou administrador de serviços gerenciados. 

1. Na navegação à esquerda do portal de Gerenciamento de Salas Microsoft Teams Pro, acesse **Configurações** > **Funções**.
2. Selecione **Criar função**.
3. Na página **Configurações gerais** , em **Propriedades de função**, insira um nome para essa função. Em **Descrição**, insira detalhes sobre essa função. Escolha **Avançar**.
4. Na página **Permissões** , em **Permissões de função**, escolha as permissões para essa função selecionando as caixas de seleção apropriadas. Escolha **Avançar** para criar a primeira atribuição para essa função.
5. Na página Atribuições, em **Propriedades de atribuição**, **insira** um nome para essa atribuição. A descrição é opcional. Em **Configurações de notificação** , selecione a caixa **de seleção notificações por email se os usuários** dessa função devem receber notificações por email do serviço em salas no **Escopo** dessa atribuição. Escolha **Avançar**.
6. Na página **Membros** , na caixa **Pesquisar usuário ou grupo de segurança** , insira o nome de um usuário ou grupo de segurança em seu locatário para o qual você deseja dar permissões e conclua a seleção. Escolha **Avançar**. 
7. Na página **Escopo** , na caixa **Pesquisar sala ou grupo de salas** , digite o nome de uma sala ou grupo de salas que o usuário poderá gerenciar. Escolha **Avançar**.
8. Na página **Concluir** , examine os detalhes da função e da atribuição. Se você estiver satisfeito com a configuração, escolha **Adicionar nova função**. Se você quiser editar uma seção, use o botão **Anterior** ou selecione a etapa na navegação à esquerda.  

## <a name="assign-a-role"></a>Atribuir uma função

Para atribuir funções, você deve ser um administrador global ou administrador de serviço gerenciado ou ter uma função com permissões de gerenciamento de função.

1. Na navegação à esquerda do portal de Gerenciamento de Salas Microsoft Teams Pro, acesse **Configurações** > **Funções**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Captura de tela da página Controle de acesso mostrando funções.":::

2. Selecione a função que você deseja atribuir.
3. No painel de função, selecione **Atribuições** > **Adicionar**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Captura de tela da opção Adicionar para adicionar uma função.":::

4. Na página **Configurações gerais** , em **Propriedades de atribuição**, insira um nome para essa atribuição. A descrição é opcional. Em **Configurações de notificação**, selecione a caixa **de seleção notificações por email se os usuários** dessa função devem receber notificações por email do serviço em salas no **Escopo** dessa atribuição. Escolha **Avançar**. 
5. Na página **Membros** , na caixa **Pesquisar usuário ou grupo de segurança** , insira o nome de um usuário ou grupo de segurança em seu locatário para o qual você deseja dar permissões e conclua a seleção. Escolha **Avançar**. 
6. Na página **Escopo** , na caixa **Pesquisar sala ou grupo de salas** , digite o nome de uma sala ou grupo de salas que o usuário poderá gerenciar. Escolha **Avançar**.
7. Na página **Concluir** , examine os detalhes da atribuição. Se você estiver satisfeito com a configuração, escolha **Adicionar atribuição**. Se você quiser editar uma seção, use o botão **Anterior** ou selecione a etapa na navegação à esquerda.  

## <a name="related-topics"></a>Tópicos relacionados

- [Portal de Gerenciamento de Salas Microsoft Teams Pro](rooms-pro-management.md)

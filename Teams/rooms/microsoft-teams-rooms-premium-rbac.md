---
title: Controle de acesso baseado em função no Portal de Gerenciamento do Microsoft Teams Pro
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
description: Saiba mais sobre o controle de acesso baseado em função no portal de gerenciamento Salas do Microsoft Teams Pro.
f1keywords: ''
ms.openlocfilehash: 8893f5dbe08203708fca21f808e3fda5c0f2b433
ms.sourcegitcommit: 021cfac01a38282a8cde6e913d74be2d54c39162
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68218520"
---
# <a name="role-based-access-control-in-the-microsoft-teams-pro-management-portal"></a>Controle de acesso baseado em função no Portal de Gerenciamento do Microsoft Teams Pro

O RBAC (controle de acesso baseado em função) no portal Salas do Microsoft Teams Pro Management ajuda você a gerenciar o acesso do usuário aos dados de recursos de sala em sua organização. Ao atribuir funções aos usuários do portal, você pode limitar o que eles podem ver e alterar. Cada função tem um conjunto de permissões que determinam quais usuários com essa função podem acessar e alterar em sua organização.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões:

- Administrador Global por meio do Azure Active Directory (Azure AD)
- Administrador de Serviços Gerenciados por meio do portal Salas do Microsoft Teams Pro Management

## <a name="what-is-a-role"></a>O que é um papel?

Uma função define o conjunto de permissões concedidas aos usuários atribuídos a essa função. Por enquanto, o portal Salas do Microsoft Teams Pro Management tem três funções internas **: Administrador** de Serviços Gerenciados, **Site Lead** e **Site Tech**. Eles abordam alguns cenários comuns para usuários em sua organização que podem estar envolvidos no gerenciamento de suas salas.

Para ver as funções, na navegação à esquerda do portal de gerenciamento do Salas do Microsoft Teams Pro, vá para Funções e selecione qualquer uma das funções para ver as propriedades, permissões e atribuições da função.  

- **Propriedades**: o nome, o tipo de função e a descrição
- **Permissões**: lista os recursos e o nível de permissões aos quais a função tem acesso.
- **Atribuições**: uma lista de atribuições de função que definem quais usuários têm as permissões configuradas no escopo das contas de recursos da sala. Uma função pode ter várias atribuições e um usuário pode estar em várias atribuições.

## <a name="built-in-roles"></a>Funções internas

Você pode atribuir funções internas a grupos ou usuários sem configuração adicional. Tenha em mente que você não pode excluir ou editar o nome, a descrição, o tipo ou as permissões de uma função interna.

- **Administrador de Serviços Gerenciados**: tem acesso completo ao portal de Gerenciamento do Microsoft Teams Room Pro.
- **Site Lead**: organiza salas, tem acesso a relatórios e pode gerenciar tíquetes. Não é possível redefinir a chave de registro ou fazer alterações nas configurações de serviço.  
- **Site Tech**: Gerencia tíquetes para salas específicas. Não tem permissões para modificar configurações de serviço ou organizar salas.

A tabela a seguir resume o que cada função pode fazer.

|Recursos |Permissão |Administrador de Serviços Gerenciados  |Cliente potencial do site  |Site Tech  |
|---------|---------|---------|---------|---------|
|Quartos     |Exibir        |&#10004;           |&#10004;           |&#10004;  |
|    |Modificar         |&#10004;           |&#10004;           |&#10004; |
|    |Redefinir chave         |&#10004;           |         ||
|    |Chave de download         |&#10004;           |&#10004;          |&#10004; |
|    |Cancelar registro         |&#10004;           |&#10004;           |&#10004; |
|Gerenciamento de grupo   |Criar         |&#10004;           |           ||
|    |Exibir       |&#10004;          |&#10004;           ||
|    |Modificar         |&#10004;           |           ||
|Gerenciamento de anel de atualização    |Criar         |&#10004;           |           ||
|    |Exibir         |&#10004;           |           ||
|    |Modificar         |&#10004;           |           ||
|Relatórios   |Exibir        |&#10004;           |&#10004;           ||
|Gerenciamento de tíquetes   |Criar incidente de cliente         |&#10004;           |&#10004;           |&#10004;  |
|    |Exibir         |&#10004;           |&#10004;           |&#10004;  |
|    |Atualizar         |&#10004;           |&#10004;           |&#10004;  |
|Salas do Microsoft Teams do serviço de Gerenciamento Pro    |Exibir         |&#10004;           |         ||
|    |Modificar        |&#10004;           |         ||
|Gerenciamento de funções    |Exibir         |&#10004;           |         ||
|    |Modificar         |&#10004;           |         ||

## <a name="create-a-custom-role"></a>Criar uma função personalizada

Se as funções internas não atenderem às suas necessidades organizacionais, você poderá criar uma função e configurar suas permissões conforme desejado. Para criar uma função, você deve ser um Administrador Global ou Administrador de Serviços Gerenciados. 

1. No painel de navegação esquerdo do portal Salas do Microsoft Teams Pro Management, vá para **Funções de Configurações** > .
2. Selecione **Criar função**.
3. Na página **Configurações gerais** , em **Propriedades de função**, insira um nome para essa função. Em **Descrição**, insira detalhes sobre essa função. Escolha **Avançar**.
4. Na página **Permissões** , em **Permissões de** função, escolha as permissões para essa função marcando as caixas de seleção apropriadas. Escolha **Avançar** para criar a primeira atribuição para essa função.
5. Na página **Atribuições** , em **Propriedades de** atribuição, insira um nome para essa atribuição. A descrição é opcional. Em **Configurações de notificação**, marque a caixa de seleção De notificações por email se os usuários dessa função devem receber notificações por email do serviço em salas no  Escopo desta atribuição. Escolha **Avançar**.
6. Na página  Membros, na caixa Pesquisar  usuário ou grupo de segurança, insira o nome de um usuário ou grupo de segurança em seu locatário para o qual você deseja conceder permissões e conclua a seleção. Escolha **Avançar**. 
7. Na página **Escopo**, na caixa Pesquisar  sala ou grupo de sala, digite o nome de uma sala ou grupo de sala que o usuário terá permissão para gerenciar. Escolha **Avançar**.
8. Na página **Concluir** , examine os detalhes da função e da atribuição. Se você estiver satisfeito com a configuração, escolha **Adicionar nova função**. Se você quiser editar uma seção, use o **botão** Anterior ou selecione a etapa no painel de navegação esquerdo.  

## <a name="assign-a-role"></a>Atribuir uma função

Para atribuir funções, você deve ser um Administrador Global ou Administrador de Serviços Gerenciados ou ter uma função com permissões de gerenciamento de função.

1. No painel de navegação esquerdo do portal Salas do Microsoft Teams Pro Management, vá para **Funções de Configurações** > .

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Captura de tela da página Controle de acesso mostrando funções.":::

2. Selecione a função que você deseja atribuir.
3. No painel de função, selecione **Adicionar Atribuições** > .

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Captura de tela da opção Adicionar para adicionar uma função.":::

4. Na página **Configurações gerais** , em Propriedades **de atribuição**, insira um nome para essa atribuição. A descrição é opcional. Em **Configurações de notificação**,  marque a caixa de seleção De notificações por email se os usuários dessa função devem receber notificações por email do serviço em salas no Escopo  desta atribuição. Escolha **Avançar**. 
5. Na página  Membros, na caixa Pesquisar  usuário ou grupo de segurança, insira o nome de um usuário ou grupo de segurança em seu locatário para o qual você deseja conceder permissões e conclua a seleção. Escolha **Avançar**. 
6. Na página **Escopo**, na caixa Pesquisar  sala ou grupo de sala, digite o nome de uma sala ou grupo de sala que o usuário terá permissão para gerenciar. Escolha **Avançar**.
7. Na página **Concluir** , examine os detalhes da atribuição. Se você estiver satisfeito com a configuração, escolha **Adicionar atribuição**. Se você quiser editar uma seção, use o **botão** Anterior ou selecione a etapa no painel de navegação esquerdo.  

## <a name="related-topics"></a>Tópicos relacionados

- [Salas do Microsoft Teams Pro Management](microsoft-teams-rooms-premium.md)

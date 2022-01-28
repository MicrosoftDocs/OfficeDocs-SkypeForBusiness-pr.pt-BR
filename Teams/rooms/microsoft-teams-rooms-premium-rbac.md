---
title: Controle de acesso baseado em função com o serviço Microsoft Teams Room Premium.
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre o controle de acesso baseado em função com o Salas do Microsoft Teams gerenciado.
f1keywords: ''
ms.openlocfilehash: c7594a04dbb1a36b60f3105c663cff3934ffd3c1
ms.sourcegitcommit: 9f1f5cd828c24676c20df727b2c67daf56ff884c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2022
ms.locfileid: "62248662"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Controle de acesso baseado em função com o serviço Salas do Microsoft Teams gerenciado

O controle de acesso baseado em função (RBAC) no serviço gerenciado Salas do Microsoft Teams ajuda você a gerenciar o acesso do usuário aos dados de recursos de sala em sua organização. Ao atribuir funções aos usuários do portal de serviço, você pode limitar o que eles podem ver e alterar. Cada função tem um conjunto de permissões que determinam quais usuários com essa função podem acessar e alterar em sua organização.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões:

- Administrador Global por Azure Active Directory (Azure AD)
- Administrador de Serviços Gerenciados por meio do portal Salas do Microsoft Teams de serviço gerenciado

## <a name="what-is-a-role"></a>O que é uma função?

Uma função define o conjunto de permissões concedidas aos usuários atribuídos a essa função. Por enquanto, o serviço Salas do Microsoft Teams gerenciado tem três funções: **Administrador** de Serviço Gerenciado, Líder de **Site** e **Site Tech**. Eles abrangem alguns cenários comuns para usuários em sua organização que podem estar envolvidos no gerenciamento de suas salas.

Para ver funções, na navegação à esquerda do portal de serviço gerenciado Salas do Microsoft Teams, vá para Funções e selecione qualquer uma das funções para ver as propriedades, permissões e atribuições da função.  

- **Propriedades**: o nome, o tipo de função e a descrição
- **Permissões**: lista os recursos e o nível de permissões aos quais a função tem acesso.
- **Atribuições**: uma lista de atribuições de função que definem quais usuários têm as permissões configuradas sobre o escopo de contas de recursos de sala. Uma função pode ter várias atribuições e um usuário pode estar em várias atribuições.

## <a name="built-in-roles"></a>Funções integrados

Você pode atribuir funções internas a grupos ou usuários sem configuração posterior. Lembre-se de que você não pode excluir ou editar o nome, a descrição, o tipo ou as permissões de uma função criada.

- **Administrador de Serviços Gerenciados**: tem acesso total ao portal de serviço Microsoft Teams sala Premium serviço.
- **Site Lead**: organiza salas, tem acesso a relatórios e pode gerenciar tíquetes. Não é possível redefinir a chave de registro ou fazer alterações na configuração do serviço.  
- **Site Tech**: Gerencia tíquetes para salas específicas. Não tem permissões para modificar o serviço ou organizar salas no serviço.

A tabela a seguir resume o que cada função pode fazer.

|Recursos |Permissão |Administrador de Serviços Gerenciados  |Site Lead  |Site Tech  |
|---------|---------|---------|---------|---------|
|Salas     |Exibir        |&#10004;           |&#10004;           |&#10004;  |
|    |Modificar         |&#10004;           |&#10004;           |&#10004; |
|    |Tecla Redefinir         |&#10004;           |         ||
|    |Chave de download         |&#10004;           |&#10004;          |&#10004; |
|    |Desemroll         |&#10004;           |&#10004;           |&#10004; |
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
|Salas do Microsoft Teams configurações de serviço gerenciado    |Exibir         |&#10004;           |         ||
|    |Modificar        |&#10004;           |         ||
|Gerenciamento de função    |Exibir         |&#10004;           |         ||
|    |Modificar         |&#10004;           |         ||

## <a name="create-a-custom-role"></a>Criar uma função personalizada

Se as funções embutida não atenderem às suas necessidades organizacionais, você poderá criar uma função e configurar suas permissões conforme desejado. Para criar uma função, você deve ser um Administrador Global ou Administrador de Serviço Gerenciado. 

1. Na navegação à esquerda do portal de serviço Salas do Microsoft Teams gerenciado, vá para **Configurações**  >  **Funções**.
2. Selecione **Criar função**.
3. Na página **Configurações Gerais,** em **Propriedades de função**, insira um nome para essa função. Em **Descrição,** insira detalhes sobre essa função. Escolha **Próximo**.
4. Na página **Permissões,** em **Permissões de** função, escolha as permissões para essa função selecionando as caixas de seleção apropriadas. Escolha **Próximo** para criar a primeira atribuição para essa função.
5. Na página **Atribuições,** em **Propriedades de atribuição,** insira um nome para essa atribuição. A descrição é opcional. Em  **Configurações de notificação,** marque a caixa de seleção Notificações por email se os usuários dessa função receberem notificações por email do serviço em salas no **Escopo** desta atribuição. Escolha **Próximo**.
6. Na página **Membros,**  na caixa Pesquisar usuário ou grupo de segurança, insira o nome de um usuário ou grupo de segurança em seu locatário para o qual você deseja dar permissões e conclua a seleção. Escolha **Próximo**. 
7. Na página **Escopo,** na caixa **Pesquisar** sala ou grupo de sala, digite o nome de uma sala ou grupo de sala que o usuário terá permissão para gerenciar. Escolha **Próximo**.
8. Na página **Concluir,** revise os detalhes da função e da atribuição. Se você estiver satisfeito com a configuração, escolha **Adicionar nova função**. Se você quiser editar uma seção, use o **botão Anterior** ou selecione a etapa na navegação à esquerda.  

## <a name="assign-a-role"></a>Atribuir uma função

Para atribuir funções, você deve ser um Administrador Global ou Administrador de Serviço Gerenciado ou ter uma função com permissões de gerenciamento de função.

1. Na navegação à esquerda do portal de serviço Salas do Microsoft Teams gerenciado, vá para **Configurações**  >  **Funções**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Captura de tela da página de controle do Access mostrando funções.":::

2. Selecione a função que você deseja atribuir.
3. No painel de funções, selecione **Atribuições**  >  **Adicionar**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Captura de tela da opção Adicionar para adicionar uma função.":::

4. Na página **Configurações Gerais,** em **Propriedades de atribuição,** insira um nome para essa atribuição. A descrição é opcional. Em  **Configurações de notificação,** marque a caixa de seleção Notificações por email se os usuários dessa função receberem notificações por email do serviço em salas no **Escopo** desta atribuição. Escolha **Próximo**. 
5. Na página **Membros,**  na caixa Pesquisar usuário ou grupo de segurança, insira o nome de um usuário ou grupo de segurança em seu locatário para o qual você deseja dar permissões e conclua a seleção. Escolha **Próximo**. 
6. Na página **Escopo,** na caixa **Pesquisar** sala ou grupo de sala, digite o nome de uma sala ou grupo de sala que o usuário terá permissão para gerenciar. Escolha **Próximo**.
7. Na página **Concluir,** revise os detalhes da atribuição. Se você estiver satisfeito com a configuração, escolha **Adicionar atribuição**. Se você quiser editar uma seção, use o **botão Anterior** ou selecione a etapa na navegação à esquerda.  

## <a name="related-topics"></a>Tópicos relacionados

- [Salas do Microsoft Teams serviço gerenciado](microsoft-teams-rooms-premium.md)

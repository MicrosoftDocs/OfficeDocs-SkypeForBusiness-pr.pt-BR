---
title: Painel de controle-pesquisa de usuário atualizada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para o Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha. Também é possível pesquisar por usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.
ms.openlocfilehash: 7b6b72275ffd5dfe8c03b41d4da2ca8ee6f40a3a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285994"
---
# <a name="control-panel---updated-user-search"></a>Painel de Controle - atualizado: Pesquisa de Usuário

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para o Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha. Também é possível pesquisar por usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Pesquisa de Usuário** do Painel de Controle:

- [Search for Lync Server 2010 Users](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Enable or Disable Users for Lync Server 2010](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Mover Usuário](move-user.md)

- [Mover Todos os Usuários](move-all-users.md)

- [Assign Policies to Users](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Enable users for Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configure Federation, Remote User Access, and Public IM Connectivity for Users](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configure Telephony for Users](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)

Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o painel de controle do Skype for Business Server, consulte [gerenciar o Skype for Business server 2015](../../manage/manage.md).

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página **Pesquisa de Usuário**.

### <a name="user-search"></a>Pesquisa de Usuário

- **Pesquisa** Procure usuários pela primeira parte do nome para exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI da linha da conta do usuário.

- **Pesquisa LDAP** Procure usuários digitando uma expressão LDAP.

- **Caixa Pesquisar usuários** Digite os dados do usuário ou a expressão LDAP para a qual você deseja pesquisa.

- **Localizar** Clique para exibir os usuários que correspondem aos valores de pesquisa inseridos na caixa **Pesquisar usuários** e.

- **Abrir consulta** Clique para abrir uma consulta de pesquisa salva.

- **Salvar consulta** Clique em para salvar uma consulta de pesquisa.

- **+ Adicionar filtro** Clique para adicionar critérios de pesquisa adicionais.

- **Campos de filtro de pesquisa** Selecione o campo no qual você deseja filtrar os resultados da pesquisa, selecione um operador para a consulta e, em seguida, digite a cadeia de caracteres que você deseja pesquisar.

- **Máximo de usuários a serem exibidos** Digite o número de resultados da pesquisa que você deseja exibir ou use as setas para cima e para baixo para especificar o número.

Adicione outro texto descritivo, conforme o apropriado.

### <a name="search-results-menus"></a>Menus de resultados da pesquisa

- **Habilitar usuários** Clique para abrir a caixa de diálogo [usuários: novo usuário do Lync Server](users-new-lync-server-user.md) , onde você pode adicionar um novo usuário ao Skype for Business Server.

    Para adicionar um novo contato, clique na seta para baixo e selecione **Habilitar contatos** para abrir a caixa de diálogo [Users: New Contact Objects](users-new-contact-objects.md).

- **Editar** Clique em **Editar** e, em seguida, clique em **Mostrar detalhes** para exibir os detalhes do usuário selecionado ou clique em **selecionar todos os resultados da pesquisa** para selecionar todos os usuários exibidos na tabela resultados.

- **Ação** Clique em **ação**e selecione a ação que você deseja executar para os usuários selecionados nos resultados da pesquisa. As ações a seguir estão disponíveis:

  - **Habilitar novamente no Lync Server** Habilita a conta de usuário selecionada depois que ela é temporariamente desabilitada.

  - **Desabilite temporariamente para o Lync Server** Desabilita a conta de usuário no Skype for Business Server até que você a habilite novamente, sem remover a conta de usuário.

  - **Atribuir políticas** Abre a caixa de diálogo [usuários: atribuir políticas](users-assign-policies.md) , onde você pode configurar as políticas atribuídas ao usuário.

  - **Exibir o status do pino** Abre a caixa de diálogo [usuários: Exibir status do pino](users-view-pin-status.md) , que exibe os dados do PIN para o usuário selecionado.

  - **Definir PIN** Abre a caixa de diálogo [definir PIN](set-pin.md) , onde você pode definir o PIN para o usuário selecionado.

  - Fixar **PIN** Bloqueia o PIN para o usuário.

  - **Desbloquear PIN** Remove o bloqueio do PIN do usuário.

  - **Remover do Lync Server** Remove a conta de usuário do Skype for Business Server. O usuário não é removido do Active Directory.

  - **Remover certificado de usuário** Remove todos os certificados concedidos ao usuário.

  - **Mover os usuários selecionados para o pool** Abre a caixa de diálogo [mover usuário](move-user.md) , na qual você pode selecionar um pool para o qual mover o usuário selecionado.

  - **Mover todos os usuários para o pool** Abre a caixa de diálogo [mover usuário](move-user.md) , na qual você pode selecionar um pool para o qual moverá todos os usuários selecionados.



---
title: Painel de Controle - Pesquisa de Usuário atualizada
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para o Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha. Você também pode procurar usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.
ms.openlocfilehash: f74c1dfe7f1b8184c59261ff03a01f2f5b39db18
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820241"
---
# <a name="control-panel---updated-user-search"></a>Painel de Controle - atualizado: Pesquisa de Usuário

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para o Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha. Você também pode procurar usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página Painel de **Controle** de Pesquisa do Usuário:

- [Pesquisar usuários](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Habilitar ou desabilitar usuários](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [Mover Usuário](ms.lync.lscp.UserMove.md)

- [Mover Todos os Usuários](ms.lync.lscp.UserMoveAll.md)

- [Atribuir políticas a usuários](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Habilitar usuários para o Enterprise Voice no Skype for Business Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configurar federação, acesso de usuário remoto e conectividade de IM pública para usuários](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configurar telefonia para usuários](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)



## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página **Pesquisa de Usuário**.

### <a name="user-search"></a>Pesquisa de Usuário

- **Pesquisa** Procure usuários pela primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário.

- **Pesquisa LDAP** Pesquise usuários digitando uma expressão LDAP.

- **Caixa Pesquisar usuários** Digite os dados do usuário ou a expressão LDAP que você deseja pesquisar.

- **Find** Clique para exibir os usuários que corresponderem aos valores de pesquisa inseridos na caixa Pesquisar **usuários.**

- **Consulta aberta** Clique para abrir uma consulta de pesquisa salva.

- **Salvar consulta** Clique para salvar uma consulta de pesquisa.

- **+ Adicionar filtro** Clique para adicionar critérios de pesquisa adicionais.

- **Campos de filtro de pesquisa** Selecione o campo no qual você deseja filtrar os resultados da pesquisa, selecione um operador para a consulta e digite a cadeia de caracteres que você deseja pesquisar.

- **Máximo de usuários a exibir** Digite o número de resultados de pesquisa que você deseja exibir ou use as setas para cima e para baixo para especificar o número.

Adicione outro texto descritivo, conforme o apropriado.

### <a name="search-results-menus"></a>Menus de resultados da pesquisa

- **Habilitar usuários** Clique para abrir a caixa de diálogo Usuários: Novo Usuário do [Lync Server,](ms.lync.lscp.UserNew.md) onde você pode adicionar um novo usuário ao Skype for Business Server.

    Para adicionar um novo contato, clique na seta para baixo e selecione **Habilitar contatos** para abrir a caixa de diálogo [Users: New Contact Objects](ms.lync.lscp.UserNewContact.md).

- **Editar** Clique **em Editar** e em **Mostrar** detalhes para exibir  os detalhes do usuário selecionado ou clique em Selecionar todos os resultados da pesquisa para selecionar todos os usuários exibidos na tabela de resultados.

- **Ação** Clique **em** Ação e selecione a ação que você deseja executar para os usuários selecionados nos resultados da pesquisa. As ações a seguir estão disponíveis:

  - **Reabilitar para o Lync Server** Habilita a conta de usuário selecionada após ela ter sido temporariamente desabilitada.

  - **Desabilitar temporariamente para o Lync Server** Desabilita a conta de usuário no Skype for Business Server até que você a reabilitar, sem remover a conta de usuário.

  - **Atribuir Políticas** Abre a [caixa de diálogo Usuários: Atribuir](ms.lync.lscp.UserAssignPolicy.md) Políticas, onde você pode configurar as políticas atribuídas ao usuário.

  - **Exibir status do PIN** Abre a [caixa de diálogo Usuários: Exibir Status](ms.lync.lscp.UserViewPin.md) do PIN, que exibe os dados de PIN do usuário selecionado.

  - **Definir PIN** Abre a caixa de diálogo Definir [PIN,](ms.lync.lscp.UserSetPin.md) onde você pode definir o PIN para o usuário selecionado.

  - **Bloquear PIN** Bloqueia o PIN do usuário.

  - **Desbloquear PIN** Remove o bloqueio no PIN do usuário.

  - **Remover do Lync Server** Remove a conta de usuário do Skype for Business Server. O usuário não é removido do Active Directory.

  - **Remover certificado de usuário** Remove todos os certificados concedidos ao usuário.

  - **Mover usuários selecionados para o pool** Abre a [caixa de diálogo](ms.lync.lscp.UserMove.md) Mover Usuário, na qual é possível selecionar um pool para o qual mover o usuário selecionado.

  - **Mover todos os usuários para o pool** Abre a [caixa de diálogo](ms.lync.lscp.UserMove.md) Mover Usuário, na qual é possível selecionar um pool para o qual mover todos os usuários selecionados.



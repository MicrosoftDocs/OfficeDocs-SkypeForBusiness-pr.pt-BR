---
title: Painel de Controle - Pesquisa de Usuário atualizada
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha. Você também pode pesquisar usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.
ms.openlocfilehash: 40a1ced2933abe628c7d1e56d9a1a7f66466769e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388489"
---
# <a name="control-panel---updated-user-search"></a>Painel de Controle - atualizado: Pesquisa de Usuário

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha. Você também pode pesquisar usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página Painel de Controle de **Pesquisa** do Usuário:

- [Pesquisar usuários do Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [Habilitar ou desabilitar usuários do Lync Server 2010](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [Mover Usuário](move-user.md)

- [Mover Todos os Usuários](move-all-users.md)

- [Atribuir políticas aos usuários](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [Habilitar usuários para Enterprise Voice no Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configurar federação, acesso de usuário remoto e conectividade de IM pública para usuários](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [Configurar telefonia para usuários](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)

Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o Painel de Controle Skype for Business Server, consulte [Manage Skype for Business Server 2015](../../manage/manage.md).

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página **Pesquisa de Usuário**.

### <a name="user-search"></a>Pesquisa de Usuário

- **Pesquisa** Procure usuários pela primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta de usuário.

- **Pesquisa LDAP** Pesquise usuários digitando uma expressão LDAP.

- **Caixa Pesquisar usuários** Digite os dados do usuário ou a expressão LDAP para a qual você deseja seachar.

- **Find** Clique para exibir os usuários que corresponderem aos valores de pesquisa inseridos na caixa **Pesquisar usuários** e.

- **Abrir consulta** Clique para abrir uma consulta de pesquisa salva.

- **Salvar consulta** Clique para salvar uma consulta de pesquisa.

- **+ Adicionar filtro** Clique para adicionar critérios de pesquisa adicionais.

- **Campos de filtro de pesquisa** Selecione o campo no qual deseja filtrar os resultados da pesquisa, selecione um operador para a consulta e digite a cadeia de caracteres em que deseja pesquisar.

- **Máximo de usuários a exibir** Digite o número de resultados de pesquisa que você deseja exibir ou use as setas para cima e para baixo para especificar o número.

Adicione outro texto descritivo, conforme o apropriado.

### <a name="search-results-menus"></a>Menus de resultados da pesquisa

- **Habilitar usuários** Clique para abrir a [caixa de diálogo Usuários: Novo Usuário do Lync Server](users-new-lync-server-user.md), onde você pode adicionar um novo usuário Skype for Business Server.

    Para adicionar um novo contato, clique na seta para baixo e selecione **Habilitar contatos** para abrir a caixa de diálogo [Users: New Contact Objects](users-new-contact-objects.md).

- **Editar** Clique **em Editar** e em **Mostrar** detalhes para exibir os detalhes do usuário selecionado ou clique em **Selecionar** todos os resultados da pesquisa para selecionar todos os usuários exibidos na tabela de resultados.

- **Ação** Clique **em Ação** e selecione a ação que você deseja executar para os usuários selecionados nos resultados da pesquisa. As ações a seguir estão disponíveis:

  - **Habilitar para o Lync Server** Habilita a conta de usuário selecionada após ter sido temporariamente desabilitada.

  - **Desabilitar temporariamente para o Lync Server** Desabilita a conta de usuário Skype for Business Server até que você a habilita, sem remover a conta de usuário.

  - **Atribuir políticas** Abre a [caixa de diálogo Usuários: Atribuir Políticas](users-assign-policies.md) , onde você pode configurar as políticas atribuídas ao usuário.

  - **Exibir status do PIN** Abre a [caixa de diálogo Usuários: Exibir Status do PIN](users-view-pin-status.md) , que exibe os dados pin do usuário selecionado.

  - **Definir PIN** Abre a [caixa de diálogo Definir PIN](set-pin.md) , onde você pode definir o PIN do usuário selecionado.

  - **PIN de bloqueio** Bloqueia o PIN do usuário.

  - **Desbloquear PIN** Remove o bloqueio no PIN do usuário.

  - **Remover do Lync Server** Remove a conta de usuário do Skype for Business Server. O usuário não é removido do Active Directory.

  - **Remover certificado de usuário** Remove todos os certificados concedidos ao usuário.

  - **Mover usuários selecionados para o pool** Abre a [caixa de diálogo Mover Usuário](move-user.md) , onde você pode selecionar um pool para mover o usuário selecionado para.

  - **Mover todos os usuários para pool** Abre a [caixa de diálogo Mover Usuário](move-user.md) , onde você pode selecionar um pool para mover todos os usuários selecionados para.
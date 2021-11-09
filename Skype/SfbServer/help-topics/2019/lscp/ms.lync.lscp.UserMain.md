---
title: Painel de Controle - Pesquisa de Usuário atualizada
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha. Você também pode pesquisar usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.
ms.openlocfilehash: 3c5bdc9de490adbc022f00342d291d012da78d4b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854925"
---
# <a name="control-panel---updated-user-search"></a>Painel de Controle - atualizado: Pesquisa de Usuário

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha. Você também pode pesquisar usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página Painel de Controle de **Pesquisa** do Usuário:

- [Pesquisar usuários](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [Habilitar ou desabilitar usuários](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [Mover Usuário](ms.lync.lscp.UserMove.md)

- [Mover Todos os Usuários](ms.lync.lscp.UserMoveAll.md)

- [Atribuir políticas aos usuários](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [Habilitar usuários para Enterprise Voice em Skype for Business Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configurar federação, acesso de usuário remoto e conectividade de IM pública para usuários](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [Configurar telefonia para usuários](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)



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

- **Habilitar usuários** Clique para abrir a caixa de diálogo Usuários: Novo Usuário do [Lync Server,](ms.lync.lscp.UserNew.md) onde você pode adicionar um novo usuário Skype for Business Server.

    Para adicionar um novo contato, clique na seta para baixo e selecione **Habilitar contatos** para abrir a caixa de diálogo [Users: New Contact Objects](ms.lync.lscp.UserNewContact.md).

- **Editar** Clique **em Editar** e em **Mostrar** detalhes para exibir os detalhes do usuário selecionado ou clique em **Selecionar** todos os resultados da pesquisa para selecionar todos os usuários exibidos na tabela de resultados.

- **Ação** Clique **em** Ação e selecione a ação que você deseja executar para os usuários selecionados nos resultados da pesquisa. As ações a seguir estão disponíveis:

  - **Habilitar para o Lync Server** Habilita a conta de usuário selecionada após ter sido temporariamente desabilitada.

  - **Desabilitar temporariamente para o Lync Server** Desabilita a conta de usuário Skype for Business Server até que você a habilita, sem remover a conta de usuário.

  - **Atribuir políticas** Abre a [caixa de diálogo Usuários: Atribuir Políticas,](ms.lync.lscp.UserAssignPolicy.md) onde você pode configurar as políticas atribuídas ao usuário.

  - **Exibir status do PIN** Abre a [caixa de diálogo Usuários: Exibir Status do PIN,](ms.lync.lscp.UserViewPin.md) que exibe os dados pin do usuário selecionado.

  - **Definir PIN** Abre a caixa de diálogo Definir [PIN,](ms.lync.lscp.UserSetPin.md) onde você pode definir o PIN do usuário selecionado.

  - **PIN de bloqueio** Bloqueia o PIN do usuário.

  - **Desbloquear PIN** Remove o bloqueio no PIN do usuário.

  - **Remover do Lync Server** Remove a conta de usuário do Skype for Business Server. O usuário não é removido do Active Directory.

  - **Remover certificado de usuário** Remove todos os certificados concedidos ao usuário.

  - **Mover usuários selecionados para o pool** Abre a caixa de diálogo Mover [Usuário,](ms.lync.lscp.UserMove.md) onde você pode selecionar um pool para mover o usuário selecionado para.

  - **Mover todos os usuários para pool** Abre a caixa de diálogo Mover [Usuário,](ms.lync.lscp.UserMove.md) onde você pode selecionar um pool para mover todos os usuários selecionados para.
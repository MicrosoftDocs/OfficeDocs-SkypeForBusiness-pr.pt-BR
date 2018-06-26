---
title: Painel de controle - atualizada pesquisa de usuário
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para Skype para Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha. Também é possível pesquisar por usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.
ms.openlocfilehash: 253dfd6a2e454b7d68211b18a5c1c3e8c6c4a837
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2018
ms.locfileid: "20046435"
---
# <a name="control-panel---updated-user-search"></a>Painel de Controle - atualizado: Pesquisa de Usuário
 
Você pode usar os resultados de uma consulta de pesquisa para configurar usuários para Skype para Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha. Também é possível pesquisar por usuários usando o Painel de Controle do Lync Server ou o snap-in Usuários e Computadores do Active Directory.
  
## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Pesquisa de Usuário** do Painel de Controle:
  
- [Pesquisa para usuários do Lync Server 2010](http://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)
    
- [Habilitar ou desabilitar usuários para o Lync Server 2010](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)
    
- [Mover usuário](ms.lync.lscp.UserMove.md)
    
- [Mover todos os usuários](ms.lync.lscp.UserMoveAll.md)
    
- [Atribuir políticas aos usuários](http://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)
    
- [Habilitar usuários para o Enterprise Voice no Skype para Business Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)
    
- [Configurar a federação, acesso de usuário remoto e conectividade de IM pública para usuários](http://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)
    
- [Configurar telefonia para usuários](http://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)
    
 
  
## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página **Pesquisa de Usuário**.
  
### <a name="user-search"></a>Pesquisa de Usuário

- **Pesquisa** Procurar usuários pela primeira parte do nome para exibição, nome, sobrenome, nome de conta SAM, endereço SIP ou URI de linha da conta do usuário.
    
- **Pesquisa LDAP** Procurar por usuários digitando uma expressão LDAP.
    
- **Caixa Pesquisar usuários** Digite os dados de usuário ou a expressão LDAP que você deseja pesquisar.
    
- **Encontre** Clique para exibir os usuários que correspondem aos valores de pesquisa que você inseriu na caixa e **usuários de pesquisa** .
    
- **Abrir consulta** Clique para abrir uma consulta de pesquisa salva.
    
- **Salvar consulta** Clique para salvar uma consulta de pesquisa.
    
- **+ Adicionar filtro** Clique para adicionar critérios de pesquisa adicionais.
    
- **Campos de filtro de pesquisa** Selecione o campo no qual você deseja filtrar os resultados da pesquisa, selecione um operador para a consulta e, em seguida, digite a cadeia de caracteres que você deseja pesquisar.
    
- **Máximo de usuários para exibir** Digite o número de resultados de pesquisa que você deseja exibir, ou use as setas e para baixo para especificar o número.
    
Adicione outro texto descritivo, conforme o apropriado.
  
### <a name="search-results-menus"></a>Menus de resultados da pesquisa

- **Permitir que os usuários** Clique para abrir o [usuários: novo usuário do Lync Server](ms.lync.lscp.UserNew.md) caixa de diálogo, onde você pode adicionar um novo usuário à Skype para Business Server.
    
    Para adicionar um novo contato, clique na seta e selecione **Habilitar contatos** para abrir o [usuários: New Contact Objects](ms.lync.lscp.UserNewContact.md) diálogo.
    
- **Editar** Clique em **Editar** e clique em **Mostrar detalhes** para exibir os detalhes do usuário selecionado, ou clique em **Selecionar todos os resultados de pesquisa** para selecionar todos os usuários exibidos na tabela de resultados.
    
- **Ação** Clique em **ação**e, em seguida, selecione a ação que você deseja executar para os usuários selecionados nos resultados da pesquisa. As ações a seguir estão disponíveis:
    
  - **Habilitar novamente para o Lync Server** Habilita a conta de usuário selecionada após ela ser temporariamente desabilitada.
    
  - **Desabilitar temporariamente para o Lync Server** Desabilita a conta de usuário no Skype para Business Server até reabilitá-lo, sem remover a conta de usuário.
    
  - **Atribuir políticas** Abre o [usuários: Atribuir políticas](ms.lync.lscp.UserAssignPolicy.md) caixa de diálogo, onde você pode configurar as políticas atribuídas ao usuário.
    
  - **Exibir status do PIN** Abre o [usuários: exibir o Status do PIN](ms.lync.lscp.UserViewPin.md) caixa de diálogo, que exibe os dados PIN do usuário selecionado.
    
  - **Definir PIN** Abre a caixa de diálogo [Definir PIN](ms.lync.lscp.UserSetPin.md) , onde é possível definir o PIN do usuário selecionado.
    
  - **Bloquear PIN** Bloqueia o PIN do usuário.
    
  - **PIN de desbloqueio** Remove o bloqueio no PIN do usuário.
    
  - **Remover do Lync Server** Remove a conta de usuário do Skype para Business Server. O usuário não é removido do Active Directory.
    
  - **Remover certificado do usuário** Remove todos os certificados concedidos ao usuário.
    
  - **Mover usuários selecionados para o pool** Abre a caixa de diálogo [Move User](ms.lync.lscp.UserMove.md) , onde você pode selecionar um pool para mover o usuário selecionado.
    
  - **Mover todos os usuários ao pool** Abre a caixa de diálogo [Move User](ms.lync.lscp.UserMove.md) , onde você pode selecionar um pool a fim de mover todos os usuários selecionados.
    


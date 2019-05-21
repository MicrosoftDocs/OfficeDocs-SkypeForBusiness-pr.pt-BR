---
title: Configuração de versão do cliente criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente. A configuração de versão do cliente global é instalada com o Skype for Business Server e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor. Quando a configuração Global é habilitada, quaisquer políticas de versão do cliente existentes entrarão em vigor quando os usuários tentarem fazer logon. É possível desabilitar a configuração da versão do cliente Global se não quiser que ocorra qualquer controle de versão de cliente.
ms.openlocfilehash: 54a7929f91e4e944cbe431ae7a0193c50a12cfbd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300483"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configuração de Versão de Cliente: Criar Nova ou Editar Existente

As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente. A configuração de versão do cliente global é instalada com o Skype for Business Server e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor. Quando a configuração Global é habilitada, quaisquer políticas de versão do cliente existentes entrarão em vigor quando os usuários tentarem fazer logon. É possível desabilitar a configuração da versão do cliente Global se não quiser que ocorra qualquer controle de versão de cliente.

Também é possível criar configurações de versão do cliente específicas do site, permitindo a habilitação ou desabilitação do controle de versão do cliente por site. A configuração específica do site tem precedência sobre a configuração Global.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Criar uma nova Configuração de Versão de Cliente** ou **Editar Configuração da Versão de Cliente**:

- Adicionar ou modificar o nome da configuração de versão do cliente.

- Habilitar ou desabilitar o controle de versão do cliente globalmente ou para o site específico.

- Adicionar ou modificar a ação padrão da configuração de versão do cliente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página.

- **Escopo** Identifica o escopo (global ou site) da configuração de versão do cliente.

- **Nome** Você pode adicionar ou modificar o nome da configuração de versão do cliente.

- **Habilitar controle de versão** Você pode habilitar ou desabilitar o controle de versão do cliente globalmente ou para o site, dependendo do escopo da configuração.

- **Ação padrão** Você pode selecionar a ação padrão que será aplicada quando um usuário tentar fazer logon usando um aplicativo cliente para o qual não há uma política de versão do cliente específica. Você tem as seguintes opções:

  - **Permite que** Permite que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de políticas de versão do cliente.

  - **Bloquear** Impede que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de políticas de versão do cliente.

  - **Bloquear com URL** Impede que o cliente faça logon se a versão do cliente não coincidir com nenhum filtro na lista políticas de versão do cliente e inclui uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.

  - **Permitir com URL** Permite que o cliente faça logon se a versão do cliente não coincidir com nenhum filtro na lista políticas de versão do cliente e inclui uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.

  - **URL** Se você selecionou **Bloquear com URL** ou **permitir com URL**, poderá especificar a URL de download do cliente a ser incluída na mensagem de erro.

Para obter detalhes sobre a interoperabilidade entre clientes e versões do cliente, consulte interoperabilidade do [cliente](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação de planejamento. Para obter detalhes sobre como trabalhar com configurações de versão de cliente, consulte [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) na documentação Operações.


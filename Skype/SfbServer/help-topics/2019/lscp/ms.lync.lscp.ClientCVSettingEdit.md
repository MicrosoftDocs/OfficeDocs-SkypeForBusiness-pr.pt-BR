---
title: Configuração de versão de cliente criar novo ou editar existente
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente. A configuração de versão de cliente Global instala com Skype para Business Server e é usada para habilitar ou desabilitar o controle de versão de cliente para a implantação de servidores inteiro. Quando a configuração Global é habilitada, quaisquer políticas de versão do cliente existentes entrarão em vigor quando os usuários tentarem fazer logon. É possível desabilitar a configuração da versão do cliente Global se não quiser que ocorra qualquer controle de versão de cliente.
ms.openlocfilehash: 6eacaddba90b123d04290640ebc8c0997e6904ce
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23263489"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configuração de Versão de Cliente: Criar Nova ou Editar Existente

As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente. A configuração de versão de cliente Global instala com Skype para Business Server e é usada para habilitar ou desabilitar o controle de versão de cliente para a implantação de servidores inteiro. Quando a configuração Global é habilitada, quaisquer políticas de versão do cliente existentes entrarão em vigor quando os usuários tentarem fazer logon. É possível desabilitar a configuração da versão do cliente Global se não quiser que ocorra qualquer controle de versão de cliente.

Também é possível criar configurações de versão do cliente específicas do site, permitindo a habilitação ou desabilitação do controle de versão do cliente por site. A configuração específica do site tem precedência sobre a configuração Global.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Criar uma nova Configuração de Versão de Cliente** ou **Editar Configuração da Versão de Cliente**:

- Adicionar ou modificar o nome da configuração de versão do cliente.

- Habilitar ou desabilitar o controle de versão do cliente globalmente ou para o site específico.

- Adicionar ou modificar a ação padrão da configuração de versão do cliente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comando, campos e propriedades na página.

- **Escopo** Identifica o escopo (Global ou Site) da configuração de versão do cliente.

- **Nome** É possível adicionar ou modificar o nome da configuração de versão do cliente.

- **Habilitar o controle de versão** Você pode habilitar ou desabilitar o controle de versão do cliente globalmente ou para o site, dependendo do escopo da configuração.

- **Ação padrão** Você pode selecionar a ação padrão que será aplicada quando um usuário tenta fazer logon usando um aplicativo de cliente para o qual não há nenhuma diretiva de versão do cliente específico. Você tem as seguintes opções:

  - **Permitir** Permite que o cliente faça logon se a versão do cliente não corresponder a nenhum filtro na lista de políticas de versão do cliente.

  - **Bloquear** Impede que o cliente logon se a versão do cliente não corresponder a nenhum filtro na lista de políticas de versão do cliente.

  - **Bloquear com URL** Impede que o cliente faça logon quando a versão do cliente não corresponder a nenhum filtro na lista de políticas de versão do cliente e inclui uma mensagem de erro que contém uma URL de onde um cliente mais recente pode ser baixado.

  - **Permitir com URL** Permite que o cliente faça logon se a versão do cliente não corresponder a nenhum filtro na lista de políticas de versão do cliente e inclui uma mensagem de erro que contém uma URL em que um cliente mais recente pode ser baixado.

  - **URL** Se você tiver selecionado **Bloquear com URL** ou **Permitir com URL**, você pode especificar a URL de download do cliente para incluir na mensagem de erro.

Para obter detalhes sobre a interoperabilidade entre clientes e versões de cliente, consulte [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação de planejamento. Para obter detalhes sobre como trabalhar com as configurações de versão de cliente, consulte [modificar a ação padrão para clientes não explicitamente suportados ou restritos](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) na documentação operações.


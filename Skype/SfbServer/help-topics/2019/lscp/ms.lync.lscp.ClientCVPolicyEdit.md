---
title: Política de versão cliente criar novo ou editar existente
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: É possível especificar a versão de clientes compatíveis com seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.
ms.openlocfilehash: 5648d96e69869171d78a3a28634bdb2b0221a234
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892988"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Política de Versão do Cliente: Criar Nova ou Editar Existente

É possível especificar a versão de clientes compatíveis com seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente. Para tornar o maior uso dos recursos incluídos em Skype para Business Server e para melhorar a experiência geral do usuário, você pode usar o filtro de versão de cliente para restringir as versões do cliente que são usadas em seu ambiente. Ao usar o filtro de versão do cliente, também é possível ajudar a reduzir os custos associados ao suporte de várias versões de cliente.

> [!IMPORTANT]
> Os filtros são listados em ordem de precedência. Por exemplo, se você tiver um filtro que permite a conexão de clientes que executam a versão 1.5 ou mais recente, seguido por um filtro que bloqueia os clientes executando uma versão anterior a 2.0, o primeiro filtro terá precedência e os clientes que executam a versão 1.5 terão permissão para se conectar.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Criar uma nova Política de Versão de Cliente** ou  **Editar Política da Versão de Cliente**:

- Adicionar ou modificar o nome ou descrição da política de versão do cliente.

- Adicionar ou modificar as regras de versão de cliente da política de versão de cliente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Escopo** Identifica o escopo (Site, Pool ou usuário) da política de versão do cliente.

- **Nome** É possível adicionar ou modificar o nome da política de versão do cliente.

- **Descrição** Você pode adicionar uma descrição para ajudar a identificar a política na lista na página política de versão do cliente.

- **Novo** Você pode adicionar uma nova regra de versão de cliente à política.

- **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções para uma regra de versão do cliente.

- **Remover** Essa opção remove a política a regra de versão de cliente selecionada.

- **Acima e abaixo setas** Essa opção move a regra de versão de cliente selecionada para cima ou para baixo na ordem de prioridade. As regras são processadas na ordem listada.

Para obter detalhes sobre a interoperabilidade entre clientes e versões de cliente, consulte [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx). Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) na documentação Operações.


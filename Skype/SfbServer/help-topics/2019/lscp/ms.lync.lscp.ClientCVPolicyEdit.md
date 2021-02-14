---
title: Política de Versão de Cliente Criar Nova ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: É possível especificar a versão de clientes suportados em seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.
ms.openlocfilehash: c2d6dc4f68a7c40668db9042d420f2f341e35ca0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824891"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Política da Versão do Cliente: Criar Nova ou Editar Existente

É possível especificar a versão de clientes suportados em seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente. Para fazer o máximo uso dos recursos incluídos no Skype for Business Server e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões de cliente que são usadas em seu ambiente. Usando o filtro de versão do cliente, também é possível reduzir os custos associados ao suporte de várias versões de clientes.

> [!IMPORTANT]
> Os filtros são listados em ordem de precedência. Por exemplo, se você tiver um filtro que permite a conexão de clientes que executam a versão 1.5 ou mais recente, seguido por um filtro que bloqueia os clientes executando uma versão anterior a 2.0, o primeiro filtro terá precedência e os clientes que executam a versão 1.5 terão permissão para se conectar.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página Nova Política **de Versão de Cliente** ou Editar Política de Versão **de** Cliente:

- Adicione ou modifique o nome ou a descrição da política de versão do cliente.

- Adicionar ou modificar regras de versão do cliente para a política de versão do cliente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Escopo** Identifica o escopo (Site, Pool ou Usuário) da política de versão do cliente.

- **Nome** Você pode adicionar ou modificar o nome da política de versão do cliente.

- **Descrição** Você pode adicionar uma descrição para ajudar a identificar a política na lista na página Política de Versão de Cliente.

- **Novo** Você pode adicionar uma nova regra de versão de cliente à política.

- **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma regra de versão do cliente.

- **Remover** Essa opção remove a regra de versão do cliente selecionada da política.

- **Setas para cima e para baixo** Essa opção move a regra de versão do cliente selecionada para cima ou para baixo com prioridade. As regras são processadas na ordem listada.

Para obter detalhes sobre interoperabilidade entre clientes e versões de cliente, consulte [Interoperabilidade de Cliente.](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) na documentação Operações.


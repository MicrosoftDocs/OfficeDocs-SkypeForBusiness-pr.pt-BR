---
title: Política de Versão do Cliente Criar Novo ou Editar Existente
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
ms.localizationpriority: medium
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: É possível especificar a versão de clientes suportados em seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.
ms.openlocfilehash: 14e13ea358f0959be0653beeef2c99267c5e095f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591795"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Política da Versão do Cliente: Criar Nova ou Editar Existente

É possível especificar a versão de clientes suportados em seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente. Para fazer o maior uso dos recursos incluídos no Skype for Business Server e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões do cliente que são usadas em seu ambiente. Usando o filtro de versão do cliente, também é possível reduzir os custos associados ao suporte de várias versões de clientes.

> [!IMPORTANT]
> Os filtros são listados em ordem de precedência. Por exemplo, se você tiver um filtro que permite a conexão de clientes que executam a versão 1.5 ou mais recente, seguido por um filtro que bloqueia os clientes executando uma versão anterior a 2.0, o primeiro filtro terá precedência e os clientes que executam a versão 1.5 terão permissão para se conectar.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página **Nova Política** de Versão do Cliente ou Editar Política de **Versão do** Cliente:

- Adicione ou modifique o nome ou a descrição da política de versão do cliente.

- Adicione ou modifique regras de versão do cliente para a política de versão do cliente.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Escopo** Identifica o escopo (Site, Pool ou Usuário) da política de versão do cliente.

- **Nome** Você pode adicionar ou modificar o nome da política de versão do cliente.

- **Descrição** Você pode adicionar uma descrição para ajudar a identificar a política na lista na página Política de Versão do Cliente.

- **Novo** Você pode adicionar uma nova regra de versão do cliente à política.

- **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma regra de versão do cliente.

- **Remover** Essa opção remove a regra de versão do cliente selecionada da política.

- **Setas para cima e para baixo** Essa opção move a regra de versão do cliente selecionada para cima ou para baixo em prioridade. As regras são processadas na ordem listada.

Para obter detalhes sobre interoperabilidade entre clientes e versões do cliente, consulte [Interoperabilidade do Cliente](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013). Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) na documentação Operações.
---
title: Política de Versão de Cliente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: É possível especificar a versão de clientes suportados em seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.
ms.openlocfilehash: 1a32329574b95ed4b918d5b323bc63f86331f617
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841843"
---
# <a name="client-version-policy"></a>Política da Versão de Cliente

É possível especificar a versão de clientes suportados em seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente. Para fazer o maior uso dos recursos incluídos no Skype for Business Server e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões do cliente que são usadas em seu ambiente. Ao usar o filtro de versão do cliente, também é possível ajudar a reduzir os custos associados ao suporte de múltiplas versões de cliente.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Política da Versão do Cliente**:

- Edite a política de versão do cliente padrão ( **Global**).

- Criar políticas de versão do cliente para um site específico ou pool.

- Criar políticas de versão do cliente que possam ser atribuídas a usuários individuais.

> [!NOTE]
> Como os usuários anônimos não são associados a um usuário, site ou serviço, os usuários anônimos são afetados somente por políticas no nível global.

## <a name="ui-reference"></a>Referência de UI

As listas a seguir descrevem os menus, comandos, campos e propriedades na página.

- **Novo** Você pode criar uma ou mais das seguintes políticas de versão do cliente:

  - Política de site

  - Política de pool

  - Política de usuário

- **Editar** Você pode alterar as opções de qualquer uma das políticas de versão do cliente. Com essa opção, é possível fazer o seguinte:

  - **Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma política de versão do cliente.

  - **Selecionar Tudo** Essa opção seleciona todas as políticas de versão do cliente na lista.

  - **Excluir** Essa opção exclui todas as políticas de versão do cliente selecionadas.

- **Atualizar** Você pode atualizar a lista de políticas de versão do cliente para verificar o status das opções de todas as políticas de versão do cliente.

Para obter detalhes sobre interoperabilidade entre clientes e versões do cliente, consulte [Interoperabilidade do](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) cliente na documentação planejamento. Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) na documentação Operações.
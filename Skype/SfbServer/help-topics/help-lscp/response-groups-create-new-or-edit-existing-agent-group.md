---
title: Grupos de resposta criar novo ou editar grupo de agentes existentes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: Os grupos de agente definem quem podem responder às chamadas para um grupo de respostas (conhecido como agentes) e as configurações que se aplicam a todos os agentes no grupo.
ms.openlocfilehash: 86dca2b0db3f0daa58c892f36fc09c7f2ea4869dc0d867a8084a16d626b327f6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309460"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Grupos de Resposta: Criar Novo ou Editar Grupo de Agentes Existente

Os grupos de agente definem quem podem responder às chamadas para um grupo de respostas (conhecido como agentes) e as configurações que se aplicam a todos os agentes no grupo.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Cada grupo de agentes requer um nome exclusivo. Use um nome descritivo que identifique a função do grupo. Por exemplo, Suporte Técnico.

- **Descrição** Este campo é opcional. Use-o para fornecer detalhes adicionais sobre o grupo.

- **Política de participação** Especifique a maneira como os agentes devem entrar no grupo de resposta:

  - Selecione **Informal** para especificar que os agentes no grupo não precisam entrar e sair. Os agentes informais são automaticamente assinados quando eles se inscredem. O padrão é **Informal**.

  - Selecione **Formal** para especificar que os agentes no grupo devem entrar e sair. Quando você seleciona essa opção, os agentes clicam em um item de menu no cliente para abrir um navegador e exibir um console de página da Web para entrar e sair.

- **Tempo de alerta (segundos)** Especifique o número de segundos para tocar um agente antes de oferecer a chamada ao próximo agente disponível. O valor precisa ser pelo menos 10 segundos e menos de 180 segundos. O padrão é 20 segundos.

- **Método Routing** Selecione o método para determinar a ordem na qual os agentes recebem chamadas:

  - Selecione **Ocioso por mais tempo** para oferecer uma nova chamada primeiro para o agente que está ocioso (com uma presença de **Disponível** ou **Inativo**) por mais tempo.

  - Selecione **Paralelo** para oferecer uma nova chamada a todos os agentes disponíveis ao mesmo tempo. A chamada é enviada ao primeiro agente que a aceita.

  - Selecione **Round robin** para oferecer uma nova chamada a um agente de cada vez.

  - Selecione **Serial** para sempre oferecer uma nova chamada aos agentes na ordem na qual eles estão relacionados na lista **Agente**.

  - Selecione **Atendente** para oferecer uma nova chamada a todos os agentes que estão assinados e ao aplicativo grupo de resposta ao mesmo tempo, independentemente de sua presença atual. Os atendedores e usuários clientes configurados como agentes podem ver todas as chamadas que estão aguardando e podem atender chamadas de espera em qualquer ordem. A chamada é enviada para o primeiro agente que a aceita, e os outros atendentes e usuários não veem mais a chamada.

- **Agentes** Selecione os usuários que devem ser agentes do grupo de resposta de uma das seguintes maneiras:

  - Selecione **Usar uma lista de distribuição de email existente** para usar uma Exchange de distribuição. Digite o endereço de email da lista de distribuição em **Endereço da lista de distribuição**.

    > [!NOTE]
    > É possível selecionar apenas uma lista de distribuição para um grupo de agentes. Se a lista de distribuição incluir listas de distribuição aninhadas, as listas de distribuição aninhadas não serão incluídas no grupo de agentes.

    > [!NOTE]
    > A ordem na qual os agentes estão listados na lista de distribuição afeta a ordem na qual os agentes recebem chamadas para round robin e roteamento em série.

    > [!NOTE]
    > Associações ocultas ou listas ocultas podem ficar visíveis para administradores ou usuários do Grupo de Resposta. Para obter detalhes, [consulte Create or modify an agent group in Skype for Business 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).

  - Selecione **Definir um grupo personalizado de operadores** para selecionar os usuários que você deseja atribuir como agentes para o grupo de respostas. Clique em **Selecionar** para adicionar um agente à lista. Clique em **Remover** para excluir um agente selecionado da lista.

    As setas para cima e para baixo movem um agente selecionado para cima e para baixo na lista de agentes. A ordem de agentes na lista afeta a ordem na qual os agentes recebem chamadas para roteamento round robin e serial.

Para obter detalhes sobre recursos e recursos do Grupo de Resposta, consulte [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação planejamento. Para obter detalhes sobre como trabalhar com grupos de agente, consulte [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) na documentação Operações.
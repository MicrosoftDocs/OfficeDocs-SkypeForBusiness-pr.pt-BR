---
title: Grupos de resposta criar novo ou Editar grupo de agentes existente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: Os grupos de agente definem quem podem responder às chamadas para um grupo de respostas (conhecido como agentes) e as configurações que se aplicam a todos os agentes no grupo.
ms.openlocfilehash: 9dbd8a5d758b9d10ae1d992cd85df91bee19988a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200608"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Grupos de Resposta: Criar Novo ou Editar Grupo de Agentes Existente

Os grupos de agente definem quem podem responder às chamadas para um grupo de respostas (conhecido como agentes) e as configurações que se aplicam a todos os agentes no grupo.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Cada grupo de operadores requer um nome exclusivo. Use um nome descritivo que identifique a função do grupo. Por exemplo, Suporte Técnico.

- **Descrição** Este campo é opcional. Use-o para fornecer detalhes adicionais sobre o grupo.

- **Política de participação** Especifica a maneira como os agentes fazem logon no grupo de resposta:

  - Selecione **Informal** para especificar que os agentes no grupo não precisam fazer logon e logoff. Agentes informais são conectados automaticamente quando fazem logon no **Informal**.

  - Selecione **Formal** para especificar que os operadores no grupo devem entrar e sair. Quando você seleciona essa opção, os operadores clique em um item de menu no cliente para abrir um navegador e exibir um console de página da web para fazer o logon e sair.

- **Tempo de alerta (segundos)** Especifique o número de segundos a ligar para um operador até repassar a chamada para o próximo operador disponível. O valor precisa ser pelo menos 10 segundos e menos de 180 segundos. O padrão é 20 segundos.

- **Método de roteamento** Selecione o método para determinar a ordem na qual os agentes recebem chamadas:

  - Selecione **Ocioso por mais tempo** para oferecer uma nova chamada primeiro para o agente que está ocioso (com uma presença de  **Disponível** ou  **Inativo**) por mais tempo.

  - Selecione **Paralelo** para oferecer uma nova chamada a todos os agentes disponíveis ao mesmo tempo. A chamada é enviada ao primeiro agente que a aceita.

  - Selecione  **Round robin** para oferecer uma nova chamada a um agente de cada vez.

  - Selecione **Serial** para sempre oferecer uma nova chamada aos agentes na ordem na qual eles estão relacionados na lista **Agente**.

  - Selecione **Attendant** para oferecer uma nova chamada para todos os agentes que estiver conectados e o aplicativo de grupo de resposta ao mesmo tempo, independentemente da sua presença atual. Atendedores e usuários de cliente que são configurados como os operadores podem ver todas as chamadas que estão em espera e podem atender chamadas em espera em qualquer ordem. A chamada é enviada ao primeiro agente que a aceita, e os outros atendedores e usuários não veem mais a chamada.

- **Agentes** Selecione os usuários que serão agentes para o grupo de resposta em uma das seguintes maneiras:

  - Selecione **usar uma lista de distribuição de email existente** para usar uma lista de distribuição do Exchange. Digite o endereço de email da lista de distribuição em **Endereço da lista de distribuição**.

    > [!NOTE]
    > É possível selecionar apenas uma lista de distribuição para um grupo de agentes. Se a lista de distribuição incluir listas de distribuição aninhadas, as listas de distribuição aninhadas não serão incluídas no grupo de agentes.

    > [!NOTE]
    > A ordem na qual os agentes estão listados na lista de distribuição afeta a ordem na qual os agentes recebem chamadas para round robin e roteamento em série.

    > [!NOTE]
    > Associações ou listas ocultas podem ficar visíveis ao grupo de resposta administradores ou usuários. Para obter detalhes, consulte [criar ou modificar um grupo de operadores em Skype para negócios 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).

  - Selecione **Definir um grupo personalizado de operadores** para selecionar os usuários que você deseja atribuir como agentes para o grupo de respostas. Clique em **Selecionar** para adicionar um agente à lista. Clique em  **Remover** para excluir um agente selecionado da lista.

    As setas para cima e para baixo movem um agente selecionado para cima e para baixo na lista de agentes. A ordem de agentes na lista afeta a ordem na qual os agentes recebem chamadas para roteamento round robin e serial.

Para obter detalhes sobre os recursos de grupo de resposta, consulte o [plano para o aplicativo de grupo de resposta no Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação de planejamento. Para obter detalhes sobre como trabalhar com grupos de agente, consulte [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) na documentação Operações.



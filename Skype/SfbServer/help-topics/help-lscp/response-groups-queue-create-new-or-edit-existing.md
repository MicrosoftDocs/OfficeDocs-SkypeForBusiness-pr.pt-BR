---
title: Fila de grupos de resposta criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: As filas do grupo de resposta mantêm chamadas para um grupo de resposta até que um agente atenda a chamada.
ms.openlocfilehash: 4e290c47842ac58cec621629419281cbac63f206
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699786"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Fila de Grupos de Resposta: Criar Nova ou Editar Existente

As filas do grupo de resposta mantêm chamadas para um grupo de resposta até que um agente atenda a chamada.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Cada fila deve ter um nome. Digite um nome descritivo para a fila.

- **Descrição** Este campo é opcional. Use-o para fornecer detalhes adicionais sobre a fila.

- **Grupos** de Selecione os grupos de agente que você deseja atribuir à fila. Clique em **Selecionar** para adicionar grupos de agente à lista. Clique em **Remover** para excluir o grupo de agentes selecionado da lista.

    As setas para cima e para baixo movem um grupo de agentes selecionado para cima e para baixo na lista. A ordem dos grupos de agente afeta a ordem em que o Skype for Business Server procura por um agente disponível. Ou seja, o primeiro grupo na lista é pesquisado primeiro em busca de um agente disponível, seguindo pelo segundo grupo e assim por diante.

- **Habilitar o tempo limite da fila** Marque esta caixa de seleção para especificar um período de tempo máximo para que um chamador aguarde em espera antes que um agente atenda a chamada. Se você selecionar essa opção, também precisará especificar o seguinte:

  - **Período de tempo limite (segundos)** Selecione ou digite o número máximo de segundos que um chamador pode aguardar antes que um agente atenda a chamada.

  - **Ação da chamada** Selecione a ação que ocorre quando uma chamada atinge o tempo limite. Suas opções são:

  - **Desconectar**

  - **Encaminhar para caixa postal** Se você selecionar essa opção, no **endereço SIP**, digite um endereço de correio de voz no formato SIP<username> @ <domainname> : (por exemplo, SIP:Bob@contoso.com).

  - **Encaminhar para número de telefone** Se você selecionar essa opção, em **endereço SIP** , digite o número de telefone no formato SIP<number> @ <domainname> : (por exemplo, SIP:+14255550121@contoso.com).

  - **Encaminhar para endereço SIP** Selecione esta opção para encaminhar a chamada para outro usuário. Em **endereço SIP**, digite o URI para o usuário no formato SIP:<username>@<domainname>.

  - **Encaminhar para outra fila** Se você selecionar essa opção, navegue até a fila para receber chamadas quando o tempo limite das chamadas for atingido.

- **Habilitar o estouro de fila** Marque esta caixa de seleção para especificar um número máximo de chamadas que a fila pode conter. Se você selecionar essa opção, também precisará especificar o seguinte:

  - **Número máximo de chamadas** Selecione ou digite o número máximo de chamadas que a fila pode conter.

  - **Encaminhar a chamada** Selecione qual chamada deve ser tomada quando o limite de estouro de fila for atingido.

  - **Ação da chamada** Selecione a ação que ocorre quando o limite de estouro de fila é atingido. Suas opções são:

  - **Desconectar**

  - **Encaminhar para caixa postal** Se você selecionar essa opção, no **endereço SIP**, digite um endereço de correio de voz no formato SIP<username> @ <domainname> : (por exemplo, SIP:Bob@contoso.com).

  - **Encaminhar para número de telefone** Se você selecionar essa opção, em **endereço SIP** , digite o número de telefone no formato SIP<number> @ <domainname> : (por exemplo, SIP:+14255550121@contoso.com).

  - **Encaminhar para endereço SIP** Selecione esta opção para encaminhar a chamada para outro usuário. Em **endereço SIP**, digite o URI para o usuário no formato SIP:<username>@<domainname>.

  - **Encaminhar para outra fila** Se você selecionar essa opção, navegue até a fila que receberá chamadas quando o limite de estouro da fila for atingido.

Para obter detalhes sobre recursos e recursos do grupo de resposta, consulte [planejar o aplicativo do grupo de resposta no Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação de planejamento. Para obter detalhes sobre como trabalhar com filas, consulte  [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) na documentação Operações.



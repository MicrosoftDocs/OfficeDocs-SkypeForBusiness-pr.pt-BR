---
title: Fila de Grupos de Resposta Criar Nova ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: As filas de espera do Grupo de Resposta rementem chamadas para um grupo de resposta até que um agente responda à chamada.
ms.openlocfilehash: cfe2d212f90f8dcdf83b8f827ebf470245ce87fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829311"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Fila de Grupos de Resposta: Criar Nova ou Editar Existente

As filas de espera do Grupo de Resposta rementem chamadas para um grupo de resposta até que um agente responda à chamada.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Cada fila deve ter um nome. Digite um nome descritivo para a fila.

- **Descrição** Esse campo é opcional. Use-o para fornecer detalhes adicionais sobre a fila.

- **Grupos** Selecione os grupos de agentes que você deseja atribuir à fila. Clique em **Selecionar** para adicionar grupos de agente à lista. Clique em **Remover** para excluir o grupo de agentes selecionado da lista.

    As setas para cima e para baixo movem um grupo de agentes selecionado para cima e para baixo na lista. A ordem dos grupos de agentes afeta a ordem na qual o Skype for Business Server procura um agente disponível. Ou seja, o primeiro grupo na lista é pesquisado primeiro em busca de um agente disponível, seguindo pelo segundo grupo e assim por diante.

- **Habilitar o tempo de espera** Marque essa caixa de seleção para especificar um período máximo de espera para um chamador antes de um agente atender à chamada. Se você selecionar essa opção, também precisará especificar o seguinte:

  - **Período de tempo de tempo (segundos)** Selecione ou digite o número máximo de segundos que um chamador pode aguardar antes de um agente atender à chamada.

  - **Ação de chamada** Selecione a ação que ocorre quando uma chamada se estiva. Suas opções são:

  - **Desconectar**

  - **Encaminhar para caixa postal** Se você selecionar essa opção, no endereço **SIP,** digite um endereço de caixa postal no formato sip: <username> @ <domainname> (por exemplo, sip:bob@contoso.com).

  - **Encaminhar para número de telefone** Se você selecionar essa opção, no endereço **SIP,** digite o número de telefone no formato sip: <number> @ <domainname> (por exemplo, sip:+14255550121@contoso.com).

  - **Encaminhar para endereço SIP** Selecione essa opção para encaminhar a chamada para outro usuário. No **endereço SIP,** digite o URI do usuário no formato sip: <username> @ <domainname> .

  - **Encaminhar para outra fila** Se você selecionar essa opção, navegue até a fila que receberá chamadas quando o tempo de espera das chamadas se passar.

- **Habilitar o estouro da fila** Marque essa caixa de seleção para especificar um número máximo de chamadas que a fila pode segurar. Se você selecionar essa opção, também precisará especificar o seguinte:

  - **Número máximo de chamadas** Selecione ou digite o número máximo de chamadas que a fila pode segurar.

  - **Encaminhar a chamada** Selecione qual chamada deve agir quando o limite de estouro da fila for atendido.

  - **Ação de chamada** Selecione a ação que ocorre quando o limite de estouro da fila é atendido. Suas opções são:

  - **Desconectar**

  - **Encaminhar para caixa postal** Se você selecionar essa opção, no endereço **SIP,** digite um endereço de caixa postal no formato sip: <username> @ <domainname> (por exemplo, sip:bob@contoso.com).

  - **Encaminhar para número de telefone** Se você selecionar essa opção, no endereço **SIP,** digite o número de telefone no formato sip: <number> @ <domainname> (por exemplo, sip:+14255550121@contoso.com).

  - **Encaminhar para endereço SIP** Selecione essa opção para encaminhar a chamada para outro usuário. No **endereço SIP,** digite o URI do usuário no formato sip: <username> @ <domainname> .

  - **Encaminhar para outra fila** Se você selecionar essa opção, navegue até a fila que receberá chamadas quando o limite de estouro da fila for atendido.

Para obter detalhes sobre recursos e recursos do Grupo de Resposta, consulte [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação planejamento. Para obter detalhes sobre como trabalhar com filas, consulte [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) na documentação Operações.



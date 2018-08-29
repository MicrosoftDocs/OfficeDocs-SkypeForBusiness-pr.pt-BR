---
title: Fila de grupos de resposta criar novo ou editar existente
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Filas de espera do grupo de resposta chamadas para um grupo de resposta em espera até que um operador responde à chamada.
ms.openlocfilehash: b55f1ad12369824a60282294dacfc63177675e02
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263834"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Fila de Grupos de Resposta: Criar Nova ou Editar Existente

Filas de espera do grupo de resposta chamadas para um grupo de resposta em espera até que um operador responde à chamada.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Cada fila precisa ter um nome. Digite um nome descritivo para a fila.

- **Descrição** Este campo é opcional. Use-o para fornecer detalhes adicionais sobre a fila.

- **Grupos** Selecione os grupos de operadores que você deseja atribuir à fila. Clique em **Selecionar** para adicionar grupos de agente à lista. Clique em **Remover** para excluir o grupo de agentes selecionado da lista.

    As setas para cima e para baixo movem um grupo de agentes selecionado para cima e para baixo na lista. A ordem dos grupos de operadores afeta a ordem na qual o Skype para Business Server procura um operador disponível. Ou seja, o primeiro grupo na lista é pesquisado primeiro em busca de um agente disponível, seguindo pelo segundo grupo e assim por diante.

- **Habilitar o tempo limite da fila** Marque esta caixa de seleção para especificar um período máximo de tempo que um chamador esperar em espera antes de um operador responde à chamada. Se você selecionar essa opção, também precisará especificar o seguinte:

  - **Período de tempo limite (segundos)** Selecione ou digite o número máximo de segundos que um chamador pode esperar antes que um operador responde à chamada.

  - **Ação de chamada** Selecione a ação que ocorre quando uma chamada expire. Suas opções são:

  - **Desconectar**

  - **Encaminhar para caixa postal** Se você selecionar essa opção, no **endereço SIP**, digite um endereço da caixa postal no formato sip:<username> @ <domainname> (por exemplo, sip:bob@contoso.com).

  - **Encaminhar para número de telefone** Se você selecionar essa opção, no **endereço SIP** digite o número de telefone no formato sip:<number> @ <domainname> (por exemplo, sip:+14255550121@contoso.com).

  - **Encaminhar para endereço SIP** Selecione essa opção para encaminhar a chamada para outro usuário. Em **endereço SIP**, digite o URI do usuário no formato sip:<username>@<domainname>.

  - **Encaminhar para outra fila de espera** Se você selecionar essa opção, navegue até a fila que receberá as chamadas quando o tempo limite de chamadas.

- **Habilitar o estouro da fila** Marque esta caixa de seleção para especificar um número máximo de chamadas que a fila pode segurar. Se você selecionar essa opção, também precisará especificar o seguinte:

  - **Número máximo de chamadas** Selecione ou digite o número máximo de chamadas que a fila pode segurar.

  - **Encaminhar a chamada** Selecione qual chamada deverá executar uma ação quando o limite de estouro da fila for atingido.

  - **Ação de chamada** Selecione a ação que ocorre quando o limite de estouro da fila for atingido. Suas opções são:

  - **Desconectar**

  - **Encaminhar para caixa postal** Se você selecionar essa opção, no **endereço SIP**, digite um endereço da caixa postal no formato sip:<username> @ <domainname> (por exemplo, sip:bob@contoso.com).

  - **Encaminhar para número de telefone** Se você selecionar essa opção, no **endereço SIP** digite o número de telefone no formato sip:<number> @ <domainname> (por exemplo, sip:+14255550121@contoso.com).

  - **Encaminhar para endereço SIP** Selecione essa opção para encaminhar a chamada para outro usuário. Em **endereço SIP**, digite o URI do usuário no formato sip:<username>@<domainname>.

  - **Encaminhar para outra fila de espera** Se você selecionar essa opção, navegue até a fila que receberá as chamadas quando o limite de estouro da fila for atingido.

Para obter detalhes sobre os recursos de grupo de resposta, consulte o [plano para o aplicativo de grupo de resposta no Skype para Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação de planejamento. Para obter detalhes sobre como trabalhar com filas, consulte [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) na documentação operações.



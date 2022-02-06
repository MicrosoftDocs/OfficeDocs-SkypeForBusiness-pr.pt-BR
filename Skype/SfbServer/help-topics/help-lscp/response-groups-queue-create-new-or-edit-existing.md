---
title: Fila de Grupos de Resposta Criar Novo ou Editar Existente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: As filas do Grupo de Resposta resitem chamadas para um grupo de resposta até que um agente responda à chamada.
---

# <a name="response-groups-queue-create-new-or-edit-existing"></a>Fila de Grupos de Resposta: Criar Nova ou Editar Existente

As filas do Grupo de Resposta resitem chamadas para um grupo de resposta até que um agente responda à chamada.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Cada fila deve ter um nome. Digite um nome descritivo para a fila.

- **Descrição** Este campo é opcional. Use-o para fornecer detalhes adicionais sobre a fila.

- **Grupos** Selecione os grupos de agentes que você deseja atribuir à fila. Clique em **Selecionar** para adicionar grupos de agente à lista. Clique em **Remover** para excluir o grupo de agentes selecionado da lista.

    As setas para cima e para baixo movem um grupo de agentes selecionado para cima e para baixo na lista. A ordem dos grupos de agentes afeta a ordem na qual Skype for Business Server procura um agente disponível. Ou seja, o primeiro grupo na lista é pesquisado primeiro em busca de um agente disponível, seguindo pelo segundo grupo e assim por diante.

- **Habilitar o tempo de espera da fila** Marque essa caixa de seleção para especificar um período máximo de tempo para um chamador aguardar em espera antes que um agente responda à chamada. Se você selecionar essa opção, também precisará especificar o seguinte:

  - **Período de tempo decoro (segundos)** Selecione ou digite o número máximo de segundos que um chamador pode esperar antes que um agente responda à chamada.

  - **Ação de chamada** Selecione a ação que ocorre quando uma chamada é o tempo de saída. Suas opções são:

  - **Desconectar**

  - **Encaminhar para caixa postal** Se você selecionar essa opção, no **endereço SIP**, digite um endereço de caixa postal no formato sip:\<username>@\<domainname> (por exemplo, sip:bob@contoso.com).

  - **Encaminhar para o número de telefone** Se você selecionar essa opção, no **endereço SIP** digite o número de telefone no formato sip:\<number>@\<domainname> (por exemplo, sip:+14255550121@contoso.com).

  - **Encaminhar para endereço SIP** Selecione essa opção para encaminhar a chamada para outro usuário. No **endereço SIP**, digite o URI do usuário no formato sip:\<username>@\<domainname>.

  - **Encaminhar para outra fila** Se você selecionar essa opção, navegue até a fila para receber chamadas quando as chamadas se desem tempo de espera.

- **Habilitar estouro de fila** Marque essa caixa de seleção para especificar um número máximo de chamadas que a fila pode realizar. Se você selecionar essa opção, também precisará especificar o seguinte:

  - **Número máximo de chamadas** Selecione ou digite o número máximo de chamadas que a fila pode realizar.

  - **Encaminhar a chamada** Selecione qual chamada deve ser tomada quando o limite de estouro da fila for atendido.

  - **Ação de chamada** Selecione a ação que ocorre quando o limite de estouro de fila é atendido. Suas opções são:

  - **Desconectar**

  - **Encaminhar para caixa postal** Se você selecionar essa opção, no **endereço SIP**, digite um endereço de caixa postal no formato sip:\<username>@\<domainname> (por exemplo, sip:bob@contoso.com).

  - **Encaminhar para o número de telefone** Se você selecionar essa opção, no **endereço SIP** digite o número de telefone no formato sip:\<number>@\<domainname> (por exemplo, sip:+14255550121@contoso.com).

  - **Encaminhar para endereço SIP** Selecione essa opção para encaminhar a chamada para outro usuário. No **endereço SIP**, digite o URI do usuário no formato sip:\<username>@\<domainname>.

  - **Encaminhar para outra fila** Se você selecionar essa opção, navegue até a fila que receberá chamadas quando o limite de estouro da fila for atendido.

Para obter detalhes sobre recursos e recursos do Grupo de Resposta, consulte [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação planejamento. Para obter detalhes sobre como trabalhar com filas, consulte [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) na documentação Operações.
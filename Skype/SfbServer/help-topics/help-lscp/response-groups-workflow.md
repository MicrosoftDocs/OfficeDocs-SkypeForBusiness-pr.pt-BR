---
title: Fluxo de Trabalho de Grupos de Resposta
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: Os grupos de resposta são compostos por grupos de agente, filas e fluxos de trabalho. Os fluxos de trabalho do Grupo de Resposta definem as ações que são tomadas quando o aplicativo grupo de resposta recebe uma chamada telefônica.
ms.openlocfilehash: 0f29bfd64cbe01026bc4959d35fa17d5640b3538
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628163"
---
# <a name="response-groups-workflow"></a>Fluxo de Trabalho de Grupos de Resposta

Os grupos de resposta são compostos por grupos de agente, filas e fluxos de trabalho. Os fluxos de trabalho do Grupo de Resposta definem as ações que são tomadas quando o aplicativo grupo de resposta recebe uma chamada telefônica.

A **página Fluxo de** Trabalho de Grupos de Resposta exibe uma lista de todos os fluxos de trabalho do Grupo de Resposta  -   definidos para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página Fluxo de Trabalho **de Grupos**  -  **de** Resposta:

- Criar ou alterar um fluxo de trabalho de grupo de busca

- Criar ou alterar um fluxo de trabalho interativo

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Criar ou editar um fluxo de trabalho** Abre a Ferramenta de Configuração de Grupo de Resposta para criar ou editar um fluxo de trabalho.

- **Atualizar** Atualiza a lista de fluxos de trabalho.

A lista a seguir descreve os campos na página.

- **Nome** O nome exclusivo atribuído ao fluxo de trabalho.

- **Serviço** O **serviço ApplicationServer** que hospeda o fluxo de trabalho.

- **Endereço SIP** O endereço SIP do grupo que atenderá chamadas ao fluxo de trabalho.

- **Telefone** O número de telefone chamado para chegar a esse grupo de resposta.

- **Idioma** O idioma usado para reconhecimento de fala e texto para fala.

- **IVR** Indica se o fluxo de trabalho é um grupo de busca ou um fluxo de trabalho interativo.

- **Habilitado** Indica se o fluxo de trabalho está ativado para receber chamadas.

Para obter detalhes sobre recursos e recursos do Grupo de Resposta, consulte [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação planejamento. Para obter detalhes sobre como trabalhar com fluxos de trabalho do Grupo de Resposta, consulte [Managing Response Group Workflows](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows) na documentação Operações.
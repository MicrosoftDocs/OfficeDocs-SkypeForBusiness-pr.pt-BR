---
title: Estacionamento de Chamada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Quando uma chamada estiver estacionada, ele será transferido para um número temporário onde a chamada é mantida até que alguém as recupere ou ele expire. Você precisa configurar uma tabela com os intervalos de números de ramal que você é reservar para chamadas estacionadas. Essas extensões precisam ser extensões virtuais (ou seja, extensões sem usuário ou telefone atribuídas a ela). Cada pool que executa o aplicativo de estacionamento de chamada pode ter um ou mais intervalos de extensões. Esses intervalos precisam ser globalmente exclusivos em sua implantação.
ms.openlocfilehash: 2470d820b6536fdcd966e25d8719cd89903b4519
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197048"
---
# <a name="call-park"></a>Estacionamento de Chamada

Quando uma chamada estiver estacionada, ele será transferido para um número temporário onde a chamada é mantida até que alguém as recupere ou ele expire. Você precisa configurar uma tabela com os intervalos de números de ramal que você é reservar para chamadas estacionadas. Essas extensões precisam ser extensões virtuais (ou seja, extensões sem usuário ou telefone atribuídas a ela). Cada pool que executa o aplicativo de estacionamento de chamada pode ter um ou mais intervalos de extensões. Esses intervalos precisam ser globalmente exclusivos em sua implantação.

Página **Estacionamento** de chamada exibe uma lista de todos os intervalos números estacionamento de chamada definidas para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Estacionamento de Chamada**:

- Criar um novo intervalo de números

- Alterar um intervalo de números existente

- Excluir um intervalo de números

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Novo** Inicia um novo intervalo de números do estacionamento de chamadas.

- **Editar** Abre o intervalo de números selecionado para edição, seleciona todos os intervalos de números na lista ou exclui o intervalo de números selecionado.

- **Atualizar** Atualiza a lista de intervalos de números.

A lista a seguir descreve os campos na página.

- **Nome** O nome exclusivo que identifica o intervalo de números.

- **Intervalo inicial** O número inicial do intervalo.

- **Intervalo final** O número final do intervalo.

- **Destino** Domínio totalmente qualificado (FQDN) nome ou ID de serviço do serviço aplicativo que hospeda o aplicativo de estacionamento de chamada para o intervalo de números.

Para obter detalhes sobre os recursos de estacionamento de chamada e capacidades, consulte [Planejar estacionamento de chamada no Skype para negócios 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obter detalhes sobre como trabalhar com intervalos de números do estacionamento de chamada, consulte [Configurar extensões de número de telefone para o estacionamento de chamadas](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).



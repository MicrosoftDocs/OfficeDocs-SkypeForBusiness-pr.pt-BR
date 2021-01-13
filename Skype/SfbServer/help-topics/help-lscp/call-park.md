---
title: Estacionamento de Chamada
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
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Quando uma chamada é estacionada, ela é transferida para um número temporário no qual a chamada é mantida até que alguém a recupere ou o tempo se esvae. Você precisa configurar uma tabela com os intervalos de ramais que você está reservando para chamadas estacionadas. Essas extensões precisam ser extensões virtuais (ou seja, extensões com nenhum usuário ou telefone atribuído a eles). Cada pool que executa o aplicativo Estacionamento de Chamada pode ter um ou mais intervalos de extensões. Esses intervalos precisam ser globalmente exclusivos em sua implantação.
ms.openlocfilehash: 7723b3bb3145725834059c73c0acc273fc67ca61
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800301"
---
# <a name="call-park"></a>Estacionamento de Chamada

Quando uma chamada é estacionada, ela é transferida para um número temporário no qual a chamada é mantida até que alguém a recupere ou o tempo se esvae. Você precisa configurar uma tabela com os intervalos de ramais que você está reservando para chamadas estacionadas. Essas extensões precisam ser extensões virtuais (ou seja, extensões com nenhum usuário ou telefone atribuído a eles). Cada pool que executa o aplicativo Estacionamento de Chamada pode ter um ou mais intervalos de extensões. Esses intervalos precisam ser globalmente exclusivos em sua implantação.

A **página Estacionamento de** Chamada exibe uma lista de todos os intervalos de números de Estacionamento de Chamada definidos para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Estacionamento de Chamada**:

- Criar um novo intervalo de números

- Alterar um intervalo de números existente

- Excluir um intervalo de números

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Novo** Inicia um novo intervalo de números de Estacionamento de Chamada.

- **Editar** Abre o intervalo de números selecionado para edição, seleciona todos os intervalos de números na lista ou exclui o intervalo de números selecionado.

- **Atualizar** Atualiza a lista de intervalos de números.

A lista a seguir descreve os campos na página.

- **Nome** O nome exclusivo que identifica o intervalo de números.

- **Intervalo inicial** O número inicial do intervalo.

- **Intervalo final** O número final do intervalo.

- **Destino** O FQDN (nome de domínio totalmente qualificado) ou ID de serviço do serviço de Aplicativo que hospeda o aplicativo Estacionamento de Chamada para o intervalo de números.

Para obter detalhes sobre recursos de Estacionamento de Chamada, consulte [Plan for Call Park in Skype for Business 2015.](../../plan-your-deployment/enterprise-voice-solution/call-park.md) Para obter detalhes sobre como trabalhar com intervalos de números de Estacionamento de Chamadas, consulte Configurar Extensões de Número de Telefone [para Estacionamento de Chamadas.](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)



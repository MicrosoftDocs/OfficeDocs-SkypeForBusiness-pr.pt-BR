---
title: Estacionamento de Chamada
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Quando uma chamada é estacionada, ela é transferida para um número temporário onde a chamada é mantida até que alguém a recupere ou ela se esvaia. Você precisa configurar uma tabela com os intervalos de números de extensão que você está reservando para chamadas estacionadas. Essas extensões precisam ser extensões virtuais (ou seja, extensões com nenhum usuário ou telefone atribuído a eles). Cada pool que executa o aplicativo Estacionamento de Chamada pode ter um ou mais intervalos de extensões. Esses intervalos precisam ser globalmente exclusivos em sua implantação.
ms.openlocfilehash: 0fc52a688ba3b95e2dd2cdd13c6aab8c4d48f97269e51a7845e363bcc55c38e4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54287480"
---
# <a name="call-park"></a>Estacionamento de Chamada

Quando uma chamada é estacionada, ela é transferida para um número temporário onde a chamada é mantida até que alguém a recupere ou ela se esvaia. Você precisa configurar uma tabela com os intervalos de números de extensão que você está reservando para chamadas estacionadas. Essas extensões precisam ser extensões virtuais (ou seja, extensões com nenhum usuário ou telefone atribuído a eles). Cada pool que executa o aplicativo Estacionamento de Chamada pode ter um ou mais intervalos de extensões. Esses intervalos precisam ser globalmente exclusivos em sua implantação.

A **página Estacionamento** de Chamada exibe uma lista de todos os intervalos de números do Estacionamento de Chamada definidos para sua organização.

## <a name="tasks-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Estacionamento de Chamada**:

- Criar um novo intervalo de números

- Alterar um intervalo de números existente

- Excluir um intervalo de números

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os comandos na página.

- **Novo** Inicia um novo intervalo de números do Estacionamento de Chamada.

- **Editar** Abre o intervalo de números selecionado para edição, seleciona todos os intervalos de números na lista ou exclui o intervalo de números selecionado.

- **Atualizar** Atualiza a lista de intervalos de números.

A lista a seguir descreve os campos na página.

- **Nome** O nome exclusivo que identifica o intervalo de números.

- **Intervalo inicial** O número inicial do intervalo.

- **Intervalo final** O número final do intervalo.

- **Destination** O FQDN (nome de domínio totalmente qualificado) ou a ID de serviço do serviço application que hospeda o aplicativo Estacionamento de Chamada para o intervalo de números.

Para obter detalhes sobre recursos e recursos do Estacionamento de Chamada, consulte [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obter detalhes sobre como trabalhar com intervalos de números do Estacionamento de Chamadas, consulte [Configure Telefone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).
---
title: Estacionamento de chamada criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Os intervalos numéricos do parque da chamada definem os números temporários nos quais as chamadas estacionadas são mantidas até que alguém as recupere ou perca o tempo limite.
ms.openlocfilehash: 7257327081be46f343ef8aeb6076ad9a788f46bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290167"
---
# <a name="call-park-create-new-or-edit-existing"></a>Estacionamento de Chamada: Criar Novo ou Editar Existente

Os intervalos numéricos do parque da chamada definem os números temporários nos quais as chamadas estacionadas são mantidas até que alguém as recupere ou perca o tempo limite.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Digite um nome descritivo que identifique o intervalo de números. Depois de salvar o intervalo de números, esse nome não pode ser alterado.

- **Intervalo de números** No primeiro campo, digite o número inicial do intervalo de números. No segundo campo, digite o número final do intervalo de números.

  - O número inicial do intervalo deve ser menor ou igual ao número final.

  - O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.

  - O intervalo de números precisa ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.

  - Se o intervalo de números começar com o \* caractere ou #, o intervalo deve ser maior que 100.

  - Valores válidos: devem corresponder à cadeia de caracteres de expressão\\regular ([* | #] ? [1-{0,7}9] \d) | ([1-9] \d{0,8}). Isso significa que o valor deve ser uma cadeia de caracteres que comece \* com o caractere ou # ou um número de 1 a 9 (o primeiro caractere não pode ser zero). Se o primeiro caractere for \* ou #, o seguinte caractere deve ser um número de 1 a 9 (não pode ser zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000"\*, "92000"\*, "95551212" e "915551212"). Se o primeiro caractere não \* for ou #, o primeiro caractere deve ser um número de 1 a 9 (ele não pode ser zero), seguido de até oito caracteres, cada um dos números de 0 a 9 (por exemplo: 915551212; 41212; 300).

  - No total, você não deve ter mais do que 50.000 números por pool. Cada intervalo de números envolve normalmente 100 ou menos números, mas pode ser muito maior, contanto que inclua menos de 10.000 números. Por exemplo, em vez de especificar um número inicial de "7000000" e um número final de "8000000", considere especificar um número inicial de"7000000" e um número final de"7000100".

- **FQDN do servidor de destino** Selecione o nome de domínio totalmente qualificado (FQDN) ou a ID de serviço do serviço de aplicativo que hospeda o aplicativo parque de chamadas. Todas as chamadas estacionadas em números dentro do intervalo especificado pelos números inicial e final serão encaminhadas para esse servidor ou pool.

Para obter detalhes sobre os recursos e recursos do parque da chamada, consulte [planejar o estacionamento de chamadas no Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obter detalhes sobre como trabalhar com intervalos numéricos do parque da chamada, consulte [Configurar extensões de número de telefone para chamadas com estacionamento](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).



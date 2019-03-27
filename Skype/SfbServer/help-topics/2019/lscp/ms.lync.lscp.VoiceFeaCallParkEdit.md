---
title: Estacionamento de chamada criar novo ou editar existente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Intervalos de números do estacionamento de chamada definem os números temporários nos quais as chamadas estacionadas são mantidas até que alguém as recupere ou tempo limite.
ms.openlocfilehash: 466dc1d02ee15ae25e6c8fe6e9e8a0006298a60d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879375"
---
# <a name="call-park-create-new-or-edit-existing"></a>Estacionamento de Chamada: Criar Novo ou Editar Existente

Intervalos de números do estacionamento de chamada definem os números temporários nos quais as chamadas estacionadas são mantidas até que alguém as recupere ou tempo limite.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Digite um nome descritivo que identifica o intervalo de números. Depois de salvar o intervalo de números, esse nome não pode ser alterado.

- **Intervalo de número** No primeiro campo, digite o número inicial do intervalo de números. No segundo campo, digite o número final do intervalo de números.

  - O número inicial do intervalo deve ser menor ou igual ao número final.

  - O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.

  - O intervalo de números precisa ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.

  - Se o intervalo de números começa com o caractere \* ou #, o intervalo deve ser maior que 100.

  - Valores válidos: deve coincidir com a cadeia de caracteres de expressão regular ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}). Isso significa que o valor deve ser uma cadeia de caracteres iniciada com o caractere \* ou #, ou um número entre 1 e 9 (o primeiro caractere não pode ser um zero). Se o primeiro caractere for \* ou #, o caractere seguinte deve ser um número entre 1 e 9 (ele não pode ser um zero). Os caracteres subsequentes podem ser qualquer número entre 0 e 9 até sete caracteres adicionais (por exemplo, "#6000", "\*92000", "\*95551212" e "915551212"). Se o primeiro caractere não for \* ou #, o primeiro caractere deve ser um número entre 1 e 9 (ele não pode ser zero), seguido por até oito caracteres, cada um número entre 0 e 9 (por exemplo: 915551212; 41212; 300).

  - No total, você não deve ter mais do que 50.000 números por pool. Cada intervalo de números envolve normalmente 100 ou menos números, mas pode ser muito maior, contanto que inclua menos de 10.000 números. Por exemplo, em vez de especificar um número inicial de "7000000" e um número final de "8000000", considere especificar um número inicial de"7000000" e um número final de"7000100".

- **FQDN do servidor de destino** Selecione o nome de domínio totalmente qualificado (FQDN) ou ID de serviço do serviço aplicativo que hospeda o aplicativo de estacionamento de chamadas. Todas as chamadas estacionadas em números dentro do intervalo especificado pelos números inicial e final serão encaminhadas para esse servidor ou pool.

Para obter detalhes sobre os recursos de estacionamento de chamada e capacidades, consulte [Planejar estacionamento de chamada no Skype para negócios](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obter detalhes sobre como trabalhar com intervalos de números do estacionamento de chamada, consulte [Configurar extensões de número de telefone para o estacionamento de chamadas](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).



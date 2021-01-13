---
title: Estacionamento de Chamada Criar Novo ou Editar Existente
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
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Os intervalos de números de Estacionamento de Chamada definem os números temporários em que as chamadas estacionadas são mantidas até que alguém as recupere ou o tempo se esvae.
ms.openlocfilehash: 5ee0891ebaabc97b965aadc5f1ab1c4390669427
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819381"
---
# <a name="call-park-create-new-or-edit-existing"></a>Estacionamento de Chamada: Criar Novo ou Editar Existente

Os intervalos de números de Estacionamento de Chamada definem os números temporários em que as chamadas estacionadas são mantidas até que alguém as recupere ou o tempo se esvae.

## <a name="ui-reference"></a>Referência de UI

A lista a seguir descreve os campos na página.

- **Nome** Digite um nome descritivo que identifique o intervalo de números. Depois de salvar o intervalo de números, esse nome não pode ser alterado.

- **Intervalo de números** No primeiro campo, digite o número inicial do intervalo de números. No segundo campo, digite o número final do intervalo de números.

  - O número inicial do intervalo deve ser menor ou igual ao número final do intervalo.

  - O valor do número inicial do intervalo deve ter a mesma extensão que o número final do intervalo.

  - O intervalo de números deve ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.

  - Se o intervalo de números começar com o caractere \* ou #, o intervalo deverá ser maior que 100.

  - Valores válidos: devem corresponder à cadeia de caracteres de expressão regular ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Isso significa que o valor deve ser uma cadeia de caracteres começando com o caractere ou # ou um número de 1 a 9 (o primeiro caractere \* não pode ser zero). Se o primeiro caractere for ou #, o caractere seguinte deverá ser um número \* de 1 a 9 (não pode ser zero). Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000", " \* 92000", " \* 95551212" e "915551212"). Se o primeiro caractere não for ou #, o primeiro caractere deverá ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um deles um número \* de 0 a 9 (por exemplo: 915551212;41212;300).

  - Você não deve ter mais de um total de 50.000 números por pool. Cada intervalo de números geralmente abrange 100 ou menos números, mas pode ser muito maior, desde que inclua menos de 10.000 números. Por exemplo, em vez de especificar um número inicial em "7000000" e um número final em "8000000", considere especificar um número inicial em "7000000" e um número final em "7000100".

- **FQDN do servidor de destino** Selecione o nome de domínio totalmente qualificado (FQDN) ou o ID de serviço do serviço de Aplicativo que hospeda o aplicativo Estacionamento de Chamada. Todas as chamadas estacionadas em números dentro do intervalo especificado pelo número inicial e número final no intervalo de números serão roteadas para este servidor ou pool.

Para obter detalhes sobre recursos de Estacionamento de Chamada, consulte [Plan for Call Park in Skype for Business 2015.](../../plan-your-deployment/enterprise-voice-solution/call-park.md) Para obter detalhes sobre como trabalhar com intervalos de números de Estacionamento de Chamadas, consulte Configurar Extensões de Número de Telefone [para Estacionamento de Chamadas.](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)



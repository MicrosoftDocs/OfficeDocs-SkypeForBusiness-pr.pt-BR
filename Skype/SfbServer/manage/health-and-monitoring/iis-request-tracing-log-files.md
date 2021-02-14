---
title: Monitorando arquivos de log de rastreamento de solicitação do IIS no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumo: saiba mais sobre o suporte do Mobility Service (Mcx) no Skype for Business Server 2015 para clientes herdados.'
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823501"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Monitorando arquivos de log de rastreamento de solicitação do IIS no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o suporte do Mobility Service (Mcx) no Skype for Business Server 2015 para clientes herdado.
  
Este tópico aplica-se a implantações que suportam apenas clientes do Lync 2010 Lync Mobile e destina-se ao Mobility Service (Mcx).

> [!NOTE]
> O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.
  
Quando você habilita o rastreamento de solicitação do IIS (Serviços de Informações da Internet) para o Serviço de Mobilidade do Skype for Business Server (Mcx), os arquivos de log gerados podem consumir até três gigabytes de espaço em disco por dia. O registro em log do rastreamento IIS está habilitado por padrão. Você deve monitorar os Servidores front-end para garantir que eles não ficam sem espaço em disco. 
  
Por padrão, o IIS armazena os arquivos de log em %SystemDrive%\inetpub\logs\LogFiles.
  
Para desativar o rastreamento de solicitação IIS para todo um servidor, na linha de comando, digite o seguinte:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Para obter detalhes sobre **o comando httpLogging,** consulte [a referência de comando.](https://go.microsoft.com/fwlink/p/?linkId=234927)
  


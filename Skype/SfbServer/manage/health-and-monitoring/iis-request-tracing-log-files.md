---
title: Monitorando arquivos de log de rastreamento de solicitações de IIS no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumo: Saiba mais sobre o serviço de mobilidade (Mcx) no Skype para Business Server 2015 suporte para clientes herdados.'
ms.openlocfilehash: 51913162603203333cd201c64ed21770825bdaf7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Monitorando arquivos de log de rastreamento de solicitações de IIS no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o serviço de mobilidade (Mcx) no Skype para Business Server 2015 suporte para clientes herdados.
  
Este tópico se aplica a implantações que oferecem suporte somente aos clientes do Lync 2010 Lync Mobile, e destina-se ao Serviço de Mobilidade (Mcx).
  
Quando você habilita o rastreamento de solicitação de serviços de informações da Internet (IIS) para o Skype para serviço de mobilidade do Business Server (Mcx), os arquivos de log gerados podem consumir até três gigabytes de espaço em disco por dia. O registro em log do rastreamento IIS está habilitado por padrão. Você deve monitorar os servidores Front-End para certificar-se de que elas não são executadas sem espaço em disco. 
  
Por padrão, o IIS armazena os arquivos de log em %SystemDrive%\inetpub\logs\LogFiles.
  
Para desativar o rastreamento de solicitação IIS para todo um servidor, na linha de comando, digite o seguinte:
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Para obter detalhes sobre o comando **httpLogging** , consulte [a referência de comandos](https://go.microsoft.com/fwlink/p/?linkId=234927).
  


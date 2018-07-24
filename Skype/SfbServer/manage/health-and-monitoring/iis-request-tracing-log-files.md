---
title: Monitorando arquivos de log de rastreamento de solicitações de IIS no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumo: Saiba mais sobre o serviço de mobilidade (Mcx) no Skype para Business Server 2015 suporte para clientes herdados.'
ms.openlocfilehash: 5ed817290bdf86d11dd4a2cf0e95c83fb4c31d9a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983823"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Monitorando arquivos de log de rastreamento de solicitações de IIS no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o serviço de mobilidade (Mcx) no Skype para Business Server 2015 suporte para clientes herdados.
  
Este tópico se aplica a implantações que oferecem suporte somente aos clientes do Lync 2010 Lync Mobile, e destina-se ao Serviço de Mobilidade (Mcx).

> [!NOTE]
> Suporte MCX para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Os usuários precisarem de atualização para um cliente atual.
  
Quando você habilita o rastreamento de solicitação de serviços de informações da Internet (IIS) para o Skype para serviço de mobilidade do Business Server (Mcx), os arquivos de log gerados podem consumir até três gigabytes de espaço em disco por dia. O registro em log do rastreamento IIS está habilitado por padrão. Você deve monitorar os servidores Front-End para certificar-se de que elas não são executadas sem espaço em disco. 
  
Por padrão, o IIS armazena os arquivos de log em %SystemDrive%\inetpub\logs\LogFiles.
  
Para desativar o rastreamento de solicitação IIS para todo um servidor, na linha de comando, digite o seguinte:
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Para obter detalhes sobre o comando **httpLogging** , consulte [a referência de comandos](https://go.microsoft.com/fwlink/p/?linkId=234927).
  


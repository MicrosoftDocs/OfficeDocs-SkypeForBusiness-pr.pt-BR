---
title: Monitorando arquivos de log de rastreamento de solicitações de IIS no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Resumo: Saiba mais sobre o serviço de mobilidade (MCX) no Skype for Business Server 2015 suporte para clientes herdados.'
ms.openlocfilehash: b8d22146de43f020b62cc249a07990fb9f0cc73c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305658"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Monitorando arquivos de log de rastreamento de solicitações de IIS no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o serviço de mobilidade (MCX) no Skype for Business Server 2015 suporte para clientes herdados.
  
Este tópico se aplica a implantações que oferecem suporte somente aos clientes do Lync 2010 Lync Mobile, e destina-se ao Serviço de Mobilidade (Mcx).

> [!NOTE]
> O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.
  
Ao habilitar o rastreamento de solicitação dos serviços de informações da Internet (IIS) para o serviço de mobilidade do Skype for Business Server (MCX), os arquivos de registro gerados podem consumir até três gigabytes de espaço em disco por dia. O registro em log do rastreamento IIS está habilitado por padrão. Você deve monitorar os servidores de front-end para ter certeza de que eles não ficam sem espaço em disco. 
  
Por padrão, o IIS armazena os arquivos de log em %SystemDrive%\inetpub\logs\LogFiles.
  
Para desativar o rastreamento de solicitação IIS para todo um servidor, na linha de comando, digite o seguinte:
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Para obter detalhes sobre o comando **httpLogging** , consulte [referência de comando](https://go.microsoft.com/fwlink/p/?linkId=234927).
  


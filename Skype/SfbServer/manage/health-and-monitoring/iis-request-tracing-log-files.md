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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="9f6f0-103">Monitorando arquivos de log de rastreamento de solicitações de IIS no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9f6f0-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9f6f0-104">**Resumo:** Saiba mais sobre o serviço de mobilidade (Mcx) no Skype para Business Server 2015 suporte para clientes herdados.</span><span class="sxs-lookup"><span data-stu-id="9f6f0-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="9f6f0-105">Este tópico se aplica a implantações que oferecem suporte somente aos clientes do Lync 2010 Lync Mobile, e destina-se ao Serviço de Mobilidade (Mcx).</span><span class="sxs-lookup"><span data-stu-id="9f6f0-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>
  
<span data-ttu-id="9f6f0-106">Quando você habilita o rastreamento de solicitação de serviços de informações da Internet (IIS) para o Skype para serviço de mobilidade do Business Server (Mcx), os arquivos de log gerados podem consumir até três gigabytes de espaço em disco por dia.</span><span class="sxs-lookup"><span data-stu-id="9f6f0-106">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="9f6f0-107">O registro em log do rastreamento IIS está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="9f6f0-107">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="9f6f0-108">Você deve monitorar os servidores Front-End para certificar-se de que elas não são executadas sem espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="9f6f0-108">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="9f6f0-109">Por padrão, o IIS armazena os arquivos de log em %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="9f6f0-109">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="9f6f0-110">Para desativar o rastreamento de solicitação IIS para todo um servidor, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9f6f0-110">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="9f6f0-111">Para obter detalhes sobre o comando **httpLogging** , consulte [a referência de comandos](https://go.microsoft.com/fwlink/p/?linkId=234927).</span><span class="sxs-lookup"><span data-stu-id="9f6f0-111">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  


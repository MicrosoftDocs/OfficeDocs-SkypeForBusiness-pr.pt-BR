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
description: 'Resumo: Saiba mais sobre o suporte do Mobility Service (Mcx) no Skype for Business Server 2015 para clientes herdados.'
ms.openlocfilehash: 7d0d15b4c3db3d768117d73ed610b38c7a819196
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118630"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="a2b73-103">Monitorando arquivos de log de rastreamento de solicitação do IIS no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a2b73-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a2b73-104">**Resumo:** Saiba mais sobre o suporte do Mobility Service (Mcx) no Skype for Business Server 2015 para clientes herdado.</span><span class="sxs-lookup"><span data-stu-id="a2b73-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="a2b73-105">Este tópico se aplica apenas às implantações que suportam clientes do Lync Lync 2010 Lync Mobile e destina-se ao Serviço de Mobilidade (Mcx).</span><span class="sxs-lookup"><span data-stu-id="a2b73-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="a2b73-106">O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a2b73-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a2b73-107">Todos os clientes móveis atuais do Skype for Business já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="a2b73-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a2b73-108">Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="a2b73-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="a2b73-109">Quando você habilita o rastreamento de solicitação do IIS (Serviços de Informações da Internet) para o Serviço de Mobilidade do Skype for Business Server (Mcx), os arquivos de log gerados podem consumir até três gigabytes de espaço em disco por dia.</span><span class="sxs-lookup"><span data-stu-id="a2b73-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="a2b73-110">O registro em log do rastreamento IIS está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="a2b73-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="a2b73-111">Você deve monitorar os Servidores Front-End para garantir que eles não ficam sem espaço em disco.</span><span class="sxs-lookup"><span data-stu-id="a2b73-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="a2b73-112">Por padrão, o IIS armazena os arquivos de log em %SystemDrive%\inetpub\logs\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="a2b73-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="a2b73-113">Para desativar o rastreamento de solicitação IIS para todo um servidor, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a2b73-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="a2b73-114">Para obter detalhes sobre o **comando httpLogging,** consulte [a referência de comando](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="a2b73-114">For details about the **httpLogging** command, see [the command reference](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).</span></span>

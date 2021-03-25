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
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Monitorando arquivos de log de rastreamento de solicitação do IIS no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o suporte do Mobility Service (Mcx) no Skype for Business Server 2015 para clientes herdado.
  
Este tópico se aplica apenas às implantações que suportam clientes do Lync Lync 2010 Lync Mobile e destina-se ao Serviço de Mobilidade (Mcx).

> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
Quando você habilita o rastreamento de solicitação do IIS (Serviços de Informações da Internet) para o Serviço de Mobilidade do Skype for Business Server (Mcx), os arquivos de log gerados podem consumir até três gigabytes de espaço em disco por dia. O registro em log do rastreamento IIS está habilitado por padrão. Você deve monitorar os Servidores Front-End para garantir que eles não ficam sem espaço em disco. 
  
Por padrão, o IIS armazena os arquivos de log em %SystemDrive%\inetpub\logs\LogFiles.
  
Para desativar o rastreamento de solicitação IIS para todo um servidor, na linha de comando, digite o seguinte:
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Para obter detalhes sobre o **comando httpLogging,** consulte [a referência de comando](/previous-versions/iis/settings-schema/aa347466(v=vs.90)).

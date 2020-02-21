---
title: 'Lync Server 2013: substituindo o xmladapter por um adaptador de conformidade do servidor de chat persistente personalizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e9cd9f2e950e835a113f64795022753e44e3ff5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Substituindo o xmladapter por um adaptador de conformidade do servidor de chat persistente personalizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Você pode escrever um adaptador personalizado em vez de usar o xmladapter que é instalado com o servidor de chat persistente. Para realizar isso, você deve oferecer um assembly .NET Framework que contém uma classe pública que implementa a interface do **IComplianceAdapter**. Você deve colocar esse assembly na pasta de instalação do servidor de chat persistente de cada servidor em seu pool de servidor de chat persistente. Qualquer um dos servidores de Conformidade podem oferecer dados de conformidade para seu adaptador, mas os servidores de conformidade não oferecerão dados de conformidade duplicados para várias instâncias do seu adaptador.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>Implementar a interface IComplianceAdapter

A interface é definida no assembly Compliance. dll no namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`. A interface define dois métodos que seu adaptador personalizado deve implementar.

    void SetConfig(AdapterConfig config)

O servidor de conformidade de chat persistente chamará este método quando o adaptador for carregado pela primeira vez. O `AdapterConfig` contém a configuração de conformidade de chat persistente que é relevante para o adaptador de conformidade.

    void Translate(ConversationCollection conversations)

O servidor de conformidade de chat persistente chama esse método em intervalos periódicos, desde que haja novos dados a serem convertidos. Esse intervalo de tempo é igual ao `RunInterval` definido na configuração de conformidade de chat persistente.

O `ConversationCollection` contém as informações de conversa coletadas da última vez que este método foi chamado.

</div>

</div>

<span> </span>

</div>

</div>

</div>


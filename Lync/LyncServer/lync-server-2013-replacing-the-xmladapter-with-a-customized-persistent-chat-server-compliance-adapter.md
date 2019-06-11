---
title: 'Lync Server 2013: substituindo o xmladapter por um adaptador de conformidade do servidor de chat persistente personalizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter
ms:assetid: 2cb70db2-663f-40a6-abcf-89ea7d4a8b65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ680106(v=OCS.15)
ms:contentKeyID: 49558152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d26e470438dc8a79dbaa3944c05ad4158cafe44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a>Substituindo o xmladapter por um adaptador de conformidade de servidor de chat persistente personalizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Você pode escrever um adaptador personalizado em vez de usar o xmladapter que está instalado com o servidor de chat persistente. Para fazer isso, você deve fornecer um assembly do .NET Framework que contenha uma classe pública que implemente a interface do **IComplianceAdapter**. Você deve colocar esse assembly na pasta de instalação do servidor de chat persistente de cada servidor em seu pool de servidores de chat persistente. Qualquer um dos servidores de Conformidade podem fornecer dados de conformidade para seu adaptador, mas os servidores de conformidade não fornecerão dados de conformidade duplicados para várias instâncias do seu adaptador.

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a>Implementando a interface IComplianceAdapter

A interface é definida no assembly Compliance. dll no namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`. A interface define dois métodos que seu adaptador personalizado deve implementar.

    void SetConfig(AdapterConfig config)

O servidor de conformidade de chat persistente chamará esse método quando o adaptador for carregado pela primeira vez. O `AdapterConfig` contém a configuração de conformidade de chat persistente que é relevante para o adaptador de conformidade.

    void Translate(ConversationCollection conversations)

O servidor de conformidade de chat persistente chama esse método em intervalos periódicos desde que novos dados sejam traduzidos. Esse intervalo de tempo é igual ao `RunInterval` definido na configuração de conformidade de chat persistente.

`ConversationCollection` Contém as informações de conversa que foram coletadas da última vez em que esse método foi chamado.

</div>

</div>

<span> </span>

</div>

</div>

</div>


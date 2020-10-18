---
title: 'Lync Server 2013: substituindo o xmladapter por um adaptador de conformidade do servidor de chat persistente personalizado'
description: 'Lync Server 2013: substituindo o xmladapter por um adaptador de conformidade do servidor de chat persistente personalizado.'
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
ms.openlocfilehash: 3a90b4df7df42ffdc6c55e9b551b0eb53d07ab1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576137"
---
# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="bf168-103">Substituindo o xmladapter por um adaptador de conformidade do servidor de chat persistente personalizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf168-103">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf168-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bf168-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bf168-105">Você pode escrever um adaptador personalizado em vez de usar o xmladapter que é instalado com o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bf168-105">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="bf168-106">Para realizar isso, você deve oferecer um assembly .NET Framework que contém uma classe pública que implementa a interface do **IComplianceAdapter**.</span><span class="sxs-lookup"><span data-stu-id="bf168-106">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="bf168-107">Você deve colocar esse assembly na pasta de instalação do servidor de chat persistente de cada servidor em seu pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bf168-107">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="bf168-108">Qualquer um dos servidores de Conformidade podem oferecer dados de conformidade para seu adaptador, mas os servidores de conformidade não oferecerão dados de conformidade duplicados para várias instâncias do seu adaptador.</span><span class="sxs-lookup"><span data-stu-id="bf168-108">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="bf168-109">Implementar a interface IComplianceAdapter</span><span class="sxs-lookup"><span data-stu-id="bf168-109">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="bf168-110">A interface é definida no assembly Compliance.dll no namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance` .</span><span class="sxs-lookup"><span data-stu-id="bf168-110">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="bf168-111">A interface define dois métodos que seu adaptador personalizado deve implementar.</span><span class="sxs-lookup"><span data-stu-id="bf168-111">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="bf168-112">O servidor de conformidade de chat persistente chamará este método quando o adaptador for carregado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="bf168-112">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="bf168-113">O `AdapterConfig` contém a configuração de conformidade de chat persistente que é relevante para o adaptador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="bf168-113">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="bf168-114">O servidor de conformidade de chat persistente chama esse método em intervalos periódicos, desde que haja novos dados a serem convertidos.</span><span class="sxs-lookup"><span data-stu-id="bf168-114">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="bf168-115">Esse intervalo de tempo é igual ao `RunInterval` definido na configuração de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="bf168-115">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="bf168-116">O `ConversationCollection` contém as informações de conversa coletadas da última vez que este método foi chamado.</span><span class="sxs-lookup"><span data-stu-id="bf168-116">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


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

# <a name="replacing-the-xmladapter-with-a-customized-persistent-chat-server-compliance-adapter-in-lync-server-2013"></a><span data-ttu-id="64b28-102">Substituindo o xmladapter por um adaptador de conformidade do servidor de chat persistente personalizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64b28-102">Replacing the XmlAdapter with a customized Persistent Chat Server Compliance adapter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64b28-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="64b28-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="64b28-104">Você pode escrever um adaptador personalizado em vez de usar o xmladapter que é instalado com o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="64b28-104">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="64b28-105">Para realizar isso, você deve oferecer um assembly .NET Framework que contém uma classe pública que implementa a interface do **IComplianceAdapter**.</span><span class="sxs-lookup"><span data-stu-id="64b28-105">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="64b28-106">Você deve colocar esse assembly na pasta de instalação do servidor de chat persistente de cada servidor em seu pool de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="64b28-106">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="64b28-107">Qualquer um dos servidores de Conformidade podem oferecer dados de conformidade para seu adaptador, mas os servidores de conformidade não oferecerão dados de conformidade duplicados para várias instâncias do seu adaptador.</span><span class="sxs-lookup"><span data-stu-id="64b28-107">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<div>

## <a name="implementing-the-icomplianceadapter-interface"></a><span data-ttu-id="64b28-108">Implementar a interface IComplianceAdapter</span><span class="sxs-lookup"><span data-stu-id="64b28-108">Implementing the IComplianceAdapter interface</span></span>

<span data-ttu-id="64b28-109">A interface é definida no assembly Compliance. dll no namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span><span class="sxs-lookup"><span data-stu-id="64b28-109">The interface is defined in the Compliance.dll assembly in the namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="64b28-110">A interface define dois métodos que seu adaptador personalizado deve implementar.</span><span class="sxs-lookup"><span data-stu-id="64b28-110">The interface defines two methods that your custom adapter must implement.</span></span>

    void SetConfig(AdapterConfig config)

<span data-ttu-id="64b28-111">O servidor de conformidade de chat persistente chamará este método quando o adaptador for carregado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="64b28-111">The Persistent Chat Compliance server will call this method when the adapter first loads.</span></span> <span data-ttu-id="64b28-112">O `AdapterConfig` contém a configuração de conformidade de chat persistente que é relevante para o adaptador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="64b28-112">The `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter.</span></span>

    void Translate(ConversationCollection conversations)

<span data-ttu-id="64b28-113">O servidor de conformidade de chat persistente chama esse método em intervalos periódicos, desde que haja novos dados a serem convertidos.</span><span class="sxs-lookup"><span data-stu-id="64b28-113">The Persistent Chat Compliance server calls this method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="64b28-114">Esse intervalo de tempo é igual ao `RunInterval` definido na configuração de conformidade de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="64b28-114">This time interval is equal to the `RunInterval` as set in the Persistent Chat Compliance configuration.</span></span>

<span data-ttu-id="64b28-115">O `ConversationCollection` contém as informações de conversa coletadas da última vez que este método foi chamado.</span><span class="sxs-lookup"><span data-stu-id="64b28-115">The `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


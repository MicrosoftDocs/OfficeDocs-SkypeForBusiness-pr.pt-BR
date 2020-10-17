---
title: 'Lync Server 2013: incluindo a central de segurança'
description: 'Lync Server 2013: incluindo a central de segurança.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23a5b01dff5e3db8293944033f1f3b675bbc4d37
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547747"
---
# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="16718-103">Incluindo a central de segurança no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16718-103">Including the security desk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16718-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="16718-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="16718-p101">Sua empresa pode exigir que a central de segurança se envolva em uma chamada de emergência. Para ajudar a decidir como integrar a Central de Segurança à sua implantação do E9-1-1, você deve responder às perguntas a seguir.</span><span class="sxs-lookup"><span data-stu-id="16718-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="16718-107">**Você deseja que o suporte de segurança seja notificado quando houver uma chamada de emergência?**</span><span class="sxs-lookup"><span data-stu-id="16718-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="16718-108">Você pode configurar a política de local para que o Lync Server envie alertas de mensagens instantâneas (IM) para os endereços SIP do Lync de um ou mais funcionários de segurança.</span><span class="sxs-lookup"><span data-stu-id="16718-108">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="16718-109">Esses alertas contêm o nome, o número e o local da pessoa que está fazendo a chamada de emergência e facilitam a segurança na assistência com a situação de emergência.</span><span class="sxs-lookup"><span data-stu-id="16718-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="16718-110">**Deseja estabelecer conferência com o suporte de segurança em cada chamada de emergência?**</span><span class="sxs-lookup"><span data-stu-id="16718-110">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="16718-p103">Se tiver suporte do provedor de serviços de emergência, você poderá configurar a política de local para incluir um número de retorno de chamada com cada chamada de emergência. Esse número é usado pelo provedor para estabelecer conferência com a equipe de segurança da sua organização em chamadas de emergência. Essa conferência pode ser configurada na política de local para ser unidirecional (somente escuta) ou bidirecional.</span><span class="sxs-lookup"><span data-stu-id="16718-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16718-p104">Se desejar, você pode configurar uma equipe de segurança diferente para cada política de local. Isso permite personalizar a resposta para áreas diferentes da empresa ou criar um comportamento diferente para chamadas de emergência que originam da parte interna em oposição à parte externa da rede. Você pode usar grupos de distribuição para especificar o pessoal que você deseja notificar.</span><span class="sxs-lookup"><span data-stu-id="16718-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>


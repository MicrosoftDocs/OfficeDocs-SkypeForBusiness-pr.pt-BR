---
title: 'Lync Server 2013: guia de provisionamento para a conectividade Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8f6e1b9262e0e7ed0f9060f3e509924aee9ba62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="c6738-102">Guia de provisionamento para a conectividade Lync-Skype no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6738-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6738-103">_**Última modificação do tópico:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="c6738-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="c6738-104">O Lync Server 2013 oferece suporte à conectividade com o Skype.</span><span class="sxs-lookup"><span data-stu-id="c6738-104">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="c6738-105">Essa conectividade permite que seus usuários do Lync 2013 adicionem contatos do Skype usando a conta da Microsoft do usuário do Skype (MSA).</span><span class="sxs-lookup"><span data-stu-id="c6738-105">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="c6738-106">Os clientes do Skype também podem adicionar usuários do Lync à sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="c6738-106">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="c6738-107">Com base nas políticas definidas administrativamente no Lync Server, os usuários do Lync e do Skype poderão se comunicar usando mensagens instantâneas, confira a presença dos outros e iniciar chamadas de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="c6738-107">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="c6738-108">A conectividade Lync-Skype também é um recurso do Lync Online e pode ser habilitada para clientes do Lync Online do centro de administração do Lync no portal do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6738-108">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="c6738-109">Se o Lync Server já estiver configurado para se conectar ao Windows Messenger usando a PIC (conectividade de mensagens instantâneas públicas), sua implantação já está configurada para a conectividade Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="c6738-109">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="c6738-110">A única alteração que você pode querer considerar é renomear sua entrada existente do Messenger PIC como Skype.</span><span class="sxs-lookup"><span data-stu-id="c6738-110">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="c6738-111">Para obter detalhes, consulte Configurar a configuração do provedor de PIC do Skype para Lync mais adiante neste guia.</span><span class="sxs-lookup"><span data-stu-id="c6738-111">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6738-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c6738-112">In This Section</span></span>

  - [<span data-ttu-id="c6738-113">Observação sobre a conectividade Lync-Skype no Lync Server 2013 para clientes do Lync Online</span><span class="sxs-lookup"><span data-stu-id="c6738-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="c6738-114">Acessando o site de provisionamento da conectividade de IM pública do Lync Server do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6738-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="c6738-115">Habilitando a conectividade Lync-Skype no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6738-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="c6738-116">Usando a conectividade Lync-Skype no Lync Server 2013 como um usuário final</span><span class="sxs-lookup"><span data-stu-id="c6738-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="c6738-117">Perguntas frequentes: provisionamento do Lync Server 2013 para conectividade do Skype</span><span class="sxs-lookup"><span data-stu-id="c6738-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


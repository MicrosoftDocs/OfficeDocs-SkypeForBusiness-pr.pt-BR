---
title: 'Lync Server 2013: Guia de configuração para conectividade Lync-Skype'
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
ms.openlocfilehash: f94da566e4322f9b8d1d039441c561f5ed60f6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="26d54-102">Guia de configuração para conectividade Lync-Skype no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d54-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d54-103">_**Tópico da última modificação:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="26d54-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="26d54-p101">O Lync Server 2013 suporta conectividade com o Skype. Essa conectividade permite que os usuários do seu Lync 2013 adicionem os contatos do Skype usando a conta da Microsoft de usuário do Skype (MSA). Os clientes do Skype podem adicionar os usuários do Lync à sua lista de contatos. Com base em políticas definidas administrativamente no Lync Server, usuários do Lync e do Skype poderão se comunicar por mensagem instantânea, ver a presença de cada um e iniciar chamadas de áudio e de vídeo. A conectividade Lync-Skype também é um recurso do Lync Online, e pode ser ativada para os clientes do Lync Online a partir do Centro Administrativo do Lync com o portal Office 365.</span><span class="sxs-lookup"><span data-stu-id="26d54-p101">Lync Server 2013 supports connectivity with Skype. This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA). Skype clients can also add Lync users to their contact list. Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls. Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="26d54-p102">Se o Servidor Lync já está configurado para conectar com o Windows Messenger usando Conectividade Pública de Mensagem Instantânea (PIC), sua implantação já está configurada para a conectividade Lync-Skype. A única mudança que você pode querer considerar é renomear sua entrada existente no Messenger PIC como do Skype. Para mais detalhes, consulte Configurar o provedor do Skype PIC definindo para Lync mais adiante, neste guia.</span><span class="sxs-lookup"><span data-stu-id="26d54-p102">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype. For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="26d54-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="26d54-112">In This Section</span></span>

  - [<span data-ttu-id="26d54-113">Observação sobre o Lync-conectividade do Skype no Lync Server 2013 para clientes do Lync Online</span><span class="sxs-lookup"><span data-stu-id="26d54-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="26d54-114">Acessando o site de configuração de conectividade a redes públicas de mensagens instantâneas do Lync Server a partir do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d54-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="26d54-115">Habilitando conectividade Lync-Skype no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d54-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="26d54-116">Usando a conectividade Lync-Skype no Lync Server 2013 como usuário final</span><span class="sxs-lookup"><span data-stu-id="26d54-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="26d54-117">Perguntas Frequentes: Configurando Lync Server 2013 para conectividade com Skype</span><span class="sxs-lookup"><span data-stu-id="26d54-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


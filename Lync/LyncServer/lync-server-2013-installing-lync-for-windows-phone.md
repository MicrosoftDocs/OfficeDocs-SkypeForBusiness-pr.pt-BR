---
title: 'Lync Server 2013: Instalando o Lync para Windows Phone'
description: 'Lync Server 2013: Instalando o Lync para Windows Phone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5da90a5dc0babdc6944e4f9c426fe896d4f156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573977"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="aaaf7-103">Instalando o Lync para Windows Phone no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aaaf7-103">Installing Lync for Windows Phone in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aaaf7-104">_**Última modificação do tópico:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="aaaf7-104">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="aaaf7-105">O Lync 2013 para Windows Phone é um aplicativo instalável pelo usuário que está disponível no Windows Phone Marketplace.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-105">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="aaaf7-106">Instalando o Lync para Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="aaaf7-106">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="aaaf7-107">Você pode instruir seus usuários a instalar o Lync 2013 para Windows Phone em seus dispositivos direcionando-os para o Windows Phone Marketplace em <https://go.microsoft.com/fwlink/p/?linkid=231901> .</span><span class="sxs-lookup"><span data-stu-id="aaaf7-107">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <https://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="aaaf7-108">Se você usar um registro SRV de DNS para publicar serviços Web do Exchange</span><span class="sxs-lookup"><span data-stu-id="aaaf7-108">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="aaaf7-109">Para habilitar a integração do Exchange para clientes do Lync, algumas organizações publicam a URL dos serviços Web do Exchange usando um registro SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-109">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="aaaf7-110">O documento "entendendo e Solucionando problemas de integração do Exchange", disponível no centro de download da Microsoft em [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) , descreve cenários nos quais isso pode ser necessário.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-110">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="aaaf7-111">No entanto, a integração do Exchange para usuários do Windows Phone não funcionará nesse cenário, porque a plataforma Windows Phone não oferece suporte a pesquisas SRV.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-111">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="aaaf7-112">Você precisará instruir os usuários do Windows Phone a especificar a URL dos serviços Web do Exchange, em vez de permitir que o telefone detecte automaticamente o servidor.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-112">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="aaaf7-113">Instrua os usuários a definir as configurações do Lync em seus telefones Windows da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="aaaf7-113">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="aaaf7-114">No Windows Phone, nas configurações do Lync, selecione a tela do **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="aaaf7-114">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="aaaf7-115">Mova o **servidor de detecção automática** para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-115">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="aaaf7-116">Toque no campo vazio e digite o nome de domínio totalmente qualificado (FQDN) ou a URL dos serviços Web do Exchange.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-116">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aaaf7-117">Você pode especificar o FQDN (nome de domínio totalmente qualificado) ou a URL completa do seu servidor de serviços Web do Exchange.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-117">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="aaaf7-118">Se você especificar o FQDN, o protocolo (https://) e o caminho do serviços Web do Exchange (/EWS/Exchange.asmx) serão adicionados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-118">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="aaaf7-119">Se o caminho dos serviços Web do Exchange for diferente, você poderá especificar a URL completa.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-119">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="aaaf7-120">Feche a tela.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-120">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="aaaf7-121">Verificando a instalação do cliente móvel</span><span class="sxs-lookup"><span data-stu-id="aaaf7-121">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="aaaf7-122">Depois de configurar o cliente e entrar com êxito, use os seguintes testes para verificar se a instalação do Lync 2013 está funcionando corretamente no seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-122">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="aaaf7-123">**Procure um contato no diretório corporativo**</span><span class="sxs-lookup"><span data-stu-id="aaaf7-123">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="aaaf7-124">Na lista Contatos, toque em **Pesquisar** na parte inferior.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-124">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="aaaf7-125">Procure um contato que conste apenas na lista de endereços global.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-125">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="aaaf7-126">Verifique se o nome do contato aparece nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-126">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="aaaf7-127">**Testar mensagens instantâneas e presença**</span><span class="sxs-lookup"><span data-stu-id="aaaf7-127">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="aaaf7-128">Na lista Contatos, toque em um contato.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-128">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="aaaf7-129">No cartão de visita, toque no ícone **IM**.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-129">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="aaaf7-130">Verifique se uma janela de mensagens instantâneas (IM) aparece e se é possível digitar e enviar uma mensagem instantânea.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-130">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="aaaf7-131">**Teste a conferência discada**</span><span class="sxs-lookup"><span data-stu-id="aaaf7-131">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="aaaf7-132">No Outlook, agende uma reunião do Lync.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-132">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="aaaf7-133">No dispositivo móvel, abra o convite de reunião.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-133">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="aaaf7-134">Clique no link da reunião para ingressar.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-134">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="aaaf7-135">Atenda à chamada do serviço de conferência e verifique se você está conectado ao áudio da reunião.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-135">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="aaaf7-136">**Teste as notificações por push**</span><span class="sxs-lookup"><span data-stu-id="aaaf7-136">**Test push notifications**</span></span>

1.  <span data-ttu-id="aaaf7-137">No dispositivo móvel do usuário A, entre no Lync com a conta do usuário A.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-137">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="aaaf7-138">Abra outro aplicativo no dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-138">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="aaaf7-139">Em um cliente diferente, entre no Lync com a conta do usuário B.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-139">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="aaaf7-140">Envie uma mensagem instantânea do usuário B para o usuário A.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-140">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="aaaf7-141">Verifique se a notificação de IM aparece no dispositivo móvel do usuário A.</span><span class="sxs-lookup"><span data-stu-id="aaaf7-141">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


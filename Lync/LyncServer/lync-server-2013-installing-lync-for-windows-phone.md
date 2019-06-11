---
title: 'Lync Server 2013: Instalando o Lync para Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeb8f43ea4f4db15a9a057bd0d7b24c55d858cb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="dac22-102">Instalar o Lync para Windows Phone no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dac22-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dac22-103">_**Tópico da última modificação:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="dac22-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="dac22-104">O Lync 2013 para Windows Phone é um aplicativo instalável pelo usuário que está disponível no Windows Phone Marketplace.</span><span class="sxs-lookup"><span data-stu-id="dac22-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="dac22-105">Instalando o Lync para Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="dac22-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="dac22-106">Você pode instruir os usuários a instalar o Lync 2013 para Windows Phone em seus dispositivos direcionando-os para o Windows Phone <http://go.microsoft.com/fwlink/p/?linkid=231901>Marketplace em.</span><span class="sxs-lookup"><span data-stu-id="dac22-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="dac22-107">Se você usar um registro SRV DNS para publicar serviços Web do Exchange</span><span class="sxs-lookup"><span data-stu-id="dac22-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="dac22-108">Para habilitar a integração do Exchange para clientes do Lync, algumas organizações publicam a URL dos serviços Web do Exchange usando um registro de servidor DNS.</span><span class="sxs-lookup"><span data-stu-id="dac22-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="dac22-109">O documento "entendendo e Solucionando problemas de integração do Exchange", disponível no centro [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)de download da Microsoft em, descreve cenários em que isso pode ser necessário.</span><span class="sxs-lookup"><span data-stu-id="dac22-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="dac22-110">No entanto, a integração do Exchange para usuários do Windows Phone não funcionará nesse cenário, porque a plataforma do Windows Phone não oferece suporte a pesquisas SRV.</span><span class="sxs-lookup"><span data-stu-id="dac22-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="dac22-111">Você precisará instruir os usuários do Windows Phone a especificar a URL dos serviços Web do Exchange em vez de permitir que o telefone detecte automaticamente o servidor.</span><span class="sxs-lookup"><span data-stu-id="dac22-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="dac22-112">Instrua os usuários a definir as configurações do Lync nos telefones Windows da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="dac22-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="dac22-113">No Windows Phone, nas configurações do Lync, selecione a tela do **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="dac22-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="dac22-114">Mova o **servidor de detecção automática** para **desativado**.</span><span class="sxs-lookup"><span data-stu-id="dac22-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="dac22-115">Toque no campo vazio e insira o nome de domínio totalmente qualificado (FQDN) ou a URL dos serviços Web do Exchange.</span><span class="sxs-lookup"><span data-stu-id="dac22-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dac22-116">Você pode especificar o nome de domínio totalmente qualificado (FQDN) ou a URL completa do servidor de serviços Web do Exchange.</span><span class="sxs-lookup"><span data-stu-id="dac22-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="dac22-117">Se você especificar o FQDN, o protocolo (https://) e o caminho dos serviços Web do Exchange (/EWS/Exchange.asmx) serão adicionados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dac22-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="dac22-118">Se o caminho dos serviços Web do Exchange for diferente, você poderá especificar a URL completa.</span><span class="sxs-lookup"><span data-stu-id="dac22-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="dac22-119">Fechar a tela.</span><span class="sxs-lookup"><span data-stu-id="dac22-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="dac22-120">Verificando a instalação do cliente móvel</span><span class="sxs-lookup"><span data-stu-id="dac22-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="dac22-121">Depois de configurar o cliente e entrar com êxito, use os seguintes testes para verificar se a sua instalação do Lync 2013 está funcionando corretamente em seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="dac22-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="dac22-122">**Procure um contato no diretório corporativo**</span><span class="sxs-lookup"><span data-stu-id="dac22-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="dac22-123">Na lista de contatos, toque em **Pesquisar** na parte inferior.</span><span class="sxs-lookup"><span data-stu-id="dac22-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="dac22-124">Procure um contato que conste apenas na lista de endereços global.</span><span class="sxs-lookup"><span data-stu-id="dac22-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="dac22-125">Verifique se o nome do contato aparece nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="dac22-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="dac22-126">**Teste mensagens instantâneas e presença**</span><span class="sxs-lookup"><span data-stu-id="dac22-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="dac22-127">Na lista Contatos, toque em um contato.</span><span class="sxs-lookup"><span data-stu-id="dac22-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="dac22-128">No cartão de visita, toque no ícone de **mensagem instantânea** .</span><span class="sxs-lookup"><span data-stu-id="dac22-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="dac22-129">Verifique se uma janela de mensagem instantânea (IM) aparece e se é possível digitar e enviar uma IM.</span><span class="sxs-lookup"><span data-stu-id="dac22-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="dac22-130">**Teste a conferência discada**</span><span class="sxs-lookup"><span data-stu-id="dac22-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="dac22-131">No Outlook, agendar uma reunião do Lync.</span><span class="sxs-lookup"><span data-stu-id="dac22-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="dac22-132">No dispositivo móvel, abra o convite de reunião.</span><span class="sxs-lookup"><span data-stu-id="dac22-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="dac22-133">Clique no link da reunião para ingressar.</span><span class="sxs-lookup"><span data-stu-id="dac22-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="dac22-134">Atenda à chamada do serviço de conferência e verifique se você está conectado ao áudio da reunião.</span><span class="sxs-lookup"><span data-stu-id="dac22-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="dac22-135">**Teste as notificações por push**</span><span class="sxs-lookup"><span data-stu-id="dac22-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="dac22-136">No dispositivo móvel do usuário A, entre no Lync com A conta do usuário A.</span><span class="sxs-lookup"><span data-stu-id="dac22-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="dac22-137">Abra outro aplicativo no dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="dac22-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="dac22-138">Em um cliente diferente, entre no Lync com a conta do usuário B.</span><span class="sxs-lookup"><span data-stu-id="dac22-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="dac22-139">Envie uma mensagem instantânea do usuário B para o usuário A.</span><span class="sxs-lookup"><span data-stu-id="dac22-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="dac22-140">Verifique se a notificação de IM aparece no dispositivo móvel do usuário A.</span><span class="sxs-lookup"><span data-stu-id="dac22-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


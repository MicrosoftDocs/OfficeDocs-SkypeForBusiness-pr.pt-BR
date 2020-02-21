---
title: 'Lync Server 2013: configurar bypass de mídia para sempre ignorar o servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ae9bfa8be276cccc6f31def6fb7014e417841d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="fcba1-102">Configurar o bypass de mídia no Lync Server 2013 para sempre ignorar o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="fcba1-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcba1-103">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="fcba1-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fcba1-104">Este tópico assume que você já configurou o desvio de mídia em qualquer conexão de tronco para um par (um gateway PSTN (Rede Telefônica Pública Comutada), um IP-PBX ou SBC (Controlador de Borda da Sessão) no ITSP (Provedor de Serviços de Telefonia da Internet)) de um local ou serviço específico no qual deseja que a mídia ignore o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="fcba1-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="fcba1-105">Você não pode configurar a mídia para sempre desviar do Servidor de Mediação, enquanto também ativa o controle de admissão de chamada.</span><span class="sxs-lookup"><span data-stu-id="fcba1-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="fcba1-106">Essas configurações são incompatíveis e, portanto, são configurações mutuamente exclusivas na interface de usuário do painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fcba1-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="fcba1-107">Além de ativar o desvio de mídia para as conexões de tronco individuais associadas a um ponto para o Servidor de Mediação, você também deve definir as configurações globais para o desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="fcba1-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="fcba1-108">Se você usar as etapas deste tópico para definir as configurações globais para bypass de mídia, pressupõe-se que você tem uma boa conectividade entre os pontos de extremidade do Lync e qualquer ponto para o qual você configurou o bypass de mídia na conexão do tronco.</span><span class="sxs-lookup"><span data-stu-id="fcba1-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="fcba1-109">Se você não tem uma boa conectividade entre os pontos de extremidade do Lync Server e todos os pares para o servidor de mediação cujas respectivas conexões de tronco foram habilitadas para bypass de mídia, você deve definir as configurações de bypass de mídia global para usar as informações do site e da região quando empregar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="fcba1-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="fcba1-110">Isso permite maior controle ao determinar quando a mídia desvia do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="fcba1-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="fcba1-111">Para fazer isso, use as etapas em [configurar as configurações globais de bypass de mídia no Lync server 2013 para usar informações de site e região](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) e [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) em vez disso.</span><span class="sxs-lookup"><span data-stu-id="fcba1-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="fcba1-112">Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="fcba1-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="fcba1-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fcba1-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fcba1-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fcba1-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="fcba1-115">Na barra de navegação da esquerda, clique em **Configuração da Rede**.</span><span class="sxs-lookup"><span data-stu-id="fcba1-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="fcba1-116">Clique duas vezes na configuração **Global** na lista.</span><span class="sxs-lookup"><span data-stu-id="fcba1-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="fcba1-117">Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.</span><span class="sxs-lookup"><span data-stu-id="fcba1-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="fcba1-118">Clique em **Sempre desviar**.</span><span class="sxs-lookup"><span data-stu-id="fcba1-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="fcba1-119">Clique em **Comprometer**.</span><span class="sxs-lookup"><span data-stu-id="fcba1-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fcba1-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="fcba1-120">See Also</span></span>


[<span data-ttu-id="fcba1-121">Configurar bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcba1-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="fcba1-122">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcba1-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="fcba1-123">Bypass de mídia e servidor de mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcba1-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="fcba1-124">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcba1-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


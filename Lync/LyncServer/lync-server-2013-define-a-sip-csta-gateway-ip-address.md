---
title: 'Lync Server 2013: definir um endereço IP de gateway SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60541799a66365275207ea998fa2d4dd218a7bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="4e625-102">Definir um endereço IP de gateway SIP/CSTA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e625-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e625-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4e625-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4e625-104">Se o Lync Server se conectar ao gateway SIP/CSTA implantado para controle de chamada remota usando uma conexão TCP (Transmission Control Protocol), você deve definir o endereço IP do gateway no construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="4e625-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="4e625-105">Esta etapa não é necessária para gateways que oferecem suporte a conexões de segurança de camada de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="4e625-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="4e625-106">Para qualquer gateway que ofereça suporte a conexões TLS, você pode ignorar esse procedimento e continuar a implantação do controle de chamada remota seguindo as etapas descritas em [habilitar usuários do Lync para controle de chamada remota no Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="4e625-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="4e625-107">Para definir o endereço IP do gateway SIP/CSTA usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="4e625-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="4e625-108">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4e625-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="4e625-109">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4e625-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="4e625-110">Escolha a opção para baixar uma topologia existente.</span><span class="sxs-lookup"><span data-stu-id="4e625-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="4e625-111">Expanda o nó **Servidores de aplicativo confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="4e625-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="4e625-112">Clique com o botão direito do mouse no pool de aplicativos confiáveis que você criou, conforme descrito em [Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4e625-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="4e625-113">Desmarque a caixa de seleção **habilitar a replicação de dados de configuração para este pool** .</span><span class="sxs-lookup"><span data-stu-id="4e625-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="4e625-114">Clique em **limitar o uso do serviço para os endereços IP selecionados**.</span><span class="sxs-lookup"><span data-stu-id="4e625-114">Click **Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="4e625-115">A configuração padrão é **usar todos os endereços IP configurados**.</span><span class="sxs-lookup"><span data-stu-id="4e625-115">The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="4e625-116">Na caixa de texto **endereço IP principal** , digite o endereço IP do gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="4e625-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="4e625-117">Para atualizar a topologia no repositório de gerenciamento central, na árvore de console, clique em **Lync Server**e, em seguida, no painel **ações** , clique em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="4e625-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e625-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="4e625-118">See Also</span></span>


[<span data-ttu-id="4e625-119">Configurar uma rota estática para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e625-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="4e625-120">Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e625-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


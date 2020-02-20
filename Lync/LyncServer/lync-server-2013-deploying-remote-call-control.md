---
title: 'Lync Server 2013: Implantando controle de chamada remota'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0ca285312264a66113e038c0f5020e47567a5f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="250fd-102">Implantando o controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="250fd-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="250fd-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="250fd-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="250fd-104">Esta seção fornece orientações para o processo de implantação da funcionalidade de controle de chamada remota para usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="250fd-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="250fd-105">Embora os recursos de controle de chamada remota estejam disponíveis aos usuários remotos enquanto estão fora do firewall da organização, os detalhes sobre a implantação de cenários de acesso externo estão fora do escopo desta documentação.</span><span class="sxs-lookup"><span data-stu-id="250fd-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="250fd-106">Para obter detalhes sobre como implantar o acesso de usuário externo, consulte <A href="lync-server-2013-deploying-external-user-access.md">Deploying external User Access in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="250fd-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="250fd-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="250fd-107">In This Section</span></span>

  - [<span data-ttu-id="250fd-108">Configurando o Lync Server 2013 para rotear para um gateway SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="250fd-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="250fd-109">Configurar uma rota estática para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="250fd-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="250fd-110">Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="250fd-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="250fd-111">[Definir um endereço IP de gateway SIP/CSTA no Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (somente se o gateway estiver configurado para usar TCP)</span><span class="sxs-lookup"><span data-stu-id="250fd-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="250fd-112">Habilitar usuários do Lync para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="250fd-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="250fd-113">Normalização de controle de chamada remota e de número de telefone no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="250fd-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="250fd-114">[Remover um host autorizado herdado no Lync Server 2013 (opcional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (somente se você estiver migrando usuários previamente habilitados para controle de chamada remota)</span><span class="sxs-lookup"><span data-stu-id="250fd-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="250fd-115">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="250fd-115">Related Sections</span></span>

[<span data-ttu-id="250fd-116">Planejando o controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="250fd-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


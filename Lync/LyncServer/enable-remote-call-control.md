---
title: Habilitar o controle de chamada remota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c32e71ddc7ef0033b6a3380d394e0fe0e559945
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a><span data-ttu-id="5a3a4-102">Habilitar o controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="5a3a4-102">Enable remote call control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a3a4-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5a3a4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5a3a4-104">O controle de chamada remota permite que os usuários controlem seus telefones de PBX (central privada de comutação telefônica) de área de trabalho usando o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-104">Remote call control enables users to control their desktop private branch exchange (PBX) phones by using Lync Server 2013.</span></span> <span data-ttu-id="5a3a4-105">Se você implantou o controle de chamada remota no seu ambiente herdado e deseja migrar o Lync Server 2013, é necessário executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="5a3a4-105">If you deployed remote call control in your legacy environment and want to migrate it Lync Server 2013, you need to perform the following tasks:</span></span>

1.  <span data-ttu-id="5a3a4-106">Instalar um gateway SIP/CSTA e configura-lo para comunicar-se com sua PBX.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-106">Install a SIP/CSTA gateway and configure it to communicate with your PBX.</span></span> <span data-ttu-id="5a3a4-107">Você precisa executar esta etapa ao implantar o pool piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-107">You need to do this step when you deploy your Lync Server 2013 pilot pool.</span></span>

2.  <span data-ttu-id="5a3a4-108">Após mesclar sua topologia e migrar suas políticas e configurações, configure o Lync Server 2013 para rotear solicitações de CSTA para o gateway SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-108">After you merge your topology and migrate your policies and settings, configure Lync Server 2013 to route CSTA requests to the SIP/CSTA gateway.</span></span> <span data-ttu-id="5a3a4-109">Esta etapa pe uma etapa manual que segue a migração automatizada.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-109">This step is a manual step that follows the automated migration.</span></span> <span data-ttu-id="5a3a4-110">Para configurar o encaminhamento de solicitações CSTA, faço o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5a3a4-110">To configure routing for CSTA requests, do the following:</span></span>
    
      - <span data-ttu-id="5a3a4-111">Remova as entradas de host autorizadas herdadas (conhecidas como *entradas de servidor confiável* no Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="5a3a4-111">Remove legacy authorized host entries (known as *trusted server entries* in Lync Server 2013).</span></span> <span data-ttu-id="5a3a4-112">Se você estiver migrando usuários de sua implantação herdada, certifique-se de remover todas as entradas de host autorizadas existentes que você criou para o gateway SIP/CSTA antes de configurar novas entradas de aplicativo confiável no pool piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-112">If you are migrating users from your legacy deployment, ensure that you remove all existing authorized host entries that you created for the SIP/CSTA gateway before you configure new trusted application entries on the Lync Server 2013 pilot pool.</span></span> <span data-ttu-id="5a3a4-113">Para obter detalhes sobre como remover as entradas de host autorizadas herdadas, consulte [remover uma entrada de host autorizada](remove-an-authorized-host-entry.md).</span><span class="sxs-lookup"><span data-stu-id="5a3a4-113">For details about how to remove legacy authorized host entries, see [Remove an authorized host entry](remove-an-authorized-host-entry.md).</span></span>
    
      - <span data-ttu-id="5a3a4-114">Configure uma rota estática para o controle de chamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-114">Configure a static route for remote call control.</span></span> <span data-ttu-id="5a3a4-115">Você pode configurar uma rota estática para pool individuais que você queira que de suporte ao controle de chamadas remotas ou você pode configurar uma rota estática global, assim cada pool que não estiver configurado com a rota estática a nível de pool usa a rota estática globa.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-115">You can configure a static route for individual pools that you want to support remote call control, or you can configure a global static route so that each pool that is not configured with a pool-level static route uses the global static route.</span></span> <span data-ttu-id="5a3a4-116">Para obter detalhes sobre como configurar a rota estática, consulte [Configurar uma rota estática para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-116">For details about how to configure the static route, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="5a3a4-117">Configure uma entrada de aplicação confiável para ocontrol de chamadas remotas em cada pool para aqueles que você queira que suporte o controle de chamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-117">Configure a trusted application entry for remote call control on each pool for which you want to support remote call control.</span></span> <span data-ttu-id="5a3a4-118">Para obter detalhes sobre como configurar uma entrada de aplicativo confiável, consulte [Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-118">For details about how to configure a trusted application entry, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="5a3a4-119">Se você implantou um gateway SIP/CSTA que usa TCP (Transmission Control Protocol) para se conectar ao Lync Server 2013, defina o endereço IP do gateway no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-119">If you deployed a SIP/CSTA gateway that uses Transmission Control Protocol (TCP) to connect to Lync Server 2013, define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="5a3a4-120">Para obter detalhes sobre como definir o endereço IP, consulte [definir um endereço IP de gateway SIP/CSTA no Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-120">For details about defining the IP address, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) in the Deployment documentation.</span></span>

4.  <span data-ttu-id="5a3a4-121">Configure os usuários do Lync 2013 para controle de chamada remota habilitando o controle de chamada remota e atribuindo um URI (Uniform Resource Identifier) do servidor de linha e um URI de linha.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-121">Configure Lync 2013 users for remote call control by enabling remote call control and assigning a line server Uniform Resource Identifier (URI) and a line URI.</span></span> <span data-ttu-id="5a3a4-122">Ao migrar usuários da implantação herdada para o Lync Server 2013, as configurações de controle de chamada remota são migradas junto com as outras configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-122">When you migrate users from your legacy deployment to Lync Server 2013, the remote call control settings are migrated along with the other user settings.</span></span>

5.  <span data-ttu-id="5a3a4-123">Se você personalizou a regras na sua implementação herdada,  é necessário realizar algumas terefas manuais após a migração automatizada das políticas e configuração esteja concluída para migrar as regras personalizadas.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-123">If you customized Address Book phone number normalization rules in your legacy deployment, you need to perform some manual tasks after the automated migration of policies and settings is complete to migrate the customized normalization rules.</span></span> <span data-ttu-id="5a3a4-124">Caso não tenha personalizado as regras, o Catálogo de Endereços é migrado juntamente com sua topologia.</span><span class="sxs-lookup"><span data-stu-id="5a3a4-124">If you did not customize normalization rules, Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="5a3a4-125">Para mais detalhes sobre como migrar manualmente as regras, consulte [Migrate Address Book](migrate-address-book_1.md).</span><span class="sxs-lookup"><span data-stu-id="5a3a4-125">For details about manually migrating customized normalization rules, see [Migrate Address Book](migrate-address-book_1.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


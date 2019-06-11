---
title: 'Lync Server 2013: Implantação de acesso do usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e8522eac5ace72f615cc3cb7b9271981d1b84c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="796ab-102">Implantação de acesso do usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-102">Deploying external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="796ab-103">_**Tópico da última modificação:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="796ab-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="796ab-104">A implantação de componentes de borda do Microsoft Lync Server 2013 possibilita a usuários externos que não estão conectados à rede interna da sua organização, incluindo usuários remotos autenticados e anônimos, parceiros federados (incluindo parceiros do XMPP) clientes móveis e usuários de serviços de mensagens instantâneas (IM) públicas para se comunicar com outros usuários em sua organização usando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="796ab-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="796ab-105">Os processos de implantação e configuração do Lync Server 2013 não são significativamente diferentes do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="796ab-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="796ab-106">As ferramentas de instalação e administração são muito parecidas com as do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="796ab-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="796ab-107">A instalação e a&nbsp;configuração do servidor de borda do Microsoft Lync Server 2013 podem ser um processo complexo que exija uma quantia potencialmente significativa de planejamento e coordenação com suas equipes internas, incluindo, mas não se limitando a – segurança, rede, considerações de firewall, sistema de nome de domínio (DNS), balanceador de carga e infraestrutura de chave pública (PKI).</span><span class="sxs-lookup"><span data-stu-id="796ab-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="796ab-108">É altamente recomendável que você examine e use o processo de planejamento e a documentação fornecida antes de implantar seus componentes de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="796ab-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="796ab-109">Isso ajudará a limitar o número e a frequência de alterações não desejadas e problemas à medida que você passar pelo processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="796ab-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="796ab-110">Para obter informações sobre como planejar o acesso de usuários externos, consulte <A href="lync-server-2013-planning-for-external-user-access.md">planejar o acesso de usuários externos no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="796ab-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="796ab-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="796ab-111">In This Section</span></span>

  - [<span data-ttu-id="796ab-112">Llista de verificação de implantação para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="796ab-113">Requisitos do sistema para componentes de acesso de usuário externo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="796ab-114">Preparando para instalação de servidores na rede de perímetro para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="796ab-115">Criando uma topologia de borda e de diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="796ab-116">[Configurando o diretor no Lync Server 2013](lync-server-2013-setting-up-the-director.md) adicionais</span><span class="sxs-lookup"><span data-stu-id="796ab-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="796ab-117">Configurando os servidores de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="796ab-118">Configurando servidores de proxy reverso para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="796ab-119">Configurando suporte para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="796ab-120">Guia de configuração para conectividade Lync-Skype no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="796ab-121">Configurando federação SIP, federação XMPP e sistema de mensagens instântaneas público no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="796ab-122">Implantando mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="796ab-123">Verificando a implantação de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="796ab-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


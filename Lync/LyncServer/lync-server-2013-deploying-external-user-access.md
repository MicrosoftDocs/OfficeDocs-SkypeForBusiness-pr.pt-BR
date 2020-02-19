---
title: 'Lync Server 2013: Implantando acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b2168e679b16ddca3a201fe375b1189642ef671
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="8ed2a-102">Implantando o acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-102">Deploying external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ed2a-103">_**Última modificação do tópico:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="8ed2a-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="8ed2a-104">A implantação de componentes de borda para o Microsoft Lync Server 2013 permite que usuários externos que não estejam conectados à rede interna da sua organização, incluindo usuários remotos autenticados e anônimos, parceiros federados (incluindo parceiros do XMPP) clientes móveis e usuários de serviços públicos de mensagens instantâneas (IM), para se comunicar com outros usuários em sua organização usando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8ed2a-104">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="8ed2a-105">Os processos de implantação e configuração do Lync Server 2013 não são significativamente diferentes do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ed2a-105">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="8ed2a-106">As ferramentas de instalação e administração são muito parecidas com as do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ed2a-106">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8ed2a-107">A instalação e a&nbsp;configuração do servidor de borda do Microsoft Lync Server 2013 podem ser um processo complexo que requer uma quantidade potencialmente significativa de planejamento e coordenação com suas equipes internas, incluindo, mas não limitado a, considerações de segurança, rede, firewall, sistema de nomes de domínio (DNS), balanceador de carga e infraestrutura de chave pública (PKI).</span><span class="sxs-lookup"><span data-stu-id="8ed2a-107">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="8ed2a-108">É altamente recomendável que você revise e use o processo de planejamento e a documentação fornecida antes de implantar seus componentes de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="8ed2a-108">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="8ed2a-109">Isso ajudará a limitar o número e a frequência de alterações indesejadas e problemas à medida que você passar pelo processo de implantação.</span><span class="sxs-lookup"><span data-stu-id="8ed2a-109">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="8ed2a-110">Para obter informações sobre como planejar o acesso de usuário externo, consulte <A href="lync-server-2013-planning-for-external-user-access.md">Planning for External User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8ed2a-110">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8ed2a-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8ed2a-111">In This Section</span></span>

  - [<span data-ttu-id="8ed2a-112">Lista de verificação de implantação para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-112">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="8ed2a-113">Requisitos do sistema para componentes de acesso de usuário externo para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-113">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="8ed2a-114">Preparando para instalação de servidores na rede de perímetro do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-114">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="8ed2a-115">Criando uma topologia de borda e de diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-115">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="8ed2a-116">[Configurando o diretor no Lync Server 2013](lync-server-2013-setting-up-the-director.md) (opcional)</span><span class="sxs-lookup"><span data-stu-id="8ed2a-116">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="8ed2a-117">Configurando servidores de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-117">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="8ed2a-118">Configurando servidores de proxy reverso para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-118">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="8ed2a-119">Configurando suporte para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-119">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="8ed2a-120">Guia de provisionamento para a conectividade Lync-Skype no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-120">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="8ed2a-121">Configurando Federação SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-121">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="8ed2a-122">Implantação de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-122">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="8ed2a-123">Verificando a implantação de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ed2a-123">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: processo de implantação de cliente móvel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14acbf4a8be4d453fc1a0c5dc4da303136433e0c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="f6212-102">Processo de implantação de cliente móvel no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6212-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6212-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f6212-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f6212-104">Após a conclusão da implantação do Microsoft Lync Server 2013, os usuários podem instalar o aplicativo Lync 2013 a partir do Mobile Marketplace em que estão acostumados a usar o para seu dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="f6212-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="f6212-105">Processo de Implantação do Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="f6212-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6212-106">Fase</span><span class="sxs-lookup"><span data-stu-id="f6212-106">Phase</span></span></th>
<th><span data-ttu-id="f6212-107">Etapas</span><span class="sxs-lookup"><span data-stu-id="f6212-107">Steps</span></span></th>
<th><span data-ttu-id="f6212-108">Permissions</span><span class="sxs-lookup"><span data-stu-id="f6212-108">Permissions</span></span></th>
<th><span data-ttu-id="f6212-109">Documentação</span><span class="sxs-lookup"><span data-stu-id="f6212-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6212-110">Execute as tarefas de pré-instalação.</span><span class="sxs-lookup"><span data-stu-id="f6212-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f6212-111">Verifique a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6212-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="f6212-112">Verifique os requisitos de certificado.</span><span class="sxs-lookup"><span data-stu-id="f6212-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f6212-113">Administrador</span><span class="sxs-lookup"><span data-stu-id="f6212-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="f6212-114"><a href="lync-server-2013-planning-for-mobility.md">Planejamento para mobilidade no Lync server 2013</a> na documentação de planejamento do servidor.</span><span class="sxs-lookup"><span data-stu-id="f6212-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="f6212-115"><a href="lync-server-2013-deploying-mobility.md">Implantação de mobilidade no Lync Server 2013</a> na documentação de implantação do servidor.</span><span class="sxs-lookup"><span data-stu-id="f6212-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="f6212-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Requisitos de infraestrutura de certificado para o Lync Server 2013</a> na documentação de planejamento do servidor.</span><span class="sxs-lookup"><span data-stu-id="f6212-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6212-117">Instale o aplicativo Lync em um dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="f6212-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f6212-118">Instale os pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="f6212-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="f6212-119">Instale de um mercado específico ao dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="f6212-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f6212-120">Administrador</span><span class="sxs-lookup"><span data-stu-id="f6212-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="f6212-121">Instruções de instalação específicas para o dispositivo móvel em <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f6212-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6212-122">Configure o cliente.</span><span class="sxs-lookup"><span data-stu-id="f6212-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f6212-123">Defina as configurações de entrada e as informações do servidor.</span><span class="sxs-lookup"><span data-stu-id="f6212-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f6212-124">Administrador</span><span class="sxs-lookup"><span data-stu-id="f6212-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="f6212-125"><a href="lync-server-2013-deploying-mobile-clients.md">Implantando clientes móveis no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f6212-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6212-126">Teste os cenários móveis.</span><span class="sxs-lookup"><span data-stu-id="f6212-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f6212-127">Testar mensagens instantâneas (IM) e presença.</span><span class="sxs-lookup"><span data-stu-id="f6212-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="f6212-128">Teste a conferência discada</span><span class="sxs-lookup"><span data-stu-id="f6212-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="f6212-129">Pesquise um contato no diretório corporativo.</span><span class="sxs-lookup"><span data-stu-id="f6212-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="f6212-130">Teste as notificações de envio por push.</span><span class="sxs-lookup"><span data-stu-id="f6212-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f6212-131">Administrador</span><span class="sxs-lookup"><span data-stu-id="f6212-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="f6212-132">Instruções de verificação específicas para o dispositivo móvel em <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f6212-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6212-133">Instale o aplicativo Lync em celulares.</span><span class="sxs-lookup"><span data-stu-id="f6212-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f6212-134">Instale os pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="f6212-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="f6212-135">Instale de um mercado específico ao dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="f6212-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f6212-136">Usuário</span><span class="sxs-lookup"><span data-stu-id="f6212-136">User</span></span></p></td>
<td><p><span data-ttu-id="f6212-137">Instruções de instalação específicas para o dispositivo móvel em <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f6212-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


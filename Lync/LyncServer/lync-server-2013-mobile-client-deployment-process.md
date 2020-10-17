---
title: 'Lync Server 2013: processo de implantação de cliente móvel'
description: 'Lync Server 2013: processo de implantação de cliente móvel.'
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
ms.openlocfilehash: 4fa4e9e1d272915e06009df5c06480309ce104e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563477"
---
# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="0623b-103">Processo de implantação de cliente móvel no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0623b-103">Mobile client deployment process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0623b-104">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="0623b-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="0623b-105">Após a conclusão da implantação do Microsoft Lync Server 2013, os usuários podem instalar o aplicativo Lync 2013 a partir do Mobile Marketplace em que estão acostumados a usar o para seu dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="0623b-105">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="0623b-106">Processo de Implantação do Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="0623b-106">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0623b-107">Fase</span><span class="sxs-lookup"><span data-stu-id="0623b-107">Phase</span></span></th>
<th><span data-ttu-id="0623b-108">Etapas</span><span class="sxs-lookup"><span data-stu-id="0623b-108">Steps</span></span></th>
<th><span data-ttu-id="0623b-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="0623b-109">Permissions</span></span></th>
<th><span data-ttu-id="0623b-110">Documentação</span><span class="sxs-lookup"><span data-stu-id="0623b-110">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0623b-111">Execute as tarefas de pré-instalação.</span><span class="sxs-lookup"><span data-stu-id="0623b-111">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="0623b-112">Verifique a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0623b-112">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="0623b-113">Verifique os requisitos de certificado.</span><span class="sxs-lookup"><span data-stu-id="0623b-113">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0623b-114">Administrador</span><span class="sxs-lookup"><span data-stu-id="0623b-114">Administrator</span></span></p></td>
<td><p><span data-ttu-id="0623b-115"><a href="lync-server-2013-planning-for-mobility.md">Planejamento para mobilidade no Lync server 2013</a> na documentação de planejamento do servidor.</span><span class="sxs-lookup"><span data-stu-id="0623b-115"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="0623b-116"><a href="lync-server-2013-deploying-mobility.md">Implantação de mobilidade no Lync Server 2013</a> na documentação de implantação do servidor.</span><span class="sxs-lookup"><span data-stu-id="0623b-116"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="0623b-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Requisitos de infraestrutura de certificado para o Lync Server 2013</a> na documentação de planejamento do servidor.</span><span class="sxs-lookup"><span data-stu-id="0623b-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0623b-118">Instale o aplicativo Lync em um dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="0623b-118">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="0623b-119">Instale os pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="0623b-119">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="0623b-120">Instale de um mercado específico ao dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="0623b-120">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0623b-121">Administrador</span><span class="sxs-lookup"><span data-stu-id="0623b-121">Administrator</span></span></p></td>
<td><p><span data-ttu-id="0623b-122">Instruções de instalação específicas para o dispositivo móvel em <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0623b-122">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0623b-123">Configure o cliente.</span><span class="sxs-lookup"><span data-stu-id="0623b-123">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0623b-124">Defina as configurações de entrada e as informações do servidor.</span><span class="sxs-lookup"><span data-stu-id="0623b-124">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0623b-125">Administrador</span><span class="sxs-lookup"><span data-stu-id="0623b-125">Administrator</span></span></p></td>
<td><p><span data-ttu-id="0623b-126"><a href="lync-server-2013-deploying-mobile-clients.md">Implantando clientes móveis no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0623b-126"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0623b-127">Teste os cenários móveis.</span><span class="sxs-lookup"><span data-stu-id="0623b-127">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="0623b-128">Testar mensagens instantâneas (IM) e presença.</span><span class="sxs-lookup"><span data-stu-id="0623b-128">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="0623b-129">Teste a conferência discada</span><span class="sxs-lookup"><span data-stu-id="0623b-129">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="0623b-130">Pesquise um contato no diretório corporativo.</span><span class="sxs-lookup"><span data-stu-id="0623b-130">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="0623b-131">Teste as notificações de envio por push.</span><span class="sxs-lookup"><span data-stu-id="0623b-131">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0623b-132">Administrador</span><span class="sxs-lookup"><span data-stu-id="0623b-132">Administrator</span></span></p></td>
<td><p><span data-ttu-id="0623b-133">Instruções de verificação específicas para o dispositivo móvel em <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0623b-133">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0623b-134">Instale o aplicativo Lync em celulares.</span><span class="sxs-lookup"><span data-stu-id="0623b-134">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="0623b-135">Instale os pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="0623b-135">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="0623b-136">Instale de um mercado específico ao dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="0623b-136">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0623b-137">Usuário</span><span class="sxs-lookup"><span data-stu-id="0623b-137">User</span></span></p></td>
<td><p><span data-ttu-id="0623b-138">Instruções de instalação específicas para o dispositivo móvel em <a href="lync-server-2013-deploying-mobile-clients.md">Deploying Mobile clients in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0623b-138">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>


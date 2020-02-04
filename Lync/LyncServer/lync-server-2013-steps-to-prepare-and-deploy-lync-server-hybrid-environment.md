---
title: 'Lync Server 2013: Etapas para preparar e implantar o ambiente híbrido do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ebcce8d0021789a409c8f41b5f635d82284b7bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="6adac-102">Etapas para preparar e implantar o ambiente híbrido do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6adac-102">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6adac-103">_**Tópico da última modificação:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="6adac-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="6adac-104">A tabela a seguir lista as etapas necessárias para preparar o ambiente para uma implantação híbrida com o Skype for Business Online e o Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="6adac-104">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6adac-105">Concluído?</span><span class="sxs-lookup"><span data-stu-id="6adac-105">Completed?</span></span></th>
<th><span data-ttu-id="6adac-106">Etapa</span><span class="sxs-lookup"><span data-stu-id="6adac-106">Step</span></span></th>
<th><span data-ttu-id="6adac-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="6adac-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="6adac-108">Criar uma conta de locatário do Office 365 e habilitar o Lync Online</span><span class="sxs-lookup"><span data-stu-id="6adac-108">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="6adac-109">Saiba mais sobre o Office 365 e o Lync Online no <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="6adac-109">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="6adac-110">Para garantir que seu ambiente esteja pronto para o Office 365, consulte os <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">requisitos do sistema</a>.</span><span class="sxs-lookup"><span data-stu-id="6adac-110">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="6adac-111">Para obter detalhes sobre a configuração do Office 365, consulte <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">introdução ao office 365</a> e <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">configurar o Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="6adac-111">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="6adac-112">Adicionar seu domínio e verificar quem é o proprietário</span><span class="sxs-lookup"><span data-stu-id="6adac-112">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="6adac-p101">Seu domínio também é mencionado algumas vezes como <em>domínio personalizado</em>. Você precisa adicionar seu domínio ao seu locatário do Office 365 e, então, seguir as etapas para validar o domínio com o Office 365. Isso serve para confirmar que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="6adac-p101">Your domain is sometimes also referred to as your <em>vanity domain</em>. You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365. This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="6adac-116">Para adicionar seu domínio ao seu locatário do Office 365, siga as etapas descritas em <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Adicionar seu domínio ao Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="6adac-116">To add your domain to your Office 365 tenant, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="6adac-117">Conclua todas as etapas em cada seção do tópico, incluindo &quot;editar registros DNS para seus serviços do Office 365.&quot;</span><span class="sxs-lookup"><span data-stu-id="6adac-117">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="6adac-118">Verificar a preparação do ambiente</span><span class="sxs-lookup"><span data-stu-id="6adac-118">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="6adac-119">Você pode usar o assistente de configuração do Office 365 para ajudá-lo a implantar o Office 365.</span><span class="sxs-lookup"><span data-stu-id="6adac-119">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="6adac-120">Para obter mais informações, consulte <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">usar o assistente de configuração para determinar a preparação do Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="6adac-120">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="6adac-121">Para obter detalhes sobre como usar a ferramenta e implantar o Office 365, consulte <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Guia de implantação do office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="6adac-121">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="6adac-122">Preparar-se para a sincronização do Active Directory</span><span class="sxs-lookup"><span data-stu-id="6adac-122">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="6adac-123">A sincronização do Active Directory mantém a sincronização contínua do Active Directory no local com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="6adac-123">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="6adac-124">Assim, é possível criar versões sincronizadas de cada grupo e conta de usuário e também habilitar a sincronização de lista de endereços global (GAL) do seu ambiente local do Microsoft Exchange Server para o Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6adac-124">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="6adac-125">Você precisa sincronizar as contas do anúncio para todos os usuários do Lync em sua organização entre suas implantações locais e online do Lync, mesmo se os usuários não forem movidos para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="6adac-125">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="6adac-126">Se você não sincronizar todos os usuários, a comunicação entre os usuários locais e online na sua organização poderá não funcionar conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="6adac-126">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="6adac-127">Para preparar seu ambiente para a sincronização do Active Directory, siga as etapas descritas no <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">mapa de sincronização de diretório</a>, incluindo a configuração de logon único.</span><span class="sxs-lookup"><span data-stu-id="6adac-127">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="6adac-128">Criar certificados para o AD FS (serviços de Federação do Active Directory)</span><span class="sxs-lookup"><span data-stu-id="6adac-128">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="6adac-129">Será necessário criar os certificados usados para a Federação de identidade com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="6adac-129">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="6adac-130">Para obter mais informações, consulte a seção "certificados do servidor de Federação" do tópico planejar e implantar o AD FS para uso com o logon único na <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">lista de verificação: Use o AD FS para implementar e gerenciar o logon único</a>.</span><span class="sxs-lookup"><span data-stu-id="6adac-130">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="6adac-131">Atribuir certificados para o AD FS</span><span class="sxs-lookup"><span data-stu-id="6adac-131">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="6adac-132">Depois de criar os certificados usados para a Federação de identidade com o Office 365, você deve instalá-los e atribuí-los.</span><span class="sxs-lookup"><span data-stu-id="6adac-132">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="6adac-133">Mover os usuários piloto para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6adac-133">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="6adac-134">Depois de concluir as etapas para preparar e configurar seu ambiente para o Skype for Business Online, você pode começar a mover os usuários piloto para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="6adac-134">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="6adac-135">Consulte <a href="lync-server-2013-move-users-to-lync-online.md">mover usuários para o Lync Online no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6adac-135">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="6adac-136">Administrando usuários em uma implantação híbrida</span><span class="sxs-lookup"><span data-stu-id="6adac-136">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="6adac-137">Para obter detalhes sobre como administrar usuários em uma implantação híbrida, consulte <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">administrando usuários em uma implantação híbrida do Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6adac-137">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


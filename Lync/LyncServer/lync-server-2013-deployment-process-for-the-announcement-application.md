---
title: 'Lync Server 2013: processo de implantação para o aplicativo de comunicado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55e0c65bfbbed55a8d7f9c3be4f7a586581c2307
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="2f0f4-102">Processo de implantação para o aplicativo de anúncio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f0f4-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f0f4-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2f0f4-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2f0f4-104">Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo de comunicado.</span><span class="sxs-lookup"><span data-stu-id="2f0f4-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="2f0f4-105">Você deve implantar o Enterprise Voice antes de configurar os comunicados.</span><span class="sxs-lookup"><span data-stu-id="2f0f4-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="2f0f4-106">Os componentes exigidos pelo aplicativo de comunicado são instalados e habilitados quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2f0f4-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="2f0f4-107">Processo de implantação do comunicado</span><span class="sxs-lookup"><span data-stu-id="2f0f4-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f0f4-108">Fase</span><span class="sxs-lookup"><span data-stu-id="2f0f4-108">Phase</span></span></th>
<th><span data-ttu-id="2f0f4-109">Etapas</span><span class="sxs-lookup"><span data-stu-id="2f0f4-109">Steps</span></span></th>
<th><span data-ttu-id="2f0f4-110">Funções</span><span class="sxs-lookup"><span data-stu-id="2f0f4-110">Roles</span></span></th>
<th><span data-ttu-id="2f0f4-111">Documentação de Implantação</span><span class="sxs-lookup"><span data-stu-id="2f0f4-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f0f4-112">Definir configurações do comunicado</span><span class="sxs-lookup"><span data-stu-id="2f0f4-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2f0f4-113">Crie o comunicado através da gravação e carregamento de arquivos de áudio ou usando texto em fala (TTS).</span><span class="sxs-lookup"><span data-stu-id="2f0f4-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="2f0f4-114">Configure os intervalos de números não atribuídos na tabela de número não atribuída e os associe com o comunicado adequado.</span><span class="sxs-lookup"><span data-stu-id="2f0f4-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2f0f4-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2f0f4-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2f0f4-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f0f4-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="2f0f4-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f0f4-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2f0f4-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f0f4-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="2f0f4-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="2f0f4-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2f0f4-120"><a href="lync-server-2013-create-an-announcement.md">Criar um comunicado no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f0f4-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2f0f4-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configurar a tabela de números não atribuídos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f0f4-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f0f4-122">Verifique a implantação do comunicado</span><span class="sxs-lookup"><span data-stu-id="2f0f4-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="2f0f4-123">Faça o teste escutando os comunicados para verificar se sua configuração funciona como o esperado.</span><span class="sxs-lookup"><span data-stu-id="2f0f4-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2f0f4-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">Opcion Verificar a implantação do comunicado no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2f0f4-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


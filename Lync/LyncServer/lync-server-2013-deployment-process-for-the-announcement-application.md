---
title: 'Lync Server 2013: processo de implantação para o aplicativo de anúncio'
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
ms.openlocfilehash: dcb56f197a32403d1207cf0a15d47e0459fc41bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="8dbec-102">Processo de implantação do aplicativo de anúncio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dbec-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dbec-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8dbec-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8dbec-104">Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo de anúncio.</span><span class="sxs-lookup"><span data-stu-id="8dbec-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="8dbec-105">Você deve implantar o Enterprise Voice antes de configurar comunicados.</span><span class="sxs-lookup"><span data-stu-id="8dbec-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="8dbec-106">Os componentes exigidos pelo aplicativo de anúncio são instalados e habilitados durante a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="8dbec-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="8dbec-107">Processo de implantação do comunicado</span><span class="sxs-lookup"><span data-stu-id="8dbec-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dbec-108">Fase</span><span class="sxs-lookup"><span data-stu-id="8dbec-108">Phase</span></span></th>
<th><span data-ttu-id="8dbec-109">Etapas</span><span class="sxs-lookup"><span data-stu-id="8dbec-109">Steps</span></span></th>
<th><span data-ttu-id="8dbec-110">Funções</span><span class="sxs-lookup"><span data-stu-id="8dbec-110">Roles</span></span></th>
<th><span data-ttu-id="8dbec-111">Documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="8dbec-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dbec-112">Definir configurações do comunicado</span><span class="sxs-lookup"><span data-stu-id="8dbec-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8dbec-113">Crie o comunicado através da gravação e carregamento de arquivos de áudio ou usando texto em fala (TTS).</span><span class="sxs-lookup"><span data-stu-id="8dbec-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="8dbec-114">Configure os intervalos de números não atribuídos na tabela de número não atribuída e os associe com o comunicado adequado.</span><span class="sxs-lookup"><span data-stu-id="8dbec-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8dbec-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8dbec-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="8dbec-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="8dbec-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="8dbec-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="8dbec-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="8dbec-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8dbec-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="8dbec-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="8dbec-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="8dbec-120"><a href="lync-server-2013-create-an-announcement.md">Criar um anúncio no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8dbec-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="8dbec-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configurar a tabela de número não atribuído no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8dbec-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dbec-122">Verifique a implantação do comunicado</span><span class="sxs-lookup"><span data-stu-id="8dbec-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="8dbec-123">Faça o teste escutando os comunicados para verificar se sua configuração funciona como o esperado.</span><span class="sxs-lookup"><span data-stu-id="8dbec-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="8dbec-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">Adicionais Verificar a implantação do lançamento no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8dbec-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: implantação'
description: 'Lync Server 2013: implantação.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750dabf9659327b19e80006d1bca05090f22fd43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555357"
---
# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="0f797-103">Implantação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-103">Deployment of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f797-104">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0f797-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0f797-105">A implantação do software de comunicações do Lync Server 2013 inclui preparar os serviços de domínio do Active Directory, implantar os servidores front-end e outros componentes internos do Lync Server 2013 e, em seguida, implantar quaisquer funções e recursos de servidor adicionais que sua organização pode exigir, como acesso de usuário externo e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0f797-105">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="0f797-106">Esta documentação descreve três cenários de implantação do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0f797-106">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="0f797-107">Nova implantação do Lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="0f797-107">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="0f797-108">Nova implantação do Lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0f797-108">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="0f797-109">Nova implantação do Lync Server 2013 Standard Edition ou Enterprise Edition em uma implantação existente do Lync Server 2010 Standard Edition ou Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="0f797-109">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="0f797-110">Para obter informações sobre a implantação do Lync Server 2013 em um ambiente existente do Microsoft Office Communications Server 2007 ou do Microsoft Office Communications Server 2007 R2, consulte a documentação de [migração](migration.md) .</span><span class="sxs-lookup"><span data-stu-id="0f797-110">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f797-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0f797-111">In This Section</span></span>

  - [<span data-ttu-id="0f797-112">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-112">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="0f797-113">Implantando o acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-113">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="0f797-114">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-114">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="0f797-115">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-115">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="0f797-116">Implantando o arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-116">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="0f797-117">Configurando a conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-117">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="0f797-118">Planejamento e implantação de vídeo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-118">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="0f797-119">Implantando sites de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-119">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="0f797-120">Implantando o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-120">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="0f797-121">Implantando clientes e dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-121">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="0f797-122">Planejando e implantando o repositório unificado de contatos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-122">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="0f797-123">Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-123">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="0f797-124">Atualizando da versão de avaliação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-124">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="0f797-125">Implantando o controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-125">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="0f797-126">Implantação de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-126">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="0f797-127">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-127">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="0f797-128">Configuração de integridade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f797-128">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


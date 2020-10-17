---
title: 'Lync Server 2013: implantação'
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
ms.openlocfilehash: b5fcba91b3017faff29ad8d1bcce20d51a32bd1d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498978"
---
# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="f965b-102">Implantação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-102">Deployment of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f965b-103">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f965b-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f965b-104">A implantação do software de comunicações do Lync Server 2013 inclui preparar os serviços de domínio do Active Directory, implantar os servidores front-end e outros componentes internos do Lync Server 2013 e, em seguida, implantar quaisquer funções e recursos de servidor adicionais que sua organização pode exigir, como acesso de usuário externo e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f965b-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="f965b-105">Esta documentação descreve três cenários de implantação do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="f965b-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="f965b-106">Nova implantação do Lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f965b-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="f965b-107">Nova implantação do Lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f965b-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="f965b-108">Nova implantação do Lync Server 2013 Standard Edition ou Enterprise Edition em uma implantação existente do Lync Server 2010 Standard Edition ou Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f965b-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="f965b-109">Para obter informações sobre a implantação do Lync Server 2013 em um ambiente existente do Microsoft Office Communications Server 2007 ou do Microsoft Office Communications Server 2007 R2, consulte a documentação de [migração](migration.md) .</span><span class="sxs-lookup"><span data-stu-id="f965b-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f965b-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f965b-110">In This Section</span></span>

  - [<span data-ttu-id="f965b-111">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="f965b-112">Implantando o acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="f965b-113">Implantando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="f965b-114">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="f965b-115">Implantando o arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="f965b-116">Configurando a conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="f965b-117">Planejamento e implantação de vídeo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="f965b-118">Implantando sites de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="f965b-119">Implantando o servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="f965b-120">Implantando clientes e dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="f965b-121">Planejando e implantando o repositório unificado de contatos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="f965b-122">Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="f965b-123">Atualizando da versão de avaliação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="f965b-124">Implantando o controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="f965b-125">Implantação de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="f965b-126">Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="f965b-127">Configuração de integridade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f965b-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: Configurando comunicados para números não atribuídos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c352e7a4f062e6a9a1aab0bf52289c20102cc7fe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517548"
---
# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="e258b-102">Configurando comunicados para números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e258b-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e258b-103">_**Última modificação do tópico:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e258b-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e258b-104">O aplicativo de anúncio é um recurso do Enterprise Voice que permite configurar o que acontece com as chamadas para extensões não atribuídas (extensões que são válidas para sua organização, mas não estão atribuídas a uma pessoa ou a um telefone).</span><span class="sxs-lookup"><span data-stu-id="e258b-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="e258b-105">Por exemplo, você pode configurar chamadas a números não atribuídos para que reproduzam uma mensagem ou sejam transferidas para um destino diferente, ou ambos.</span><span class="sxs-lookup"><span data-stu-id="e258b-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="e258b-106">O aplicativo de anúncio é instalado como um recurso do aplicativo grupo de resposta no servidor front-end ou servidor Standard Edition quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e258b-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e258b-107">Você precisa configurar Comunicados carregando arquivos de áudio ou configurando o mecanismo TTS (conversão de texto em fala) e a tabela de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="e258b-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="e258b-108">Esta seção orienta você durante a configuração de comunicados do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e258b-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="e258b-109">Ele pressupõe que você já tenha lido as seções de planejamento relacionadas aos comunicados e implantado um servidor Enterprise Edition ou um servidor Standard Edition com o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e258b-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e258b-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e258b-110">In This Section</span></span>

  - [<span data-ttu-id="e258b-111">Pré-requisitos e funções de configuração de comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e258b-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="e258b-112">Processo de implantação para o aplicativo de anúncio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e258b-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="e258b-113">Criar um comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e258b-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="e258b-114">Configurar a tabela de números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e258b-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="e258b-115">Opcion Verificar a implantação do comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e258b-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e258b-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="e258b-116">See Also</span></span>


[<span data-ttu-id="e258b-117">Planejamento de recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e258b-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


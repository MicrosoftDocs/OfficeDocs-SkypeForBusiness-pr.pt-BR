---
title: 'Lync Server 2013: Configurando comunicados de números não atribuídos'
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
ms.openlocfilehash: 52d7e8ad1aa4fcfe3db9aabee61e317810707194
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="713aa-102">Configurando comunicados de números não atribuídos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713aa-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="713aa-103">_**Tópico da última modificação:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="713aa-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="713aa-104">O aplicativo de anúncio é um recurso de voz empresarial que permite que você configure o que acontece às chamadas para extensões não atribuídas (extensões que são válidas para sua organização, mas não são atribuídas a uma pessoa ou telefone).</span><span class="sxs-lookup"><span data-stu-id="713aa-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="713aa-105">Por exemplo, você pode configurar chamadas a números não atribuídos para que reproduzam uma mensagem ou sejam transferidas para um destino diferente, ou ambos.</span><span class="sxs-lookup"><span data-stu-id="713aa-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="713aa-106">O aplicativo de anúncio é instalado como um recurso do aplicativo de grupo de resposta no servidor front-end ou Standard Edition ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="713aa-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="713aa-107">Você precisa configurar Comunicados carregando arquivos de áudio ou configurando o mecanismo TTS (conversão de texto em fala) e a tabela de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="713aa-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="713aa-108">Esta seção orienta você na configuração de comunicados do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="713aa-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="713aa-109">Ele pressupõe que você já leu as seções de planejamento relacionadas aos comunicados e implantou um servidor Enterprise Edition ou um servidor Standard Edition com Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="713aa-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="713aa-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="713aa-110">In This Section</span></span>

  - [<span data-ttu-id="713aa-111">Pré-requisitos e funções de configuração de Comunicado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713aa-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="713aa-112">Processo de implantação do aplicativo de anúncio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713aa-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="713aa-113">Criar um anúncio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713aa-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="713aa-114">Configurar a tabela de número não atribuído no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713aa-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="713aa-115">Adicionais Verificar a implantação do lançamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713aa-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="713aa-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="713aa-116">See Also</span></span>


[<span data-ttu-id="713aa-117">Planejando os recursos de gerenciamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="713aa-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


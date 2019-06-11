---
title: 'Lync Server 2013: configurações de política de grupo para o Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e075af74fd081e49daad0768a33c9769e8a633bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="cbb57-102">Configurações da política de grupo para o Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cbb57-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbb57-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="cbb57-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="cbb57-104">Em versões anteriores do Lync e do Office Communicator, um modelo administrativo autônomo do Communicator. ADM estava disponível para definir as configurações de política de grupo de cliente.</span><span class="sxs-lookup"><span data-stu-id="cbb57-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="cbb57-105">Para o Lync 2013, novos arquivos de modelo administrativo (arquivos. admx e. adml) estão incluídos juntamente com o modelo administrativo de política de grupo do Office.</span><span class="sxs-lookup"><span data-stu-id="cbb57-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="cbb57-106">A disponibilidade de arquivos. admx e. adml do Lync 2013 permite baixar modelos e gerenciar centralmente as configurações de política de grupo para todos os programas e pacotes de idiomas do Office.</span><span class="sxs-lookup"><span data-stu-id="cbb57-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="cbb57-107">Para obter detalhes, consulte os arquivos de modelo administrativo do Office 2013 (ADMX, ADML) "na documentação do <http://go.microsoft.com/fwlink/p/?linkid=267516>Office 2013 em.</span><span class="sxs-lookup"><span data-stu-id="cbb57-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="cbb57-108">Políticas de inicialização do cliente</span><span class="sxs-lookup"><span data-stu-id="cbb57-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="cbb57-109">Há várias políticas de inicialização do cliente que você deve configurar antes que os usuários entrem no servidor pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="cbb57-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="cbb57-110">Como essas diretivas entram em vigor antes de o cliente entrar e começar a receber configurações de provisionamento em banda do servidor, você pode usar a política de grupo para configurá-la.</span><span class="sxs-lookup"><span data-stu-id="cbb57-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="cbb57-111">Para obter mais informações, consulte Configurando [as políticas de inicialização do cliente no Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="cbb57-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


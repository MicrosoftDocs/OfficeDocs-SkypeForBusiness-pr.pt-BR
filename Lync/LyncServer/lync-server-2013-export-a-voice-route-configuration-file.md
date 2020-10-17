---
title: 'Lync Server 2013: exportar um arquivo de configuração de rota de voz'
description: 'Lync Server 2013: exportar um arquivo de configuração de rota de voz.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bf342e11be41015df3cfd76f6a875381cb8b64
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564787"
---
# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="3223f-103">Exportar um arquivo de configuração de rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3223f-103">Export a voice route configuration file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3223f-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3223f-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3223f-105">Se você quiser salvar sua configuração de roteamento de voz sem publicá-la, siga estas etapas para usar os comandos exportar e importar da configuração do painel de controle do Lync Server para salvar e recuperar um instantâneo da sua configuração de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="3223f-105">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="3223f-106">Quando você importa um arquivo de configuração de roteamento de voz (. vcfg), mas foram feitas alterações na configuração de roteamento de voz no servidor enquanto isso, as páginas no grupo de **Roteamento de voz** no painel de controle do Lync Server indicarão que há alterações não confirmadas no roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="3223f-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="3223f-107">Essas alterações não confirmadas são as diferenças entre as duas configurações que exigem reconciliação.</span><span class="sxs-lookup"><span data-stu-id="3223f-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="3223f-108">Se você tiver feito alterações não confirmadas nas configurações de qualquer página dentro do grupo, as alterações serão salvas no arquivo de configuração de voz exportado (. vcfg).</span><span class="sxs-lookup"><span data-stu-id="3223f-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="3223f-109">Isso permite que você faça alterações de configuração de roteamento de voz durante várias sessões antes de publicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="3223f-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="3223f-110">Para exportar uma configuração de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="3223f-110">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="3223f-111">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3223f-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3223f-112">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3223f-112">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3223f-113">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3223f-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3223f-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3223f-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3223f-115">Na barra de navegação esquerda, clique em **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="3223f-115">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="3223f-116">No menu **Ações**, clique em **Exportar configuração**.</span><span class="sxs-lookup"><span data-stu-id="3223f-116">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="3223f-117">Especifique um local e nome de arquivo e então clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3223f-117">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3223f-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="3223f-118">See Also</span></span>


[<span data-ttu-id="3223f-119">Importar um arquivo de configuração de rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3223f-119">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: exportando e importando configuração de roteamento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3a65c0ab32f40c78c6c679f7be7b86a4ccca1e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="9fe51-102">Exportando e importando a configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe51-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fe51-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9fe51-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9fe51-104">Se você quiser salvar sua configuração de roteamento de voz sem publicá-la, siga estas etapas para usar os comandos exportar e importar da configuração do painel de controle do Lync Server para salvar e recuperar um instantâneo da sua configuração de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="9fe51-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="9fe51-105">Quando você importa um arquivo de configuração de roteamento de voz (. vcfg), mas foram feitas alterações na configuração de roteamento de voz no servidor enquanto isso, as páginas no grupo de **Roteamento de voz** no painel de controle do Lync Server indicarão que há alterações não confirmadas no roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="9fe51-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="9fe51-106">Essas alterações não confirmadas são as diferenças entre as duas configurações que exigem reconciliação.</span><span class="sxs-lookup"><span data-stu-id="9fe51-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9fe51-107">Se você tiver feito qualquer alteração não confirmada na configurações de qualquer página dentro do grupo <STRONG>Roteamento de Voz</STRONG>, as alterações serão salvas no arquivo de configuração de voz exportado (.vcfg).</span><span class="sxs-lookup"><span data-stu-id="9fe51-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="9fe51-108">Isso permite que você faça alterações de configuração de roteamento de voz durante várias sessões do painel de controle do Lync Server antes de publicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="9fe51-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9fe51-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9fe51-109">In This Section</span></span>

  - [<span data-ttu-id="9fe51-110">Exportar um arquivo de configuração de rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe51-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="9fe51-111">Importar um arquivo de configuração de rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fe51-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="9fe51-112">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="9fe51-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


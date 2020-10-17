---
title: 'Lync Server 2013: cmdlets do Lync Server por categoria'
description: 'Lync Server 2013: cmdlets do Lync Server por categoria.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df562bd11d54c9ecda4fe3d6172ed1d8bd2627d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571867"
---
# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="ac70d-103">Cmdlets do Lync Server 2013 por categoria</span><span class="sxs-lookup"><span data-stu-id="ac70d-103">Lync Server 2013 cmdlets by category</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac70d-104">_**Última modificação do tópico:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="ac70d-104">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="ac70d-105">O Microsoft Lync Server 2013 vem com quase 550 cmdlets projetados especificamente para permitir que os administradores gerenciem o Lync Server a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="ac70d-105">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="ac70d-106">Você acessa os cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ac70d-106">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="ac70d-107">É possível obter ajuda sobre um cmdlet diretamente na linha de comando, digitando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="ac70d-107">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="ac70d-108">O comando anterior recuperará toda a Ajuda disponível para o cmdlet **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="ac70d-108">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="ac70d-109">Substitua a referência ao **New-CsVoicePolicy** pelo nome do cmdlet para o qual você deseja recuperar a ajuda.</span><span class="sxs-lookup"><span data-stu-id="ac70d-109">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="ac70d-110">Para recuperar uma lista completa de cmdlets disponíveis para o gerenciamento do Microsoft Lync Server 2013, digite o seguinte no prompt de comando do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="ac70d-110">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="ac70d-p103">Se você não tiver certeza de quais cmdlets precisa, também fornecemos uma lista categorizada de cmdlets e seus tópicos da Ajuda. Você perceberá que alguns cmdlets são mostrados em mais de uma categoria, o que foi intencional, pois elas se aplicam a várias áreas do produto. A seguir está uma lista de categorias:</span><span class="sxs-lookup"><span data-stu-id="ac70d-p103">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics. You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product. The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ac70d-114">A referência de cmdlet do Skype for Business foi movida para o docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ac70d-114">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="ac70d-115">Clicando nos links abaixo, você será retirado da nova página do docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ac70d-115">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="ac70d-116">O conteúdo agora é aberto e está disponível para contribuições da Comunidade por meio do GitHub.</span><span class="sxs-lookup"><span data-stu-id="ac70d-116">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="ac70d-117">Interessado em contribuir?</span><span class="sxs-lookup"><span data-stu-id="ac70d-117">Interested in contributing?</span></span> <span data-ttu-id="ac70d-118">Confira o LEIAme no repositório aqui: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="ac70d-118">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ac70d-119">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ac70d-119">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac70d-120"><a href="lync-server-2013-user-management-cmdlets.md">Cmdlets de gerenciamento de usuário no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-120"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac70d-121"><a href="lync-server-2013-voice-application-cmdlets.md">Cmdlets de aplicativo de voz no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-121"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac70d-122"><a href="lync-server-2013-client-management-cmdlets.md">Cmdlets de gerenciamento de cliente no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-122"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac70d-123"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Cmdlets avançados do Enterprise Voice no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-123"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac70d-124"><a href="lync-server-2013-im-and-presence-cmdlets.md">Cmdlets de IM e presença no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-124"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac70d-125"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Cmdlets de conectividade PSTN no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-125"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac70d-126"><a href="lync-server-2013-conferencing-cmdlets.md">Cmdlets de conferência no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-126"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac70d-127"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Cmdlets de telefones e dispositivos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-127"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac70d-128"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Cmdlets de infraestrutura e implantação no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-128"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac70d-129"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Cmdlets de migração e de coexistência no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-129"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac70d-130"><a href="lync-server-2013-security-cmdlets.md">Cmdlets de segurança no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-130"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac70d-131"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Cmdlets de configuração do Shell de gerenciamento do Lync Server no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-131"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac70d-132"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Cmdlets de serviços e funções de servidor no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-132"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac70d-133"><a href="lync-server-2013-mobility-cmdlets.md">Cmdlets de mobilidade no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-133"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac70d-134"><a href="lync-server-2013-application-management-cmdlets.md">Cmdlets de gerenciamento de aplicativos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-134"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac70d-135"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Cmdlets do servidor de chat persistente no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-135"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac70d-136"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Cmdlets de Federação e acesso externo no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-136"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="ac70d-137"><a href="lync-server-2013-centralized-logging-cmdlets.md">Cmdlets de registro centralizado no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-137"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac70d-138"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Cmdlets do Enterprise Voice no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ac70d-138"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac70d-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="ac70d-139">See Also</span></span>


[<span data-ttu-id="ac70d-140">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ac70d-140">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


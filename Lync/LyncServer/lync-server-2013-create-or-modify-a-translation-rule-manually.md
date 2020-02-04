---
title: 'Lync Server 2013: criar ou modificar manualmente uma regra de tradução'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 372b394619a83ec01ca7a36bac4037c815f09fc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="f3967-102">Criar ou modificar uma regra de tradução manualmente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3967-102">Create or modify a translation rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3967-103">_**Tópico da última modificação:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="f3967-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="f3967-104">Siga estas etapas se quiser definir uma regra de tradução escrevendo uma expressão regular para o padrão correspondente e regra de tradução.</span><span class="sxs-lookup"><span data-stu-id="f3967-104">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="f3967-105">Você também pode inserir um conjunto de valores na ferramenta **construir uma regra de tradução** e habilitar o painel de controle do Lync Server para gerar o padrão correspondente e a regra de tradução para você.</span><span class="sxs-lookup"><span data-stu-id="f3967-105">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="f3967-106">Para obter detalhes, consulte [criar ou modificar uma regra de tradução usando a ferramenta criar regra de tradução no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span><span class="sxs-lookup"><span data-stu-id="f3967-106">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="f3967-107">Para definir uma regra de tradução manualmente</span><span class="sxs-lookup"><span data-stu-id="f3967-107">To define a translation rule manually</span></span>

1.  <span data-ttu-id="f3967-108">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f3967-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f3967-109">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f3967-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f3967-110">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3967-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f3967-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f3967-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f3967-112">Para começar a definir uma regra de tradução, siga as etapas em [configurar um tronco com bypass de mídia no Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) até a etapa 10 ou [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) até a etapa 9.</span><span class="sxs-lookup"><span data-stu-id="f3967-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="f3967-113">No campo **nome** da página **nova regra de tradução** ou **Editar regra de tradução** , digite um nome que descreva o padrão de número que está sendo traduzido.</span><span class="sxs-lookup"><span data-stu-id="f3967-113">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="f3967-114">Adicionais Em **Descrição**, digite uma descrição da regra de tradução, por exemplo, para a **discagem de longa distância internacional dos EUA**.</span><span class="sxs-lookup"><span data-stu-id="f3967-114">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="f3967-115">Clique em **Editar** na parte inferior da seção **construir uma regra de tradução** .</span><span class="sxs-lookup"><span data-stu-id="f3967-115">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="f3967-116">Digite o seguinte em **Digitar uma expressão regular**:</span><span class="sxs-lookup"><span data-stu-id="f3967-116">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="f3967-117">Em **coincidir com esse padrão**, especifique o padrão que será usado para corresponder os números a serem traduzidos.</span><span class="sxs-lookup"><span data-stu-id="f3967-117">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="f3967-118">Em **regra de tradução**, especifique um padrão para o formato dos números traduzidos.</span><span class="sxs-lookup"><span data-stu-id="f3967-118">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="f3967-119">Por exemplo, se você digitar \*\* ^ \\+ (\\d{9}\\+) $\*\* em **Match this Pattern** e **011 $1** na **regra de tradução**, a regra irá traduzir + 441235551010 para 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="f3967-119">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="f3967-120">Clique em **OK** para salvar a regra de tradução.</span><span class="sxs-lookup"><span data-stu-id="f3967-120">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="f3967-121">Clique em **OK** para salvar a configuração do tronco.</span><span class="sxs-lookup"><span data-stu-id="f3967-121">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="f3967-122">Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="f3967-122">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3967-123">Sempre que você cria ou modifica uma regra de tradução, deve executar o comando <STRONG>Commit All</STRONG> para publicar a alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="f3967-123">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="f3967-124">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="f3967-124">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3967-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="f3967-125">See Also</span></span>


[<span data-ttu-id="f3967-126">Criar ou modificar uma regra de tradução usando a ferramenta construir uma regra de tradução no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3967-126">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="f3967-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3967-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="f3967-128">Configurar um tronco sem bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3967-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="f3967-129">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3967-129">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="f3967-130">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3967-130">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Criar ou modificar uma regra de conversão usando a ferramenta compilar uma regra de conversão
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8321603c699fb0f25fc0a3a1b94e8b216761c6b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="ee15e-102">Criar ou modificar uma regra de conversão usando a ferramenta compilar uma regra de conversão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee15e-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee15e-103">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="ee15e-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="ee15e-104">Siga estas etapas se você quiser definir uma regra de conversão inserindo um conjunto de valores na ferramenta **criar uma regra de conversão** e habilitando o painel de controle do Lync Server para gerar o padrão correspondente e a regra de conversão para você.</span><span class="sxs-lookup"><span data-stu-id="ee15e-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="ee15e-105">Se preferir, é possível gravar uma expressão regular manualmente para definir o padrão de correspondência e a regra de conversão.</span><span class="sxs-lookup"><span data-stu-id="ee15e-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="ee15e-106">Para obter detalhes, consulte [criar ou modificar uma regra de conversão manualmente no Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="ee15e-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="ee15e-107">Para definir uma regra usando a ferramenta Compilar uma Regra de Conversão</span><span class="sxs-lookup"><span data-stu-id="ee15e-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="ee15e-108">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ee15e-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ee15e-109">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ee15e-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ee15e-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ee15e-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ee15e-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ee15e-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ee15e-112">Para começar a definir uma regra de conversão, siga as etapas em [configurar um tronco com bypass de mídia no Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) até a etapa 10 ou [configurar um tronco sem bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) até a etapa 9.</span><span class="sxs-lookup"><span data-stu-id="ee15e-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="ee15e-113">Em **Nome** na página **Nova Regra de Conversão** ou **Editar Regra de Conversão**, digite um nome que descreve o padrão numérico que está convertido.</span><span class="sxs-lookup"><span data-stu-id="ee15e-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="ee15e-114">(Opcional) Em **Descrição**, digite uma descrição da regra de conversão, por exemplo **Discagem de longa distância internacional EUA**.</span><span class="sxs-lookup"><span data-stu-id="ee15e-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="ee15e-115">Na seção **Compilar uma Regra de Conversão** da caixa de diálogo, insira valores nos seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="ee15e-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="ee15e-116">**Dígitos iniciais**: (Opcional) especifique os dígitos iniciais dos números com os quais você deseja que o padrão corresponda.</span><span class="sxs-lookup"><span data-stu-id="ee15e-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="ee15e-117">Por exemplo, insira **+** neste campo para corresponder os números no formato E. 164 (que começa com +).</span><span class="sxs-lookup"><span data-stu-id="ee15e-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="ee15e-p105">**Comprimento**: especifique o número de dígitos no padrão de correspondência e selecione se deseja que o padrão corresponda a números exatamente com esse comprimento, com um comprimento menor ou qualquer comprimento. Por exemplo, digite **11** e selecione **No mínimo** na lista suspensa para fazer a correspondência de números com no mínimo 11 dígitos de comprimento.</span><span class="sxs-lookup"><span data-stu-id="ee15e-p105">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length. For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="ee15e-120">**Dígitos a serem removidos**: (Opcional) especifique o número de dígitos iniciais a serem removidos.</span><span class="sxs-lookup"><span data-stu-id="ee15e-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="ee15e-121">Por exemplo, insira **1** para retirar o **+** desde o início do número.</span><span class="sxs-lookup"><span data-stu-id="ee15e-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="ee15e-p107">**Dígitos a adicionar**: (Opcional) especifique os dígitos a serem anexados aos números convertidos. Por exemplo, digite **011** se quiser que 011 seja anexado aos números convertidos quando a regra é aplicada.</span><span class="sxs-lookup"><span data-stu-id="ee15e-p107">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="ee15e-p108">Os valores inseridos nesses campos são refletidos nos campos **Padrão a ser correspondido** e **Regra de conversão**. Por exemplo, se você especificar os valores do exemplo anterior, a expressão regular resultante no campo **Padrão a ser correspondido** será:</span><span class="sxs-lookup"><span data-stu-id="ee15e-p108">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="ee15e-126">**^\\+ (\\d{9}\\d +) $**</span><span class="sxs-lookup"><span data-stu-id="ee15e-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="ee15e-p109">O campo **Regra de conversão** especifica um padrão para o formato de números convertidos. Esse padrão tem duas partes:</span><span class="sxs-lookup"><span data-stu-id="ee15e-p109">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
      - <span data-ttu-id="ee15e-129">Um valor (por exemplo, **$1**) que representa o número de dígitos no padrão correspondido</span><span class="sxs-lookup"><span data-stu-id="ee15e-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="ee15e-130">(Opcional) Um valor que pode ser anexado digitando no campo **Dígitos a adicionar**</span><span class="sxs-lookup"><span data-stu-id="ee15e-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="ee15e-131">Usando os valores do exemplo anterior, **011$1** aparece no campo **Regra de conversão**.</span><span class="sxs-lookup"><span data-stu-id="ee15e-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="ee15e-132">Quando essa regra de conversão é aplicada, +441235551010 se torna 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="ee15e-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="ee15e-133">Clique em **OK** para salvar a regra de tradução.</span><span class="sxs-lookup"><span data-stu-id="ee15e-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="ee15e-134">Clique em **OK** para salvar a configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="ee15e-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="ee15e-135">Na página **Configuração do Tronco**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="ee15e-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ee15e-136">Sempre que criar ou modificar uma regra de tradução, será necessário executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="ee15e-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ee15e-137">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="ee15e-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ee15e-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="ee15e-138">See Also</span></span>


[<span data-ttu-id="ee15e-139">Criar ou modificar uma regra de conversão manualmente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee15e-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="ee15e-140">Configurar um tronco com bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee15e-140">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="ee15e-141">Configurar um tronco sem bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee15e-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="ee15e-142">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee15e-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="ee15e-143">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee15e-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


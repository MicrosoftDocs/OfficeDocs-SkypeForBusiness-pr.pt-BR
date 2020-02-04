---
title: 'Lync Server 2013: Criar ou modificar uma regra de normalização manualmente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf7693eb4a8bac814c81ef69b9f158edb3684f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a><span data-ttu-id="3e120-102">Criar ou modificar uma regra de normalização manualmente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e120-102">Create or modify a normalization rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e120-103">_**Tópico da última modificação:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="3e120-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="3e120-104">Conclua as etapas a seguir se desejar criar ou modificar uma regra de normalização manualmente.</span><span class="sxs-lookup"><span data-stu-id="3e120-104">Complete the following steps if you want to create or modify a normalization rule manually.</span></span> <span data-ttu-id="3e120-105">Se você quiser criar ou modificar uma regra de normalização usando criar uma regra de normalização no painel de controle do Lync Server, consulte [criar ou modificar uma regra de normalização usando a regra criar uma normalização no Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span><span class="sxs-lookup"><span data-stu-id="3e120-105">If you want to create or modify a normalization rule by using Build a Normalization Rule in Lync Server Control Panel, see [Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span></span>

<div>

## <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="3e120-106">Para definir uma regra de normalização manualmente</span><span class="sxs-lookup"><span data-stu-id="3e120-106">To define a normalization rule manually</span></span>

1.  <span data-ttu-id="3e120-107">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3e120-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3e120-108">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3e120-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3e120-109">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e120-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e120-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3e120-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e120-111">Adicionais Siga as etapas em [criar um plano de discagem no Lync server 2013](lync-server-2013-create-a-dial-plan.md) ou [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="3e120-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

4.  <span data-ttu-id="3e120-112">Em **Nova regra de normalização** ou **Editar regra de normalização**, digite um nome que descreve o padrão de número que está sendo normalizado em **Nome** (por exemplo, o nome da regra de normalização **5DigitExtension**).</span><span class="sxs-lookup"><span data-stu-id="3e120-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>

5.  <span data-ttu-id="3e120-113">(Opcional) No campo **Descrição**, digite uma descrição da regra de normalização (por exemplo, "Traduzir extensões de 5 dígitos").</span><span class="sxs-lookup"><span data-stu-id="3e120-113">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="3e120-114">Em **Compilar uma regra de normalização**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3e120-114">In **Build a Normalization Rule**, click **Edit**.</span></span>

7.  <span data-ttu-id="3e120-115">Digite o seguinte em **Digitar uma expressão regular**:</span><span class="sxs-lookup"><span data-stu-id="3e120-115">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="3e120-116">Em **Corresponder este padrão**, especifique o padrão que você deseja usar para coincidir com o número de telefone discado.</span><span class="sxs-lookup"><span data-stu-id="3e120-116">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
      - <span data-ttu-id="3e120-117">Em **Regra de conversão**, especifique um padrão para o formato dos números de telefone E.164 convertidos.</span><span class="sxs-lookup"><span data-stu-id="3e120-117">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="3e120-118">Por exemplo, se você inserir **^ (\\d{7}) $** em **coincidir este padrão** e **+ 1425 $1** na **regra de tradução**, a regra normalizará 5550100 para + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="3e120-118">For example, if you enter **^(\\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="3e120-119">(Opcional) Se a regra de normalização resulta em um número de telefone interno à sua organização, selecione **Extensão interna**.</span><span class="sxs-lookup"><span data-stu-id="3e120-119">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="3e120-p104">(Opcional) Insira um número para testar a regra de normalização e clique em **Ir**. Os resultados do teste são exibidos em **Inserir um número para testar**.</span><span class="sxs-lookup"><span data-stu-id="3e120-p104">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e120-122">É possível salvar uma regra de normalização que ainda não passou no teste e reconfigurá-la posteriormente.</span><span class="sxs-lookup"><span data-stu-id="3e120-122">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="3e120-123">Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3e120-123">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="3e120-124">Clique em **OK** para salvar a regra de normalização.</span><span class="sxs-lookup"><span data-stu-id="3e120-124">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="3e120-125">Clique em **OK** para salvar o plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="3e120-125">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="3e120-126">Na página **Plano de Discagem**, clique em **Confirmar** e clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="3e120-126">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e120-127">Sempre que criar ou alterar uma regra de normalização, você deve executar o comando <STRONG>Confirmar todos</STRONG> para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="3e120-127">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="3e120-128">Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="3e120-128">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e120-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="3e120-129">See Also</span></span>


[<span data-ttu-id="3e120-130">Criar ou modificar uma regra de normalização usando criar uma regra de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e120-130">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[<span data-ttu-id="3e120-131">Criar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e120-131">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="3e120-132">Modificar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e120-132">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="3e120-133">Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e120-133">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="3e120-134">Testar roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e120-134">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


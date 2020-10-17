---
title: 'Lync Server 2013: implantar aparência de linha compartilhada'
description: 'Lync Server 2013: implantar aparência de linha compartilhada.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c83c06bbc9b91e11cabc0abee20de28fc7281205
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558617"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="5fd18-103">Implantar aparência de linha compartilhada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fd18-103">Deploy Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fd18-104">_**Última modificação do tópico:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="5fd18-104">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="5fd18-105">Leia este tópico para saber como implantar a aparência da linha compartilhada (SLA) no Lync Server 2013, atualização cumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="5fd18-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="5fd18-106">O SLA é um recurso para lidar com várias chamadas em um número específico chamado de número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="5fd18-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="5fd18-107">Para obter mais informações sobre esse recurso, consulte [Plan for Shared line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="5fd18-107">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="5fd18-108">A aparência de linha compartilhada (SLA) é um novo recurso no Lync Server 2013, atualização cumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="5fd18-108">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="5fd18-109">Para habilitar esse recurso, primeiro você deve implantar esta atualização cumulativa.</span><span class="sxs-lookup"><span data-stu-id="5fd18-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="5fd18-110">Instalar a aparência da linha compartilhada</span><span class="sxs-lookup"><span data-stu-id="5fd18-110">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="5fd18-111">Após o Lync Server 2013, a atualização cumulativa de abril de 2016 é implantada, o aplicativo SLA não é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="5fd18-111">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="5fd18-112">Para habilitar o aplicativo, siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="5fd18-112">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="5fd18-113">Registre o SLA como um aplicativo de servidor executando o seguinte comando para cada pool:</span><span class="sxs-lookup"><span data-stu-id="5fd18-113">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="5fd18-114">em que% FQDN% é o nome de domínio totalmente qualificado do pool.</span><span class="sxs-lookup"><span data-stu-id="5fd18-114">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="5fd18-115">Execute o seguinte comando para atualizar as funções RBAC para os cmdlets de SLA:</span><span class="sxs-lookup"><span data-stu-id="5fd18-115">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="5fd18-116">Reinicie todos os servidores front-end (serviço RTCSRV) em todos os pools em que o SLA foi instalado e habilitado:</span><span class="sxs-lookup"><span data-stu-id="5fd18-116">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="5fd18-117">Criar um grupo de SLA e adicionar usuários a ele</span><span class="sxs-lookup"><span data-stu-id="5fd18-117">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="5fd18-118">Crie o grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="5fd18-118">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="5fd18-119">O cmdlet Set-CsSlaConfiguration marca a conta do Enterprise Voice SLAGroup1 como uma entidade SLA e o número de SLAGroup1 se torna o número do grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="5fd18-119">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="5fd18-120">Todas as chamadas para o SLAGroup1 tocarão todo o grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="5fd18-120">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="5fd18-121">O exemplo a seguir cria um grupo de SLA para um usuário existente do Enterprise Voice, SLAGroup1, e usa o número atribuído para SLAGroup1 como o número principal de SLA.</span><span class="sxs-lookup"><span data-stu-id="5fd18-121">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="5fd18-122">O comando define o número máximo de chamadas simultâneas para o novo grupo de SLA como 3 e para as chamadas que excedem o sinal de ocupado:</span><span class="sxs-lookup"><span data-stu-id="5fd18-122">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="5fd18-123">Você pode usar Set-CsSlaConfiguration para criar um novo grupo de SLA ou modificar um existente.</span><span class="sxs-lookup"><span data-stu-id="5fd18-123">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5fd18-124">Observe que o que você especificar para <CODE>-Identity</CODE> deve ser uma conta de usuário válida habilitada para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5fd18-124">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="5fd18-125">Adicione representantes ao grupo usando o cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="5fd18-125">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="5fd18-126">O exemplo a seguir adiciona um usuário ao grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="5fd18-126">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="5fd18-127">Cada usuário adicionado ao grupo deve ser um usuário habilitado para Enterprise Voice válido:</span><span class="sxs-lookup"><span data-stu-id="5fd18-127">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="5fd18-128">Repita o cmdlet para cada usuário que você deseja adicionar ao grupo.</span><span class="sxs-lookup"><span data-stu-id="5fd18-128">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="5fd18-129">Os usuários só podem pertencer a um único grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="5fd18-129">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="5fd18-130">Configurar a opção ocupado do grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="5fd18-130">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="5fd18-131">Configure a opção ocupado do grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="5fd18-131">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="5fd18-132">O exemplo a seguir define chamadas que excedem o número máximo de chamadas simultâneas a serem encaminhadas para o número de telefone 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="5fd18-132">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="5fd18-133">O destino pode ser um usuário em sua organização em vez de um número de telefone; Nesse caso, a sintaxe da pessoa que receberá as chamadas encaminhadas será o mesmo que quando você especificar um representante: `sip:<NameofDelegate@domain>` .</span><span class="sxs-lookup"><span data-stu-id="5fd18-133">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="5fd18-134">O outro parâmetro possível para `BusyOption` é `Voicemail` :</span><span class="sxs-lookup"><span data-stu-id="5fd18-134">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="5fd18-135">Configurar a opção de chamada perdida do grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="5fd18-135">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="5fd18-136">Configure a opção de chamada perdida do grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) :</span><span class="sxs-lookup"><span data-stu-id="5fd18-136">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="5fd18-137">O exemplo a seguir especifica que as chamadas perdidas devem ser encaminhadas para o usuário chamado `sla_forward_number` .</span><span class="sxs-lookup"><span data-stu-id="5fd18-137">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="5fd18-138">As opções válidas para o `-MissedCallOption` parâmetro são `Forward` , `BusySignal` ou `Disconnect` .</span><span class="sxs-lookup"><span data-stu-id="5fd18-138">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="5fd18-139">Se escolher `Forward` , você também deve incluir o `-MissedCallForwardTarget` parâmetro, com um número de usuário ou de telefone como o destino:</span><span class="sxs-lookup"><span data-stu-id="5fd18-139">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="5fd18-140">Remover um representante de um grupo</span><span class="sxs-lookup"><span data-stu-id="5fd18-140">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="5fd18-141">Remover um representante de um grupo usando o cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="5fd18-141">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="5fd18-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5fd18-142">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="5fd18-143">Excluir um grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="5fd18-143">Delete an SLA group</span></span>

1.  <span data-ttu-id="5fd18-144">Exclua um grupo SLA usando o cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="5fd18-144">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="5fd18-145">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5fd18-145">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>


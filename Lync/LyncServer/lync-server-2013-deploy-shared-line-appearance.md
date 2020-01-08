---
title: 'Lync Server 2013: implantar a aparência da linha compartilhada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da81073fc239822a682f926e1b782c8555153bf6
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="c7bd4-102">Implantar a aparência da linha compartilhada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7bd4-102">Deploy Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7bd4-103">_**Tópico da última modificação:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="c7bd4-103">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="c7bd4-104">Leia este tópico para aprender a implantar a aparência da linha compartilhada (SLA) no Lync Server 2013, atualização cumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-104">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="c7bd4-105">O SLA é um recurso para administrar várias chamadas em um número específico chamado número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-105">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="c7bd4-106">Para obter mais informações sobre esse recurso, consulte [planejar a aparência de uma linha compartilhada no Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="c7bd4-106">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="c7bd4-107">A aparência da linha compartilhada (SLA) é um novo recurso do Lync Server 2013, atualização cumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-107">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="c7bd4-108">Para habilitar este recurso, você deve primeiro ter implantado essa atualização cumulativa.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-108">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="c7bd4-109">Instalar Aparência de Linha Compartilhada</span><span class="sxs-lookup"><span data-stu-id="c7bd4-109">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="c7bd4-110">Após o Lync Server 2013, a atualização cumulativa de abril 2016 é implantada, o aplicativo SLA não é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-110">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="c7bd4-111">Para habilitar o aplicativo, siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="c7bd4-111">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="c7bd4-112">Registrar SLA como um aplicativo de servidor executando o seguinte comando para cada pool:</span><span class="sxs-lookup"><span data-stu-id="c7bd4-112">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="c7bd4-113">onde %FQDN% é o nome de domínio totalmente qualificado do pool.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-113">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="c7bd4-114">Execute o seguinte comando para atualizar as funções do RBAC para cmdlets de SLA:</span><span class="sxs-lookup"><span data-stu-id="c7bd4-114">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="c7bd4-115">Reiniciar todos os Servidores Front-end (serviço RTCSRV) em todos os pools onde o SLA foi instalado e ativado:</span><span class="sxs-lookup"><span data-stu-id="c7bd4-115">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="c7bd4-116">Criar um grupo SLA e adicionar usuários a ele</span><span class="sxs-lookup"><span data-stu-id="c7bd4-116">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="c7bd4-117">Criar o grupo SLA utilizando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):</span><span class="sxs-lookup"><span data-stu-id="c7bd4-117">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="c7bd4-p104">O cmdlet Set-Cs SlaConfiguration marca a conta SLAGroup1 da conta do Enterprise Voice como uma entidade SLA, e o número de SLAGroup1 transforma-se no número para o grupo SLA. Todas as chamadas para SLAGroup1 tocarão no grupo SLA inteiro.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-p104">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="c7bd4-120">O exemplo a seguir cria um grupo SLA para um usuário Enterprise Voice existente, SLAGroup1 e usa o número atribuído para SLAGroup1 como número principal de SLA.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-120">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="c7bd4-121">O comando define o número máximo de chamadas simultâneas para o novo grupo SLA em 3, e chamadas além desse número ouvirão um sinal de ocupado:</span><span class="sxs-lookup"><span data-stu-id="c7bd4-121">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="c7bd4-122">Você pode usar Set-Cs SlaConfiguration para criar um novo grupo SLA ou modificar um existente.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-122">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c7bd4-123">Observe que o que você especificar <CODE>-Identity</CODE> para deve ser uma conta de usuário válida habilitada para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-123">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="c7bd4-124">Adicionar representantes ao grupo utilizando o cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates):</span><span class="sxs-lookup"><span data-stu-id="c7bd4-124">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="c7bd4-125">O exemplo a seguir adiciona um usuário ao grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-125">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="c7bd4-126">Cada usuário adicionado ao grupo deve ser um usuário habilitado para o Enterprise Voice habilitado:</span><span class="sxs-lookup"><span data-stu-id="c7bd4-126">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="c7bd4-p106">Repita o cmdlet para cada usuário que você deseja adicionar ao grupo. Os usuários podem somente pertencer a um único grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-p106">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="c7bd4-129">Configuração da Opção Ocupado do grupo SLA</span><span class="sxs-lookup"><span data-stu-id="c7bd4-129">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="c7bd4-130">Configurar a Opção Ocupado do grupo SLA usando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):</span><span class="sxs-lookup"><span data-stu-id="c7bd4-130">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="c7bd4-131">O exemplo a seguir define que as chamadas excedendo o número máximo de chamadas simultâneas serão encaminhadas ao número de telefone 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-131">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="c7bd4-132">O destino pode ser um usuário em sua organização em vez de um número de telefone; Nesse caso, a sintaxe para a pessoa que receber as chamadas encaminhadas é a mesma que quando você especifica um representante: `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-132">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="c7bd4-133">O outro parâmetro possível para `BusyOption` é `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="c7bd4-133">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="c7bd4-134">Configuração da Opção de Chamada perdida do grupo SLA</span><span class="sxs-lookup"><span data-stu-id="c7bd4-134">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="c7bd4-135">Configurar a Opção de Chamada Perdida do grupo SLA usando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):</span><span class="sxs-lookup"><span data-stu-id="c7bd4-135">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="c7bd4-136">O exemplo a seguir especifica que as chamadas perdidas serão encaminhadas para o usuário `sla_forward_number`chamado.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-136">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="c7bd4-137">As opções válidas para `-MissedCallOption` o parâmetro `Forward`são `BusySignal`, ou `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="c7bd4-137">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="c7bd4-138">Se você escolher `Forward`, também deverá incluir o `-MissedCallForwardTarget` parâmetro, com um número de usuário ou de telefone como o destino:</span><span class="sxs-lookup"><span data-stu-id="c7bd4-138">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="c7bd4-139">Remover um representante de um grupo</span><span class="sxs-lookup"><span data-stu-id="c7bd4-139">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="c7bd4-140">Remover um representante de um grupo usando o cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates):</span><span class="sxs-lookup"><span data-stu-id="c7bd4-140">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="c7bd4-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c7bd4-141">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="c7bd4-142">Excluir um grupo SLA</span><span class="sxs-lookup"><span data-stu-id="c7bd4-142">Delete an SLA group</span></span>

1.  <span data-ttu-id="c7bd4-143">Excluir um grupo SLA utilizando o cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="c7bd4-143">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="c7bd4-144">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c7bd4-144">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>


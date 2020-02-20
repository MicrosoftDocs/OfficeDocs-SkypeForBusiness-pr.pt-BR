---
title: Implantar aparência de linha compartilhada no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Leia este tópico para saber como implantar a aparência da linha compartilhada (SLA) no Skype for Business Server 2015, atualização cumulativa de novembro de 2015. O SLA é um recurso para lidar com várias chamadas em um número específico chamado de número compartilhado.
ms.openlocfilehash: 2009b313b343d9746f3eeff5f53fec4899c2f9a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129304"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="319b5-104">Implantar aparência de linha compartilhada no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="319b5-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="319b5-105">Leia este tópico para saber como implantar a aparência da linha compartilhada (SLA) no Skype for Business Server 2015, atualização cumulativa de novembro de 2015.</span><span class="sxs-lookup"><span data-stu-id="319b5-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="319b5-106">O SLA é um recurso para lidar com várias chamadas em um número específico chamado de número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="319b5-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="319b5-107">Para obter mais informações sobre esse recurso, consulte [Plan for Shared line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="319b5-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="319b5-108">A aparência de linha compartilhada (SLA) é um novo recurso no Skype for Business Server, atualização cumulativa de novembro de 2015.</span><span class="sxs-lookup"><span data-stu-id="319b5-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="319b5-109">Para habilitar esse recurso, primeiro você deve implantar esta atualização cumulativa.</span><span class="sxs-lookup"><span data-stu-id="319b5-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="319b5-110">Instalar a aparência da linha compartilhada</span><span class="sxs-lookup"><span data-stu-id="319b5-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="319b5-111">Após o Skype for Business Server, a atualização cumulativa de novembro de 2015 é `SkypeServerUpdateInstaller.exe` implantada, execute o patch em cada servidor de front-end no pool.</span><span class="sxs-lookup"><span data-stu-id="319b5-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="319b5-112">O instalador implantará a versão mais recente do aplicativo SLA, no entanto, o aplicativo não está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="319b5-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="319b5-113">Ele é habilitado seguindo as etapas descritas abaixo:</span><span class="sxs-lookup"><span data-stu-id="319b5-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="319b5-114">a.</span><span class="sxs-lookup"><span data-stu-id="319b5-114">a.</span></span> <span data-ttu-id="319b5-115">Registre o SLA como um aplicativo de servidor executando o seguinte comando para cada pool:</span><span class="sxs-lookup"><span data-stu-id="319b5-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="319b5-116">em que% FQDN% é o nome de domínio totalmente qualificado do pool.</span><span class="sxs-lookup"><span data-stu-id="319b5-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="319b5-117">b.</span><span class="sxs-lookup"><span data-stu-id="319b5-117">b.</span></span> <span data-ttu-id="319b5-118">Execute o seguinte comando para atualizar as funções RBAC para os cmdlets de SLA:</span><span class="sxs-lookup"><span data-stu-id="319b5-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="319b5-119">c.</span><span class="sxs-lookup"><span data-stu-id="319b5-119">c.</span></span> <span data-ttu-id="319b5-120">Reinicie todos os servidores front-end (serviço RTCSRV) em todos os pools em que o SLA foi instalado e habilitado:</span><span class="sxs-lookup"><span data-stu-id="319b5-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="319b5-121">Criar um grupo de SLA e adicionar usuários a ele</span><span class="sxs-lookup"><span data-stu-id="319b5-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="319b5-122">Crie o grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="319b5-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="319b5-123">O cmdlet Set-CsSlaConfiguration marca a conta do Enterprise Voice SLAGroup1 como uma entidade SLA e o número de SLAGroup1 se torna o número do grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="319b5-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="319b5-124">Todas as chamadas para o SLAGroup1 tocarão todo o grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="319b5-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="319b5-125">O exemplo a seguir cria um grupo de SLA para um usuário existente do Enterprise Voice, SLAGroup1, e usa o número atribuído para SLAGroup1 como o número principal de SLA.</span><span class="sxs-lookup"><span data-stu-id="319b5-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="319b5-126">O comando define o número máximo de chamadas simultâneas para o novo grupo de SLA como 3 e para as chamadas que excedem o sinal de ocupado:</span><span class="sxs-lookup"><span data-stu-id="319b5-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="319b5-127">Você pode usar set-CsSlaConfiguration para criar um novo grupo de SLA ou modificar um existente.</span><span class="sxs-lookup"><span data-stu-id="319b5-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="319b5-128">Observe que o que você especificar `-Identity` para deve ser uma conta de usuário válida habilitada para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="319b5-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="319b5-129">Adicione representantes ao grupo usando o cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="319b5-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="319b5-130">O exemplo a seguir adiciona um usuário ao grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="319b5-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="319b5-131">Cada usuário adicionado ao grupo deve ser um usuário habilitado para Enterprise Voice válido:</span><span class="sxs-lookup"><span data-stu-id="319b5-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="319b5-132">Repita o cmdlet para cada usuário que você deseja adicionar ao grupo.</span><span class="sxs-lookup"><span data-stu-id="319b5-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="319b5-133">Os usuários só podem pertencer a um único grupo de SLA.</span><span class="sxs-lookup"><span data-stu-id="319b5-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="319b5-134">Configurar a opção ocupado do grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="319b5-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="319b5-135">Configure a opção ocupado do grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="319b5-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="319b5-136">O exemplo a seguir define chamadas que excedem o número máximo de chamadas simultâneas a serem encaminhadas para o número de telefone 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="319b5-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="319b5-137">O destino pode ser um usuário em sua organização em vez de um número de telefone; Nesse caso, a sintaxe da pessoa que receberá as chamadas encaminhadas será o mesmo que quando você especificar um representante: `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="319b5-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="319b5-138">O outro parâmetro possível para `BusyOption` é `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="319b5-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="319b5-139">Configurar a opção de chamada perdida do grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="319b5-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="319b5-140">Configure a opção de chamada perdida do grupo SLA usando o cmdlet [set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="319b5-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="319b5-141">O exemplo a seguir especifica que as chamadas perdidas devem ser encaminhadas para o `sla_forward_number`usuário chamado.</span><span class="sxs-lookup"><span data-stu-id="319b5-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="319b5-142">As opções válidas para `-MissedCallOption` o parâmetro `Forward`são `BusySignal`, ou `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="319b5-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="319b5-143">Se escolher `Forward`, você também deve incluir o `-MissedCallForwardTarget` parâmetro, com um número de usuário ou de telefone como o destino:</span><span class="sxs-lookup"><span data-stu-id="319b5-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="319b5-144">Remover um representante de um grupo</span><span class="sxs-lookup"><span data-stu-id="319b5-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="319b5-145">Remover um representante de um grupo usando o cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="319b5-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="319b5-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="319b5-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="319b5-147">Excluir um grupo de SLA</span><span class="sxs-lookup"><span data-stu-id="319b5-147">Delete an SLA group</span></span>

- <span data-ttu-id="319b5-148">Exclua um grupo SLA usando o cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="319b5-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="319b5-149">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="319b5-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```



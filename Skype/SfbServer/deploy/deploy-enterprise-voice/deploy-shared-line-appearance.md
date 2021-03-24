---
title: Implantar a aparência de linha compartilhada no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Leia este tópico para saber como implantar a Aparência de Linha Compartilhada (SLA) no Skype for Business Server 2015, Atualização Cumulativa de novembro de 2015. SLA é um recurso para lidar com várias chamadas em um número específico chamado número compartilhado.
ms.openlocfilehash: 7758354b7c4be123cb9b5a482af3304b069931a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104907"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="19e7e-104">Implantar a aparência de linha compartilhada no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="19e7e-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="19e7e-105">Leia este tópico para saber como implantar a Aparência de Linha Compartilhada (SLA) no Skype for Business Server 2015, Atualização Cumulativa de novembro de 2015.</span><span class="sxs-lookup"><span data-stu-id="19e7e-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="19e7e-106">SLA é um recurso para lidar com várias chamadas em um número específico chamado número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="19e7e-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="19e7e-107">Para obter mais informações sobre esse recurso, consulte [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="19e7e-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="19e7e-108">A Aparência de Linha Compartilhada (SLA) é um novo recurso no Skype for Business Server, Atualização Cumulativa de novembro de 2015.</span><span class="sxs-lookup"><span data-stu-id="19e7e-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="19e7e-109">Para habilitar esse recurso, você deve ter implantado primeiro essa atualização cumulativa.</span><span class="sxs-lookup"><span data-stu-id="19e7e-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="19e7e-110">Instalar a aparência de linha compartilhada</span><span class="sxs-lookup"><span data-stu-id="19e7e-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="19e7e-111">Depois que o Skype for Business Server, a Atualização Cumulativa de novembro de 2015 for implantada, execute o patch em cada  `SkypeServerUpdateInstaller.exe` Servidor de Front-End no pool.</span><span class="sxs-lookup"><span data-stu-id="19e7e-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="19e7e-112">O instalador implantará a versão mais recente do aplicativo SLA, no entanto, o aplicativo não está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="19e7e-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="19e7e-113">Ele é habilitado seguindo as etapas descritas abaixo:</span><span class="sxs-lookup"><span data-stu-id="19e7e-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="19e7e-114">a.</span><span class="sxs-lookup"><span data-stu-id="19e7e-114">a.</span></span> <span data-ttu-id="19e7e-115">Registre o SLA como um aplicativo de servidor executando o seguinte comando para cada pool:</span><span class="sxs-lookup"><span data-stu-id="19e7e-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="19e7e-116">onde %FQDN% é o nome de domínio totalmente qualificado do pool.</span><span class="sxs-lookup"><span data-stu-id="19e7e-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="19e7e-117">b.</span><span class="sxs-lookup"><span data-stu-id="19e7e-117">b.</span></span> <span data-ttu-id="19e7e-118">Execute o seguinte comando para atualizar as funções RBAC dos cmdlets SLA:</span><span class="sxs-lookup"><span data-stu-id="19e7e-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="19e7e-119">c.</span><span class="sxs-lookup"><span data-stu-id="19e7e-119">c.</span></span> <span data-ttu-id="19e7e-120">Reinicie todos os Servidores front-end (serviço RTCSRV) em todos os pools onde o SLA foi instalado e habilitado:</span><span class="sxs-lookup"><span data-stu-id="19e7e-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="19e7e-121">Criar um grupo SLA e adicionar usuários a ele</span><span class="sxs-lookup"><span data-stu-id="19e7e-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="19e7e-122">Crie o grupo SLA usando o cmdlet [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="19e7e-122">Create the SLA group by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="19e7e-123">O Set-CsSlaConfiguration cmdlet marca o SLAGroup1 da conta Enterprise Voice como uma entidade SLA, e o número de SLAGroup1 se torna o número do grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="19e7e-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="19e7e-124">Todas as chamadas para SLAGroup1 tocarão todo o grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="19e7e-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="19e7e-125">O exemplo a seguir cria um grupo SLA para um usuário Enterprise Voice existente, SLAGroup1, e usa o número atribuído para SLAGroup1 como o número de linha principal SLA.</span><span class="sxs-lookup"><span data-stu-id="19e7e-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="19e7e-126">O comando define o número máximo de chamadas simultâneas para o novo grupo SLA como 3 e para chamadas em excesso ouvirem um sinal de ocupado:</span><span class="sxs-lookup"><span data-stu-id="19e7e-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="19e7e-127">Você pode usar Set-CsSlaConfiguration para criar um novo grupo SLA ou modificar um existente.</span><span class="sxs-lookup"><span data-stu-id="19e7e-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="19e7e-128">Observe que o que você especificar deve ser uma conta de usuário Enterprise Voice  `-Identity` habilitada para uso.</span><span class="sxs-lookup"><span data-stu-id="19e7e-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="19e7e-129">Adicione representantes ao grupo usando o cmdlet [Add-CsSlaDelegates:](/powershell/module/skype/add-cssladelegates?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="19e7e-129">Add delegates to the group by using the [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="19e7e-130">O exemplo a seguir adiciona um usuário ao grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="19e7e-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="19e7e-131">Cada usuário adicionado ao grupo deve ser um usuário Enterprise Voice habilitado para uso válido:</span><span class="sxs-lookup"><span data-stu-id="19e7e-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="19e7e-132">Repita o cmdlet para cada usuário que você deseja adicionar ao grupo.</span><span class="sxs-lookup"><span data-stu-id="19e7e-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="19e7e-133">Os usuários só podem pertencer a um único grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="19e7e-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="19e7e-134">Configurar a opção de ocupado do grupo SLA</span><span class="sxs-lookup"><span data-stu-id="19e7e-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="19e7e-135">Configure a Opção de Ocupado do grupo SLA usando o cmdlet [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="19e7e-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="19e7e-136">O exemplo a seguir define chamadas que excedem o número máximo de chamadas simultâneas a serem encaminhadas para o número de telefone 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="19e7e-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="19e7e-137">O destino pode ser um usuário em sua organização em vez de um número de telefone; nesse caso, a sintaxe para a pessoa receber as chamadas encaminhadas é a mesma que quando você especifica um representante:  `sip:<NameofDelegate@domain>` .</span><span class="sxs-lookup"><span data-stu-id="19e7e-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="19e7e-138">O outro parâmetro possível para  `BusyOption` `Voicemail` é :</span><span class="sxs-lookup"><span data-stu-id="19e7e-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="19e7e-139">Configurar a opção de chamada perdida do grupo SLA</span><span class="sxs-lookup"><span data-stu-id="19e7e-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="19e7e-140">Configure a opção de chamada perdida do grupo SLA usando o cmdlet [Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="19e7e-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="19e7e-141">O exemplo a seguir especifica que as chamadas perdidas devem ser encaminhadas para o usuário chamado  `sla_forward_number` .</span><span class="sxs-lookup"><span data-stu-id="19e7e-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="19e7e-142">As opções válidas para  `-MissedCallOption` o parâmetro são , ou `Forward`  `BusySignal`  `Disconnect` .</span><span class="sxs-lookup"><span data-stu-id="19e7e-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="19e7e-143">Se você escolher  `Forward` , também deverá incluir o parâmetro, com um usuário ou número de telefone como o  `-MissedCallForwardTarget` destino:</span><span class="sxs-lookup"><span data-stu-id="19e7e-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="19e7e-144">Remover um representante de um grupo</span><span class="sxs-lookup"><span data-stu-id="19e7e-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="19e7e-145">Remova um representante de um grupo usando o cmdlet [Remove-CsSlaDelegates:](/powershell/module/skype/remove-cssladelegates?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="19e7e-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="19e7e-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="19e7e-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="19e7e-147">Excluir um grupo SLA</span><span class="sxs-lookup"><span data-stu-id="19e7e-147">Delete an SLA group</span></span>

- <span data-ttu-id="19e7e-148">Exclua um grupo SLA usando o cmdlet [Remove-CsSlaConfiguration:](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="19e7e-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="19e7e-149">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="19e7e-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
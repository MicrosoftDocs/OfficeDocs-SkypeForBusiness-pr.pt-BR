---
title: Implantar Aparência de linha compartilhada no Skype for Business Server 2015
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
description: Leia este tópico para aprender como implantar a Aparência de linha compartilhada (SLA) no Skype for Business Server 2015, Atualização Cumulativa de novembro de 2015. O SLA é um recurso para administrar várias chamadas em um número específico chamado número compartilhado.
ms.openlocfilehash: c9c4eef43de2f03be32e92c23e8384020e24b099
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767504"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="d1279-104">Implantar Aparência de linha compartilhada no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d1279-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="d1279-p102">Leia este tópico para aprender como implantar a Aparência de linha compartilhada (SLA) no Skype for Business Server 2015, Atualização Cumulativa de novembro de 2015. O SLA é um recurso para administrar várias chamadas em um número específico chamado número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="d1279-p102">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update. SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="d1279-107">Para obter mais informações sobre esse recurso, consulte [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="d1279-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="d1279-108">A aparência da linha compartilhada (SLA) é um novo recurso no Skype for Business Server, atualização cumulativa de novembro de 2015.</span><span class="sxs-lookup"><span data-stu-id="d1279-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="d1279-109">Para habilitar este recurso, você deve primeiro ter implantado essa atualização cumulativa.</span><span class="sxs-lookup"><span data-stu-id="d1279-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="d1279-110">Instalar Aparência de Linha Compartilhada</span><span class="sxs-lookup"><span data-stu-id="d1279-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="d1279-111">Após o Skype for Business Server, a atualização cumulativa de novembro de 2015 é `SkypeServerUpdateInstaller.exe` implementada, executa o patch em cada servidor front-end do pool.</span><span class="sxs-lookup"><span data-stu-id="d1279-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="d1279-p104">O instalador implantará a versão mais recente do aplicativo SLA, no entanto, o aplicativo não está habilitado por padrão. Ele será habilitado quando as etapas descritas abaixo forem seguidas:</span><span class="sxs-lookup"><span data-stu-id="d1279-p104">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default. It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="d1279-114">a.</span><span class="sxs-lookup"><span data-stu-id="d1279-114">a.</span></span> <span data-ttu-id="d1279-115">Registrar SLA como um aplicativo de servidor executando o seguinte comando para cada pool:</span><span class="sxs-lookup"><span data-stu-id="d1279-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="d1279-116">onde %FQDN% é o nome de domínio totalmente qualificado do pool.</span><span class="sxs-lookup"><span data-stu-id="d1279-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="d1279-117">b.</span><span class="sxs-lookup"><span data-stu-id="d1279-117">b.</span></span> <span data-ttu-id="d1279-118">Execute o seguinte comando para atualizar as funções do RBAC para cmdlets de SLA:</span><span class="sxs-lookup"><span data-stu-id="d1279-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="d1279-119">c.</span><span class="sxs-lookup"><span data-stu-id="d1279-119">c.</span></span> <span data-ttu-id="d1279-120">Reiniciar todos os Servidores Front-end (serviço RTCSRV) em todos os pools onde o SLA foi instalado e ativado:</span><span class="sxs-lookup"><span data-stu-id="d1279-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="d1279-121">Criar um grupo SLA e adicionar usuários a ele</span><span class="sxs-lookup"><span data-stu-id="d1279-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="d1279-122">Criar o grupo SLA utilizando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="d1279-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="d1279-p108">O cmdlet Set-Cs SlaConfiguration marca a conta SLAGroup1 da conta do Enterprise Voice como uma entidade SLA, e o número de SLAGroup1 transforma-se no número para o grupo SLA. Todas as chamadas para SLAGroup1 tocarão no grupo SLA inteiro.</span><span class="sxs-lookup"><span data-stu-id="d1279-p108">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="d1279-125">O exemplo a seguir cria um grupo SLA para um usuário Enterprise Voice existente, SLAGroup1 e usa o número atribuído para SLAGroup1 como número principal de SLA.</span><span class="sxs-lookup"><span data-stu-id="d1279-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="d1279-126">O comando define o número máximo de chamadas simultâneas para o novo grupo SLA em 3, e chamadas além desse número ouvirão um sinal de ocupado:</span><span class="sxs-lookup"><span data-stu-id="d1279-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="d1279-127">Você pode usar Set-Cs SlaConfiguration para criar um novo grupo SLA ou modificar um existente.</span><span class="sxs-lookup"><span data-stu-id="d1279-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d1279-128">Observe que o que você especificar `-Identity` para deve ser uma conta de usuário válida habilitada para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d1279-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="d1279-129">Adicionar representantes ao grupo utilizando o cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="d1279-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="d1279-130">O exemplo a seguir adiciona um usuário ao grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="d1279-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="d1279-131">Cada usuário adicionado ao grupo deve ser um usuário habilitado para o Enterprise Voice habilitado:</span><span class="sxs-lookup"><span data-stu-id="d1279-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="d1279-p110">Repita o cmdlet para cada usuário que você deseja adicionar ao grupo. Os usuários podem somente pertencer a um único grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="d1279-p110">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="d1279-134">Configuração da Opção Ocupado do grupo SLA</span><span class="sxs-lookup"><span data-stu-id="d1279-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="d1279-135">Configurar a Opção Ocupado do grupo SLA usando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="d1279-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="d1279-136">O exemplo a seguir define que as chamadas excedendo o número máximo de chamadas simultâneas serão encaminhadas ao número de telefone 202-555-1234.</span><span class="sxs-lookup"><span data-stu-id="d1279-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="d1279-137">O destino pode ser um usuário em sua organização em vez de um número de telefone; Nesse caso, a sintaxe para a pessoa que receber as chamadas encaminhadas é a mesma que quando você especifica um representante: `sip:<NameofDelegate@domain>`.</span><span class="sxs-lookup"><span data-stu-id="d1279-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="d1279-138">O outro parâmetro possível para `BusyOption` é `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="d1279-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="d1279-139">Configuração da Opção de Chamada perdida do grupo SLA</span><span class="sxs-lookup"><span data-stu-id="d1279-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="d1279-140">Configurar a Opção de Chamada Perdida do grupo SLA usando o cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="d1279-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="d1279-141">O exemplo a seguir especifica que as chamadas perdidas serão encaminhadas para o usuário `sla_forward_number`chamado.</span><span class="sxs-lookup"><span data-stu-id="d1279-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="d1279-142">As opções válidas para `-MissedCallOption` o parâmetro `Forward`são `BusySignal`, ou `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="d1279-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="d1279-143">Se você escolher `Forward`, também deverá incluir o `-MissedCallForwardTarget` parâmetro, com um número de usuário ou de telefone como o destino:</span><span class="sxs-lookup"><span data-stu-id="d1279-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="d1279-144">Remover um representante de um grupo</span><span class="sxs-lookup"><span data-stu-id="d1279-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="d1279-145">Remover um representante de um grupo usando o cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="d1279-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="d1279-146">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d1279-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="d1279-147">Excluir um grupo SLA</span><span class="sxs-lookup"><span data-stu-id="d1279-147">Delete an SLA group</span></span>

- <span data-ttu-id="d1279-148">Excluir um grupo SLA utilizando o cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="d1279-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="d1279-149">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d1279-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```



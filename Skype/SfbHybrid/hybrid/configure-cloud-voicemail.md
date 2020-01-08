---
title: Configurar o serviço de caixa postal na nuvem para usuários locais
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para implementar a caixa postal baseada em nuvem para usuários hospedados no Skype for Business Server.
ms.openlocfilehash: e3b18f8048f8779eac322dece88e5919b2aa7a96
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962999"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="e110a-103">Configurar o serviço de caixa postal na nuvem para usuários locais</span><span class="sxs-lookup"><span data-stu-id="e110a-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="e110a-104">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="e110a-104">Overview</span></span> 
<span data-ttu-id="e110a-105">Este artigo descreve como configurar o serviço de caixa postal do Microsoft Cloud para seus usuários locais do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e110a-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="e110a-106">Este artigo pressupõe que você já tem o Skype for Business Server implantado em uma topologia com suporte e que você atende aos pré-requisitos para a configuração da conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="e110a-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="e110a-107">Para obter mais informações sobre os benefícios, considerações de planejamento e requisitos para a implementação da caixa postal em nuvem, consulte [Plan Cloud Cloud Service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="e110a-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="e110a-108">A configuração da caixa postal em nuvem envolve as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="e110a-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="e110a-109">Verifique se você atende aos pré-requisitos, conforme descrito em [Plan Cloud Cloud Service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="e110a-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="e110a-110">Verifique se você configurou a conectividade híbrida conforme descrito em [Plan Hybrid Connectivity](plan-hybrid-connectivity.md) e [Configure Hybrid Connectivity](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="e110a-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="e110a-111">[Configure a caixa postal na nuvem como o provedor de hospedagem no servidor de borda](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) , conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e110a-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="e110a-112">[Configure uma política de caixa postal hospedada](#configure-a-hosted-voicemail-policy) , conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e110a-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="e110a-113">[Atribua uma política de caixa postal hospedada](#assign-a-hosted-voicemail-policy) , conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e110a-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="e110a-114">[Habilitar um usuário para caixa postal na nuvem](#enable-a-user-for-cloud-voicemail) , conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e110a-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="e110a-115">Configurar a caixa postal na nuvem como o provedor de hospedagem no servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e110a-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="e110a-116">Você configura a caixa postal na nuvem como o provedor de hospedagem em um servidor front-end usando o cmdlet New-CsHostingProvider com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="e110a-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="e110a-117">**Identity** especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando; por exemplo, caixa postal em nuvem.</span><span class="sxs-lookup"><span data-stu-id="e110a-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="e110a-118">**Habilitado** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado.</span><span class="sxs-lookup"><span data-stu-id="e110a-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="e110a-119">Esse parâmetro deve ser definido como true.</span><span class="sxs-lookup"><span data-stu-id="e110a-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="e110a-120">**EnabledSharedAddressSpace**indica se o provedor de hospedagem será usado no cenário de espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="e110a-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="e110a-121">Esse parâmetro deve ser definido como true.</span><span class="sxs-lookup"><span data-stu-id="e110a-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="e110a-122">**HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar contas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e110a-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="e110a-123">Esse parâmetro deve ser definido como false.</span><span class="sxs-lookup"><span data-stu-id="e110a-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="e110a-124">**ProxyFQDN** especifica o nome de domínio totalmente qualificado (FQDN) para o servidor proxy usado pelo provedor de hospedagem; por exemplo, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e110a-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="e110a-125">Entre em contato com seu provedor de hospedagem por esta informação.</span><span class="sxs-lookup"><span data-stu-id="e110a-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="e110a-126">Este valor não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="e110a-126">This value cannot be modified.</span></span> <span data-ttu-id="e110a-127">Se o provedor de hospedagem alterar seu servidor proxy, será necessário excluir e recriar a entrada desse provedor.</span><span class="sxs-lookup"><span data-stu-id="e110a-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="e110a-128">**IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e110a-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="e110a-129">Esse parâmetro deve ser definido como false.</span><span class="sxs-lookup"><span data-stu-id="e110a-129">This parameter must be set to False.</span></span>

<span data-ttu-id="e110a-130">Por exemplo, no Shell de gerenciamento do Skype for Business, o seguinte cmdlet configura a caixa postal na nuvem como o provedor de hospedagem:</span><span class="sxs-lookup"><span data-stu-id="e110a-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="e110a-131">Configurar uma política de caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="e110a-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="e110a-132">Para garantir que a caixa postal de sua organização seja encaminhada para o serviço de caixa postal na nuvem, você deve configurar uma política de caixa postal hospedada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e110a-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="e110a-133">Em muitos casos, apenas uma política de caixa postal hospedada é necessária e você pode modificar a política global para atender a todas as suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="e110a-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="e110a-134">Se sua organização requer várias políticas de caixa postal hospedadas, você pode adicionar políticas usando o cmdlet New-CsHostedVoiceMailPolicy.</span><span class="sxs-lookup"><span data-stu-id="e110a-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="e110a-135">Para modificar a política global, execute o seguinte comando no Shell de gerenciamento do Skype for Business Server após atualizar sua organização e Tenantid:</span><span class="sxs-lookup"><span data-stu-id="e110a-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -Tenant “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="e110a-136">**Destination** especifica o FQDN (nome de domínio totalmente qualificado) do serviço de caixa postal hospedado na nuvem.</span><span class="sxs-lookup"><span data-stu-id="e110a-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="e110a-137">Esse valor deve ser definido como **exap.um.Outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="e110a-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="e110a-138">**Organização** é o domínio padrão atribuído ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="e110a-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="e110a-139">Você pode recuperar essas informações com o administrador de locatários para fazer logon no office.com, clique no aplicativo do centro de administração, navegue até a **instalação** à esquerda e clique em **domínios**.</span><span class="sxs-lookup"><span data-stu-id="e110a-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="e110a-140">Por exemplo: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e110a-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="e110a-141">O nome da organização também é o nome de domínio padrão no Office 365.</span><span class="sxs-lookup"><span data-stu-id="e110a-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="e110a-142">O **locatário** é usado para identificar seu locatário no Office 365.</span><span class="sxs-lookup"><span data-stu-id="e110a-142">**Tenant** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="e110a-143">Para obter mais informações, consulte [Find Your Office 365 locatário ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span><span class="sxs-lookup"><span data-stu-id="e110a-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="e110a-144">Para garantir que uma política de caixa postal hospedada seja criada com êxito, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e110a-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="e110a-145">Atribuir uma política de caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="e110a-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="e110a-146">Por padrão, a política de caixa postal hospedada global é atribuída a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="e110a-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="e110a-147">Se você usar uma política diferente, antes de habilitar os usuários para caixa postal hospedada, deverá primeiro conceder aos usuários a política de caixa postal hospedada desejada usando o cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e110a-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="e110a-148">Por exemplo, o seguinte comando atribui uma política de caixa postal hospedada não global a um usuário:</span><span class="sxs-lookup"><span data-stu-id="e110a-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="e110a-149">Habilitar um usuário para caixa postal em nuvem</span><span class="sxs-lookup"><span data-stu-id="e110a-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="e110a-150">Para permitir que as chamadas de caixa postal de um usuário sejam encaminhadas para a caixa postal na nuvem, use o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) com o parâmetro HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="e110a-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="e110a-151">Por exemplo, o seguinte comando habilita uma conta de usuário para caixa postal em nuvem:</span><span class="sxs-lookup"><span data-stu-id="e110a-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="e110a-152">O cmdlet verifica se a política de caixa postal da nuvem, no nível global, de site ou de usuário, se aplica a este usuário.</span><span class="sxs-lookup"><span data-stu-id="e110a-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="e110a-153">Se nenhuma política for aplicada, o cmdlet falhará.</span><span class="sxs-lookup"><span data-stu-id="e110a-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="e110a-154">O próximo exemplo desabilita uma conta de usuário para a caixa postal na nuvem:</span><span class="sxs-lookup"><span data-stu-id="e110a-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="e110a-155">O cmdlet verifica se nenhuma política de caixa postal hospedada, no nível global, de site ou de usuário, se aplica a este usuário.</span><span class="sxs-lookup"><span data-stu-id="e110a-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="e110a-156">Se uma política for aplicada, o cmdlet falhará.</span><span class="sxs-lookup"><span data-stu-id="e110a-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="e110a-157">Os usuários devem ter o Enterprise-Voice habilitado para usar o serviço de caixa postal do Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="e110a-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>

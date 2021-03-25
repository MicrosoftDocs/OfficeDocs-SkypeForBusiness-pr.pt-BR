---
title: Configurar o serviço de Caixa Postal na Nuvem para usuários locais
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para implementar a caixa postal baseada em nuvem para usuários que estão no Skype for Business Server.
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118980"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="b8e33-103">Configurar o serviço de Caixa Postal na Nuvem para usuários locais</span><span class="sxs-lookup"><span data-stu-id="b8e33-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="b8e33-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="b8e33-104">Overview</span></span> 
<span data-ttu-id="b8e33-105">Este artigo descreve como configurar o serviço de Caixa Postal na Nuvem da Microsoft para seus usuários locais do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b8e33-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="b8e33-106">Este artigo supõe que você já tenha o Skype for Business Server implantado em uma topologia suportada e que você atendeu aos pré-requisitos para configurar a conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="b8e33-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="b8e33-107">Para obter mais informações sobre os benefícios, considerações de planejamento e requisitos para implementar a Caixa Postal na Nuvem, consulte [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="b8e33-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="b8e33-108">Configurar a Caixa Postal na Nuvem envolve as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="b8e33-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="b8e33-109">Verifique se você atendeu aos pré-requisitos conforme descrito em [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="b8e33-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="b8e33-110">Verifique se você configurou a conectividade híbrida conforme descrito em [Plan hybrid connectivity e](plan-hybrid-connectivity.md) Configure hybrid [connectivity](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="b8e33-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="b8e33-111">[Configure a Caixa Postal na Nuvem como o provedor de hospedagem no Servidor Front-End](#configure-cloud-voicemail-as-the-hosting-provider) conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b8e33-111">[Configure Cloud Voicemail as the hosting provider on the Front End Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="b8e33-112">[Configure uma política de caixa postal hospedada](#configure-a-hosted-voicemail-policy) conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b8e33-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="b8e33-113">[Atribua uma política de caixa postal hospedada](#assign-a-hosted-voicemail-policy) conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b8e33-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="b8e33-114">[Habilitar um usuário para a Caixa Postal](#enable-a-user-for-cloud-voicemail) na Nuvem, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b8e33-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="b8e33-115">Configurar a Caixa Postal na Nuvem como provedor de hospedagem</span><span class="sxs-lookup"><span data-stu-id="b8e33-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="b8e33-116">Você configura a Caixa Postal na Nuvem como o provedor de hospedagem em um Servidor Front-End usando o cmdlet New-CsHostingProvider com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="b8e33-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="b8e33-117">**Identity** especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando; por exemplo, Cloud Voicemail.</span><span class="sxs-lookup"><span data-stu-id="b8e33-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="b8e33-118">**Habilitado** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b8e33-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="b8e33-119">Esse parâmetro deve ser definido como True.</span><span class="sxs-lookup"><span data-stu-id="b8e33-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="b8e33-120">**EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado no cenário de espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="b8e33-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="b8e33-121">Esse parâmetro deve ser definido como True.</span><span class="sxs-lookup"><span data-stu-id="b8e33-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="b8e33-122">**HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar contas do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b8e33-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="b8e33-123">Esse parâmetro deve ser definido como False.</span><span class="sxs-lookup"><span data-stu-id="b8e33-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="b8e33-124">**ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem; por exemplo, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b8e33-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="b8e33-125">Entre em contato com seu provedor de hospedagem por esta informação.</span><span class="sxs-lookup"><span data-stu-id="b8e33-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="b8e33-126">Este valor não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="b8e33-126">This value cannot be modified.</span></span> <span data-ttu-id="b8e33-127">Se o provedor de hospedagem mudar seu servidor proxy, você precisará excluir e, em seguida, re-criar a entrada para esse provedor.</span><span class="sxs-lookup"><span data-stu-id="b8e33-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="b8e33-128">**IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido na topologia do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b8e33-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="b8e33-129">Esse parâmetro deve ser definido como False.</span><span class="sxs-lookup"><span data-stu-id="b8e33-129">This parameter must be set to False.</span></span>

<span data-ttu-id="b8e33-130">Por exemplo, no shell gerenciamento do Skype for Business, o cmdlet a seguir configura o Cloud Voicemail como o provedor de hospedagem:</span><span class="sxs-lookup"><span data-stu-id="b8e33-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="b8e33-131">Configurar uma política de caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="b8e33-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="b8e33-132">Para garantir que a caixa postal da sua organização seja roteada para o serviço de Caixa Postal na Nuvem, você deve configurar uma política de caixa postal hospedada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b8e33-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="b8e33-133">Em muitos casos, apenas uma política de caixa postal hospedada é necessária e você pode modificar a política global para atender a todas as suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="b8e33-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="b8e33-134">Se sua organização exigir várias políticas de caixa postal hospedadas, você poderá adicionar políticas usando o cmdlet new-cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="b8e33-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="b8e33-135">Para modificar a política global, execute o seguinte comando no shell de gerenciamento do Skype for Business Server após atualizar sua Organização e TenantID:</span><span class="sxs-lookup"><span data-stu-id="b8e33-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="b8e33-136">**Destination** especifica o FQDN (nome de domínio totalmente qualificado) do serviço de Caixa Postal na Nuvem hospedado.</span><span class="sxs-lookup"><span data-stu-id="b8e33-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="b8e33-137">Esse valor deve ser definido como **exap.um.outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="b8e33-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="b8e33-138">**A** organização é o domínio padrão atribuído ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="b8e33-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="b8e33-139">Você pode recuperar essas informações fazendo com que o administrador de locatário faça logoff office.com, clique no aplicativo centro de administração, navegue até **Instalação** à esquerda e clique em **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="b8e33-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="b8e33-140">Por exemplo: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="b8e33-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="b8e33-141">O nome da organização também é o nome de domínio padrão no Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8e33-141">The Organization name is also the Default Domain name in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="b8e33-142">Para garantir que uma política de caixa postal hospedada tenha sido criada com êxito, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b8e33-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="b8e33-143">Atribuir uma política de caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="b8e33-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="b8e33-144">Por padrão, a política de caixa postal hospedada global é atribuída a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="b8e33-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="b8e33-145">Se você usar uma política diferente, antes de habiliar usuários para caixa postal hospedada, primeiro você deve conceder aos usuários a política de caixa postal hospedada desejada usando o cmdlet [Grant-CSHostedVoicemailPolicy.](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b8e33-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="b8e33-146">Por exemplo, o seguinte comando atribui uma política de caixa postal hospedada não Global a um usuário:</span><span class="sxs-lookup"><span data-stu-id="b8e33-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="b8e33-147">Habilitar um usuário para Caixa Postal na Nuvem</span><span class="sxs-lookup"><span data-stu-id="b8e33-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="b8e33-148">Para habilitar as chamadas de caixa postal de um usuário a serem roteadas para o Cloud Voicemail, use o cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) com o parâmetro HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="b8e33-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="b8e33-149">Por exemplo, o comando a seguir habilita uma conta de usuário para o Cloud Voicemail:</span><span class="sxs-lookup"><span data-stu-id="b8e33-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="b8e33-150">O cmdlet verifica se uma política de Caixa Postal na Nuvem, no nível global, do site ou do usuário, se aplica a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="b8e33-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="b8e33-151">Se nenhuma política se aplicar, o cmdlet falhará.</span><span class="sxs-lookup"><span data-stu-id="b8e33-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="b8e33-152">O próximo exemplo desabilita uma conta de usuário para a Caixa Postal na Nuvem:</span><span class="sxs-lookup"><span data-stu-id="b8e33-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="b8e33-153">O cmdlet verifica se nenhuma política de caixa postal hospedada no nível global, do site ou do usuário se aplica a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="b8e33-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="b8e33-154">Se uma política se aplicar, o cmdlet falhará.</span><span class="sxs-lookup"><span data-stu-id="b8e33-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="b8e33-155">Os usuários devem estar habilitados para uso do Serviço de Caixa Postal na Nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b8e33-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
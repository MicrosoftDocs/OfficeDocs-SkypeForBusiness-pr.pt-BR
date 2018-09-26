---
title: Configurar o serviço de correio de voz de nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para o correio de voz implementing baseado em nuvem para usuários hospedagem no Skype para Business Server.
ms.openlocfilehash: 9cc990cbaecfea74b269809d9e31588d61eee93c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027813"
---
# <a name="configure-cloud-voicemail-service"></a><span data-ttu-id="09ec9-103">Configurar o serviço de correio de voz de nuvem</span><span class="sxs-lookup"><span data-stu-id="09ec9-103">Configure Cloud Voicemail service</span></span>


[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a><span data-ttu-id="09ec9-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="09ec9-104">Overview</span></span> 
<span data-ttu-id="09ec9-105">Este artigo descreve como configurar o serviço de correio de voz do Microsoft Cloud para seu Skype para usuários do local de negócios.</span><span class="sxs-lookup"><span data-stu-id="09ec9-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="09ec9-106">Este artigo pressupõe que você já tem Skype para Business Server implantado em uma topologia com suporte e que você cumpre os pré-requisitos para configurar a conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="09ec9-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="09ec9-107">Para obter mais informações sobre os benefícios, considerações sobre planejamento e requisitos necessários para implementar a caixa postal de nuvem, consulte [serviço de caixa postal de nuvem planejar](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="09ec9-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="09ec9-108">A configuração de caixa postal de nuvem envolve as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="09ec9-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="09ec9-109">Certifique-se de que você cumpre os pré-requisitos conforme descrito no [serviço de caixa postal planejar de nuvem](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="09ec9-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="09ec9-110">Certifique-se de que você tiver configurado a conectividade híbrida, conforme descrito em [conectividade de híbrido plano](plan-hybrid-connectivity.md) e [Configure híbrida](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="09ec9-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="09ec9-111">[Configurar caixa postal de nuvem como o provedor de hospedagem no servidor de borda](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="09ec9-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="09ec9-112">[Configure uma política de caixa postal hospedada](#configure-a-hosted-voicemail-policy) conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="09ec9-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="09ec9-113">[Atribuir uma política de caixa postal hospedada](#assign-a-hosted-voicemail-policy) , conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="09ec9-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="09ec9-114">[Habilitar um usuário para caixa postal de nuvem](#enable-a-user-for-cloud-voicemail) , conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="09ec9-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="09ec9-115">Configurar caixa postal de nuvem como o provedor de hospedagem no servidor de borda</span><span class="sxs-lookup"><span data-stu-id="09ec9-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="09ec9-116">Você pode configurar caixa postal de nuvem como o provedor de hospedagem no servidor de borda usando o cmdlet New-CsHostingProvider, com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="09ec9-116">You configure Cloud Voicemail as the hosting provider on the Edge Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="09ec9-117">**Identidade** Especifica um identificador de valor de cadeia de caracteres exclusiva para o provedor de hospedagem que você está criando; Por exemplo, nuvem caixa postal.</span><span class="sxs-lookup"><span data-stu-id="09ec9-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="09ec9-118">\*\*Habilitado \*\* indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado.</span><span class="sxs-lookup"><span data-stu-id="09ec9-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="09ec9-119">Este parâmetro deve ser definido como True.</span><span class="sxs-lookup"><span data-stu-id="09ec9-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="09ec9-120">**EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado em um cenário de espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="09ec9-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="09ec9-121">Este parâmetro deve ser definido como True.</span><span class="sxs-lookup"><span data-stu-id="09ec9-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="09ec9-122">**HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Skype para contas de servidores de negócios.</span><span class="sxs-lookup"><span data-stu-id="09ec9-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="09ec9-123">Este parâmetro deve ser definido como False.</span><span class="sxs-lookup"><span data-stu-id="09ec9-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="09ec9-124">**ProxyFQDN** Especifica o nome de domínio totalmente qualificado (FQDN) para o servidor proxy usado pelo provedor de hospedagem; Por exemplo, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="09ec9-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="09ec9-125">Contate seu provedor de hospedagem para essas informações.</span><span class="sxs-lookup"><span data-stu-id="09ec9-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="09ec9-126">Esse valor não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="09ec9-126">This value cannot be modified.</span></span> <span data-ttu-id="09ec9-127">Se o provedor de hospedagem altera seu servidor proxy, você precisará excluir e recriar a entrada desse provedor.</span><span class="sxs-lookup"><span data-stu-id="09ec9-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="09ec9-128">**IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido dentro de sua Skype para a topologia de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="09ec9-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="09ec9-129">Este parâmetro deve ser definido como False.</span><span class="sxs-lookup"><span data-stu-id="09ec9-129">This parameter must be set to False.</span></span>

<span data-ttu-id="09ec9-130">Por exemplo, no Skype do shell de gerenciamento de negócios, o cmdlet a seguir configura caixa postal de nuvem como um provedor de hospedagem:</span><span class="sxs-lookup"><span data-stu-id="09ec9-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="09ec9-131">Configurar uma política de caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="09ec9-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="09ec9-132">Para garantir que caixa postal para sua organização é encaminhada para o serviço de correio de voz de nuvem, você deve configurar uma política de caixa postal hospedada para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="09ec9-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="09ec9-133">Em muitos casos, apenas um correio de voz hospedada diretiva é necessária e você pode modificar a política global para atender a todas as suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="09ec9-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="09ec9-134">Se sua organização requer várias políticas de caixa postal hospedada, você pode adicionar políticas usando o cmdlet new-cshostedvoicemailpolicy.</span><span class="sxs-lookup"><span data-stu-id="09ec9-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="09ec9-135">Para modificar a política global, execute o seguinte comando no Skype para Business Server shell de gerenciamento após a atualização de sua organização e a TenantID:</span><span class="sxs-lookup"><span data-stu-id="09ec9-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="09ec9-136">**Destino** Especifica o nome de domínio totalmente qualificado (FQDN) do serviço de nuvem de caixa postal hospedado.</span><span class="sxs-lookup"><span data-stu-id="09ec9-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="09ec9-137">Este valor deve ser definido como **exap**.</span><span class="sxs-lookup"><span data-stu-id="09ec9-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="09ec9-138">**Organização** é o domínio padrão atribuído ao seu locatário.</span><span class="sxs-lookup"><span data-stu-id="09ec9-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="09ec9-139">É possível recuperar essas informações fazendo com que o administrador proprietário faça logon no office.com, clique no aplicativo Admin Center, navegue para a **instalação** à esquerda e clique em **domínios**.</span><span class="sxs-lookup"><span data-stu-id="09ec9-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="09ec9-140">Por exemplo: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="09ec9-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="09ec9-141">O nome da organização também é o nome de domínio padrão no Office 365.</span><span class="sxs-lookup"><span data-stu-id="09ec9-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="09ec9-142">**TenantID** é usado para identificar o seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="09ec9-142">**TenantID** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="09ec9-143">Para obter mais informações, consulte [Encontre seu ID de Inquilino do Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span><span class="sxs-lookup"><span data-stu-id="09ec9-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="09ec9-144">Para garantir que uma política de caixa postal hospedada foi criada com êxito, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="09ec9-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="09ec9-145">Atribuir uma política de caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="09ec9-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="09ec9-146">Por padrão, o Global hospedado política de caixa postal é atribuída a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="09ec9-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="09ec9-147">Se você usar uma política diferente, antes de habilitar usuários para caixa postal hospedada, você deve primeiro conceder aos usuários a política de correio de voz hospedada desejado usando o cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="09ec9-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="09ec9-148">Por exemplo, o comando a seguir atribui uma política de caixa postal de hospedada não Global a um usuário:</span><span class="sxs-lookup"><span data-stu-id="09ec9-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="09ec9-149">Habilitar um usuário para caixa postal de nuvem</span><span class="sxs-lookup"><span data-stu-id="09ec9-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="09ec9-150">Para habilitar chamadas de caixa postal de um usuário sejam roteadas para caixa postal de nuvem, você pode usar o cmdlet [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) com o parâmetro HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="09ec9-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="09ec9-151">Por exemplo, o comando a seguir habilita uma conta de usuário para caixa postal de nuvem:</span><span class="sxs-lookup"><span data-stu-id="09ec9-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="09ec9-152">O cmdlet verifica se uma diretiva de caixa postal de nuvem--em escopo global, site ou nível de usuário – se aplica a este usuário.</span><span class="sxs-lookup"><span data-stu-id="09ec9-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="09ec9-153">Se nenhuma diretiva aplicável, o cmdlet falhará.</span><span class="sxs-lookup"><span data-stu-id="09ec9-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="09ec9-154">O próximo exemplo desabilita uma conta de usuário para caixa postal de nuvem:</span><span class="sxs-lookup"><span data-stu-id="09ec9-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="09ec9-155">O cmdlet verifica que nenhuma diretiva de caixa postal hospedada--em escopo global, site ou nível de usuário – se aplica a este usuário.</span><span class="sxs-lookup"><span data-stu-id="09ec9-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="09ec9-156">Se aplicar uma política, o cmdlet falhará.</span><span class="sxs-lookup"><span data-stu-id="09ec9-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="09ec9-157">Os usuários devem ser habilitado para usar o serviço de correio de voz de nuvem da Microsoft enterprise-voice.</span><span class="sxs-lookup"><span data-stu-id="09ec9-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
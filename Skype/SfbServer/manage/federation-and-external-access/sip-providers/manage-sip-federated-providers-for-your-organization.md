---
title: Gerenciar fornecedores SIP federados para sua organização
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Saiba como configurar o suporte para os usuários de provedores federados SIP.
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818362"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="c34cf-103">Gerenciar provedores federados SIP para sua organização no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c34cf-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="c34cf-104">Para configurar o suporte para os usuários de provedores federados SIP, você precisa fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c34cf-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="c34cf-105">Configurar uma ou mais políticas de acesso de usuários externos para dar suporte à comunicação com contatos do provedor federado SIP</span><span class="sxs-lookup"><span data-stu-id="c34cf-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="c34cf-106">Especificar a quais provedores hospedados você deseja dar suporte</span><span class="sxs-lookup"><span data-stu-id="c34cf-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="c34cf-107">Especificar a quais provedores públicos de IM você deseja dar suporte</span><span class="sxs-lookup"><span data-stu-id="c34cf-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="c34cf-108">Criar ou editar provedores federados SIP públicos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c34cf-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="c34cf-109">A conectividade de mensagens de chat (IM) públicas permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores públicos.</span><span class="sxs-lookup"><span data-stu-id="c34cf-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="c34cf-110">O Skype for Business Server tem configurações de provedor público para mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="c34cf-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="c34cf-111">Cada provedor público é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor, e o nível de verificação padrão **permite que os usuários se comuniquem somente com as pessoas da lista de contatos que usam esse provedor**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="c34cf-112">Como uma configuração padrão, nenhum dos provedores públicos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c34cf-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="c34cf-113">Você deve concluir o contrato de licença e o provisionamento do trabalho antes de habilitar os provedores públicos.</span><span class="sxs-lookup"><span data-stu-id="c34cf-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="c34cf-114">Você pode habilitar o provedor antes de concluir o trabalho de licenciamento e provisionamento.</span><span class="sxs-lookup"><span data-stu-id="c34cf-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="c34cf-115">Os usuários não poderão se comunicar com os contatos desses provedores até que o trabalho pré-requisito seja concluído.</span><span class="sxs-lookup"><span data-stu-id="c34cf-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="c34cf-116">Para obter detalhes sobre licenciamento e provisionamento de provedores públicos, consulte [Configurar políticas para controlar o acesso ao usuário público](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="c34cf-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="c34cf-117">Use o procedimento a seguir para criar ou editar provedores públicos.</span><span class="sxs-lookup"><span data-stu-id="c34cf-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="c34cf-118">Para criar ou editar provedores públicos</span><span class="sxs-lookup"><span data-stu-id="c34cf-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="c34cf-119">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c34cf-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c34cf-120">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c34cf-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c34cf-121">Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **provedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="c34cf-122">Se você precisar criar um novo provedor público, clique em **novo** e, em seguida, clique em **provedor público**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="c34cf-123">Se precisar editar uma entrada da lista de provedores públicos, selecione um provedor público, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="c34cf-124">Na página **Editar Provedor federado SIP** , você pode digitar ou editar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c34cf-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="c34cf-125">**Habilitar comunicações com este provedor**   selecionar essa configuração habilita mensagens instantâneas com os usuários do provedor.</span><span class="sxs-lookup"><span data-stu-id="c34cf-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="c34cf-126">**Nome do provedor:**   uma propriedade necessária, digite o nome do provedor como ele será refletido na listagem de provedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="c34cf-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="c34cf-127">**Serviço de borda de acesso (FQDN):**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="c34cf-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="c34cf-128">Essas informações são fornecidas como um item padrão e só devem ser alteradas se o provedor público fizer uma alteração no FQDN do serviço de borda de acesso no provedor público.</span><span class="sxs-lookup"><span data-stu-id="c34cf-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="c34cf-129">**Nível de verificação padrão:**   a configuração padrão, **permitir que os usuários se comuniquem com as pessoas da lista de contatos que usam esse provedor** limitarão a comunicação com os contatos que você aceitou e estão na sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="c34cf-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="c34cf-130">Selecionar **permitir que os usuários se comuniquem com todos que usam esse provedor** remove a restrição que você deve ter recebido e aceito um convite de contato.</span><span class="sxs-lookup"><span data-stu-id="c34cf-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="c34cf-131">Esta configuração não limita quem pode contatá-lo na rede do provedor público.</span><span class="sxs-lookup"><span data-stu-id="c34cf-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="c34cf-132">Quando terminar de definir as configurações, clique em **confirmar** para salvar ou clique em **Cancelar** para descartar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c34cf-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="c34cf-133">Criar ou editar provedores federados SIP hospedados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c34cf-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="c34cf-134">A conectividade de mensagens instantâneas do provedor hospedado permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com os usuários de serviços de mensagens instantâneas fornecidos pelos provedores hospedados.</span><span class="sxs-lookup"><span data-stu-id="c34cf-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="c34cf-135">Cada provedor hospedado é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor, e o nível de verificação padrão **permite que os usuários se comuniquem somente com as pessoas da lista de contatos que usam esse provedor**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="c34cf-136">Use o procedimento a seguir para criar ou editar provedores hospedados.</span><span class="sxs-lookup"><span data-stu-id="c34cf-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="c34cf-137">Para criar ou editar provedores hospedados</span><span class="sxs-lookup"><span data-stu-id="c34cf-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="c34cf-138">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c34cf-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c34cf-139">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c34cf-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c34cf-140">Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **provedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="c34cf-141">Se você precisar criar um novo provedor hospedado, clique em **novo** e em **provedor hospedado**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="c34cf-142">Se você precisar editar uma entrada da lista de provedores hospedados, selecione um provedor hospedado, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="c34cf-143">Na página **Editar Provedor federado SIP** , você pode digitar ou editar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c34cf-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="c34cf-144">**Habilitar comunicações com este provedor**   selecionar essa configuração permite a comunicação com os usuários do provedor.</span><span class="sxs-lookup"><span data-stu-id="c34cf-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="c34cf-145">**Nome do provedor:**   uma propriedade necessária, digite o nome do provedor como ele será refletido na listagem de provedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="c34cf-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="c34cf-146">**Serviço de borda de acesso (FQDN):**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor hospedado que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="c34cf-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="c34cf-147">Essas informações devem ser fornecidas pelo provedor de hospedagem e só devem ser alteradas se o provedor hospedado fizer uma alteração no FQDN do serviço de borda de acesso no provedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="c34cf-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="c34cf-148">**Nível de verificação padrão:**   a configuração padrão, **permitir que os usuários se comuniquem com as pessoas da lista de contatos que usam esse provedor** limitarão a comunicação com os contatos que você aceitou e estão na sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="c34cf-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="c34cf-149">Selecionar **permitir que os usuários se comuniquem com todos que usam esse provedor** remove a restrição que você deve ter recebido e aceito um convite de contato.</span><span class="sxs-lookup"><span data-stu-id="c34cf-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="c34cf-150">Essa configuração não limita quem pode contatá-lo na rede do provedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="c34cf-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="c34cf-151">Quando terminar de definir as configurações, clique em **confirmar** para salvar ou clique em **Cancelar** para descartar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c34cf-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="c34cf-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="c34cf-152">See Also</span></span>


[<span data-ttu-id="c34cf-153">Configurar políticas para controlar o acesso ao usuário público</span><span class="sxs-lookup"><span data-stu-id="c34cf-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="c34cf-154">Habilitar ou desabilitar federação e conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="c34cf-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)


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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Saiba como configurar o suporte de provedores federados de usuários do SIP.
ms.openlocfilehash: 64b5dcd657b72f03b25fe6de2ff6c0cda21b676d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903163"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="99ecd-103">Gerenciar provedores federados SIP para sua organização no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="99ecd-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="99ecd-104">Para configurar o suporte de provedores federados de usuários do SIP, você precisa fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="99ecd-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="99ecd-105">Configurar uma ou mais políticas de acesso de usuário externo para suportar a comunicação com contatos de provedor federados SIP</span><span class="sxs-lookup"><span data-stu-id="99ecd-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="99ecd-106">Especifique quais provedores hospedados você deseja suportar</span><span class="sxs-lookup"><span data-stu-id="99ecd-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="99ecd-107">Especifique quais provedores públicos de IM você deseja suportar</span><span class="sxs-lookup"><span data-stu-id="99ecd-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="99ecd-108">Criar ou editar provedores federados SIP no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="99ecd-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="99ecd-109">Conectividade pública de instantâneas (IM) de mensagens permite aos usuários em sua organização usar mensagens Instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores públicos.</span><span class="sxs-lookup"><span data-stu-id="99ecd-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="99ecd-110">Skype para Business Server tem as configurações do provedor público de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="99ecd-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="99ecd-111">Cada provedor público é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor e o nível de verificação padrão **Permitir que os usuários se comuniquem somente com pessoas na sua lista de contatos que usam esse provedor**.</span><span class="sxs-lookup"><span data-stu-id="99ecd-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="99ecd-112">Como uma configuração padrão, nenhuma dos provedores públicos são habilitadas.</span><span class="sxs-lookup"><span data-stu-id="99ecd-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="99ecd-113">Você deve concluir o contrato de licença e provisionamento de trabalho antes de habilitar os provedores públicos.</span><span class="sxs-lookup"><span data-stu-id="99ecd-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="99ecd-114">É possível habilitar o provedor antes de concluir o licenciamento e trabalho de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="99ecd-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="99ecd-115">Os usuários não poderão se comunicar com contatos nesses provedores até que o trabalho de pré-requisito seja concluído.</span><span class="sxs-lookup"><span data-stu-id="99ecd-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="99ecd-116">Para obter detalhes sobre o licenciamento e provisionamento de provedores públicos, consulte [Configure políticas para controlar o acesso de usuário público](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="99ecd-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="99ecd-117">Use o procedimento a seguir para criar ou editar provedores públicos.</span><span class="sxs-lookup"><span data-stu-id="99ecd-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="99ecd-118">Para criar ou editar provedores públicos</span><span class="sxs-lookup"><span data-stu-id="99ecd-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="99ecd-119">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="99ecd-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99ecd-120">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="99ecd-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="99ecd-121">Na barra de navegação à esquerda, clique em **federação e acesso externo**e clique em **Provedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="99ecd-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="99ecd-122">Se você precisar criar um novo provedor público, clique em **novo** e clique em **provedor público**.</span><span class="sxs-lookup"><span data-stu-id="99ecd-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="99ecd-123">Se for necessário editar uma entrada da lista de provedores públicos, selecione um provedor público, clique em **Editar**e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="99ecd-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="99ecd-124">Na página **Editar provedor federado SIP** , você pode digitar ou editar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="99ecd-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="99ecd-125">**Habilitar comunicações com este provedor**   selecionar esta configuração permite mensagens Instantâneas com usuários desse provedor.</span><span class="sxs-lookup"><span data-stu-id="99ecd-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="99ecd-126">**Nome do provedor:**   uma propriedade obrigatória, digite o nome do provedor conforme ele será refletido na listagem de provedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="99ecd-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="99ecd-127">**(FQDN) do serviço de borda de acesso:**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="99ecd-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="99ecd-128">Essas informações são fornecidas como um item padrão e devem ser alteradas somente se o provedor público fizer uma alteração para o FQDN do serviço do provedor público de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="99ecd-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="99ecd-129">**Nível de verificação padrão:**   a configuração padrão, **Permitir que os usuários se comuniquem com pessoas na sua lista de contatos que usam esse provedor** limitará a comunicação com contatos que você tiverem aceitado e está em sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="99ecd-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="99ecd-130">A seleção de **Permitir que os usuários se comuniquem com todos usando esse provedor** remove a restrição de que você deve ter recebido e aceitou convidar um contato.</span><span class="sxs-lookup"><span data-stu-id="99ecd-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="99ecd-131">Essa configuração não limitar quem pode contatá-lo da rede do provedor público.</span><span class="sxs-lookup"><span data-stu-id="99ecd-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="99ecd-132">Quando você estiver definindo as configurações, clique em **Confirmar** para salvar ou clique em **Cancelar** para descartar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="99ecd-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="99ecd-133">Criar ou editar provedores de federados SIP hospedados no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="99ecd-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="99ecd-134">Hospedado provedor (IM) conectividade permite que os usuários em sua organização para usar mensagens Instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores hospedados de mensagens instantânea.</span><span class="sxs-lookup"><span data-stu-id="99ecd-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="99ecd-135">Cada provedor hospedado é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor e o nível de verificação padrão **Permitir que os usuários se comuniquem somente com pessoas na sua lista de contatos que usam esse provedor**.</span><span class="sxs-lookup"><span data-stu-id="99ecd-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="99ecd-136">Use o procedimento a seguir para criar ou editar os provedores hospedados.</span><span class="sxs-lookup"><span data-stu-id="99ecd-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="99ecd-137">Para criar ou editar provedores hospedados</span><span class="sxs-lookup"><span data-stu-id="99ecd-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="99ecd-138">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="99ecd-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="99ecd-139">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="99ecd-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="99ecd-140">Na barra de navegação à esquerda, clique em **federação e acesso externo**e clique em **Provedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="99ecd-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="99ecd-141">Se você precisar criar um novo provedor hospedado, clique em **novo** e clique em **provedor hospedado**.</span><span class="sxs-lookup"><span data-stu-id="99ecd-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="99ecd-142">Se for necessário editar uma entrada da lista de provedores hospedados, selecione um provedor hospedado, clique em **Editar**e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="99ecd-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="99ecd-143">Na página **Editar provedor federado SIP** , você pode digitar ou editar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="99ecd-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="99ecd-144">**Habilitar comunicações com este provedor**   selecionar esta configuração habilita as comunicações com usuários desse provedor.</span><span class="sxs-lookup"><span data-stu-id="99ecd-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="99ecd-145">**Nome do provedor:**   uma propriedade obrigatória, digite o nome do provedor conforme ele será refletido na listagem de provedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="99ecd-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="99ecd-146">**(FQDN) do serviço de borda de acesso:**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor hospedado que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="99ecd-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="99ecd-147">Essas informações devem ser fornecidas pelo provedor hospedado e só deverá ser alteradas se o provedor hospedado fizer uma alteração para o FQDN do serviço do provedor hospedado de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="99ecd-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="99ecd-148">**Nível de verificação padrão:**   a configuração padrão, **Permitir que os usuários se comuniquem com pessoas na sua lista de contatos que usam esse provedor** limitará a comunicação com contatos que você tiverem aceitado e está em sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="99ecd-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="99ecd-149">A seleção de **Permitir que os usuários se comuniquem com todos usando esse provedor** remove a restrição de que você deve ter recebido e aceitou convidar um contato.</span><span class="sxs-lookup"><span data-stu-id="99ecd-149">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="99ecd-150">Essa configuração não limitar quem pode contatá-lo da rede do provedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="99ecd-150">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="99ecd-151">Quando você estiver definindo as configurações, clique em **Confirmar** para salvar ou clique em **Cancelar** para descartar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="99ecd-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="99ecd-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="99ecd-152">See Also</span></span>


[<span data-ttu-id="99ecd-153">Configurar políticas para controlar o acesso de usuário público</span><span class="sxs-lookup"><span data-stu-id="99ecd-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="99ecd-154">Habilitar ou desabilitar federação e conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="99ecd-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)


---
title: Gerenciar fornecedores SIP federados para sua organização
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Saiba como configurar o suporte para usuários de provedores sip federados.
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823561"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a><span data-ttu-id="12f7c-103">Gerenciar provedores SIP federados para sua organização no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="12f7c-103">Manage SIP federated providers for your organization in Skype for Business Server</span></span>

<span data-ttu-id="12f7c-104">Para configurar o suporte de usuários de provedores SIP federados, você precisará fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="12f7c-104">To configure support for users of SIP federated providers, you need to do the following:</span></span>

  - <span data-ttu-id="12f7c-105">Configurar uma ou mais políticas de acesso do usuário externo se comunicando com contatos do provedor federado SIP</span><span class="sxs-lookup"><span data-stu-id="12f7c-105">Configure one or more external user access policies to support communicating with SIP federated provider contacts</span></span>

  - <span data-ttu-id="12f7c-106">Especifique quais provedores hospedados você deseja suportar.</span><span class="sxs-lookup"><span data-stu-id="12f7c-106">Specify which hosted providers you want to support</span></span>

  - <span data-ttu-id="12f7c-107">Especifique quais provedores públicos de IM você deseja suportar</span><span class="sxs-lookup"><span data-stu-id="12f7c-107">Specify which public IM providers you want to support</span></span>

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="12f7c-108">Criar ou editar provedores sip públicos federados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="12f7c-108">Create or edit public SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="12f7c-109">A conectividade pública de mensagens instantâneas (IM) permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de mensagens instantâneas fornecidos por provedores públicos.</span><span class="sxs-lookup"><span data-stu-id="12f7c-109">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public providers.</span></span>

<span data-ttu-id="12f7c-110">O Skype for Business Server tem configurações de provedor público para mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="12f7c-110">Skype for Business Server has public provider configurations for instant messaging.</span></span> <span data-ttu-id="12f7c-111">Cada provedor público é configurado com o nome de domínio totalmente qualificado do servidor de Borda do provedor e o nível de verificação padrão permite que os usuários se comuniquem somente com pessoas em sua lista de Contatos que usam esse **provedor.**</span><span class="sxs-lookup"><span data-stu-id="12f7c-111">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="12f7c-112">Como configuração padrão, nenhum dos provedores públicos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="12f7c-112">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="12f7c-113">Você deve concluir o contrato de licença e o trabalho de provisionamento antes de habilitá-los.</span><span class="sxs-lookup"><span data-stu-id="12f7c-113">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="12f7c-114">Você pode habilitar o provedor antes de concluir o trabalho de licenciamento e provisionamento.</span><span class="sxs-lookup"><span data-stu-id="12f7c-114">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="12f7c-115">Os usuários não poderão se comunicar com os contatos desses provedores até que o trabalho de pré-requisito seja concluído.</span><span class="sxs-lookup"><span data-stu-id="12f7c-115">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="12f7c-116">Para obter detalhes sobre licenciamento e provisionamento de provedores públicos, consulte Configurar políticas [para controlar o acesso de usuários públicos.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="12f7c-116">For details on licensing and provisioning of public providers, see [Configure policies to control public user acces](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="12f7c-117">Use o procedimento a seguir para criar ou editar provedores públicos.</span><span class="sxs-lookup"><span data-stu-id="12f7c-117">Use the following procedure to create or edit Public providers.</span></span>


### <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="12f7c-118">Para criar ou editar provedores públicos</span><span class="sxs-lookup"><span data-stu-id="12f7c-118">To create or edit public providers</span></span>

1.  <span data-ttu-id="12f7c-119">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="12f7c-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="12f7c-120">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="12f7c-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="12f7c-121">Na barra de navegação à esquerda, clique em **Federação e Acesso Externo** e em **Provedores Federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="12f7c-121">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="12f7c-122">Se você precisar criar um novo provedor público, clique em **Novo** e em **Provedor público.**</span><span class="sxs-lookup"><span data-stu-id="12f7c-122">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="12f7c-123">Se você precisar editar uma entrada da lista de provedores públicos, selecione um provedor público, clique em **Editar** e em **Mostrar detalhes.**</span><span class="sxs-lookup"><span data-stu-id="12f7c-123">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="12f7c-124">Na página **Editar Provedor Federado SIP**, você pode digitar ou editar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="12f7c-124">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="12f7c-125">**Habilitar comunicações com este provedor**   Selecionar essa configuração habilita as IMs com os usuários desse provedor.</span><span class="sxs-lookup"><span data-stu-id="12f7c-125">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="12f7c-126">**Nome do provedor:**    Uma propriedade obrigatória, digite o nome do provedor conforme ele será refletido na listagem de Provedores Federados SIP.</span><span class="sxs-lookup"><span data-stu-id="12f7c-126">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="12f7c-127">**Serviço de Borda de Acesso (FQDN):**   Uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de Borda de Acesso do provedor que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="12f7c-127">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="12f7c-128">Essas informações são fornecidas como um item padrão e só devem ser alteradas se o provedor público fizer uma alteração no FQDN do serviço de Borda de Acesso no provedor público.</span><span class="sxs-lookup"><span data-stu-id="12f7c-128">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="12f7c-129">**Nível de verificação padrão:**    A configuração padrão, **Permitir que os usuários se comuniquem somente com pessoas em suas listas de Contatos que usam este provedor**, limitará a comunicação aos contatos que foram aceitos e estão em sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="12f7c-129">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="12f7c-130">Selecionar **Permitir que os usuários se comuniquem com todos que usam este provedor** remove a restrição de que você deve ter recebido e aceitado o convite de um contato.</span><span class="sxs-lookup"><span data-stu-id="12f7c-130">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="12f7c-131">Essa configuração não limita quem pode entrar em contato com você a partir da rede do provedor público.</span><span class="sxs-lookup"><span data-stu-id="12f7c-131">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="12f7c-132">Ao concluir a configuração das definições, clique em **Confirmar** para salvar ou em **Cancelar** para descartar as alterações.</span><span class="sxs-lookup"><span data-stu-id="12f7c-132">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a><span data-ttu-id="12f7c-133">Criar ou editar provedores federados SIP hospedados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="12f7c-133">Create or edit hosted SIP federated providers in Skype for Business Server</span></span>

<span data-ttu-id="12f7c-134">A conectividade de mensagens instantâneas (IM) do provedor hospedado permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de mensagens instantâneas fornecidos por provedores hospedados.</span><span class="sxs-lookup"><span data-stu-id="12f7c-134">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers.</span></span>

<span data-ttu-id="12f7c-135">Cada provedor hospedado é configurado com o nome de domínio totalmente qualificado do servidor de Borda do provedor e o nível de verificação padrão **Permitir que os usuários se comuniquem somente com pessoas em suas listas de Contatos que usam este provedor**.</span><span class="sxs-lookup"><span data-stu-id="12f7c-135">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="12f7c-136">Use o procedimento a seguir para criar ou editar provedores hospedados.</span><span class="sxs-lookup"><span data-stu-id="12f7c-136">Use the following procedure to create or edit hosted providers.</span></span>

### <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="12f7c-137">Para criar ou editar provedores hospedados</span><span class="sxs-lookup"><span data-stu-id="12f7c-137">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="12f7c-138">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="12f7c-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="12f7c-139">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="12f7c-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="12f7c-140">Na barra de navegação à esquerda, clique em **Federação e Acesso Externo** e em **Provedores Federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="12f7c-140">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="12f7c-141">Se for necessário criar um novo provedor hospedado, clique em **Novo** e em **Provedor hospedado**.</span><span class="sxs-lookup"><span data-stu-id="12f7c-141">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="12f7c-142">Se for necessário editar uma entrada da lista de provedores hospedados, selecione um provedor hospedado, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="12f7c-142">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="12f7c-143">Na página **Editar Provedor Federado SIP**, você pode digitar ou editar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="12f7c-143">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="12f7c-144">**Habilitar comunicações com este provedor**   Selecionar esta configuração habilita as comunicações com os usuários deste provedor.</span><span class="sxs-lookup"><span data-stu-id="12f7c-144">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="12f7c-145">**Nome do provedor:**    Uma propriedade obrigatória, digite o nome do provedor conforme ele será refletido na listagem de Provedores Federados SIP.</span><span class="sxs-lookup"><span data-stu-id="12f7c-145">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="12f7c-146">**Serviço de Borda de Acesso (FQDN):**   Uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de Borda de Acesso do provedor hospedado que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="12f7c-146">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="12f7c-147">Esta informação deve ser fornecida pelo provedor hospedado, e só deve ser alterada se o provedor fizer uma mudança no FQDN do serviço de Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="12f7c-147">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="12f7c-148">**Nível de verificação padrão:**    A configuração padrão, **Permitir que os usuários se comuniquem somente com pessoas em suas listas de Contatos que usam este provedor**, limitará a comunicação aos contatos que foram aceitos e estão em sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="12f7c-148">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="12f7c-p106">Selecionar **Permitir que os usuários se comuniquem com todos que usam este provedor** remove a restrição de que você deve ter recebido e aceitado o convite de um contato. Esta configuração não limita quem pode entrar em contato com você a partir da rede do provedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="12f7c-p106">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="12f7c-151">Ao concluir a configuração das definições, clique em **Confirmar** para salvar ou em **Cancelar** para descartar as alterações.</span><span class="sxs-lookup"><span data-stu-id="12f7c-151">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>


## <a name="see-also"></a><span data-ttu-id="12f7c-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="12f7c-152">See Also</span></span>


[<span data-ttu-id="12f7c-153">Configurar políticas para controlar as acessos de usuário público</span><span class="sxs-lookup"><span data-stu-id="12f7c-153">Configure policies to control public user acces</span></span>](../external-access-policies/configure-policies-to-control-public-user-access.md)

[<span data-ttu-id="12f7c-154">Habilitar ou desabilitar federação e conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="12f7c-154">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)


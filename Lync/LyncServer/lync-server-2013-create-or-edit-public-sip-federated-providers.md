---
title: 'Lync Server 2013: Criar ou editar fornecedores SIP públicos federados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876a79e840990afb0c9cf0bae4fc819ec10db5d8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="253f0-102">Criar ou editar fornecedores SIP públicos federados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="253f0-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="253f0-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="253f0-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="253f0-104">A conectividade de mensagens instantâneas públicas permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com os usuários de serviços de mensagens instantâneas fornecidos por provedores de serviço de\!mensagens instantâneas públicos, incluindo Windows Live Messenger, Yahoo e AOL.</span><span class="sxs-lookup"><span data-stu-id="253f0-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="253f0-105">O Lync Server 2013 tem configurações de provedor público para o America Online, o Windows Live e o Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="253f0-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="253f0-106">mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="253f0-106">instant messaging.</span></span> <span data-ttu-id="253f0-107">Cada provedor público é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor, e o nível de verificação padrão **permite que os usuários se comuniquem somente com as pessoas da lista de contatos que usam esse provedor**.</span><span class="sxs-lookup"><span data-stu-id="253f0-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="253f0-108">Como uma configuração padrão, nenhum dos provedores públicos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="253f0-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="253f0-109">Você deve concluir o contrato de licença e o provisionamento do trabalho antes de habilitar os provedores públicos.</span><span class="sxs-lookup"><span data-stu-id="253f0-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="253f0-110">Você pode habilitar o provedor antes de concluir o trabalho de licenciamento e provisionamento.</span><span class="sxs-lookup"><span data-stu-id="253f0-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="253f0-111">Os usuários não poderão se comunicar com os contatos desses provedores até que o trabalho pré-requisito seja concluído.</span><span class="sxs-lookup"><span data-stu-id="253f0-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="253f0-112">Para obter detalhes sobre licenciamento e provisionamento de provedores públicos, consulte [Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="253f0-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="253f0-113">Use o procedimento a seguir para criar ou editar provedores públicos:</span><span class="sxs-lookup"><span data-stu-id="253f0-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="253f0-114">Para criar ou editar provedores públicos</span><span class="sxs-lookup"><span data-stu-id="253f0-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="253f0-115">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="253f0-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="253f0-116">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="253f0-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="253f0-117">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="253f0-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="253f0-118">Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **provedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="253f0-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="253f0-119">Se você precisar criar um novo provedor público, clique em **novo** e, em seguida, clique em **provedor público**.</span><span class="sxs-lookup"><span data-stu-id="253f0-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="253f0-120">Se precisar editar uma entrada da lista de provedores públicos, selecione um provedor público, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="253f0-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="253f0-121">Na página **Editar Provedor federado SIP** , você pode digitar ou editar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="253f0-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="253f0-122">**Habilitar comunicações com este provedor**   selecionar essa configuração habilita mensagens instantâneas com os usuários do provedor.</span><span class="sxs-lookup"><span data-stu-id="253f0-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="253f0-123">**Nome do provedor:**   uma propriedade necessária, digite o nome do provedor como ele será refletido na listagem de provedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="253f0-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="253f0-124">**Serviço de borda de acesso (FQDN):**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="253f0-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="253f0-125">Essas informações são fornecidas como um item padrão e só devem ser alteradas se o provedor público fizer uma alteração no FQDN do serviço de borda de acesso no provedor público.</span><span class="sxs-lookup"><span data-stu-id="253f0-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="253f0-126">**Nível de verificação padrão:**   a configuração padrão, **permitir que os usuários se comuniquem com as pessoas da lista de contatos que usam esse provedor** limitarão a comunicação com os contatos que você aceitou e estão na sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="253f0-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="253f0-127">Selecionar **permitir que os usuários se comuniquem com todos que usam esse provedor** remove a restrição que você deve ter recebido e aceito um convite de contato.</span><span class="sxs-lookup"><span data-stu-id="253f0-127">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="253f0-128">Esta configuração não limita quem pode contatá-lo na rede do provedor público.</span><span class="sxs-lookup"><span data-stu-id="253f0-128">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="253f0-129">Quando terminar de definir as configurações, clique em **confirmar** para salvar ou clique em **Cancelar** para descartar as alterações.</span><span class="sxs-lookup"><span data-stu-id="253f0-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="253f0-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="253f0-130">See Also</span></span>


[<span data-ttu-id="253f0-131">Configurar políticas para controlar o acesso de usuário público no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="253f0-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="253f0-132">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="253f0-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


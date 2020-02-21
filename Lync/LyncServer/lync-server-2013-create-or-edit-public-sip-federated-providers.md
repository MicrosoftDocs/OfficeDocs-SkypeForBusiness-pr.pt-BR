---
title: 'Lync Server 2013: criar ou editar provedores federados de SIP públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8a8da9937e31f0544dd93b1994745dc3a9eb10b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="1e9a6-102">Criar ou editar provedores federados SIP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e9a6-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e9a6-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1e9a6-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1e9a6-104">A conectividade de mensagens instantâneas (IM) pública permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores de serviço de\!im públicos, incluindo o Windows Live Messenger, o Yahoo e o AOL.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="1e9a6-105">Lync Server 2013 tem configurações de provedor público para America Online, Windows Live e Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="1e9a6-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="1e9a6-106">mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-106">instant messaging.</span></span> <span data-ttu-id="1e9a6-107">Cada provedor público é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor e o nível de verificação padrão **permite que os usuários se comuniquem somente com pessoas em suas listas de contatos que usam esse provedor**.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="1e9a6-108">Como configuração padrão, nenhum dos provedores públicos está habilitado.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="1e9a6-109">Você deve concluir o contrato de licença e o provisionamento de trabalho antes de habilitar os provedores públicos.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="1e9a6-110">Você pode habilitar o provedor antes de concluir o trabalho de licenciamento e provisionamento.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="1e9a6-111">Os usuários não conseguirão se comunicar com os contatos desses provedores até que o trabalho de pré-requisito seja concluído.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="1e9a6-112">Para obter detalhes sobre licenciamento e provisionamento de provedores públicos, consulte [Configure Policies to Control Public User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1e9a6-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="1e9a6-113">Use o procedimento a seguir para criar ou editar provedores públicos:</span><span class="sxs-lookup"><span data-stu-id="1e9a6-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="1e9a6-114">Para criar ou editar provedores públicos</span><span class="sxs-lookup"><span data-stu-id="1e9a6-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="1e9a6-115">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1e9a6-116">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1e9a6-117">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1e9a6-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1e9a6-118">Na barra de navegação à esquerda, clique em **Federação e Acesso Externo** e em **Provedores Federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="1e9a6-119">Se você precisar criar um novo provedor público, clique em **novo** e em **provedor público**.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="1e9a6-120">Se for necessário editar uma entrada da lista de provedores públicos, selecione um provedor público, clique em **Editar**e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="1e9a6-121">Na página **Editar Provedor Federado SIP**, você pode digitar ou editar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="1e9a6-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="1e9a6-122">**Habilitar comunicações com este provedor**   selecionar essa configuração habilita im com os usuários desse provedor.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="1e9a6-123">**Nome do provedor:**   uma propriedade obrigatória, digite o nome do provedor conforme ele será refletido na lista de provedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="1e9a6-124">**Serviço de borda de acesso (FQDN):**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="1e9a6-125">Essas informações são fornecidas como um item padrão e só devem ser alteradas se o provedor público fizer uma alteração no FQDN do serviço de borda de acesso no provedor público.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="1e9a6-126">**Nível de verificação padrão:**   a configuração padrão, **permitir que os usuários se comuniquem com pessoas em suas listas de contatos que usam este provedor** limitarão a comunicação aos contatos que você aceitou e estão em sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="1e9a6-127">Selecionar **Permitir que os usuários se comuniquem com todos que usam este provedor** remove a restrição de que você deve ter recebido e aceitado o convite de um contato.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-127">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="1e9a6-128">Essa configuração não limita quem pode contatá-lo da rede do provedor público.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-128">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="1e9a6-129">Ao concluir a configuração das definições, clique em **Confirmar** para salvar ou em **Cancelar** para descartar as alterações.</span><span class="sxs-lookup"><span data-stu-id="1e9a6-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e9a6-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="1e9a6-130">See Also</span></span>


[<span data-ttu-id="1e9a6-131">Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e9a6-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="1e9a6-132">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e9a6-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


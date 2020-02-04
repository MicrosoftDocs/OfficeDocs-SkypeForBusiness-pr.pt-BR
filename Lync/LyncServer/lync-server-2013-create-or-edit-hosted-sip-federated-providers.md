---
title: 'Lync Server 2013: Criar ou editar provedores hospedados federados SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6c97255ce1dc9fce00d9eca6f358f4c68e1ff8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="093aa-102">Criar ou editar provedores hospedados federados SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="093aa-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="093aa-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="093aa-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="093aa-104">A conectividade de mensagens instantâneas do provedor hospedado permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com os usuários de serviços de mensagens instantâneas fornecidos pelos provedores hospedados, incluindo o Microsoft Office 365 e o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="093aa-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including the Microsoft Office 365 and Lync Online.</span></span>

<span data-ttu-id="093aa-105">Cada provedor hospedado é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor, e o nível de verificação padrão **permite que os usuários se comuniquem somente com as pessoas da lista de contatos que usam esse provedor**.</span><span class="sxs-lookup"><span data-stu-id="093aa-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="093aa-106">Use o procedimento a seguir para criar ou editar provedores hospedados:</span><span class="sxs-lookup"><span data-stu-id="093aa-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="093aa-107">Para criar ou editar provedores hospedados</span><span class="sxs-lookup"><span data-stu-id="093aa-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="093aa-108">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="093aa-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="093aa-109">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="093aa-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="093aa-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="093aa-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="093aa-111">Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **provedores federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="093aa-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="093aa-112">Se você precisar criar um novo provedor hospedado, clique em **novo** e em **provedor hospedado**.</span><span class="sxs-lookup"><span data-stu-id="093aa-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="093aa-113">Se você precisar editar uma entrada da lista de provedores hospedados, selecione um provedor hospedado, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="093aa-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="093aa-114">Na página **Editar Provedor federado SIP** , você pode digitar ou editar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="093aa-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="093aa-115">**Habilitar comunicações com este provedor**   selecionar essa configuração permite a comunicação com os usuários do provedor.</span><span class="sxs-lookup"><span data-stu-id="093aa-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="093aa-116">**Nome do provedor:**   uma propriedade necessária, digite o nome do provedor como ele será refletido na listagem de provedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="093aa-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="093aa-117">**Serviço de borda de acesso (FQDN):**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor hospedado que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="093aa-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="093aa-118">Essas informações devem ser fornecidas pelo provedor de hospedagem e só devem ser alteradas se o provedor hospedado fizer uma alteração no FQDN do serviço de borda de acesso no provedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="093aa-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="093aa-119">**Nível de verificação padrão:**   a configuração padrão, **permitir que os usuários se comuniquem com as pessoas da lista de contatos que usam esse provedor** limitarão a comunicação com os contatos que você aceitou e estão na sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="093aa-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="093aa-120">Selecionar **permitir que os usuários se comuniquem com todos que usam esse provedor** remove a restrição que você deve ter recebido e aceito um convite de contato.</span><span class="sxs-lookup"><span data-stu-id="093aa-120">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="093aa-121">Essa configuração não limita quem pode contatá-lo na rede do provedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="093aa-121">This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="093aa-122">Quando terminar de definir as configurações, clique em **confirmar** para salvar ou clique em **Cancelar** para descartar as alterações.</span><span class="sxs-lookup"><span data-stu-id="093aa-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="093aa-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="093aa-123">See Also</span></span>


[<span data-ttu-id="093aa-124">Configurar políticas para controlar o acesso de usuário público no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="093aa-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="093aa-125">Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="093aa-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


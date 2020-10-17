---
title: 'Lync Server 2013: criar ou editar provedores federados SIP hospedados'
description: 'Lync Server 2013: crie ou edite provedores federados SIP hospedados.'
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
ms.openlocfilehash: aaaa1b29b9a85332b85dfb7a1f258503fa4e9c77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553877"
---
# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="73914-103">Criar ou editar provedores federados SIP hospedados Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73914-103">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73914-104">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="73914-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="73914-105">A conectividade de mensagens instantâneas do provedor hospedado permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores hospedados, incluindo o Microsoft 365 e o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="73914-105">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including Microsoft 365 and Lync Online.</span></span>

<span data-ttu-id="73914-106">Cada provedor hospedado é configurado com o nome de domínio totalmente qualificado do servidor de Borda do provedor e o nível de verificação padrão **Permitir que os usuários se comuniquem somente com pessoas em suas listas de Contatos que usam este provedor**.</span><span class="sxs-lookup"><span data-stu-id="73914-106">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="73914-107">Use o procedimento a seguir para criar ou editar provedores hospedados:</span><span class="sxs-lookup"><span data-stu-id="73914-107">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="73914-108">Para criar ou editar provedores hospedados</span><span class="sxs-lookup"><span data-stu-id="73914-108">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="73914-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="73914-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="73914-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73914-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="73914-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="73914-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="73914-112">Na barra de navegação à esquerda, clique em **Federação e Acesso Externo** e em **Provedores Federados SIP**.</span><span class="sxs-lookup"><span data-stu-id="73914-112">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="73914-113">Se for necessário criar um novo provedor hospedado, clique em **Novo** e em **Provedor hospedado**.</span><span class="sxs-lookup"><span data-stu-id="73914-113">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="73914-114">Se for necessário editar uma entrada da lista de provedores hospedados, selecione um provedor hospedado, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="73914-114">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="73914-115">Na página **Editar Provedor Federado SIP**, você pode digitar ou editar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="73914-115">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="73914-116">**Habilitar comunicações com este provedor**     A seleção dessa configuração permite a comunicação com os usuários desse provedor.</span><span class="sxs-lookup"><span data-stu-id="73914-116">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="73914-117">**Nome do provedor:**     Uma propriedade Required, digite o nome do provedor conforme ele será refletido na lista de provedores federados SIP.</span><span class="sxs-lookup"><span data-stu-id="73914-117">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="73914-118">**Serviço de borda de acesso (FQDN):**     Uma propriedade Required, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor hospedado que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="73914-118">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="73914-119">Esta informação deve ser fornecida pelo provedor hospedado, e só deve ser alterada se o provedor fizer uma mudança no FQDN do serviço de Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="73914-119">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="73914-120">**Nível de verificação padrão:**     A configuração padrão, **permitir que os usuários se comuniquem com pessoas em suas listas de contatos, que usam esse provedor** , limitarão a comunicação aos contatos que você aceitou e estão em sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="73914-120">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="73914-p103">Selecionar **Permitir que os usuários se comuniquem com todos que usam este provedor** remove a restrição de que você deve ter recebido e aceitado o convite de um contato. Esta configuração não limita quem pode entrar em contato com você a partir da rede do provedor hospedado.</span><span class="sxs-lookup"><span data-stu-id="73914-p103">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="73914-123">Ao concluir a configuração das definições, clique em **Confirmar** para salvar ou em **Cancelar** para descartar as alterações.</span><span class="sxs-lookup"><span data-stu-id="73914-123">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73914-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="73914-124">See Also</span></span>


[<span data-ttu-id="73914-125">Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73914-125">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="73914-126">Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73914-126">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


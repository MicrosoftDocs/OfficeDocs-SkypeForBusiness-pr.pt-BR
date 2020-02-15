---
title: 'Lync Server 2013: habilitar ou desabilitar a descoberta de parceiros de Federação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6fd924d4aef6a9a6657829fa225da9595f52fe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="cb306-102">Habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb306-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb306-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cb306-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cb306-p101">Na ocasião em que você implantou seus Servidores de Borda e habilitou a federação para a sua organização, deve ter especificado se haveria suporte para a descoberta automática de domínios parceiros federados. Use o procedimento deste tópico para alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="cb306-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cb306-106">O procedimento a seguir assume que você já habilitou a federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb306-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="cb306-107">Para obter detalhes sobre como habilitar a Federação, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A> na documentação de implantação ou na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="cb306-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="cb306-108">Para habilitar ou desabilitar a descoberta automática de domínios federados para a sua organização</span><span class="sxs-lookup"><span data-stu-id="cb306-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="cb306-109">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="cb306-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cb306-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cb306-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cb306-111">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cb306-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cb306-112">Na barra de navegação à esquerda, clique em **Acesso de Usuário Externo** e em **Configuração da Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="cb306-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="cb306-113">Na página **Configuração da Borda de Acesso**, clique em **Global**, **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="cb306-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cb306-114">Em **Editar Configuração da Borda de Acesso**, sob **Habilitar comunicações com usuários federados**, selecione ou desmarque a opção **Habilitar descoberta de domínios de parceiros** para habilitar ou desabilitar a descoberta automática de domínios de parceiros.</span><span class="sxs-lookup"><span data-stu-id="cb306-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="cb306-115">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="cb306-115">Click **Commit**.</span></span>

<span data-ttu-id="cb306-116">Para permitir que usuários federados colaborem com usuários na sua implantação do Lync Server, você também deve ter configurado pelo menos uma política de acesso externo para dar suporte ao acesso de usuários federados.</span><span class="sxs-lookup"><span data-stu-id="cb306-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="cb306-117">Para obter detalhes, consulte [habilitar ou desabilitar Federação e conectividade de im pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) na documentação de implantação ou na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="cb306-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="cb306-118">Para obter detalhes sobre como controlar o acesso para domínios federados específicos, consulte [Manage SIP Federated Domains for Your Organization in Lync server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP Federated Providers for Your Organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) e [Manage XMPP Federated Partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="cb306-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cb306-119">Habilitar ou desabilitar a descoberta de parceiros de Federação usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb306-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cb306-120">A descoberta de parceiros de Federação pode ser gerenciada usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cb306-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="cb306-121">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb306-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cb306-122">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="cb306-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="cb306-123">Para habilitar a descoberta de parceiros de Federação</span><span class="sxs-lookup"><span data-stu-id="cb306-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="cb306-p106">Para habilitar a descoberta de parceiros de federação, defina o valor da propriedade **EnablePartnerDiscovery** como Verdadeiro ($True). Observe que é necessário habilitar o roteamento DNS SRV para alterar o valor dessa propriedade.</span><span class="sxs-lookup"><span data-stu-id="cb306-p106">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True). Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="cb306-126">Para desabilitar a descoberta de parceiros de Federação</span><span class="sxs-lookup"><span data-stu-id="cb306-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="cb306-127">Para desabilitar a descoberta de parceiros de federação, defina o valor da propriedade **EnablePartnerDiscovery** como Falso ($False).</span><span class="sxs-lookup"><span data-stu-id="cb306-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Habilitar ou desabilitar descoberta de parceiros de federação
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: No momento em que você implantou seus servidores de borda e habilitou a Federação para a sua organização, você deve especificar se deseja dar suporte à descoberta automática de domínios de parceiro federado.
ms.openlocfilehash: a5569639cf870d2a5da16ef81aa733724a6701b3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280254"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="25767-103">Habilitar ou desabilitar a descoberta de parceiros de Federação no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="25767-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="25767-104">No momento em que você implantou seus servidores de borda e habilitou a Federação para a sua organização, você deve especificar se deseja dar suporte à descoberta automática de domínios de parceiro federado.</span><span class="sxs-lookup"><span data-stu-id="25767-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="25767-105">Use o procedimento deste tópico para alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="25767-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="25767-106">O procedimento a seguir pressupõe que você já habilitou a Federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="25767-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="25767-107">Para obter detalhes sobre como habilitar a Federação, consulte [habilitar ou desabilitar o acesso de usuários remotos](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="25767-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="25767-108">Para habilitar ou desabilitar a descoberta automática de domínios federados para a sua organização</span><span class="sxs-lookup"><span data-stu-id="25767-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="25767-109">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="25767-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="25767-110">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="25767-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="25767-111">Na barra de navegação à esquerda, clique em **acesso de usuário externo**, clique em **configuração de borda de acesso**.</span><span class="sxs-lookup"><span data-stu-id="25767-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="25767-112">Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="25767-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="25767-113">Em **Editar configuração de borda de acesso**, em **habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **habilitar descoberta de domínio parceiro** para habilitar ou desabilitar a descoberta automática de domínios de parceiros.</span><span class="sxs-lookup"><span data-stu-id="25767-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="25767-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="25767-114">Click **Commit**.</span></span>

<span data-ttu-id="25767-115">Para permitir que os usuários federados colaborem com usuários na implantação do Skype for Business Server, você também deve ter configurado pelo menos uma política de acesso externo para dar suporte ao acesso de usuários federados.</span><span class="sxs-lookup"><span data-stu-id="25767-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="25767-116">Para obter detalhes, consulte [habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="25767-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="25767-117">Para obter detalhes sobre o controle do acesso a domínios federados específicos, consulte [gerenciar domínios federados SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) e [gerenciar provedores federados SIP](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="25767-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="25767-118">Habilitar ou desabilitar a descoberta de parceiros de Federação usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="25767-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="25767-119">A descoberta de parceiros de Federação pode ser gerenciada usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="25767-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="25767-120">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25767-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="25767-121">Para habilitar a descoberta de parceiros de Federação</span><span class="sxs-lookup"><span data-stu-id="25767-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="25767-122">Para habilitar a descoberta de parceiros de Federação, defina o valor da propriedade **EnablePartnerDiscovery** como True ($true).</span><span class="sxs-lookup"><span data-stu-id="25767-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="25767-123">Observe que você deve habilitar o roteamento de SRV DNS para alterar esse valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="25767-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="25767-124">Para desabilitar a descoberta de parceiros de Federação</span><span class="sxs-lookup"><span data-stu-id="25767-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="25767-125">Para desabilitar a descoberta de parceiros de Federação, defina o valor da propriedade **EnablePartnerDiscovery** como False ($false):</span><span class="sxs-lookup"><span data-stu-id="25767-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False


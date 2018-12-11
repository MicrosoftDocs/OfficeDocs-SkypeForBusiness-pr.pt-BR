---
title: Habilitar ou desabilitar descoberta de parceiros de federação
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: No momento você implantado servidores de borda e habilitado a federação para sua organização, você deve especificou se deseja suportar a descoberta automática de domínios de parceiro federado.
ms.openlocfilehash: afa022ae1a52124c3dabaf788de8308ba9834227
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222846"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="74a31-103">Habilitar ou desabilitar a descoberta de parceiros de federação no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="74a31-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="74a31-104">No momento você implantado servidores de borda e habilitado a federação para sua organização, você deve especificou se deseja suportar a descoberta automática de domínios de parceiro federado.</span><span class="sxs-lookup"><span data-stu-id="74a31-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="74a31-105">Use o procedimento neste tópico para alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="74a31-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="74a31-106">O procedimento a seguir pressupõe que você já tiver habilitado a federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="74a31-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="74a31-107">Para obter detalhes sobre como habilitar a federação, consulte [Habilitar ou desabilitar o acesso de usuário remoto](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="74a31-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="74a31-108">Para habilitar ou desabilitar a descoberta automática de domínios federados para sua organização</span><span class="sxs-lookup"><span data-stu-id="74a31-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="74a31-109">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="74a31-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="74a31-110">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="74a31-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="74a31-111">Na barra de navegação à esquerda, clique em **Acesso de usuário externo**, clique em **Configuração de borda de acesso**.</span><span class="sxs-lookup"><span data-stu-id="74a31-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="74a31-112">Na página **Configuração de borda de acesso** , clique em **Global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="74a31-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="74a31-113">Em **Editar configuração de borda de acesso**, sob **Habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **Habilitar a descoberta de domínio do parceiro** para habilitar ou desabilitar a descoberta automática de domínios de parceiros.</span><span class="sxs-lookup"><span data-stu-id="74a31-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="74a31-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="74a31-114">Click **Commit**.</span></span>

<span data-ttu-id="74a31-115">Para habilitar os usuários federados colaborar com usuários em sua Skype para implantação Business Server, você também deve ter configurado pelo menos uma política de acesso externo para suportar o acesso de usuário federado.</span><span class="sxs-lookup"><span data-stu-id="74a31-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="74a31-116">Para obter detalhes, consulte [Habilitar ou desabilitar a federação e conectividade IM pública](enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="74a31-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="74a31-117">Para obter detalhes sobre como controlar o acesso de domínios federados específicos, consulte [Gerenciar SIP domínios federados](../sip-domains/manage-sip-federated-domains-for-your-organization.md) e [provedores federados de SIP de gerenciar](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="74a31-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="74a31-118">Habilitar ou desabilitar a descoberta de parceiros de Federação usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74a31-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="74a31-119">Descoberta de parceiros de Federação pode ser gerenciada usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="74a31-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="74a31-120">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74a31-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="74a31-121">Para habilitar a descoberta de parceiros de Federação</span><span class="sxs-lookup"><span data-stu-id="74a31-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="74a31-122">Para habilitar a descoberta de parceiros federados, defina o valor da propriedade **EnablePartnerDiscovery** como True ($True).</span><span class="sxs-lookup"><span data-stu-id="74a31-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="74a31-123">Observe que você deve habilitar o roteamento para alterar esse valor de propriedade de SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="74a31-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="74a31-124">Para desabilitar a descoberta de parceiros de Federação</span><span class="sxs-lookup"><span data-stu-id="74a31-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="74a31-125">Para desabilitar a descoberta de parceiros de federação, defina o valor da propriedade **EnablePartnerDiscovery** como falso ($False):</span><span class="sxs-lookup"><span data-stu-id="74a31-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False


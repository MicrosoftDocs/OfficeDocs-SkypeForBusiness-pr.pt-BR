---
title: Habilitar ou desabilitar descoberta de parceiros de federação
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: Na ocasião em que você implantou seus Servidores de Borda e habilitou a federação para a sua organização, deve ter especificado se haveria suporte para a descoberta automática de domínios parceiros federados.
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817421"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="f6a1b-103">Habilitar ou desabilitar a descoberta de parceiros de federação no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f6a1b-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="f6a1b-p101">Na ocasião em que você implantou seus Servidores de Borda e habilitou a federação para a sua organização, deve ter especificado se haveria suporte para a descoberta automática de domínios parceiros federados. Use o procedimento deste tópico para alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="f6a1b-106">O procedimento a seguir assume que você já habilitou a federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="f6a1b-107">Para obter detalhes sobre como habilitar a federação, [consulte Habilitar ou desabilitar o acesso de usuário remoto.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="f6a1b-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="f6a1b-108">Para habilitar ou desabilitar a descoberta automática de domínios federados para a sua organização</span><span class="sxs-lookup"><span data-stu-id="f6a1b-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="f6a1b-109">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6a1b-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="f6a1b-111">Na barra de navegação à esquerda, clique em **Acesso de Usuário Externo** e em **Configuração da Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f6a1b-112">Na página **Configuração da Borda de Acesso**, clique em **Global**, **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f6a1b-113">Em **Editar Configuração da Borda de Acesso**, sob **Habilitar comunicações com usuários federados**, selecione ou desmarque a opção **Habilitar descoberta de domínios de parceiros** para habilitar ou desabilitar a descoberta automática de domínios de parceiros.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="f6a1b-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-114">Click **Commit**.</span></span>

<span data-ttu-id="f6a1b-115">Para permitir que usuários federados colaborem com usuários em sua implantação do Skype for Business Server, você também deve ter configurado pelo menos uma política de acesso externo para suportar o acesso de usuário federado.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="f6a1b-116">Para obter detalhes, [consulte Habilitar ou desabilitar federação e conectividade de IM pública.](enable-or-disable-federation-and-public-im-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="f6a1b-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="f6a1b-117">Para obter detalhes sobre como controlar o acesso a domínios federados específicos, consulte [Gerenciar domínios sip federados](../sip-domains/manage-sip-federated-domains-for-your-organization.md) e gerenciar [provedores sip federados.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="f6a1b-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f6a1b-118">Habilitando ou desabilitando a descoberta de parceiros de federação usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6a1b-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f6a1b-119">A descoberta de parceiros de federação pode ser gerenciada usando o Windows PowerShell e o Set-CsAccessEdgeConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="f6a1b-120">Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="f6a1b-121">Para habilitar a descoberta de parceiros de federação</span><span class="sxs-lookup"><span data-stu-id="f6a1b-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="f6a1b-p105">Para habilitar a descoberta de parceiros de federação, defina o valor da propriedade **EnablePartnerDiscovery** como Verdadeiro ($True). Observe que é necessário habilitar o roteamento DNS SRV para alterar o valor dessa propriedade.</span><span class="sxs-lookup"><span data-stu-id="f6a1b-p105">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True). Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="f6a1b-124">Para desabilitar a descoberta de parceiros de federação</span><span class="sxs-lookup"><span data-stu-id="f6a1b-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="f6a1b-125">Para desabilitar a descoberta de parceiros de federação, defina o valor da propriedade **EnablePartnerDiscovery** como Falso ($False).</span><span class="sxs-lookup"><span data-stu-id="f6a1b-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False


---
title: Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
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
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817351"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="67a4b-102">Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="67a4b-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="67a4b-p101">No momento em que você implantou seus Servidores de Borda e habilitou a federação para a sua organização, deve ter especificado se enviaria automaticamente a isenção de arquivamento para parceiros federados. Se você arquiva comunicações externas, deverá habilitar o envio de uma isenção de arquivamento. Use o procedimento deste tópico para alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="67a4b-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners. If you archive external communications, you should enable the sending of an archiving disclaimer. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="67a4b-106">O procedimento a seguir assume que você já habilitou a federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="67a4b-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="67a4b-107">Para obter detalhes sobre como habilitar a federação, [consulte Habilitar ou desabilitar o acesso de usuário remoto.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="67a4b-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="67a4b-108">Para habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados</span><span class="sxs-lookup"><span data-stu-id="67a4b-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="67a4b-109">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="67a4b-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67a4b-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="67a4b-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="67a4b-111">Na barra de navegação esquerda, clique em **Acesso de Usuário Externo** e clique em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="67a4b-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="67a4b-112">Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="67a4b-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="67a4b-113">Em **Editar Configuração de Borda de Acesso**, em **Habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **Enviar aviso de isenção de responsabilidade de arquivamento para parceiros federados** para habilitar ou desabilitar o envio automático do aviso de isenção de responsabilidade de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="67a4b-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="67a4b-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="67a4b-114">Click **Commit**.</span></span>

<span data-ttu-id="67a4b-115">Para permitir que usuários federados colaborem com usuários em sua implantação do Skype for Business Server, você também deve ter configurado pelo menos uma política de acesso externo para suportar o acesso de usuário federado.</span><span class="sxs-lookup"><span data-stu-id="67a4b-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="67a4b-116">Para obter detalhes sobre como controlar o acesso para domínios federados específicos, consulte [Configurar o suporte para domínios externos permitidos.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="67a4b-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="67a4b-117">Habilitando ou desabilitando o aviso de isenção de responsabilidade de arquivamento usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67a4b-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="67a4b-118">O uso do aviso de isenção de responsabilidade de arquivamento pode ser gerenciado usando o Windows PowerShell e o Set-CsAccessEdgeConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67a4b-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="67a4b-119">Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67a4b-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="67a4b-120">Para habilitar o aviso de isenção de responsabilidade de arquivamento</span><span class="sxs-lookup"><span data-stu-id="67a4b-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="67a4b-121">Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para True ($True):</span><span class="sxs-lookup"><span data-stu-id="67a4b-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="67a4b-122">Para desabilitar o aviso de isenção de responsabilidade de arquivamento</span><span class="sxs-lookup"><span data-stu-id="67a4b-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="67a4b-123">Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para False ($False):</span><span class="sxs-lookup"><span data-stu-id="67a4b-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False



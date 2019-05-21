---
title: Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280212"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="6a498-102">Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a498-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="6a498-103">No momento em que você implantou seus servidores de borda e habilitou a Federação para a sua organização, você deve especificar se deseja enviar automaticamente a isenção de arquivo para parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="6a498-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="6a498-104">Se você arquivar comunicações externas, habilite o envio de uma isenção de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="6a498-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="6a498-105">Use o procedimento deste tópico para alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="6a498-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="6a498-106">O procedimento a seguir pressupõe que você já habilitou a Federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6a498-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="6a498-107">Para obter detalhes sobre como habilitar a Federação, consulte [habilitar ou desabilitar o acesso de usuários remotos](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="6a498-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="6a498-108">Para habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados</span><span class="sxs-lookup"><span data-stu-id="6a498-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="6a498-109">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="6a498-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6a498-110">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6a498-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="6a498-111">Na barra de navegação à esquerda, clique em **acesso de usuário externo**, clique em **configuração de borda de acesso**.</span><span class="sxs-lookup"><span data-stu-id="6a498-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="6a498-112">Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6a498-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6a498-113">Em **Editar configuração de borda de acesso**, em **habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **Enviar isenção de arquivamento para parceiros federados** para habilitar ou desabilitar o envio automático do arquivamento isenção.</span><span class="sxs-lookup"><span data-stu-id="6a498-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="6a498-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6a498-114">Click **Commit**.</span></span>

<span data-ttu-id="6a498-115">Para permitir que os usuários federados colaborem com usuários na implantação do Skype for Business Server, você também deve ter configurado pelo menos uma política de acesso externo para dar suporte ao acesso de usuários federados.</span><span class="sxs-lookup"><span data-stu-id="6a498-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="6a498-116">Para obter detalhes sobre o controle do acesso a domínios federados específicos, consulte [Configurar o suporte para domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="6a498-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6a498-117">Habilitar ou desabilitar o arquivamento de isenção de responsabilidade usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a498-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="6a498-118">O uso da isenção de responsabilidade de arquivamento pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6a498-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="6a498-119">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a498-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="6a498-120">Para habilitar a isenção de responsabilidade de arquivamento</span><span class="sxs-lookup"><span data-stu-id="6a498-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="6a498-121">Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Verdadeiro ($True):</span><span class="sxs-lookup"><span data-stu-id="6a498-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="6a498-122">Para desativar a isenção de responsabilidade de arquivamento</span><span class="sxs-lookup"><span data-stu-id="6a498-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="6a498-123">Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Falso ($False):</span><span class="sxs-lookup"><span data-stu-id="6a498-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False



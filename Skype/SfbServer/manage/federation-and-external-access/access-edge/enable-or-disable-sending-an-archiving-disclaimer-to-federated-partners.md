---
title: Habilitar ou desabilitar o envio de um aviso de isenção de responsabilidade de Arquivamento a parceiros federados
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 859b4e295a90fd44ce69efe4af7daa63ddc8812c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885316"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="03c47-102">Habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="03c47-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="03c47-103">No momento você implantado servidores de borda e habilitado a federação para sua organização, você deve especificou se é enviar automaticamente a isenção de responsabilidade de arquivamento para parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="03c47-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="03c47-104">Se você arquivar comunicações externas, você deve habilitar o envio de uma isenção de responsabilidade de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="03c47-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="03c47-105">Use o procedimento neste tópico para alterar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="03c47-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="03c47-106">O procedimento a seguir pressupõe que você já tiver habilitado a federação para sua organização.</span><span class="sxs-lookup"><span data-stu-id="03c47-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="03c47-107">Para obter detalhes sobre como habilitar a federação, consulte [Habilitar ou desabilitar o acesso de usuário remoto](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="03c47-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="03c47-108">Para habilitar ou desabilitar o envio de uma isenção de responsabilidade de arquivamento para parceiros federados</span><span class="sxs-lookup"><span data-stu-id="03c47-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="03c47-109">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="03c47-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03c47-110">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="03c47-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="03c47-111">Na barra de navegação à esquerda, clique em **Acesso de usuário externo**, clique em **Configuração de borda de acesso**.</span><span class="sxs-lookup"><span data-stu-id="03c47-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="03c47-112">Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="03c47-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="03c47-113">Em **Editar configuração de borda de acesso**, sob **Habilitar comunicações com usuários federados**, marque ou desmarque a caixa de seleção **Enviar aviso de isenção para parceiros federados de arquivamento** para habilitar ou desabilitar o envio automaticamente o arquivamento isenção de responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="03c47-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="03c47-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="03c47-114">Click **Commit**.</span></span>

<span data-ttu-id="03c47-115">Para habilitar os usuários federados colaborar com usuários em sua Skype para implantação Business Server, você também deve ter configurado pelo menos uma política de acesso externo para suportar o acesso de usuário federado.</span><span class="sxs-lookup"><span data-stu-id="03c47-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="03c47-116">Para obter detalhes sobre como controlar o acesso de domínios federados específicos, consulte [Configure suporte a domínios externos permitidos](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="03c47-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="03c47-117">Habilitar ou desabilitar a isenção de responsabilidade de arquivamento usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="03c47-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="03c47-118">O uso da isenção de responsabilidade de arquivamento pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="03c47-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="03c47-119">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03c47-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="03c47-120">Para habilitar a isenção de responsabilidade de arquivamento</span><span class="sxs-lookup"><span data-stu-id="03c47-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="03c47-121">Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Verdadeiro ($True):</span><span class="sxs-lookup"><span data-stu-id="03c47-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="03c47-122">Para desabilitar a isenção de responsabilidade de arquivamento</span><span class="sxs-lookup"><span data-stu-id="03c47-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="03c47-123">Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Falso ($False):</span><span class="sxs-lookup"><span data-stu-id="03c47-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False



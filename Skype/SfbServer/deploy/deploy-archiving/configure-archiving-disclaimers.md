---
title: Configurar avisos de isenção de responsabilidade de arquivamento para usuários externos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumo: Leia este tópico para saber como configurar um aviso de isenção de responsabilidade de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820661"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="9cc91-103">Configurar avisos de isenção de responsabilidade de arquivamento para usuários externos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9cc91-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="9cc91-104">**Resumo:** Leia este tópico para saber como configurar um aviso de isenção de responsabilidade de arquivamento para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9cc91-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="9cc91-105">Se sua organização se comunica com parceiros externos, você precisa informar a eles que está arquivando as comunicações com eles.</span><span class="sxs-lookup"><span data-stu-id="9cc91-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="9cc91-106">Ao implantar um Servidor de Borda e habilitar a federação para sua organização, você será perguntado se deseja enviar automaticamente um aviso de isenção de responsabilidade de arquivamento para parceiros externos.</span><span class="sxs-lookup"><span data-stu-id="9cc91-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="9cc91-107">Se você precisar alterar essa configuração, poderá usar o Painel de Controle do Skype for Business Server ou o cmdlet **Set-CsAccessEdgeConfiguration** do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cc91-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="9cc91-108">Os cmdlets podem ser executados a partir do shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cc91-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="9cc91-109">Para permitir que usuários externos colaborem com usuários em sua implantação do Skype for Business Server, você também deve configurar pelo menos uma política de acesso externo para suportar o acesso de usuários externos.</span><span class="sxs-lookup"><span data-stu-id="9cc91-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="9cc91-110">Para obter detalhes, consulte Gerenciar Parceiros Federados XMPP para Sua Organização.</span><span class="sxs-lookup"><span data-stu-id="9cc91-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="9cc91-111">Para obter detalhes sobre como controlar o acesso a domínios federados específicos, consulte Control Access by Individual Federated Domains.</span><span class="sxs-lookup"><span data-stu-id="9cc91-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="9cc91-112">Habilitar ou desabilitar o aviso de isenção de responsabilidade de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="9cc91-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="9cc91-113">Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9cc91-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9cc91-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9cc91-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9cc91-115">Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="9cc91-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="9cc91-116">Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9cc91-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9cc91-117">Em **Editar** Configuração de Borda de Acesso, em Habilitar federação e conectividade de **IM** pública, marque ou des limpe a caixa de seleção Enviar aviso de isenção de responsabilidade de arquivamento para parceiros **federados** para habilitar ou desabilitar o envio automático do aviso de isenção de responsabilidade de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="9cc91-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="9cc91-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9cc91-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="9cc91-119">Habilitar ou desabilitar o aviso de isenção de responsabilidade de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cc91-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="9cc91-120">Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para True ($True):</span><span class="sxs-lookup"><span data-stu-id="9cc91-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="9cc91-121">Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para False ($False):</span><span class="sxs-lookup"><span data-stu-id="9cc91-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```



---
title: Configurar avisos de isenção de arquivamento para usuários externos no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumo: Leia este tópico para saber como configurar uma isenção de responsabilidade de arquivamento do Skype para Business Server 2015.'
ms.openlocfilehash: 3790160024010084c69df7d9865f17622fca4f0d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server-2015"></a><span data-ttu-id="0dfe9-103">Configurar avisos de isenção de arquivamento para usuários externos no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0dfe9-103">Configure archiving disclaimers for external users in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0dfe9-104">**Resumo:** Leia este tópico para saber como configurar uma isenção de responsabilidade de arquivamento do Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0dfe9-105">Se a sua organização se comunica com parceiros externos, você precisa avisá-los de que está arquivando sua comunicação com eles.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="0dfe9-106">Quando você implanta um servidor de borda e habilitar a federação para sua organização, você será solicitado que se você deseja enviar automaticamente uma isenção de responsabilidade de arquivamento para parceiros externos.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="0dfe9-107">Se você precisar alterar essa configuração, você pode usar o Skype para painel de controle do Business Server ou o cmdlet do Windows PowerShell **Set-CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0dfe9-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="0dfe9-108">Cmdlets pode ser executados a partir do Skype do shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="0dfe9-109">Para permitir que usuários externos colaborar com usuários em sua Skype para implantação Business Server, você também deve configurar pelo menos uma política de acesso externo para suportar o acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="0dfe9-110">Para obter detalhes, consulte Manage XMPP Federated Partners for Your Organization.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="0dfe9-111">Para obter detalhes sobre como controlar o acesso para domínios federados específicos, consulte Controlar Acesso por Domínios Federados Individuais.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="0dfe9-112">Habilitar ou desabilitar um aviso de isenção de responsabilidade de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="0dfe9-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="0dfe9-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0dfe9-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0dfe9-115">Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="0dfe9-116">Na guia **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0dfe9-117">Em **Editar Configuração de Borda de Acesso**, em **Habilitar federação e conectividade de IM pública**, marque ou desmarque a caixa de seleção **Enviar aviso de isenção de responsabilidade de arquivamento para parceiros federados** para habilitar ou desabilitar o envio automático do aviso de isenção de responsabilidade de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="0dfe9-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0dfe9-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="0dfe9-119">Habilitar ou desabilitar um aviso de isenção de responsabilidade de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dfe9-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="0dfe9-120">Para habilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Verdadeiro ($True):</span><span class="sxs-lookup"><span data-stu-id="0dfe9-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="0dfe9-121">Para desabilitar a isenção de responsabilidade de arquivamento, defina o valor da propriedade **EnableArchivingDisclaimer** para Falso ($False):</span><span class="sxs-lookup"><span data-stu-id="0dfe9-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```



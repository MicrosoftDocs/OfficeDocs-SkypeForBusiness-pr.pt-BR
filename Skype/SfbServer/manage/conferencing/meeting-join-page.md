---
title: Configurar a reunião página de ingresso em Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumo: Saiba como configurar a reunião página de ingresso em Skype para Business Server.'
ms.openlocfilehash: 4f737bdab0586cb342d1271f348cf765ae093c5c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875543"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="eafa9-103">Configurar a reunião página de ingresso em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="eafa9-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="eafa9-104">**Resumo:** Saiba como configurar a reunião página de ingresso em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="eafa9-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="eafa9-105">Quando um usuário clica em um link da reunião em uma solicitação de reunião, a reunião página de ingresso detecta se um Skype para o cliente de negócios já está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="eafa9-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="eafa9-106">Se um cliente já estiver instalado, o cliente abre e participa da reunião.</span><span class="sxs-lookup"><span data-stu-id="eafa9-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="eafa9-107">Se um cliente não estiver instalado, por padrão o Skype para negócios cliente será aberta.</span><span class="sxs-lookup"><span data-stu-id="eafa9-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="eafa9-108">Configurar a página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="eafa9-108">Configure the meeting join page</span></span>

<span data-ttu-id="eafa9-109">Você pode modificar o comportamento de participação da reunião se você quiser permitir que os usuários ingressem em reuniões com outras versões do cliente de página.</span><span class="sxs-lookup"><span data-stu-id="eafa9-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="eafa9-110">Essas opções de configuração foram removidas do Skype para painel de controle do servidor de negócios, mas você pode configurá-los usando o cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="eafa9-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="eafa9-111">**Parâmetros de Set-CsWebServiceConfiguration página ingressar em reunião**</span><span class="sxs-lookup"><span data-stu-id="eafa9-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="eafa9-112">**Parâmetro Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="eafa9-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="eafa9-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="eafa9-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eafa9-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="eafa9-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="eafa9-115">Este parâmetro foi reduzido para uso com a versão local do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="eafa9-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="eafa9-116">Se definido como True, usuários participando de uma reunião usando um aplicativo cliente diferente do Skype para negócios receberá a oportunidade para ingressar na reunião usando o seu aplicativo atual do cliente.</span><span class="sxs-lookup"><span data-stu-id="eafa9-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="eafa9-117">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="eafa9-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="eafa9-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="eafa9-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="eafa9-119">Este parâmetro foi reduzido para uso com a versão local do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="eafa9-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="eafa9-120">Se definido como True, alternativo opções para ingressar em uma conferência online são expandidos automaticamente e mostrada para os usuários.</span><span class="sxs-lookup"><span data-stu-id="eafa9-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="eafa9-121">Se definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções para si próprios.</span><span class="sxs-lookup"><span data-stu-id="eafa9-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   


---
title: Configurar a página ingressar na reunião no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumo: saiba como configurar a página ingressar na reunião no Skype for Business Server.'
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818512"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="e58b4-103">Configurar a página ingressar na reunião no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e58b4-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="e58b4-104">**Resumo:** Saiba como configurar a página ingressar na reunião no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e58b4-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="e58b4-105">Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página ingressar na reunião detecta se um cliente Skype for Business já está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="e58b4-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="e58b4-106">Se um cliente já estiver instalado, o cliente abrirá e ingressará na reunião.</span><span class="sxs-lookup"><span data-stu-id="e58b4-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="e58b4-107">Se um cliente não estiver instalado, por padrão, o cliente Skype for Business será aberto.</span><span class="sxs-lookup"><span data-stu-id="e58b4-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="e58b4-108">Configurar a página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="e58b4-108">Configure the meeting join page</span></span>

<span data-ttu-id="e58b4-109">Você pode modificar o comportamento da página de associação de reunião se desejar permitir que os usuários ingressem em reuniões com outras versões do cliente.</span><span class="sxs-lookup"><span data-stu-id="e58b4-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="e58b4-110">Essas opções de configuração foram removidas do painel de controle do Skype for Business Server, mas você as configura usando o cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e58b4-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="e58b4-111">**Parâmetros do conjunto de páginas de associação de reunião-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="e58b4-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="e58b4-112">**Parâmetro Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="e58b4-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="e58b4-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e58b4-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e58b4-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="e58b4-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="e58b4-115">Esse parâmetro foi preterido para uso com a versão local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e58b4-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="e58b4-116">Se definido como true, os usuários que ingressam em uma reunião usando um aplicativo cliente diferente do Skype for Business terão a oportunidade de ingressar na reunião usando o aplicativo cliente atual.</span><span class="sxs-lookup"><span data-stu-id="e58b4-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="e58b4-117">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="e58b4-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="e58b4-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="e58b4-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="e58b4-119">Esse parâmetro foi preterido para uso com a versão local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e58b4-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="e58b4-120">Se definido como true, as opções alternativas para ingressar em uma conferência online serão automaticamente expandidas e exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="e58b4-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="e58b4-121">Se definido como falso (o valor padrão), essas opções estarão disponíveis, mas o usuário precisará exibir a lista de opções para si mesmo.</span><span class="sxs-lookup"><span data-stu-id="e58b4-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   


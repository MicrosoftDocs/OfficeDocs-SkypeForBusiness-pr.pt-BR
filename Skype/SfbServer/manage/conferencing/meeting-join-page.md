---
title: Configurar a página de junção de reunião no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Resumo: Saiba como configurar a página de junção de reunião no Skype for Business Server.'
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828031"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="66d83-103">Configurar a página de junção de reunião no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="66d83-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="66d83-104">**Resumo:** Saiba como configurar a página de junção de reunião no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="66d83-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="66d83-105">Quando um usuário clica em um link de reunião em uma solicitação de reunião, a página de entrada da reunião detecta se um cliente do Skype for Business já está instalado no computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="66d83-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="66d83-106">Se um cliente já estiver instalado, ele abre e participa da reunião.</span><span class="sxs-lookup"><span data-stu-id="66d83-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="66d83-107">Se um cliente não estiver instalado, por padrão, o cliente Skype for Business será aberto.</span><span class="sxs-lookup"><span data-stu-id="66d83-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="66d83-108">Configurar a página de ingresso na reunião</span><span class="sxs-lookup"><span data-stu-id="66d83-108">Configure the meeting join page</span></span>

<span data-ttu-id="66d83-109">Você pode modificar o comportamento da página de entrada da reunião se quiser permitir que os usuários participem de reuniões com outras versões do cliente.</span><span class="sxs-lookup"><span data-stu-id="66d83-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="66d83-110">Essas opções de configuração foram removidas do Painel de Controle do Skype for Business Server, mas você as configura usando o Set-CsWebServiceConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="66d83-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="66d83-111">**Parâmetros de página de Set-CsWebServiceConfiguration reunião**</span><span class="sxs-lookup"><span data-stu-id="66d83-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="66d83-112">**Parâmetro Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="66d83-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="66d83-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="66d83-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="66d83-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="66d83-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="66d83-115">Esse parâmetro foi preterido para uso com a versão local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="66d83-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="66d83-116">Se for definido como True, os usuários que ingressarem em uma reunião usando um aplicativo cliente diferente do Skype for Business terão a oportunidade de participar da reunião usando seu aplicativo cliente atual.</span><span class="sxs-lookup"><span data-stu-id="66d83-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="66d83-117">O valor padrão é False.</span><span class="sxs-lookup"><span data-stu-id="66d83-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="66d83-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="66d83-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="66d83-119">Esse parâmetro foi preterido para uso com a versão local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="66d83-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="66d83-120">Se for definido como True, as opções alternativas para ingressar em uma conferência online serão automaticamente expandidas e mostradas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="66d83-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="66d83-121">Se for definido como False (o valor padrão), essas opções estarão disponíveis, mas o usuário terá que exibir a lista de opções por conta própria.</span><span class="sxs-lookup"><span data-stu-id="66d83-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   


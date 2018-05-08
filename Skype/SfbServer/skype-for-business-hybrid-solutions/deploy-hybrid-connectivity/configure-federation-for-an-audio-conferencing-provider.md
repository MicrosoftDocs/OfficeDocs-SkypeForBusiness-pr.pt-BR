---
title: Configure a federação para um provedor de serviços de audioconferência em sua implantação híbrida
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
description: 'Resumo: Saiba como configurar a federação para um provedor de serviços de audioconferência no Skype para Business Online.'
ms.openlocfilehash: 95ca4e369e42bf265d243842067f531907e26531
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="4a89a-103">Configure a federação para um provedor de serviços de audioconferência em sua implantação híbrida</span><span class="sxs-lookup"><span data-stu-id="4a89a-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>
 
<span data-ttu-id="4a89a-104">**Resumo:** Saiba como configurar a federação para um provedor de serviços de audioconferência no Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="4a89a-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>
  
<span data-ttu-id="4a89a-105">Se você pretende usar um Provedor de Conferência de Áudio (ACP) em sua implantação híbrida (no local com online), será necessário configurar a federação entre sua implantação no local e o parceiro ACP como um Servidor Parceiro Permitido.</span><span class="sxs-lookup"><span data-stu-id="4a89a-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="4a89a-106">É possível configurar a federação adicionando o domínio do parceiro ACP e o servidor de Borda (também conhecido como Proxy de Acesso) à lista de Domínios de Federação para sua implantação no local.</span><span class="sxs-lookup"><span data-stu-id="4a89a-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="4a89a-107">Seu parceiro ACP precisará adicionar o FQDN de seu pool de Servidor de Borda no local à lista de domínios de federação permitidos.</span><span class="sxs-lookup"><span data-stu-id="4a89a-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="4a89a-108">Entre em contato com o provedor ACP para obter detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="4a89a-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="4a89a-109">Seu parceiro ACP precisará adicionar o FQDN de seu pool de Servidor de Borda no local à lista de domínios de federação permitidos.</span><span class="sxs-lookup"><span data-stu-id="4a89a-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>
  
- <span data-ttu-id="4a89a-110">**Adição do domínio ACP e do servidor de borda como um domínio federado permitido**</span><span class="sxs-lookup"><span data-stu-id="4a89a-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>
    
    <span data-ttu-id="4a89a-111">Para adicionar o domínio de ACP como um servidor de parceiro permitido (permitido domínio federado), siga as etapas em [Configurar suporte a domínios externos permitidos](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span><span class="sxs-lookup"><span data-stu-id="4a89a-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](http://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="4a89a-112">Para o servidor de borda, adicione o FQDN do servidor de borda do parceiro ACP.</span><span class="sxs-lookup"><span data-stu-id="4a89a-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="4a89a-113">Pode ser necessário entrar em contato com seu parceiro ACP para obter o FQDN do Servidor de Borda, que também pode ser mencionado pelo ACP como Proxy de Acesso.</span><span class="sxs-lookup"><span data-stu-id="4a89a-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>
    
- <span data-ttu-id="4a89a-114">**Forneça o FQDN do seu pool do servidor de borda ao parceiro ACP**</span><span class="sxs-lookup"><span data-stu-id="4a89a-114">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>
    
    <span data-ttu-id="4a89a-115">O parceiro ACP precisa configurar a federação para adicionar seu domínio no local como um Servidor Parceiro Permitido, adicionando o FQDN de seu pool de Servidor de Borda como um domínio de Federação permitido.</span><span class="sxs-lookup"><span data-stu-id="4a89a-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>
    


---
title: Configurar a Federação para um provedor de audioconferência em sua implantação híbrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Resumo: saiba como configurar a Federação para um provedor de conferência de áudio no Skype for Business online.'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160374"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="bac33-103">Configurar a Federação para um provedor de audioconferência em sua implantação híbrida</span><span class="sxs-lookup"><span data-stu-id="bac33-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="bac33-104">**Resumo:** Saiba como configurar a Federação para um provedor de conferência de áudio no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="bac33-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="bac33-105">Se quiser usar um provedor de serviços de audioconferência (ACP) em sua implantação híbrida (local com online), você precisará configurar a Federação entre sua implantação local e o parceiro ACP como um servidor parceiro permitido.</span><span class="sxs-lookup"><span data-stu-id="bac33-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="bac33-106">Você pode configurar a Federação adicionando o domínio de parceiro ACP e o servidor de borda (isso também pode ser chamado de proxy de acesso) à lista de domínios federados para sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="bac33-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="bac33-107">O parceiro ACP precisará adicionar o FQDN do pool de servidores de borda local à lista de domínios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="bac33-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="bac33-108">Entre em contato com seu provedor ACP para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="bac33-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="bac33-109">O parceiro ACP precisará adicionar o FQDN do pool de servidores de borda local à lista de domínios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="bac33-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="bac33-110">**Adicionar o domínio ACP e o servidor de borda como um domínio federado permitido**</span><span class="sxs-lookup"><span data-stu-id="bac33-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="bac33-111">Para adicionar o domínio ACP como um servidor parceiro permitido (domínio federado permitido), siga as etapas em [Configurar suporte para domínios externos permitidos](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span><span class="sxs-lookup"><span data-stu-id="bac33-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="bac33-112">Para o servidor de borda, adicione o FQDN do servidor de borda do parceiro ACP.</span><span class="sxs-lookup"><span data-stu-id="bac33-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="bac33-113">Talvez seja necessário entrar em contato com seu parceiro ACP para obter o FQDN do servidor de borda, que também pode ser mencionado pelo ACP como proxy de acesso.</span><span class="sxs-lookup"><span data-stu-id="bac33-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="bac33-114">**Fornecer o FQDN do pool do servidor de borda ao parceiro ACP**</span><span class="sxs-lookup"><span data-stu-id="bac33-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="bac33-115">O parceiro ACP precisa configurar a Federação para adicionar seu domínio local como um servidor parceiro permitido adicionando o FQDN do seu pool de servidor de borda como um domínio federado permitido.</span><span class="sxs-lookup"><span data-stu-id="bac33-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>



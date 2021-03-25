---
title: Configurar federação para um provedor de audioconferência em sua implantação híbrida
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
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
description: 'Resumo: saiba como configurar a federação para um provedor de audioconferência no Skype for Business Online.'
ms.openlocfilehash: 5d9c49299452f579cd7c58adf54facb09f0b8a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118970"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="f17bf-103">Configurar federação para um provedor de audioconferência em sua implantação híbrida</span><span class="sxs-lookup"><span data-stu-id="f17bf-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="f17bf-104">**Resumo:** Saiba como configurar a federação para um provedor de audioconferência no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="f17bf-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="f17bf-105">Se você quiser usar um Provedor de Audioconferência (ACP) em sua implantação híbrida (local com online), você precisará configurar a federação entre sua implantação local e o parceiro ACP como um Servidor parceiro permitido.</span><span class="sxs-lookup"><span data-stu-id="f17bf-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="f17bf-106">Você pode configurar a federação adicionando o domínio do parceiro ACP e o servidor de Borda (isso também pode ser chamado de Proxy de Acesso) à lista Domínios Federados para sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="f17bf-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="f17bf-107">Em seguida, seu parceiro ACP precisa adicionar o FQDN do pool de Servidor de Borda local à lista de domínios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="f17bf-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="f17bf-108">Entre em contato com seu provedor ACP para obter detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="f17bf-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="f17bf-109">Em seguida, seu parceiro ACP precisa adicionar o FQDN do pool de Servidor de Borda local à lista de domínios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="f17bf-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="f17bf-110">**Adicionando o Domínio ACP e o Servidor de Borda como um Domínio Federado Permitido**</span><span class="sxs-lookup"><span data-stu-id="f17bf-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="f17bf-111">Para adicionar o domínio ACP como um Servidor parceiro permitido (domínio federado permitido), siga as etapas em [Configure Support for Allowed External Domains](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains).</span><span class="sxs-lookup"><span data-stu-id="f17bf-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains).</span></span> <span data-ttu-id="f17bf-112">Para o Servidor de Borda, adicione o FQDN do Servidor de Borda do parceiro ACP.</span><span class="sxs-lookup"><span data-stu-id="f17bf-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="f17bf-113">Talvez seja necessário entrar em contato com seu parceiro ACP para obter o FQDN para seu Servidor de Borda, que também pode ser chamado pelo seu ACP como Proxy de Acesso.</span><span class="sxs-lookup"><span data-stu-id="f17bf-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="f17bf-114">**Fornecendo o FQDN do pool de servidores de borda para o parceiro ACP**</span><span class="sxs-lookup"><span data-stu-id="f17bf-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="f17bf-115">O parceiro ACP precisa configurar a federação para adicionar seu domínio local como um Servidor parceiro permitido adicionando o FQDN do pool do Servidor de Borda como um domínio federado permitido.</span><span class="sxs-lookup"><span data-stu-id="f17bf-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>
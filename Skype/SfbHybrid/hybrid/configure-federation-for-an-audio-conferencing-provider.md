---
title: Configurar federação para um provedor de serviços de audioconferência em sua implantação híbrida
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
description: 'Resumo: saiba como configurar a federação para um provedor de serviços de audioconferência no Skype for Business Online.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726881"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="05d81-103">Configurar federação para um provedor de serviços de audioconferência em sua implantação híbrida</span><span class="sxs-lookup"><span data-stu-id="05d81-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="05d81-104">**Resumo:** Saiba como configurar a federação para um provedor de serviços de audioconferência no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="05d81-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="05d81-105">Se você quiser usar um Provedor de Audioconferência (ACP) em sua implantação híbrida (local com online), será necessário configurar a federação entre sua implantação local e o parceiro ACP como um Servidor parceiro permitido.</span><span class="sxs-lookup"><span data-stu-id="05d81-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="05d81-106">Você pode configurar a federação adicionando o domínio do parceiro ACP e o servidor de Borda (isso também pode ser chamado de Proxy de Acesso) à lista de Domínios Federados para sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="05d81-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="05d81-107">Seu parceiro ACP precisa adicionar o FQDN do pool do Servidor de Borda local à lista de domínios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="05d81-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="05d81-108">Entre em contato com seu provedor ACP para obter detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="05d81-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="05d81-109">Seu parceiro ACP precisa adicionar o FQDN do pool do Servidor de Borda local à lista de domínios federados permitidos.</span><span class="sxs-lookup"><span data-stu-id="05d81-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="05d81-110">**Adicionando o domínio ACP e o servidor de borda como um domínio federado permitido**</span><span class="sxs-lookup"><span data-stu-id="05d81-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="05d81-111">Para adicionar o domínio ACP como um Servidor parceiro permitido (domínio federado permitido), siga as etapas em Configurar Suporte [para Domínios Externos Permitidos.](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)</span><span class="sxs-lookup"><span data-stu-id="05d81-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="05d81-112">Para o Servidor de Borda, adicione o FQDN do Servidor de Borda do parceiro ACP.</span><span class="sxs-lookup"><span data-stu-id="05d81-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="05d81-113">Talvez seja necessário entrar em contato com seu parceiro ACP para obter o FQDN do Servidor de Borda, que também pode ser chamado pelo seu ACP como Proxy de Acesso.</span><span class="sxs-lookup"><span data-stu-id="05d81-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="05d81-114">**Fornecendo o FQDN do seu Pool de Servidores de Borda para o parceiro ACP**</span><span class="sxs-lookup"><span data-stu-id="05d81-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="05d81-115">O parceiro ACP precisa configurar a federação para adicionar seu domínio local como um Servidor parceiro permitido adicionando o FQDN do seu pool de Servidores de Borda como um domínio federado permitido.</span><span class="sxs-lookup"><span data-stu-id="05d81-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>



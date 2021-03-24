---
title: Solucionar problemas de conectividade com o cliente do Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Solucione problemas de conectividade do cliente Microsoft Teams causados principalmente pelo firewall ou pela conexão do proxy, e saiba como corrigi-los.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 25a4fc51e0bb8dec810ce921e3678a529ee7a4cf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101157"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="7164d-103">Solucionar problemas de conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7164d-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="7164d-104">A maioria dos problemas descobertos com o cliente Microsoft Teams pode ser remetida para o firewall ou para a conectividade do proxy.</span><span class="sxs-lookup"><span data-stu-id="7164d-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="7164d-105">Verificar se as URLs, os endereços IP e as portas necessárias estão abertas no seu firewall ou no seu proxy minimizará uma resolução de problemas desnecessária.</span><span class="sxs-lookup"><span data-stu-id="7164d-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="7164d-106">Para obter informações específicas sobre URLs e IPs necessárias para o Microsoft Teams, consulte o artigo de suporte a URLs e endereço IP do [Microsoft 365 e office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="7164d-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="7164d-107">Os cenários a seguir exigem que portas e URLs específicas sejam abertas no firewall.</span><span class="sxs-lookup"><span data-stu-id="7164d-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="7164d-108">Autenticação</span><span class="sxs-lookup"><span data-stu-id="7164d-108">Authentication</span></span>

- <span data-ttu-id="7164d-109">Conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7164d-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="7164d-110">Colaboração</span><span class="sxs-lookup"><span data-stu-id="7164d-110">Collaboration</span></span>

- <span data-ttu-id="7164d-111">Mídia</span><span class="sxs-lookup"><span data-stu-id="7164d-111">Media</span></span>

- <span data-ttu-id="7164d-112">Serviços Compartilhados</span><span class="sxs-lookup"><span data-stu-id="7164d-112">Shared Services</span></span>

- <span data-ttu-id="7164d-113">Integração de terceiros</span><span class="sxs-lookup"><span data-stu-id="7164d-113">Third Party Integration</span></span>

- <span data-ttu-id="7164d-114">Interoperabilidade do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7164d-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="7164d-115">Interoperabilidade do cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7164d-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="7164d-116">Quando o Teams está offline ou em condições de baixa largura de banda</span><span class="sxs-lookup"><span data-stu-id="7164d-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="7164d-117">A boa notícia é que o Teams continua em execução mesmo quando você está offline ou em condições de baixa largura de banda.</span><span class="sxs-lookup"><span data-stu-id="7164d-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="7164d-118">O Teams salva todas as mensagens não enviadas para chats existentes (por até 24 horas) e as envia assim que você estiver online novamente.</span><span class="sxs-lookup"><span data-stu-id="7164d-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="7164d-119">Se você estiver offline por mais de 24 horas, o Teams permitirá que você escolha re-enviar ou excluir mensagens não enviadas.</span><span class="sxs-lookup"><span data-stu-id="7164d-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="7164d-120">Estamos trabalhando para adicionar essa funcionalidade a novos chats e atualizaremos essa documentação quando estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="7164d-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7164d-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7164d-121">Related topics</span></span>

[<span data-ttu-id="7164d-122">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="7164d-122">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
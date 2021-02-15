---
title: Solucionar problemas de conectividade com o cliente teams
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
ms.openlocfilehash: 59041734887a667eca325a3d2650425d6d336b78
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918537"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="48fd2-103">Solucionar problemas de conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48fd2-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="48fd2-104">A maioria dos problemas descobertos com o cliente Microsoft Teams pode ser remetida para o firewall ou para a conectividade do proxy.</span><span class="sxs-lookup"><span data-stu-id="48fd2-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="48fd2-105">Verificar se as URLs, os endereços IP e as portas necessárias estão abertas no seu firewall ou no seu proxy minimizará uma resolução de problemas desnecessária.</span><span class="sxs-lookup"><span data-stu-id="48fd2-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="48fd2-106">Para obter informações específicas sobre URLs e IPs necessárias para o Microsoft Teams, consulte o artigo de suporte a URLs e endereço IP do Microsoft 365 e do [Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="48fd2-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="48fd2-107">Os cenários a seguir exigem que portas e URLs específicas sejam abertas no firewall.</span><span class="sxs-lookup"><span data-stu-id="48fd2-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="48fd2-108">Autenticação</span><span class="sxs-lookup"><span data-stu-id="48fd2-108">Authentication</span></span>

- <span data-ttu-id="48fd2-109">Conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48fd2-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="48fd2-110">Colaboração</span><span class="sxs-lookup"><span data-stu-id="48fd2-110">Collaboration</span></span>

- <span data-ttu-id="48fd2-111">Mídia</span><span class="sxs-lookup"><span data-stu-id="48fd2-111">Media</span></span>

- <span data-ttu-id="48fd2-112">Serviços Compartilhados</span><span class="sxs-lookup"><span data-stu-id="48fd2-112">Shared Services</span></span>

- <span data-ttu-id="48fd2-113">Integração de terceiros</span><span class="sxs-lookup"><span data-stu-id="48fd2-113">Third Party Integration</span></span>

- <span data-ttu-id="48fd2-114">Interoperabilidade do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="48fd2-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="48fd2-115">Interoperabilidade do cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="48fd2-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="48fd2-116">Quando o Teams está offline ou em condições de pouca largura de banda</span><span class="sxs-lookup"><span data-stu-id="48fd2-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="48fd2-117">A boa notícia é que o Teams continua em execução mesmo quando você está offline ou em condições de baixa largura de banda.</span><span class="sxs-lookup"><span data-stu-id="48fd2-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="48fd2-118">O Teams salva todas as suas mensagens não enviadas para chats existentes (por até 24 horas) e as envia assim que você estiver online novamente.</span><span class="sxs-lookup"><span data-stu-id="48fd2-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="48fd2-119">Se você estiver offline por mais de 24 horas, o Teams permitirá que você opte por reendê-los ou excluir mensagens não enviadas.</span><span class="sxs-lookup"><span data-stu-id="48fd2-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="48fd2-120">Estamos trabalhando para adicionar essa funcionalidade a novos chats e atualizaremos essa documentação quando isso estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="48fd2-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="48fd2-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="48fd2-121">Related topics</span></span>

[<span data-ttu-id="48fd2-122">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="48fd2-122">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

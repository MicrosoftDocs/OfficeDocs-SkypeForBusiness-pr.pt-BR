---
title: Verificar o acesso remoto e de federação para usuários externos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após a transição da rota de Federação para o servidor de borda do Skype for Business Server 2019, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado. Os testes de acesso de usuário externo devem incluir cada tipo de usuário externo compatível com a sua organização, incluindo qualquer um ou todos os itens a seguir.
ms.openlocfilehash: a07cbfc8596cfd49760af1fcee7df90eca362229
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292169"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="66de1-104">Verificar o acesso remoto e de federação para usuários externos</span><span class="sxs-lookup"><span data-stu-id="66de1-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="66de1-105">Após a transição da rota de Federação para o servidor de borda do Skype for Business Server 2019, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="66de1-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="66de1-106">Os testes de acesso de usuário externo devem incluir cada tipo de usuário externo compatível com a sua organização, incluindo qualquer um ou todos os itens a seguir.</span><span class="sxs-lookup"><span data-stu-id="66de1-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="66de1-107">Testar a conectividade de usuários externos e acesso externo</span><span class="sxs-lookup"><span data-stu-id="66de1-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="66de1-108">Usuários de pelo menos um domínio federado, um usuário interno do Skype for Business Server 2019 e um usuário na instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="66de1-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="66de1-109">Testar mensagens instantâneas (IM), presença, áudio/vídeo (A/V) e compartilhamento da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="66de1-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="66de1-110">Os usuários de cada provedor de serviço de mensagens de chat público compatível com a sua organização (e para a qual o provisionamento foi concluído) se comunicando com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="66de1-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="66de1-111">Verifique se usuários anônimos podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="66de1-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="66de1-112">Um usuário hospedado na instalação herdada usando o acesso de usuário remoto (registro em log eu sou Lync Server/Skype for Business de fora da intranet, mas sem VPN) com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="66de1-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="66de1-113">Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="66de1-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="66de1-114">Um usuário hospedado no Skype for Business Server 2019 usando acesso de usuário remoto (conectando-se ao Skype for Business Server 2019 de fora da intranet, mas sem VPN), com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="66de1-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="66de1-115">Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="66de1-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    


---
title: Verificar o acesso remoto e de federação para usuários externos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após a transição da rota de federação para o Skype para o servidor de borda de 2019 Business Server, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado. Testes de acesso de usuário externo devem incluir a cada tipo de usuário externo que sua organização suporta, incluindo qualquer um ou todos os itens a seguir.
ms.openlocfilehash: 3a520b39d76ab93f4ec7fcaacd139b3f83a3326a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876694"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="9f3ce-104">Verificar o acesso remoto e de federação para usuários externos</span><span class="sxs-lookup"><span data-stu-id="9f3ce-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="9f3ce-105">Após a transição da rota de federação para o Skype para o servidor de borda de 2019 Business Server, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="9f3ce-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="9f3ce-106">Testes de acesso de usuário externo devem incluir a cada tipo de usuário externo que sua organização suporta, incluindo qualquer um ou todos os itens a seguir.</span><span class="sxs-lookup"><span data-stu-id="9f3ce-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="9f3ce-107">Testar a conectividade de usuários externos e acesso externo</span><span class="sxs-lookup"><span data-stu-id="9f3ce-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="9f3ce-108">Os usuários de pelo menos um domínio federado, um usuário interno no Skype para Business Server 2019 e um usuário no antigo instalar.</span><span class="sxs-lookup"><span data-stu-id="9f3ce-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="9f3ce-109">Testar mensagens instantâneas (IM), presença, áudio/vídeo (A / V) e o compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9f3ce-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="9f3ce-110">Os usuários de cada provedor de serviços IM públicos que ofereçam suporte à sua empresa (e para o qual o provisionamento esteja concluído) se comunicando com um usuário no Skype para Business Server 2019 e um usuário na instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="9f3ce-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="9f3ce-111">Verifique se usuários anônimos podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="9f3ce-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="9f3ce-112">Instalar de um usuário hospedado no antigo usando o acesso de usuário remoto (log i nPara Lync Server/Skype para negócios de fora da intranet, mas sem VPN) com um usuário no Skype para Business Server 2019 e um usuário na instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="9f3ce-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="9f3ce-113">Teste de IM, presença, A / V e área de trabalho de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="9f3ce-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="9f3ce-114">Um usuário hospedado no Skype para Business Server 2019 usando o acesso de usuário remoto (fazer logon no Skype para negócios 2019 de servidor de fora da intranet, mas sem VPN) com um usuário do Skype para Business Server 2019 e um usuário na instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="9f3ce-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="9f3ce-115">Teste de IM, presença, A / V e área de trabalho de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="9f3ce-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    


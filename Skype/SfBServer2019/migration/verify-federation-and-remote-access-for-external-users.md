---
title: Verifique o acesso remoto e de federação para usuários externos
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Após a transição da rota de Federação para o servidor de borda do Skype for Business Server 2019, você deve executar alguns testes funcionais para verificar se a Federação é executada conforme o esperado. Os testes de acesso do usuários externo devem incluir qualquer tipo de usuário externo suportado pela sua organização, incluindo qualquer um ou todos os seguintes.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751663"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="d112d-104">Verifique o acesso remoto e de federação para usuários externos</span><span class="sxs-lookup"><span data-stu-id="d112d-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="d112d-105">Após a transição da rota de Federação para o servidor de borda do Skype for Business Server 2019, você deve executar alguns testes funcionais para verificar se a Federação é executada conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="d112d-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="d112d-106">Os testes de acesso do usuários externo devem incluir qualquer tipo de usuário externo suportado pela sua organização, incluindo qualquer um ou todos os seguintes.</span><span class="sxs-lookup"><span data-stu-id="d112d-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="d112d-107">Testar a conectividade de usuários externos e acesso externo</span><span class="sxs-lookup"><span data-stu-id="d112d-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="d112d-108">Usuários de pelo menos um domínio federado, um usuário interno no Skype for Business Server 2019 e um usuário na instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="d112d-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="d112d-109">Teste as mensagens instantâneas (IM), presença, áudio/vídeo (A / V) e o compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d112d-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="d112d-110">Os usuários de cada provedor de serviços públicos de IM que sua organização suporta (e para o qual o provisionamento foi concluído) comunicando-se com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="d112d-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="d112d-111">Verifique se usuários anônimos podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="d112d-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="d112d-112">Um usuário hospedado na instalação herdada usando acesso de usuário remoto (registro em log eu sou o Lync Server/Skype for Business de fora da intranet, mas sem VPN) com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="d112d-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="d112d-113">Testar a IM, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d112d-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="d112d-114">Um usuário hospedado no Skype for Business Server 2019 usando o acesso de usuário remoto (fazendo logon no Skype for Business Server 2019 de fora da intranet, mas sem VPN) com um usuário no Skype for Business Server 2019, e um usuário na instalação herdada.</span><span class="sxs-lookup"><span data-stu-id="d112d-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="d112d-115">Testar a IM, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d112d-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    


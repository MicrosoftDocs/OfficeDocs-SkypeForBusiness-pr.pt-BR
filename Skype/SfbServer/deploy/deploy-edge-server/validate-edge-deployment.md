---
title: Validar sua implantação de Borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumo: Saiba como verificar se a implantação do Servidor de Borda ou pool de Servidores de Borda está funcionando no Skype for Business Server.'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804351"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="c1f9e-103">Validar sua implantação de Borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1f9e-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="c1f9e-104">**Resumo:** Saiba como verificar se a implantação do Servidor de Borda ou pool de Servidores de Borda está funcionando no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="c1f9e-105">Depois de ter implantado seu Servidor de Borda ou pool de Servidores de Borda, você precisará saber se ele está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="c1f9e-106">Aqui estão algumas coisas que podem ajudar na confirmação de que seu ambiente de Borda está conectado aos seus servidores internos e também que seus usuários externos podem se conectar ao seu ambiente do Skype for Business Server por meio de sua Borda.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="c1f9e-107">Verificar a conectividade entre os servidores internos e os servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="c1f9e-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="c1f9e-108">Embora a validação da conectividade seja feita automaticamente no Servidor de Borda ou no pool do Servidor de Borda quando os Servidores de Borda são instalados, você ainda pode confirmar isso por conta própria com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="c1f9e-109">Execute o cmdlet Get-CsManagementStoreReplicationStatus no servidor interno que tem o armazenamento de Gerenciamento Central ou em qualquer computador ingressado no domínio no qual os Componentes Principais do Skype for Business Server (OcsCore.msi) estão instalados.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="c1f9e-110">O resultado inicial da execução deste comando pode dar um status False, em vez de True, para replicação.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="c1f9e-111">Se isso acontecer, execute o Invoke-CsManagementStoreReplication cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="c1f9e-112">Dê algum tempo para concluir a replicação e execute o cmdlet Get-CsManagementStoreReplicationStatus novamente.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="c1f9e-113">Verificar a conectividade de seus usuários externos</span><span class="sxs-lookup"><span data-stu-id="c1f9e-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="c1f9e-114">Temos uma ótima ferramenta para confirmar sua configuração do Servidor de Borda e a capacidade de se conectar, enviar e receber as mensagens corretas para cenários do Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="c1f9e-115">É o site [De análogo de Conectividade Remota.](https://testconnectivity.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="c1f9e-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="c1f9e-116">Este é um site gerenciado e mantido pelo Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="c1f9e-117">Para usar essa ferramenta, navegue até o site e siga as instruções para escolher o cenário certo para você.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="c1f9e-118">Itens a considerar ao testar a conectividade do usuário externo</span><span class="sxs-lookup"><span data-stu-id="c1f9e-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="c1f9e-119">Qualquer teste de acesso de usuário externo precisa incluir cada tipo de usuário interno compatível com sua organização, o que pode incluir qualquer um ou todos os seguintes:</span><span class="sxs-lookup"><span data-stu-id="c1f9e-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="c1f9e-120">Os usuários de pelo menos um domínio federado (recomendamos testá-los todos).</span><span class="sxs-lookup"><span data-stu-id="c1f9e-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="c1f9e-121">Usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-121">Anonymous users.</span></span>
    
- <span data-ttu-id="c1f9e-122">Usuários em sua organização que estão conectados ao Skype for Business remotamente, mas não estão usando VPN.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="c1f9e-123">Esses testes determinarão se o Servidor de Borda é:</span><span class="sxs-lookup"><span data-stu-id="c1f9e-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="c1f9e-124">Escuta as portas necessárias usando um cliente telnet de fora da rede.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="c1f9e-125">Por exemplo: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="c1f9e-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="c1f9e-126">Você deve realizar o teste anterior nas portas que está usando no seu Servidor de Borda ou pool de Servidores de Borda, dependendo da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="c1f9e-127">Executa a resolução DNS externa precisa.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="c1f9e-128">De fora da rede, ping em cada um dos FQDNs externos do seu Servidor de Borda ou pool de Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="c1f9e-129">Mesmo que o ping falhe, você verá os endereços IP, que podem ser comparados aos endereços IP atribuídos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c1f9e-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    


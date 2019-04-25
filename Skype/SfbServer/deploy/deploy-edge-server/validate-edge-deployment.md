---
title: Validar sua implantação de borda no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Resumo: Saiba como verificar se sua implantação do servidor de borda ou pool de servidor de borda está funcionando no Skype para Business Server.'
ms.openlocfilehash: 63c4cb1af599da191d0e0f4b95cfdaa775a64ba4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223786"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="29afe-103">Validar sua implantação de borda no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="29afe-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="29afe-104">**Resumo:** Saiba como verificar se sua implantação do servidor de borda ou pool de servidor de borda está funcionando no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="29afe-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="29afe-105">Depois que você implantou o servidor de borda ou pool de servidor de borda, você precisa saber se ela está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="29afe-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="29afe-106">Aqui estão algumas coisas que possa ajudar com confirmando seu ambiente de borda está conectada por seus servidores internos e também que os usuários externos podem se conectam ao seu Skype para ambiente de servidor de negócios por meio de sua borda.</span><span class="sxs-lookup"><span data-stu-id="29afe-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="29afe-107">Verificar conectividade entre seus servidores internos e seus servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="29afe-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="29afe-108">Enquanto a validação de conectividade é feita automaticamente no servidor de borda ou pool de servidores de borda quando os servidores de borda estão instalados, você pode confirmar isso para si mesmo ainda com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29afe-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="29afe-109">Execute o cmdlet Get-CsManagementStoreReplicationStatus no servidor interno que tem gerenciamento Central armazenar ou qualquer computador que ingressou domínio no qual Skype para componentes de principais (ocscore. msi) do Business Server estão instaladas.</span><span class="sxs-lookup"><span data-stu-id="29afe-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="29afe-p103">O resultado inicial da execução deste comando pode mostrar um status Falso, em vez de Verdadeiro, para a replicação. Caso isso ocorra, execute o cmdlet Invoke-CsManagementStoreReplication. Aguarde até ele concluir a replicação e depois execute o cmdlet Get-CsManagementStoreReplicationStatus novamente.</span><span class="sxs-lookup"><span data-stu-id="29afe-p103">The initial result of running this command may give a False status, rather than True, for replication. If that happens run the Invoke-CsManagementStoreReplication cmdlet. Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="29afe-113">Verificar conectividade de seus usuários externos</span><span class="sxs-lookup"><span data-stu-id="29afe-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="29afe-114">Temos uma ótima ferramenta para confirmar a configuração do servidor de borda e a capacidade de se conectar, enviar e receber as mensagens corretas para cenários de servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="29afe-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="29afe-115">É o [site de Anaylzer de conectividade remota](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="29afe-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="29afe-116">Este é um site gerenciado e mantido pelo Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="29afe-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="29afe-117">Para utilizar esta ferramenta, navegue até o site e siga as instruções para escolher o cenário correto para você.</span><span class="sxs-lookup"><span data-stu-id="29afe-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="29afe-118">Elementos a serem levados em consideração ao testar a conectividade de usuários externos</span><span class="sxs-lookup"><span data-stu-id="29afe-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="29afe-119">Os testes de acesso de usuários externos devem incluir qualquer tipo de usuário interno suportado pela sua organização, incluindo qualquer um ou todos os seguintes:</span><span class="sxs-lookup"><span data-stu-id="29afe-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="29afe-120">Usuários de pelo menos um domínio federado (porém, recomendamos testar todos).</span><span class="sxs-lookup"><span data-stu-id="29afe-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="29afe-121">Usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="29afe-121">Anonymous users.</span></span>
    
- <span data-ttu-id="29afe-122">Usuários em sua organização que estão conectados a Skype para negócios remotamente, mas não estiverem usando a VPN.</span><span class="sxs-lookup"><span data-stu-id="29afe-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="29afe-123">Esses testes determinará se o seu servidor de borda é:</span><span class="sxs-lookup"><span data-stu-id="29afe-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="29afe-124">Escuta as portas necessárias usando um cliente telnet de fora da rede.</span><span class="sxs-lookup"><span data-stu-id="29afe-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="29afe-125">Por exemplo: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="29afe-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="29afe-126">Você deve executar o teste anterior nas portas que você está usando no seu servidor de borda ou pool de servidores de borda, dependendo da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="29afe-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="29afe-127">Executa a resolução DNS externa precisa.</span><span class="sxs-lookup"><span data-stu-id="29afe-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="29afe-128">De fora da rede, execute ping cada um dos FQDNs externos do seu servidor de borda ou pool de servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="29afe-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="29afe-129">Mesmo se o ping falhar, você verá os endereços IP, que você possa comparar os endereços IP que você atribuiu anteriormente.</span><span class="sxs-lookup"><span data-stu-id="29afe-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    


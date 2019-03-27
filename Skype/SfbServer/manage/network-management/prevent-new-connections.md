---
title: Impedindo novas conexões
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: bc9b4a1e7d6e17f09643ff14ac0e69261c326922
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889723"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="52c35-102">Impedindo novas conexões Skype para Business Server para manutenção do servidor</span><span class="sxs-lookup"><span data-stu-id="52c35-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="52c35-103">Skype para Business Server permite colocar um servidor offline (por exemplo, para aplicar atualizações de software ou hardware) sem que ocorra perda de serviço aos usuários.</span><span class="sxs-lookup"><span data-stu-id="52c35-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="52c35-104">Quando você especifica a opção para evitar novas conexões ou chamadas para um servidor em um pool, ele bloqueia aproveitando quaisquer novas conexões e chamadas assim que você implemente essa opção.</span><span class="sxs-lookup"><span data-stu-id="52c35-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="52c35-105">Essas novas conexões e as chamadas são roteadas através de outros servidores no pool.</span><span class="sxs-lookup"><span data-stu-id="52c35-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="52c35-106">Um servidor que está impedindo novas conexões permite que suas sessões em conexões existentes para continuar até que elas terminam naturalmente.</span><span class="sxs-lookup"><span data-stu-id="52c35-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="52c35-107">Quando todas as sessões existentes tiverem terminado, o servidor está pronto para ser colocado offline.</span><span class="sxs-lookup"><span data-stu-id="52c35-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="52c35-108">Quando você evitar novas conexões a um servidor Front-End, alguns Skype para recursos de servidor de negócios e serviços dependem de DNS com carga balanceada para garantir que ele funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="52c35-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="52c35-109">Se você não estiver usando o DNS com carga balanceada no pool, conexões por meio desses serviços podem não ser redirecionadas para outros servidores durante o período que o servidor está impedindo novas conexões, e, portanto, quando o servidor for colocado offline algumas sessões e as chamadas podem ser interrompida.</span><span class="sxs-lookup"><span data-stu-id="52c35-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="52c35-110">Os recursos que dependem de DNS com carga balanceada para garantir que essa opção funcione corretamente são:</span><span class="sxs-lookup"><span data-stu-id="52c35-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="52c35-111">Atendedor</span><span class="sxs-lookup"><span data-stu-id="52c35-111">Attendant</span></span>

  - <span data-ttu-id="52c35-112">Aplicativo Comunicado de Conferência</span><span class="sxs-lookup"><span data-stu-id="52c35-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="52c35-113">Aplicativo Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="52c35-113">Response Group application</span></span>

  - <span data-ttu-id="52c35-114">Aplicativo Comunicado</span><span class="sxs-lookup"><span data-stu-id="52c35-114">Announcement application</span></span>

  - <span data-ttu-id="52c35-115">Aplicativo de Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="52c35-115">Call Park application</span></span>

<span data-ttu-id="52c35-116">Para obter detalhes sobre o balanceamento de carga DNS, consulte [requisitos de balanceamento de carga](../../plan-your-deployment/network-requirements/load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="52c35-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="52c35-117">Além de evitar novas conexões para todos os serviços em um servidor executando o Skype para Business Server, você também pode impedir novas conexões para Skype individual para serviços de Business Server.</span><span class="sxs-lookup"><span data-stu-id="52c35-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="52c35-118">Por exemplo, esse método é útil em uma situação em que você precisa aplicar um Skype para atualização do servidor de negócios que não requer que o servidor inteiro seja encerrado.</span><span class="sxs-lookup"><span data-stu-id="52c35-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="52c35-119">Observe que quando você impede conexões para um serviço, você deve selecionar um serviço ao serem agrupada e exibido na lista de serviços Windows.</span><span class="sxs-lookup"><span data-stu-id="52c35-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="52c35-120">Por exemplo, o Skype para serviço de front-end Server de negócios e o agente de coleta de dados de monitoramento são Skype separado para os serviços de Business Server, mas na lista de serviços do Windows estão consolidadas e mostrados como o Skype para negócios servidor Front-End serviço.</span><span class="sxs-lookup"><span data-stu-id="52c35-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="52c35-121">Você pode impedir novas conexões para o Skype para serviço de negócios servidor Front-End, mas você não pode impedir novas conexões para essas duas Skype individuais de subjacente para serviços de Business Server separadamente.</span><span class="sxs-lookup"><span data-stu-id="52c35-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52c35-122">Quando você configura um servidor para impedir novas conexões e, em seguida, reiniciar o servidor, por padrão o servidor imediatamente começará aceitando novas conexões após ele ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="52c35-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="52c35-123">Para impedir isso, defina o servidor só pausar e retomar manualmente, antes de reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="52c35-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="52c35-124">Para evitar novas conexões Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="52c35-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="52c35-125">Faça logon no computador local como membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="52c35-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="52c35-126">Abra o console do snap-in Serviços: clique em **Iniciar**, aponte para **Todos os programas**, aponte para **Ferramentas administrativas**e clique em **Serviços**.</span><span class="sxs-lookup"><span data-stu-id="52c35-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="52c35-127">Na lista, clique duas vezes o Skype para serviço de Business Server Windows ao qual você deseja evitar novas conexões.</span><span class="sxs-lookup"><span data-stu-id="52c35-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="52c35-128">Na caixa de diálogo Propriedades, sob **status de serviço: iniciado**, clique em **Pausar**.</span><span class="sxs-lookup"><span data-stu-id="52c35-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="52c35-129">Opcionalmente, mas recomendado, ao lado de **tipo de inicialização**, clique em **Manual**.</span><span class="sxs-lookup"><span data-stu-id="52c35-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="52c35-130">Quando você configura um servidor para impedir novas conexões e, em seguida, reiniciar o servidor, por padrão o servidor imediatamente começará aceitando novas conexões após ele ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="52c35-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="52c35-131">Para impedir isso, defina o servidor só pausar e retomar manualmente, antes de reiniciar o servidor.</span><span class="sxs-lookup"><span data-stu-id="52c35-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

---
title: Impedir novas conexões
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823461"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="9ab1e-102">Impedindo novas conexões com o Skype for Business Server para manutenção de servidor</span><span class="sxs-lookup"><span data-stu-id="9ab1e-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="9ab1e-103">O Skype for Business Server permite que você leve um servidor offline (por exemplo, para aplicar atualizações de software ou hardware) sem perda de serviço para os usuários.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="9ab1e-104">Quando você especifica a opção para impedir novas conexões ou chamadas a um servidor em um pool, ele para de aceitar novas conexões e chamadas assim que você implementa essa opção.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="9ab1e-105">As novas conexões e chamadas são roteadas através de outros servidores no pool.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="9ab1e-106">Um servidor que está impedindo novas conexões permite que suas sessões em conexões existentes continuem até terminarem de modo natural.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="9ab1e-107">Quando todas as sessões existentes são concluídas, o servidor está pronto para ser colocado offline.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="9ab1e-108">Quando você impede novas conexões com um Servidor Front-End, alguns recursos e serviços do Skype for Business Server dependem do balanceamento de carga DNS para garantir que ele funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="9ab1e-109">Se você não estiver usando o balanceamento de carga DNSno pool, as conexões por meio desses serviços poderão não ser redirecionados para outros servidores durante o período no qual o servidor está impedindo novas conexões e, portanto, quando o servidor é colocado offline, algumas sessões e chamadas podem ser interrompidas.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="9ab1e-110">Estes são os recursos que dependem do balanceamento de carga DNS para garantir que esta opção funcione corretamente:</span><span class="sxs-lookup"><span data-stu-id="9ab1e-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="9ab1e-111">Attendant</span><span class="sxs-lookup"><span data-stu-id="9ab1e-111">Attendant</span></span>

  - <span data-ttu-id="9ab1e-112">Aplicativo Comunicado de Conferência</span><span class="sxs-lookup"><span data-stu-id="9ab1e-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="9ab1e-113">Aplicativo Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="9ab1e-113">Response Group application</span></span>

  - <span data-ttu-id="9ab1e-114">Aplicativo de comunicado</span><span class="sxs-lookup"><span data-stu-id="9ab1e-114">Announcement application</span></span>

  - <span data-ttu-id="9ab1e-115">Call Park application</span><span class="sxs-lookup"><span data-stu-id="9ab1e-115">Call Park application</span></span>

<span data-ttu-id="9ab1e-116">Para obter detalhes sobre o balanceamento de carga DNS, consulte [Requisitos de balanceamento de carga.](../../plan-your-deployment/network-requirements/load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="9ab1e-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="9ab1e-117">Além de impedir novas conexões para todos os serviços em um servidor que executa o Skype for Business Server, você também pode impedir novas conexões para serviços individuais do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="9ab1e-118">Por exemplo, esse método é útil em uma situação em que você precisa aplicar uma atualização do Skype for Business Server que não exige que todo o servidor seja desligado.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="9ab1e-119">Observe que, quando você impede conexões com um serviço, deve selecionar um serviço que é agrupado e exibido na lista de serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="9ab1e-120">Por exemplo, o serviço de Front-End do Skype for Business Server e o agente de coleta de dados para Monitoramento são serviços separados do Skype for Business Server, mas na lista de serviços do Windows eles são consolidados e mostrados como o serviço front-end do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="9ab1e-121">Você pode impedir novas conexões para o serviço front-end do Skype for Business Server, mas não pode impedir novas conexões para esses dois serviços individuais subjacentes do Skype for Business Server separadamente.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ab1e-p104">Quando você define um servidor para impedir novas conexões e reiniciar o servidor, por padrão, o servidor começa imediatamente a aceitar novas conexões depois de ser inicializado. Para evitar isso, defina o servidor para apenas pausar e reiniciar manualmente antes de reiniciá-lo.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="9ab1e-124">Para impedir novas conexões com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9ab1e-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="9ab1e-125">Faça logoff no computador local como membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="9ab1e-126">Abra o console do snap-in Serviços: **Clique** em Iniciar , aponte para Todos os **Programas,** aponte para Ferramentas Administrativas e clique em **Serviços.**</span><span class="sxs-lookup"><span data-stu-id="9ab1e-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="9ab1e-127">Na lista, clique duas vezes no serviço Windows do Skype for Business Server para o qual você deseja impedir novas conexões.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="9ab1e-128">Na caixa de diálogo Propriedades, em **Status do serviço: Iniciado,** clique em **Pausar.**</span><span class="sxs-lookup"><span data-stu-id="9ab1e-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="9ab1e-129">Opcionalmente, mas recomendado, ao lado do tipo **de inicialização,** clique em **Manual**.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9ab1e-p105">Quando você define um servidor para impedir novas conexões e reiniciar o servidor, por padrão, o servidor começa imediatamente a aceitar novas conexões depois de ser inicializado. Para evitar isso, defina o servidor para apenas pausar e reiniciar manualmente antes de reiniciá-lo.</span><span class="sxs-lookup"><span data-stu-id="9ab1e-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

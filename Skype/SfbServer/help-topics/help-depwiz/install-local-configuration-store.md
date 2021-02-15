---
title: Instalar Repositório de Configuração Local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Para iniciar a instalação de um novo servidor de função do Skype for Business Server 2015, você deve primeiro instalar o SQL Server local que hospedará o armazenamento de configuração local. O armazenamento de configuração local atuará como uma réplica somente leitura do CmS (armazenamento de Gerenciamento Central) do Skype for Business Server. Você deve estar conectado ao servidor no qual está executando a etapa Instalar o Repositório de Configuração Local como administrador local no computador e deve ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Se estiver executando a configuração em um Servidor de Borda, não precisará ser um membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. O documento de definição do Construtor de Topologias será lido a partir do documento de definição exportado em vez do armazenamento de Gerenciamento Central. Para exportar o documento de definição do Construtor de Topologias e torná-lo disponível para os Servidores de Borda, consulte o tópico Export Your Topology and Copy It to External Media for Edge Installation.
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827141"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="04e4d-108">Instalar Repositório de Configuração Local</span><span class="sxs-lookup"><span data-stu-id="04e4d-108">Install Local Configuration Store</span></span>

<span data-ttu-id="04e4d-109">Para iniciar a instalação de um novo servidor de função do Skype for Business Server 2015, você deve primeiro instalar o SQL Server local que hospedará o armazenamento de configuração local.</span><span class="sxs-lookup"><span data-stu-id="04e4d-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="04e4d-110">O armazenamento de configuração local atuará como uma réplica somente leitura do CmS (armazenamento de Gerenciamento Central) do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="04e4d-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="04e4d-111">Você deve estar conectado ao servidor no qual está executando a etapa **Instalar o Repositório de Configuração Local** como administrador local no computador e deve ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="04e4d-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="04e4d-112">Se estiver executando a configuração em um Servidor de Borda, não precisará ser um membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="04e4d-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="04e4d-113">O documento de definição do Construtor de Topologias será lido a partir do documento de definição exportado em vez do armazenamento de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="04e4d-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="04e4d-114">Para exportar o documento de definição do Construtor de Topologias e torná-lo disponível para os Servidores de Borda, consulte o tópico [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="04e4d-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="04e4d-115">Para iniciar a instalação:</span><span class="sxs-lookup"><span data-stu-id="04e4d-115">To begin the installation:</span></span>

1. <span data-ttu-id="04e4d-116">Na página do Skype for Business Server 2015, ao lado de **Step1: Install Local Configuration Store**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="04e4d-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="04e4d-117">Na página **Configuração do Servidor Local**, certifique-se de que a opção **Recuperar a configuração automaticamente do Repositório de Gerenciamento Central** esteja selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="04e4d-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="04e4d-118">Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="04e4d-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="04e4d-119">A instalação do SQL Server local pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="04e4d-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="04e4d-120">Você não verá atualizações sobre o progresso na tela de resumo da instalação enquanto o SQL Server estiver sendo instalado.</span><span class="sxs-lookup"><span data-stu-id="04e4d-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="04e4d-121">Se você quiser monitorar o progresso da instalação, use o Gerenciador de Tarefas para observar a configuração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04e4d-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>



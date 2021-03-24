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
description: Para começar a instalação de um novo servidor de função do Skype for Business Server 2015, você deve primeiro instalar o SQL Server local que hospedará o armazenamento de configuração local. O armazenamento de configuração local atuará como uma réplica somente leitura do armazenamento de Gerenciamento Central do Skype for Business Server (CMS). Você deve estar conectado ao servidor no qual está executando a etapa Instalar o Repositório de Configuração Local como administrador local no computador e deve ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Se estiver executando a configuração em um Servidor de Borda, não precisará ser um membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. O documento de definição do Construtor de Topologias será lido do documento de definição exportado em vez do armazenamento de Gerenciamento Central. Para exportar o documento de definição do Construtor de Topologias e torná-lo disponível para os Servidores de Borda, consulte o tópico Export Your Topology and Copy It to External Media for Edge Installation.
ms.openlocfilehash: 62a16e441cc95e77aaed7e09152ef2a79221d85f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108737"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="aca04-108">Instalar Repositório de Configuração Local</span><span class="sxs-lookup"><span data-stu-id="aca04-108">Install Local Configuration Store</span></span>

<span data-ttu-id="aca04-109">Para começar a instalação de um novo servidor de função do Skype for Business Server 2015, você deve primeiro instalar o SQL Server local que hospedará o armazenamento de configuração local.</span><span class="sxs-lookup"><span data-stu-id="aca04-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="aca04-110">O armazenamento de configuração local atuará como uma réplica somente leitura do armazenamento de Gerenciamento Central do Skype for Business Server (CMS).</span><span class="sxs-lookup"><span data-stu-id="aca04-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="aca04-111">Você deve estar conectado ao servidor no qual está executando a etapa **Instalar o Repositório de Configuração Local** como administrador local no computador e deve ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="aca04-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="aca04-112">Se estiver executando a configuração em um Servidor de Borda, não precisará ser um membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="aca04-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="aca04-113">O documento de definição do Construtor de Topologias será lido do documento de definição exportado em vez do armazenamento de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="aca04-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="aca04-114">Para exportar o documento de definição do Construtor de Topologias e torná-lo disponível para os Servidores de Borda, consulte o tópico [Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span><span class="sxs-lookup"><span data-stu-id="aca04-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span></span>

<span data-ttu-id="aca04-115">Para iniciar a instalação:</span><span class="sxs-lookup"><span data-stu-id="aca04-115">To begin the installation:</span></span>

1. <span data-ttu-id="aca04-116">Na página Skype for Business Server 2015, ao lado **de Step1: Install Local Configuration Store**, click **Run**.</span><span class="sxs-lookup"><span data-stu-id="aca04-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="aca04-117">Na página **Configuração do Servidor Local**, certifique-se de que a opção **Recuperar a configuração automaticamente do Repositório de Gerenciamento Central** esteja selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="aca04-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="aca04-118">Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="aca04-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="aca04-119">A instalação do SQL Server local pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="aca04-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="aca04-120">Você não verá atualizações sobre o andamento na tela de resumo da instalação enquanto SQL Server está sendo instalado.</span><span class="sxs-lookup"><span data-stu-id="aca04-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="aca04-121">Se você quiser monitorar o andamento da instalação, use o Gerenciador de Tarefas para observar a SQL Server configuração.</span><span class="sxs-lookup"><span data-stu-id="aca04-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>
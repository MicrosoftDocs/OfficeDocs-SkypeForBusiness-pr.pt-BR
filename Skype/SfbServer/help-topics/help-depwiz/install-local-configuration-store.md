---
title: Instalar Repositório de Configuração Local
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/13/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Para iniciar a instalação de um novo Skype para servidor de função Business Server 2015, você deve instalar primeiro o servidor local de SQL que hospedará o repositório de configuração local. O repositório de configuração local irão agir como uma réplica somente leitura do Skype para o repositório de gerenciamento Central do Business Server (CMS). Você precisa estar conectado ao servidor que está executando a etapa Instalar o Repositório de Configuração Local como o administrador local no computador, e ter associação no grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Se você estiver executando a configuração em um Servidor de Borda, não precisará ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. O documento de definição do construtor de topologia serão lidas do documento em vez de definição exportada do repositório de gerenciamento Central. Para exportar o documento de definição do construtor de topologias e disponibilizá-lo aos servidores de borda, consulte o tópico exportar Your Topology e cópia-la na mídia externa para instalação de borda.
ms.openlocfilehash: 758b32178dcb574e5e929c88bc5744d495b6420f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201248"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="40ae7-108">Instalar Repositório de Configuração Local</span><span class="sxs-lookup"><span data-stu-id="40ae7-108">Install Local Configuration Store</span></span>

<span data-ttu-id="40ae7-109">Para iniciar a instalação de um novo Skype para servidor de função Business Server 2015, você deve instalar primeiro o servidor local de SQL que hospedará o repositório de configuração local.</span><span class="sxs-lookup"><span data-stu-id="40ae7-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="40ae7-110">O repositório de configuração local irão agir como uma réplica somente leitura do Skype para o repositório de gerenciamento Central do Business Server (CMS).</span><span class="sxs-lookup"><span data-stu-id="40ae7-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="40ae7-111">Você precisa estar conectado ao servidor que está executando a etapa **Instalar o Repositório de Configuração Local** como o administrador local no computador, e ter associação no grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="40ae7-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="40ae7-112">Se você estiver executando a configuração em um Servidor de Borda, não precisará ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="40ae7-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="40ae7-113">O documento de definição do construtor de topologia serão lidas do documento em vez de definição exportada do repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="40ae7-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="40ae7-114">Para exportar o documento de definição do construtor de topologias e disponibilizá-lo aos servidores de borda, consulte o tópico [Exportar Your Topology and Copy-la na mídia externa para instalação de borda](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="40ae7-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="40ae7-115">Para começar a instalação:</span><span class="sxs-lookup"><span data-stu-id="40ae7-115">To begin the installation:</span></span>

1. <span data-ttu-id="40ae7-116">Sobre o Skype para Business Server 2015 página, próxima ao **etapa 1: instalar repositório de configuração Local**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="40ae7-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="40ae7-117">Na página **Configuração do Servidor Local**, certifique-se de que a opção **Recuperar a configuração automaticamente do Repositório de Gerenciamento Central** esteja selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="40ae7-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="40ae7-118">Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="40ae7-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="40ae7-119">A instalação do SQL Server local pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="40ae7-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="40ae7-120">Você não verá as atualizações em progresso na tela se resumo instalação enquanto o SQL Server está sendo instalado.</span><span class="sxs-lookup"><span data-stu-id="40ae7-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="40ae7-121">Se você deseja monitorar o progresso da instalação, use o Gerenciador de tarefas para assistir a instalação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40ae7-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>



---
title: Instalar Repositório de Configuração Local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Para começar a instalação de um novo servidor de função do Skype for Business Server, você deve primeiro instalar o SQL Server local que hospedará o armazenamento de configuração local. O armazenamento de configuração local atuará como uma réplica somente leitura do armazenamento de Gerenciamento Central do Skype for Business Server (CMS).
ms.openlocfilehash: 78492f8ce913d8f73336ae4f6cdf06fd340ed5f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095975"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="255f2-104">Instalar Repositório de Configuração Local</span><span class="sxs-lookup"><span data-stu-id="255f2-104">Install Local Configuration Store</span></span>

<span data-ttu-id="255f2-105">Para começar a instalação de um novo servidor de função do Skype for Business Server, você deve primeiro instalar o SQL Server local que hospedará o armazenamento de configuração local.</span><span class="sxs-lookup"><span data-stu-id="255f2-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="255f2-106">O armazenamento de configuração local atuará como uma réplica somente leitura do armazenamento de Gerenciamento Central do Skype for Business Server (CMS).</span><span class="sxs-lookup"><span data-stu-id="255f2-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="255f2-107">Você deve estar conectado ao servidor no qual está executando a etapa **Instalar o Repositório de Configuração Local** como administrador local no computador e deve ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="255f2-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="255f2-108">Se estiver executando a configuração em um Servidor de Borda, não precisará ser um membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="255f2-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="255f2-109">O documento de definição do Construtor de Topologias será lido do documento de definição exportado em vez do armazenamento de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="255f2-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="255f2-110">Para exportar o documento de definição do Construtor de Topologias e torná-lo disponível para os Servidores de Borda, consulte o tópico[Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span><span class="sxs-lookup"><span data-stu-id="255f2-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span></span>

<span data-ttu-id="255f2-111">Para iniciar a instalação:</span><span class="sxs-lookup"><span data-stu-id="255f2-111">To begin the installation:</span></span>

1. <span data-ttu-id="255f2-112">Na página Skype for Business Server, ao lado **de Step1: Install Local Configuration Store**, click **Run**.</span><span class="sxs-lookup"><span data-stu-id="255f2-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="255f2-113">Na página **Configuração do Servidor Local**, certifique-se de que a opção **Recuperar a configuração automaticamente do Repositório de Gerenciamento Central** esteja selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="255f2-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="255f2-114">Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="255f2-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="255f2-115">A instalação do SQL Server local pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="255f2-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="255f2-116">Você não verá atualizações sobre o andamento na tela de resumo da instalação enquanto SQL Server está sendo instalado.</span><span class="sxs-lookup"><span data-stu-id="255f2-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="255f2-117">Se você quiser monitorar o andamento da instalação, use o Gerenciador de Tarefas para observar a SQL Server configuração.</span><span class="sxs-lookup"><span data-stu-id="255f2-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>
---
title: Instalar Repositório de Configuração Local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Para começar a instalação de um novo servidor de função do Skype for Business Server, primeiro você deve instalar o SQL Server local que irá hospedar o repositório de configuração local. O repositório de configuração local atuará como uma réplica somente leitura do CMS (repositório de gerenciamento central) do Skype for Business Server.
ms.openlocfilehash: 365529c3c9cb15ea50cd6a482bd2a69143daa219
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794790"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="e771d-104">Instalar Repositório de Configuração Local</span><span class="sxs-lookup"><span data-stu-id="e771d-104">Install Local Configuration Store</span></span>

<span data-ttu-id="e771d-105">Para começar a instalação de um novo servidor de função do Skype for Business Server, primeiro você deve instalar o SQL Server local que irá hospedar o repositório de configuração local.</span><span class="sxs-lookup"><span data-stu-id="e771d-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="e771d-106">O repositório de configuração local atuará como uma réplica somente leitura do CMS (repositório de gerenciamento central) do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e771d-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="e771d-107">Você precisa estar conectado ao servidor que está executando a etapa **Instalar o Repositório de Configuração Local** como o administrador local no computador, e ter associação no grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="e771d-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="e771d-108">Se você estiver executando a configuração em um Servidor de Borda, não precisará ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="e771d-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="e771d-109">O documento de definição do construtor de topologias será lido do documento de definição exportado, em vez de do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="e771d-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="e771d-110">Para exportar o documento de definição do construtor de topologia e disponibilizá-lo para os servidores de borda, consulte o tópico[exportar sua topologia e copiá-la para mídia externa para instalação do Edge](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="e771d-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="e771d-111">Para começar a instalação:</span><span class="sxs-lookup"><span data-stu-id="e771d-111">To begin the installation:</span></span>

1. <span data-ttu-id="e771d-112">Na página do Skype for Business Server, ao lado de **Step1: instalar o repositório de configuração local**, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="e771d-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="e771d-113">Na página **Configuração do Servidor Local**, certifique-se de que a opção **Recuperar a configuração automaticamente do Repositório de Gerenciamento Central** esteja selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e771d-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="e771d-114">Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="e771d-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="e771d-115">A instalação do SQL Server local pode demorar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="e771d-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="e771d-116">Você não verá atualizações em andamento na tela Resumo da instalação enquanto o SQL Server estiver sendo instalado.</span><span class="sxs-lookup"><span data-stu-id="e771d-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="e771d-117">Se você quiser monitorar o andamento da instalação, use o Gerenciador de tarefas para assistir à configuração do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e771d-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>



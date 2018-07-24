---
title: Instalar Repositório de Configuração Local
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Para iniciar a instalação de um novo Skype para o servidor de função de servidor de negócios, você deve instalar primeiro o servidor local de SQL que hospedará o repositório de configuração local. O repositório de configuração local irão agir como uma réplica somente leitura do Skype para o repositório de gerenciamento Central do Business Server (CMS).
ms.openlocfilehash: ab19a45925a25b97e9b1c478c631ee71fe999b83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993667"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="d22fb-104">Instalar Repositório de Configuração Local</span><span class="sxs-lookup"><span data-stu-id="d22fb-104">Install Local Configuration Store</span></span>
 
<span data-ttu-id="d22fb-105">Para iniciar a instalação de um novo Skype para o servidor de função de servidor de negócios, você deve instalar primeiro o servidor local de SQL que hospedará o repositório de configuração local.</span><span class="sxs-lookup"><span data-stu-id="d22fb-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="d22fb-106">O repositório de configuração local irão agir como uma réplica somente leitura do Skype para o repositório de gerenciamento Central do Business Server (CMS).</span><span class="sxs-lookup"><span data-stu-id="d22fb-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="d22fb-107">Você precisa estar conectado ao servidor que está executando a etapa **Instalar o Repositório de Configuração Local** como o administrador local no computador, e ter associação no grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="d22fb-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="d22fb-108">Se você estiver executando a configuração em um Servidor de Borda, não precisará ser membro do grupo RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="d22fb-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="d22fb-109">O documento de definição do construtor de topologia serão lidas do documento em vez de definição exportada do repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="d22fb-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="d22fb-110">Para exportar o documento de definição do construtor de topologias e disponibilizá-lo aos servidores de borda, consulte o tópico[Exportar Your Topology and Copy-la na mídia externa para instalação de borda](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="d22fb-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>
  
<span data-ttu-id="d22fb-111">Para começar a instalação:</span><span class="sxs-lookup"><span data-stu-id="d22fb-111">To begin the installation:</span></span>
  
1. <span data-ttu-id="d22fb-112">Sobre o Skype para página Business Server, ao lado de **etapa 1: instalar repositório de configuração Local**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="d22fb-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>
    
2. <span data-ttu-id="d22fb-113">Na página **Configuração do Servidor Local**, certifique-se de que a opção **Recuperar a configuração automaticamente do Repositório de Gerenciamento Central** esteja selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d22fb-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>
    
3. <span data-ttu-id="d22fb-114">Quando a instalação da configuração do servidor local estiver concluída, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="d22fb-114">When the local server configuration installation is complete, click **Finish**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d22fb-115">A instalação do SQL Server local pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="d22fb-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="d22fb-116">Você não verá as atualizações em progresso na tela se resumo instalação enquanto o SQL Server está sendo instalado.</span><span class="sxs-lookup"><span data-stu-id="d22fb-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="d22fb-117">Se você deseja monitorar o progresso da instalação, use o Gerenciador de tarefas para assistir a instalação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d22fb-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span> 
  


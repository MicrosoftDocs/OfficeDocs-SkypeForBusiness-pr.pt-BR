---
title: Preparar Servidor Standard Edition Único (Introdução)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Para iniciar a instalação de um Skype para servidor de Business Server 2015 Standard Edition que irá manter o repositório de gerenciamento Central e outros serviços colocados selecionado, você deve estar logado como membro do grupo Administradores local no servidor que irá Torne-se o servidor Standard Edition. A página Preparar Servidor Standard Edition único detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
ms.openlocfilehash: 0f3980ec0fc8e65b6737dcbaf2deff5dccaca5e4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201262"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="7169d-105">Preparar Servidor Standard Edition Único (Introdução)</span><span class="sxs-lookup"><span data-stu-id="7169d-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="7169d-106">Para iniciar a instalação de um Skype para servidor de Business Server 2015 Standard Edition que irá manter o repositório de gerenciamento Central e outros serviços colocados selecionado, você deve estar logado como membro do grupo Administradores local no servidor que irá Torne-se o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7169d-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="7169d-107">A página **Preparar Servidor Standard Edition único** detalha os requisitos para a instalação inicial.</span><span class="sxs-lookup"><span data-stu-id="7169d-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="7169d-108">O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.</span><span class="sxs-lookup"><span data-stu-id="7169d-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="7169d-109">Essa tarefa específica foi projetada para configurar um servidor Standard Edition como o primeiro servidor em sua infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="7169d-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="7169d-110">Esta tarefa instala o repositório de gerenciamento Central, que é o SQL Server Express, logon no servidor do Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7169d-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="7169d-111">Se você já tiver outro servidor Standard Edition ou Pool de Front-Ends implantado, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="7169d-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7169d-112">Depois de concluir esta tarefa, você instalará o construtor de topologia (se você não tiver instalado-lo) e configurar o documento de topologia.</span><span class="sxs-lookup"><span data-stu-id="7169d-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="7169d-113">Não é possível publicar seu documento de topologia até exista um repositório de Gerenciamento Central disponível—que é implantado por meio da conclusão da tarefa descrita neste tópico.</span><span class="sxs-lookup"><span data-stu-id="7169d-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  


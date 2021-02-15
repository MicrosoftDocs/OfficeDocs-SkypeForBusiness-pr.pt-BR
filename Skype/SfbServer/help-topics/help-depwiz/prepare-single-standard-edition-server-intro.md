---
title: Preparar Servidor Standard Edition Único (Introdução)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Para iniciar a instalação de um servidor Skype for Business Server 2015 Standard Edition que armazenará o armazenamento de Gerenciamento Central e outros serviços alocados selecionados, você deve estar conectado como membro do grupo local administradores no servidor que se tornará o servidor Standard Edition. A página Preparar Servidor Standard Edition único detalha os requisitos para a instalação inicial. O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.
ms.openlocfilehash: 0523645350c6d6f2c0e42237b944f29193e06555
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829777"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="b89c1-105">Preparar Servidor Standard Edition Único (Introdução)</span><span class="sxs-lookup"><span data-stu-id="b89c1-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="b89c1-106">Para iniciar a instalação de um servidor Skype for Business Server 2015 Standard Edition que armazenará o armazenamento de Gerenciamento Central e outros serviços alocados selecionados, você deve estar conectado como membro do grupo local administradores no servidor que se tornará o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b89c1-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="b89c1-107">A página **Preparar Servidor Standard Edition único** detalha os requisitos para a instalação inicial.</span><span class="sxs-lookup"><span data-stu-id="b89c1-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="b89c1-108">O computador precisa ser membro do domínio no qual você o implantará, e você precisa ter concluído com êxito a preparação do Esquema, Floresta e Domínio de sua floresta.</span><span class="sxs-lookup"><span data-stu-id="b89c1-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="b89c1-109">Essa tarefa específica foi projetada para configurar um servidor Standard Edition como o primeiro servidor em sua infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="b89c1-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="b89c1-110">Essa tarefa instala o armazenamento de Gerenciamento Central, que é o SQL Server Express, no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b89c1-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="b89c1-111">Se você já tiver outro servidor Standard Edition ou pool de Front-Ends implantado, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="b89c1-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b89c1-112">Depois de concluir essa tarefa, você instalará o Construtor de Topologias (se ainda não a tiver instalado) e configurará seu documento de topologia.</span><span class="sxs-lookup"><span data-stu-id="b89c1-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="b89c1-113">Não é possível publicar seu documento de topologia até exista um repositório de Gerenciamento Central disponível—que é implantado por meio da conclusão da tarefa descrita neste tópico.</span><span class="sxs-lookup"><span data-stu-id="b89c1-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  


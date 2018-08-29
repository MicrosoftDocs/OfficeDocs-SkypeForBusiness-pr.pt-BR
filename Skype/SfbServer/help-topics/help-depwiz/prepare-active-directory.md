---
title: Preparar o Active Directory
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Para começar a instalação do Skype para Business Server 2015, você deve preparar o esquema, floresta e domínios que irá hospedar servidores e usuários do Active Directory Domain Services. O Skype para o Assistente de implantação do Business Server vai orientá-lo durante as etapas necessárias para preparar o Active Directory, começando com o esquema e, em seguida, para a preparação da floresta. Depois de confirmar se a replicação do Active Directory foi bem-sucedida, então você preparar cada domínio que hospedará usuários ou servidores.
ms.openlocfilehash: 31111aef02bd29e1584dd09e838405b107cd3868
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23241431"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="27155-105">Preparar o Active Directory</span><span class="sxs-lookup"><span data-stu-id="27155-105">Prepare Active Directory</span></span>

<span data-ttu-id="27155-106">Para começar a instalação do Skype para Business Server 2015, você deve preparar o esquema, floresta e domínios que irá hospedar servidores e usuários do Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="27155-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="27155-107">O Skype para o Assistente de implantação do Business Server vai orientá-lo durante as etapas necessárias para preparar o Active Directory, começando com o esquema e, em seguida, para a preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="27155-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="27155-108">Depois de confirmar se a replicação do Active Directory foi bem-sucedida, então você preparar cada domínio que hospedará usuários ou servidores.</span><span class="sxs-lookup"><span data-stu-id="27155-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27155-p103">Para preparar o esquema, é necessário estar conectado como membro do grupo Administradores de Empresa e do grupo Administradores de Esquema. Para preparar a floresta, é necessário estar conectado como membro do grupo Administradores de Empresa ou conectado como administrador na raiz da floresta. Para preparação do domínio, é necessário estar conectado como membro do grupo Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="27155-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="27155-112">Para obter detalhes sobre as topologias com suporte do Active Directory, consulte [Suporte do Active Directory](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="27155-112">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="27155-113">Para obter detalhes sobre a preparação do Active Directory, consulte [Visão geral do domínio serviços preparação do Active Directory](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="27155-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>



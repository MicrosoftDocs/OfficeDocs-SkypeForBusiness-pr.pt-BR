---
title: Preparar o Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Para começar a instalação do Skype for Business Server 2015, você deve preparar o esquema, a floresta e os domínios dos Serviços de Domínio Active Directory que hospedarão servidores e usuários. O Assistente de Implantação do Skype for Business Server orientará você pelas etapas necessárias para preparar o Active Directory, começando com o esquema e, em seguida, na preparação da floresta. Depois de confirmar se a replicação do Active Directory foi bem-sucedida, você prepara cada domínio que hospedará usuários ou servidores.
ms.openlocfilehash: b76361e855dc41ee0515939855932ae5f6920662
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104557"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="4c4fc-105">Preparar o Active Directory</span><span class="sxs-lookup"><span data-stu-id="4c4fc-105">Prepare Active Directory</span></span>

<span data-ttu-id="4c4fc-106">Para começar a instalação do Skype for Business Server 2015, você deve preparar o esquema, a floresta e os domínios dos Serviços de Domínio Active Directory que hospedarão servidores e usuários.</span><span class="sxs-lookup"><span data-stu-id="4c4fc-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="4c4fc-107">O Assistente de Implantação do Skype for Business Server orientará você pelas etapas necessárias para preparar o Active Directory, começando com o esquema e, em seguida, na preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="4c4fc-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="4c4fc-108">Depois de confirmar se a replicação do Active Directory foi bem-sucedida, você prepara cada domínio que hospedará usuários ou servidores.</span><span class="sxs-lookup"><span data-stu-id="4c4fc-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c4fc-p103">Para preparar o esquema com sucesso você deve estar conectado como um membro do grupo de Administradores de Empresa e do grupo Administradores de Esquema. Para preparar a floresta, você deve estar conectado como um membro do grupo de Administradores de Empresa ou como um administrador na raiz da floresta. Para a preparação de domínio, você deve estar conectado como um membro do grupo de Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="4c4fc-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="4c4fc-112">Para obter detalhes sobre as topologias suportadas do Active Directory, consulte [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) na documentação Suporte.</span><span class="sxs-lookup"><span data-stu-id="4c4fc-112">For details about supported Active Directory topologies, see [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) in the Supportability documentation.</span></span> <span data-ttu-id="4c4fc-113">Para obter detalhes sobre a preparação do Active Directory, consulte [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) na documentação Implantação.</span><span class="sxs-lookup"><span data-stu-id="4c4fc-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) in the Deployment documentation.</span></span>
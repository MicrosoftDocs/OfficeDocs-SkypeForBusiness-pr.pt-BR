---
title: Preparar o Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Para começar a instalação do Skype for Business Server, você deve preparar o esquema, a floresta e os domínios dos Serviços de Domínio Active Directory que hospedarão servidores e usuários. O Assistente de Implantação do Skype for Business Server orientará você pelas etapas necessárias para preparar o Active Directory, começando com o esquema e depois na preparação da floresta. Depois de confirmar que a replicação do Active Directory foi bem-sucedida, prepare cada domínio que hospedará usuários ou servidores.
ms.openlocfilehash: 4e2951643ddc0f569df6802b6ff5fdd8d2c12a82
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825041"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="f7c68-105">Preparar o Active Directory</span><span class="sxs-lookup"><span data-stu-id="f7c68-105">Prepare Active Directory</span></span>

<span data-ttu-id="f7c68-106">Para começar a instalação do Skype for Business Server, você deve preparar o esquema, a floresta e os domínios dos Serviços de Domínio Active Directory que hospedarão servidores e usuários.</span><span class="sxs-lookup"><span data-stu-id="f7c68-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="f7c68-107">O Assistente de Implantação do Skype for Business Server orientará você pelas etapas necessárias para preparar o Active Directory, começando com o esquema e depois na preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="f7c68-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="f7c68-108">Depois de confirmar que a replicação do Active Directory foi bem-sucedida, prepare cada domínio que hospedará usuários ou servidores.</span><span class="sxs-lookup"><span data-stu-id="f7c68-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7c68-p103">Para preparar o esquema com sucesso você deve estar conectado como um membro do grupo de Administradores de Empresa e do grupo Administradores de Esquema. Para preparar a floresta, você deve estar conectado como um membro do grupo de Administradores de Empresa ou como um administrador na raiz da floresta. Para a preparação de domínio, você deve estar conectado como um membro do grupo de Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="f7c68-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="f7c68-112">Para obter detalhes sobre as topologias suportadas do Active Directory, consulte [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) na documentação Suporte.</span><span class="sxs-lookup"><span data-stu-id="f7c68-112">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="f7c68-113">Para obter detalhes sobre a preparação do Active Directory, consulte [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) na documentação Implantação.</span><span class="sxs-lookup"><span data-stu-id="f7c68-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>



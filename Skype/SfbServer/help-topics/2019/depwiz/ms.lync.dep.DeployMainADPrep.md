---
title: Preparar o Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Para começar a instalação do Skype for Business Server, você deve preparar o esquema, a floresta e os domínios dos serviços de domínio Active Directory que hospedarão servidores e usuários. O assistente de implantação do Skype for Business Server guiará você pelas etapas necessárias para preparar o Active Directory, começando com o esquema e depois na preparação da floresta. Depois de confirmar que a replicação do Active Directory foi bem-sucedida, você prepara cada domínio que hospedará usuários ou servidores.
ms.openlocfilehash: bbdd4eebe3a0e385d2b3cf8367e12339e2e943b7
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798368"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="0dcef-105">Preparar o Active Directory</span><span class="sxs-lookup"><span data-stu-id="0dcef-105">Prepare Active Directory</span></span>

<span data-ttu-id="0dcef-106">Para começar a instalação do Skype for Business Server, você deve preparar o esquema, a floresta e os domínios dos serviços de domínio Active Directory que hospedarão servidores e usuários.</span><span class="sxs-lookup"><span data-stu-id="0dcef-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="0dcef-107">O assistente de implantação do Skype for Business Server guiará você pelas etapas necessárias para preparar o Active Directory, começando com o esquema e depois na preparação da floresta.</span><span class="sxs-lookup"><span data-stu-id="0dcef-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="0dcef-108">Depois de confirmar que a replicação do Active Directory foi bem-sucedida, você prepara cada domínio que hospedará usuários ou servidores.</span><span class="sxs-lookup"><span data-stu-id="0dcef-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dcef-p103">Para preparar o esquema, é necessário estar conectado como membro do grupo Administradores de Empresa e do grupo Administradores de Esquema. Para preparar a floresta, é necessário estar conectado como membro do grupo Administradores de Empresa ou conectado como administrador na raiz da floresta. Para preparação do domínio, é necessário estar conectado como membro do grupo Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="0dcef-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="0dcef-p104">Para obter detalhes sobre as topologias suportadas do Active Directory, consulte [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) na documentação Suporte. Para obter detalhes sobre a preparação do Active Directory, consulte [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) na documentação Implantação.</span><span class="sxs-lookup"><span data-stu-id="0dcef-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>



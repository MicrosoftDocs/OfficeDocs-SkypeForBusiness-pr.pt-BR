---
title: Criar um mapa de construção para o painel de qualidade de chamada (CQD)
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Saiba como criar um mapa de construção que você pode usar para carregar locatários e construir dados no painel de qualidade de chamada (CQD).
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085998"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="43020-103">Criar um mapa de construção para o painel de qualidade de chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="43020-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="43020-104">Em uma implantação do Microsoft Teams ou do Skype for Business Online, todos os clientes são externos.</span><span class="sxs-lookup"><span data-stu-id="43020-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="43020-105">Como resultado, por padrão, todos os clientes são relatados como externos no painel de qualidade de chamada (CQD), independentemente de o cliente estar conectado a uma rede corporativa interna.</span><span class="sxs-lookup"><span data-stu-id="43020-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="43020-106">Ao trabalhar com o CQD, você precisa saber a localização de um ponto de extremidade e se ele está conectado a uma rede que você pode gerenciar ou uma rede que não pode gerenciar, a pressuposição é que você só pode melhorar as redes que você pode gerenciar.</span><span class="sxs-lookup"><span data-stu-id="43020-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="43020-107">Ao carregar as informações de sub-rede e de construção no CQD, você habilita o CQD para determinar se o ponto de extremidade foi conectado a uma rede interna (gerenciada) ou a uma rede externa (não gerenciada).</span><span class="sxs-lookup"><span data-stu-id="43020-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="43020-108">É por isso que é importante criar um mapa de construção para sua organização e [carregá-lo no CQD](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="43020-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="43020-109">Ferramentas de mapeamento de construção</span><span class="sxs-lookup"><span data-stu-id="43020-109">Building mapping tools</span></span>

<span data-ttu-id="43020-110">Há muitas maneiras de mapear as sub-redes da sua organização.</span><span class="sxs-lookup"><span data-stu-id="43020-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="43020-111">Se precisar de ajuda, você pode usar o módulo do PowerShell CQDTools descrito nesta [postagem de blog](https://aka.ms/cqdtools).</span><span class="sxs-lookup"><span data-stu-id="43020-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="43020-112">Essas ferramentas se baseiam no PowerShell e usam sites e serviços do Active Directory (AD) e os serviços DHCP da Microsoft para ajudar a preencher previamente o seu arquivo de construção.</span><span class="sxs-lookup"><span data-stu-id="43020-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="43020-113">Essas ferramentas ajudarão nas seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="43020-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="43020-114">Consultar sites e serviços de anúncios e criar um arquivo de construção com base nas informações contidas em.</span><span class="sxs-lookup"><span data-stu-id="43020-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="43020-115">Consulta um servidor ou servidores DHCP da Microsoft para extrair informações de sub-rede e criar automaticamente um arquivo de construção.</span><span class="sxs-lookup"><span data-stu-id="43020-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="43020-116">Valide um arquivo de construção existente, verificando se há duplicatas e sobrepostas.</span><span class="sxs-lookup"><span data-stu-id="43020-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="43020-117">Localizar sub-redes não mapeadas no CQD.</span><span class="sxs-lookup"><span data-stu-id="43020-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="43020-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="43020-118">Related topics</span></span>

[<span data-ttu-id="43020-119">Carregar o locatário e compilar dados no CQD</span><span class="sxs-lookup"><span data-stu-id="43020-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)
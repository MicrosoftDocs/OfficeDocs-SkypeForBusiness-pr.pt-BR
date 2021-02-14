---
title: Criar um mapa de construção para o CQD (Painel de Qualidade da Chamada)
ms.author: serdars
author: SerdarSoysal
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
description: Saiba como criar um mapa de construção que você pode usar para carregar o locatário e criar dados no Painel de Qualidade de Chamada (CQD).
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584030"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="748aa-103">Criar um mapa de construção para o CQD (Painel de Qualidade da Chamada)</span><span class="sxs-lookup"><span data-stu-id="748aa-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="748aa-104">Em uma implantação do Microsoft Teams ou do Skype for Business Online, todos os clientes são externos.</span><span class="sxs-lookup"><span data-stu-id="748aa-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="748aa-105">Como resultado, por padrão, todos os clientes são relatados como externos no Painel de Qualidade de Chamada (CQD), independentemente de o cliente estar conectado em uma rede corporativa interna.</span><span class="sxs-lookup"><span data-stu-id="748aa-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="748aa-106">Ao trabalhar com o CQD, você precisa saber a localização de um ponto de extremidade e se ele foi conectado a uma rede que você pode gerenciar ou uma rede que não pode gerenciar, a suposição é de que você só pode melhorar as redes que pode gerenciar.</span><span class="sxs-lookup"><span data-stu-id="748aa-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="748aa-107">Ao carregar informações de sub-rede e de criação no CQD, você habilita o CQD para determinar se o ponto de extremidade estava conectado a uma rede interna (gerenciada) ou a uma rede externa (não gerenciada).</span><span class="sxs-lookup"><span data-stu-id="748aa-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="748aa-108">É por isso que é importante criar um mapa de construção para sua organização e [enviá-lo para o CQD.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="748aa-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="748aa-109">Ferramentas de mapeamento de construção</span><span class="sxs-lookup"><span data-stu-id="748aa-109">Building mapping tools</span></span>

<span data-ttu-id="748aa-110">Há várias maneiras de mapear as sub-redes da sua organização.</span><span class="sxs-lookup"><span data-stu-id="748aa-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="748aa-111">Se precisar de ajuda, você pode usar o Módulo CQDTools PowerShell descrito nesta [postagem de blog.](https://aka.ms/cqdtools)</span><span class="sxs-lookup"><span data-stu-id="748aa-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="748aa-112">Essas ferramentas se baseiam no PowerShell e usam Sites e Serviços do Active Directory (AD) e serviços DHCP da Microsoft para ajudar a preencher previamente o arquivo de construção.</span><span class="sxs-lookup"><span data-stu-id="748aa-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="748aa-113">Essas ferramentas ajudarão com as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="748aa-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="748aa-114">Sites e Serviços do AD de Consulta e crie um arquivo de construção com base nas informações contidas nele.</span><span class="sxs-lookup"><span data-stu-id="748aa-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="748aa-115">Consultar um servidor DHCP da Microsoft ou servidores para obter informações da sub-rede e criar automaticamente um arquivo de construção.</span><span class="sxs-lookup"><span data-stu-id="748aa-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="748aa-116">Validar um arquivo de construção existente, verificando se há duplicatas e sobreposições.</span><span class="sxs-lookup"><span data-stu-id="748aa-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="748aa-117">Encontre sub-redes não mapeadas no CQD.</span><span class="sxs-lookup"><span data-stu-id="748aa-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="748aa-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="748aa-118">Related topics</span></span>

[<span data-ttu-id="748aa-119">Carregar dados de locatário e de construção no CQD</span><span class="sxs-lookup"><span data-stu-id="748aa-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)
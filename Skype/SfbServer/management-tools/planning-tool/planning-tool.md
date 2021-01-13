---
title: Ferramenta de Planejamento do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Diretrizes sobre como usar a Ferramenta de Planejamento do Skype for Business Server 2015.
ms.openlocfilehash: aef46fac65ba1d5651cada81bc79cfc21021bf54
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832381"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="66a4a-103">Ferramenta de Planejamento do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66a4a-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="66a4a-104">Diretrizes sobre como usar a Ferramenta de Planejamento do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="66a4a-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="66a4a-105">A Ferramenta de Planejamento do Skype for Business Server 2015 é uma ferramenta orientada por assistentes, que faz perguntas sobre a topologia do Skype for Business Server 2015 que você está projetando.</span><span class="sxs-lookup"><span data-stu-id="66a4a-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="66a4a-106">A Ferramenta de Planejamento usa as informações fornecidas, juntamente com as práticas preferenciais para design e capacidade da topologia, para apresentar uma topologia recomendada com base nas respostas fornecidas.</span><span class="sxs-lookup"><span data-stu-id="66a4a-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="66a4a-107">Você pode baixar a Ferramenta de Planejamento da [Ferramenta de Planejamento do Skype for Business Server 2015.](https://go.microsoft.com/fwlink/p/?LinkID=282725)</span><span class="sxs-lookup"><span data-stu-id="66a4a-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="66a4a-108">Por fim, o objetivo da Ferramenta de Planejamento é facilitar a complexidade potencial de projetar uma topologia completa do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="66a4a-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="66a4a-109">A ferramenta também fornece referências contextuais à documentação de planejamento e implantação dentro da ferramenta, desde que uma conexão com a Internet está disponível para se conectar ao site da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66a4a-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="66a4a-110">Depois de personalizar a topologia com os endereços TCP/IP da infraestrutura e os FQDNs (nomes de domínio totalmente qualificados), a Ferramenta de Planejamento disponibiliza uma série de relatórios que abrangem a nomenalização de DNS (Sistema de Nomes de Domínio), regras de firewall, certificados e muito mais.</span><span class="sxs-lookup"><span data-stu-id="66a4a-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="66a4a-111">Usar essa ferramenta é a primeira etapa no planejamento da implementação.</span><span class="sxs-lookup"><span data-stu-id="66a4a-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="66a4a-112">A próxima etapa seria inserir informações específicas do seu site na Calculadora de Capacidade do [Skype for Business Server 2015,](https://www.microsoft.com/download/details.aspx?id=51196)ajustar conforme necessário e usar a Ferramenta de Stress and Performance do Skype for Business Server [2015](https://www.microsoft.com/download/details.aspx?id=50367) para simular e verificar se a implementação atenderá às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="66a4a-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="66a4a-113">A Ferramenta de Planejamento também oferece a capacidade de exportar informações em dois formatos:</span><span class="sxs-lookup"><span data-stu-id="66a4a-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="66a4a-114">Microsoft Excel (planilha .xml)</span><span class="sxs-lookup"><span data-stu-id="66a4a-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="66a4a-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="66a4a-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="66a4a-116">Os tópicos a seguir apresentam e detalham a Ferramenta de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="66a4a-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="66a4a-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="66a4a-117">In this section</span></span>

- [<span data-ttu-id="66a4a-118">Instalar a Ferramenta de Planejamento no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66a4a-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="66a4a-119">Software opcional</span><span class="sxs-lookup"><span data-stu-id="66a4a-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="66a4a-120">Navegar na Ferramenta de Planejamento no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66a4a-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="66a4a-121">Criar o design de topologia inicial para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66a4a-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="66a4a-122">Editar a topologia no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66a4a-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="66a4a-123">Editar o diagrama de configuração de rede</span><span class="sxs-lookup"><span data-stu-id="66a4a-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="66a4a-124">Revisar os relatórios de administrador no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66a4a-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="66a4a-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="66a4a-125">See also</span></span>

[<span data-ttu-id="66a4a-126">Instalar o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66a4a-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="66a4a-127">Planejar mensagens instantâneas e presença no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="66a4a-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)

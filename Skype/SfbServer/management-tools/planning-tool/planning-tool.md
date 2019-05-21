---
title: Ferramenta de Planejamento do Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Orientação sobre como usar a ferramenta de planejamento do Skype for Business Server 2015.
ms.openlocfilehash: b130ca05200ea30bed8008399050affa96438644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288947"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="5a18b-103">Skype for Business Server 2015 Planning Tool</span><span class="sxs-lookup"><span data-stu-id="5a18b-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="5a18b-104">Orientação sobre como usar a ferramenta de planejamento do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5a18b-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="5a18b-105">A ferramenta de planejamento do Skype for Business Server 2015 é uma ferramenta do tipo entrevistada orientada por um assistente que faz perguntas sobre a topologia do Skype for Business Server 2015 que você está criando.</span><span class="sxs-lookup"><span data-stu-id="5a18b-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="5a18b-106">A ferramenta de planejamento usa as informações fornecidas, combinadas com práticas preferenciais de design e capacidade de topologia, para apresentar uma topologia recomendada com base nas respostas fornecidas.</span><span class="sxs-lookup"><span data-stu-id="5a18b-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="5a18b-107">Você pode baixar a ferramenta de planejamento da [ferramenta de planejamento do Skype for Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span><span class="sxs-lookup"><span data-stu-id="5a18b-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="5a18b-108">Por fim, o objetivo da ferramenta de planejamento é facilitar a complexidade potencial de projetar uma topologia completa do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5a18b-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="5a18b-109">A ferramenta também fornece referências contextuais à documentação de planejamento e implantação dentro da ferramenta, desde que uma conexão com a Internet esteja disponível para conexão com o website da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a18b-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="5a18b-110">Após personalizar a topologia com os endereços TCP/IP da infraestrutura e FQDNs (nomes de domínio totalmente qualificados), a ferramenta de planejamento disponibiliza uma série de relatórios que abrangem o nome DNS, as regras de firewall, os certificados e muito mais.</span><span class="sxs-lookup"><span data-stu-id="5a18b-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="5a18b-111">A utilização desta ferramenta é a primeira etapa no planejamento de sua implementação.</span><span class="sxs-lookup"><span data-stu-id="5a18b-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="5a18b-112">A próxima etapa seria inserir as informações específicas do seu site na calculadora de [capacidade do Skype for Business server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=51196), ajustar conforme necessário e, em seguida, usar a [ferramenta de stress e desempenho do Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50367) para simular e verificar a a implementação vai atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="5a18b-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="5a18b-113">A ferramenta de planejamento também fornece a capacidade de exportar informações em dois formatos:</span><span class="sxs-lookup"><span data-stu-id="5a18b-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="5a18b-114">Microsoft Excel (planilha .xml)</span><span class="sxs-lookup"><span data-stu-id="5a18b-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="5a18b-115">Microsoft Visio ( .vdx)</span><span class="sxs-lookup"><span data-stu-id="5a18b-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="5a18b-116">Os tópicos a seguir introduzem e detalham a ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="5a18b-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5a18b-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5a18b-117">In this section</span></span>

- [<span data-ttu-id="5a18b-118">Install the Planning Tool in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a18b-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="5a18b-119">Optional Software</span><span class="sxs-lookup"><span data-stu-id="5a18b-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="5a18b-120">Navigate the Planning Tool in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a18b-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="5a18b-121">Create the initial topology design for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a18b-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="5a18b-122">Edit the topology in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a18b-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="5a18b-123">Edit the network configuration diagram</span><span class="sxs-lookup"><span data-stu-id="5a18b-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="5a18b-124">Review the Administrator Reports in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a18b-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="5a18b-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="5a18b-125">See also</span></span>

[<span data-ttu-id="5a18b-126">Instalar o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a18b-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="5a18b-127">Plan for instant messaging and presence in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a18b-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)

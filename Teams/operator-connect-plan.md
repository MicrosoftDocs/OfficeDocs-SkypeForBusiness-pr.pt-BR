---
title: Operador Conexão
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre o Conexão, como requisitos e planejamento para implantação.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694536"
---
# <a name="plan-for-operator-connect"></a><span data-ttu-id="77282-103">Plan for Operator Conexão</span><span class="sxs-lookup"><span data-stu-id="77282-103">Plan for Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="77282-104">O Conexão de operador está disponível apenas na **visualização pública.**</span><span class="sxs-lookup"><span data-stu-id="77282-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="77282-105">A visualização pública permite testar os recursos futuros e fornecer comentários.</span><span class="sxs-lookup"><span data-stu-id="77282-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="77282-106">Os recursos incluídos na visualização pública podem não estar completos, podem sofrer alterações e não têm suporte no Office 365 Government Cloud.</span><span class="sxs-lookup"><span data-stu-id="77282-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Cloud.</span></span>

<span data-ttu-id="77282-107">O Conexão operador é outra opção para fornecer conectividade PSTN (Rede Telefônica Pública Comutado) com Teams e Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="77282-107">Operator Connect is another option for providing Public Switched Telephone Network (PSTN) connectivity with Teams and Phone System.</span></span>  

<span data-ttu-id="77282-108">Este artigo descreve benefícios e requisitos e lista os operadores participantes do Programa Conexão Operador.</span><span class="sxs-lookup"><span data-stu-id="77282-108">This article describes benefits and requirements, and lists the operators participating in the Operator Connect Program.</span></span>  <span data-ttu-id="77282-109">Se você decidir que o operador Conexão é a solução certa para sua organização, depois de ler este artigo, consulte [Configure Operator Conexão](operator-connect-configure.md).</span><span class="sxs-lookup"><span data-stu-id="77282-109">If you decide Operator Connect is the right solution for your organization, after reading this article, see [Configure Operator Connect](operator-connect-configure.md).</span></span>  

## <a name="benefits"></a><span data-ttu-id="77282-110">Benefícios</span><span class="sxs-lookup"><span data-stu-id="77282-110">Benefits</span></span>

<span data-ttu-id="77282-111">Com o Conexão operador, se o operador existente for um participante do programa de Conexão do Microsoft Operator, ele poderá gerenciar o serviço para trazer a chamada PSTN para Teams.</span><span class="sxs-lookup"><span data-stu-id="77282-111">With Operator Connect, if your existing operator is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="77282-112">O programa Conexão de operador fornece os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="77282-112">The Operator Connect program provides the following benefits:</span></span>

- <span data-ttu-id="77282-113">**Aproveite os contratos existentes ou encontre um novo operador.**</span><span class="sxs-lookup"><span data-stu-id="77282-113">**Leverage existing contracts, or find a new operator.**</span></span> <span data-ttu-id="77282-114">Mantenha seu operador e contratos preferenciais ou escolha um novo de uma seleção de operadores participantes para atender às suas necessidades comerciais.</span><span class="sxs-lookup"><span data-stu-id="77282-114">You keep your preferred operator and contracts, or choose a new one from a selection of participating operators to meet your business needs.</span></span>

- <span data-ttu-id="77282-115">**Infraestrutura gerenciada pelo operador.**</span><span class="sxs-lookup"><span data-stu-id="77282-115">**Operator-managed infrastructure.**</span></span> <span data-ttu-id="77282-116">Seu operador gerencia os serviços de chamada PSTN e controladores de borda de sessão (SBCs), permitindo que você salve na compra e gerenciamento de hardware.</span><span class="sxs-lookup"><span data-stu-id="77282-116">Your operator manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

- <span data-ttu-id="77282-117">**Implantação mais rápida e fácil.**</span><span class="sxs-lookup"><span data-stu-id="77282-117">**Faster, easier deployment.**</span></span> <span data-ttu-id="77282-118">Você pode se conectar rapidamente à sua operadora e atribuir números de telefone aos usuários -– tudo a partir do Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="77282-118">You can quickly connect to your operator and assign phone numbers to users -– all from the Teams Admin Center.</span></span>

- <span data-ttu-id="77282-119">**Suporte e confiabilidade aprimorados.**</span><span class="sxs-lookup"><span data-stu-id="77282-119">**Enhanced support and reliability.**</span></span> <span data-ttu-id="77282-120">Os operadores fornecem suporte técnico e contratos de nível de serviço compartilhados para melhorar o serviço de suporte, enquanto o peering direto do Azure cria uma conexão de rede um para um para melhorar a confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="77282-120">Operators provide technical support and shared service level agreements to improve support service, while direct peering powered by Azure creates a one-to-one network connection for enhanced reliability.</span></span>

## <a name="requirements"></a><span data-ttu-id="77282-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77282-121">Requirements</span></span>

 <span data-ttu-id="77282-122">O Conexão operador pode ser a solução certa para sua organização se:</span><span class="sxs-lookup"><span data-stu-id="77282-122">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="77282-123">O Plano de Chamada da Microsoft não está disponível em sua localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="77282-123">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="77282-124">Seu operador preferencial é um participante do programa microsoft operator Conexão.</span><span class="sxs-lookup"><span data-stu-id="77282-124">Your preferred operator is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="77282-125">Você deseja encontrar um novo operador para habilitar a chamada no Teams.</span><span class="sxs-lookup"><span data-stu-id="77282-125">You want to find a new operator to enable calling in Teams.</span></span>

<span data-ttu-id="77282-126">Para habilitar atribuições de números de telefone com Conexão operador, certifique-se de que seus usuários sejam:</span><span class="sxs-lookup"><span data-stu-id="77282-126">To enable phone number assignments with Operator Connect, make sure your users are:</span></span>

- <span data-ttu-id="77282-127">Teams Telefone licenciado.</span><span class="sxs-lookup"><span data-stu-id="77282-127">Teams Phone licensed.</span></span> <span data-ttu-id="77282-128">Para saber mais, confira [O que é Sistema de Telefonia?](what-is-phone-system-in-office-365.md) e [Atribuir Teams licenças](teams-add-on-licensing/assign-teams-add-on-licenses.md)de complemento aos usuários .</span><span class="sxs-lookup"><span data-stu-id="77282-128">To learn more, see [What is Phone System?](what-is-phone-system-in-office-365.md) and [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>
- <span data-ttu-id="77282-129">No modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="77282-129">In TeamsOnly mode.</span></span> <span data-ttu-id="77282-130">Para saber mais, consulte [Understand Microsoft Teams and Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="77282-130">To learn more, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

## <a name="available-operators"></a><span data-ttu-id="77282-131">Operadores disponíveis</span><span class="sxs-lookup"><span data-stu-id="77282-131">Available Operators</span></span>

<span data-ttu-id="77282-132">Os operadores a seguir são participantes do programa Conexão Microsoft Operator:</span><span class="sxs-lookup"><span data-stu-id="77282-132">The following operators are participants in the Microsoft Operator Connect program:</span></span>

| <span data-ttu-id="77282-133">Operador</span><span class="sxs-lookup"><span data-stu-id="77282-133">Operator</span></span> | <span data-ttu-id="77282-134">Recursos</span><span class="sxs-lookup"><span data-stu-id="77282-134">Capability</span></span> | <span data-ttu-id="77282-135">Cobertura do país</span><span class="sxs-lookup"><span data-stu-id="77282-135">Country coverage</span></span> |
| --- | --- | --- |
| `BT`  | <span data-ttu-id="77282-136">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-136">Calling</span></span> | <span data-ttu-id="77282-137">Bélgica, Dinamarca, Finlândia, França, Alemanha, Irlanda, Itália, Luxemburgo, Países Baixos, Noruega, Polônia, África do Sul, Espanha, Suécia, Suíça, Reino Unido</span><span class="sxs-lookup"><span data-stu-id="77282-137">Belgium, Denmark, Finland, France, Germany, Ireland, Italy, Luxembourg, Netherlands, Norway, Poland, South Africa, Spain, Sweden, Switzerland, United Kingdom</span></span> |
| `Intrado` | <span data-ttu-id="77282-138">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-138">Calling</span></span> | <span data-ttu-id="77282-139">Bélgica, Canadá, Dinamarca, França, Alemanha, Irlanda, Luxemburgo, Países Baixos, Espanha, Suécia, Reino Unido, Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="77282-139">Belgium, Canada, Denmark, France, Germany, Ireland, Luxembourg, Netherlands, Spain, Sweden, United Kingdom, United States</span></span>  |
| `NTT`  | <span data-ttu-id="77282-140">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-140">Calling</span></span> | <span data-ttu-id="77282-141">Áustria, Bélgica, Brasil, Canadá, Tcheco, Dinamarca, Finlândia, França, Alemanha, Irlanda, Itália, Luxemburgo, México, Países Baixos, Noruega, Polônia, Portugal, Porto Rico, Romênia, África do Sul, Espanha, Suécia, Suíça, Reino Unido, Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="77282-141">Austria, Belgium, Brazil, Canada, Czechia, Denmark, Finland,  France, Germany, Ireland, Italy, Luxembourg, Mexico, Netherlands, Norway, Poland, Portugal, Puerto Rico, Romania, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span> |
| `NuWave` | <span data-ttu-id="77282-142">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-142">Calling</span></span> | <span data-ttu-id="77282-143">Áustria, Bélgica, Canadá, Dinamarca, França, Alemanha, Irlanda, Itália, Países Baixos, Portugal, Espanha, Suécia, Suíça, Reino Unido, Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="77282-143">Austria, Belgium, Canada, Denmark, France, Germany, Ireland, Italy, Netherlands, Portugal, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>   |
| `Orange Business Services` | <span data-ttu-id="77282-144">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-144">Calling</span></span> | <span data-ttu-id="77282-145">Áustria, Bélgica, Tcheca, Dinamarca, Finlândia, França, Guiana Francesa, Alemanha, Guadalupe, Irlanda, Itália, Luxemburgo, Martinica, Mayotte, Países Baixos, Noruega, Polônia, Portugal, Réunion, Saint Barthélemy, Saint Martin, Espanha, Svalbard, Suécia, Suíça, Reino Unido</span><span class="sxs-lookup"><span data-stu-id="77282-145">Austria, Belgium, Czechia, Denmark, Finland, France, French Guiana, Germany, Guadeloupe, Ireland, Italy, Luxembourg, Martinique, Mayotte, Netherlands, Norway, Poland, Portugal, Réunion, Saint Barthélemy, Saint Martin, Spain, Svalbard, Sweden, Switzerland, United Kingdom</span></span>  |
| `Pure IP` | <span data-ttu-id="77282-146">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-146">Calling</span></span> | <span data-ttu-id="77282-147">Austrália, Áustria, Bélgica, Brasil, Bulgária, Canadá, Chile, Colômbia, Croácia, Chipre, Tcheca, Dinamarca, Finlândia, França, Alemanha, Grécia, Hong Kong S.A.R., Irlanda, Itália, Japão, Lituânia, Luxemburgo, Malásia, México, Países Baixos, Nova Zelândia, Noruega, Panamá, Polônia, Portugal, Porto Rico, Romênia, Cingapura, Eslováquia, Eslovênia, África do Sul, Espanha, Suécia, Suíça, Reino Unido, Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="77282-147">Australia, Austria, Belgium, Brazil, Bulgaria, Canada, Chile, Colombia, Croatia, Cyprus, Czechia, Denmark, Finland, France, Germany, Greece, Hong Kong S.A.R., Ireland, Italy, Japan, Lithuania, Luxembourg, Malaysia, Mexico, Netherlands, New Zealand, Norway, Panama, Poland, Portugal, Puerto Rico, Romania, Singapore, Slovakia, Slovenia, South Africa, Spain, Sweden, Switzerland, United Kingdom, United States</span></span>  |
| `Rogers Business` | <span data-ttu-id="77282-148">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-148">Calling</span></span> | <span data-ttu-id="77282-149">Canadá</span><span class="sxs-lookup"><span data-stu-id="77282-149">Canada</span></span>  |
| `TATA Communications` | <span data-ttu-id="77282-150">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-150">Calling</span></span> | <span data-ttu-id="77282-151">Austrália, Áustria, Bélgica, Canadá, Tcheca, Dinamarca, França, Alemanha, Hong Kong S.A.R., Hungria, Irlanda, Itália, Malásia, México, Países Baixos, Nova Zelândia, Polônia, Portugal, Romênia, Cingapura, Coreia do Sul, Espanha, Suécia, Suíça, Tailândia, Reino Unido, Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="77282-151">Australia, Austria, Belgium, Canada, Czechia, Denmark, France, Germany, Hong Kong S.A.R., Hungary, Ireland, Italy, Malaysia, Mexico, Netherlands, New Zealand, Poland, Portugal, Romania, Singapore, South Korea, Spain, Sweden, Switzerland, Thailand, United Kingdom, United States</span></span> |
| `Telekom Deutschland` | <span data-ttu-id="77282-152">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-152">Calling</span></span> | <span data-ttu-id="77282-153">Alemanha</span><span class="sxs-lookup"><span data-stu-id="77282-153">Germany</span></span>  |
| `Telenor` | <span data-ttu-id="77282-154">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-154">Calling</span></span> | <span data-ttu-id="77282-155">Dinamarca, Finlândia, Noruega, Suécia</span><span class="sxs-lookup"><span data-stu-id="77282-155">Denmark, Finland, Norway, Sweden</span></span>  |
| `Verizon` | <span data-ttu-id="77282-156">Chamadas</span><span class="sxs-lookup"><span data-stu-id="77282-156">Calling</span></span> | <span data-ttu-id="77282-157">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="77282-157">United States</span></span> |

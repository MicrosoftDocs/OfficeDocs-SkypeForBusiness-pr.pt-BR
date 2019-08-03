---
title: Desabilitar a migração híbrida para concluir a nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para desabilitar o híbrido como parte da consolidação em nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160388"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="5e067-103">Desabilitar a migração híbrida para concluir a nuvem</span><span class="sxs-lookup"><span data-stu-id="5e067-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="5e067-104">Após mover todos os usuários do local para a nuvem, você poderá encerrar a implantação do Skype for Business local.</span><span class="sxs-lookup"><span data-stu-id="5e067-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="5e067-105">Além de remover qualquer hardware, uma etapa crítica é separar logicamente a implantação local do Office 365 desabilitando o híbrido.</span><span class="sxs-lookup"><span data-stu-id="5e067-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="5e067-106">A desabilitação híbrida consiste em três etapas:</span><span class="sxs-lookup"><span data-stu-id="5e067-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="5e067-107">Atualizar registros DNS para apontar para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e067-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="5e067-108">Desabilitar o domínio de divisão no locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e067-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="5e067-109">Desabilitar a capacidade no local para se comunicar com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e067-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="5e067-110">Essas etapas devem ser feitas juntas como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="5e067-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="5e067-111">Os detalhes são fornecidos abaixo.</span><span class="sxs-lookup"><span data-stu-id="5e067-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="5e067-112">Em casos raros, alterar o DNS de apontar para local para o Office 365 para sua organização pode fazer com que a Federação com algumas outras organizações pare de funcionar até que outra organização Atualize sua configuração de Federação:</span><span class="sxs-lookup"><span data-stu-id="5e067-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="5e067-113">Todas as organizações federadas que usam o modelo de Federação direta mais antigo (também conhecido como servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN do proxy.</span><span class="sxs-lookup"><span data-stu-id="5e067-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="5e067-114">Esse modelo de Federação herdado não é baseado nos registros SRV DNS, portanto, essa configuração se tornará desatualizada quando sua organização for movida para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="5e067-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="5e067-115">Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed. online. Lync. <span>com precisará atualizar sua configuração para habilitar isso.</span><span class="sxs-lookup"><span data-stu-id="5e067-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="5e067-116">Essa situação só é possível se a organização federada estiver exclusivamente local e nunca federada com nenhum locatário híbrido ou online.</span><span class="sxs-lookup"><span data-stu-id="5e067-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="5e067-117">Nesse caso, a Federação com essas organizações não funcionará até que o provedor de hospedagem seja habilitado.</span><span class="sxs-lookup"><span data-stu-id="5e067-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="5e067-118">Se você suspeita que qualquer um dos seus parceiros federados pode usar Federação direta ou federado com qualquer organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso ao se preparar para concluir a migração para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="5e067-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="5e067-119">*Atualize o DNS para apontar para o Office 365.*</span><span class="sxs-lookup"><span data-stu-id="5e067-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="5e067-120">O DNS externo da organização para a organização local precisa ser atualizado para que os registros do Skype for Business apontem para o Office 365 em vez da implantação local.</span><span class="sxs-lookup"><span data-stu-id="5e067-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="5e067-121">Especificamente:</span><span class="sxs-lookup"><span data-stu-id="5e067-121">Specifically:</span></span>

    |<span data-ttu-id="5e067-122">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="5e067-122">Record type</span></span>|<span data-ttu-id="5e067-123">Nome</span><span class="sxs-lookup"><span data-stu-id="5e067-123">Name</span></span>|<span data-ttu-id="5e067-124">TTL</span><span class="sxs-lookup"><span data-stu-id="5e067-124">TTL</span></span>|<span data-ttu-id="5e067-125">Valor</span><span class="sxs-lookup"><span data-stu-id="5e067-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="5e067-126">SRV</span><span class="sxs-lookup"><span data-stu-id="5e067-126">SRV</span></span>|<span data-ttu-id="5e067-127">_sipfederationtls. _ TCP</span><span class="sxs-lookup"><span data-stu-id="5e067-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="5e067-128">3600</span><span class="sxs-lookup"><span data-stu-id="5e067-128">3600</span></span>|<span data-ttu-id="5e067-129">100 1 5061 sipfed. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="5e067-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="5e067-130">SRV</span><span class="sxs-lookup"><span data-stu-id="5e067-130">SRV</span></span>|<span data-ttu-id="5e067-131">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="5e067-131">_sip._tls</span></span>|<span data-ttu-id="5e067-132">3600</span><span class="sxs-lookup"><span data-stu-id="5e067-132">3600</span></span>|<span data-ttu-id="5e067-133">100 1 443 sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="5e067-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="5e067-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="5e067-134">CNAME</span></span>| <span data-ttu-id="5e067-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5e067-135">lyncdiscover</span></span>|   <span data-ttu-id="5e067-136">3600</span><span class="sxs-lookup"><span data-stu-id="5e067-136">3600</span></span>|   <span data-ttu-id="5e067-137">Webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="5e067-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="5e067-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="5e067-138">CNAME</span></span>| <span data-ttu-id="5e067-139">sip</span><span class="sxs-lookup"><span data-stu-id="5e067-139">sip</span></span>|    <span data-ttu-id="5e067-140">3600</span><span class="sxs-lookup"><span data-stu-id="5e067-140">3600</span></span>|   <span data-ttu-id="5e067-141">sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="5e067-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="5e067-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="5e067-142">CNAME</span></span>| <span data-ttu-id="5e067-143">cumpra</span><span class="sxs-lookup"><span data-stu-id="5e067-143">meet</span></span>|   <span data-ttu-id="5e067-144">3600</span><span class="sxs-lookup"><span data-stu-id="5e067-144">3600</span></span>|   <span data-ttu-id="5e067-145">Webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="5e067-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="5e067-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="5e067-146">CNAME</span></span>| <span data-ttu-id="5e067-147">Dialin</span><span class="sxs-lookup"><span data-stu-id="5e067-147">dialin</span></span>  |<span data-ttu-id="5e067-148">3600</span><span class="sxs-lookup"><span data-stu-id="5e067-148">3600</span></span>|  <span data-ttu-id="5e067-149">Webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="5e067-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="5e067-150">*Desabilitar o espaço de endereçamento SIP compartilhado no locatário do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="5e067-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="5e067-151">O comando a seguir precisa ser feito de uma janela do PowerShell do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="5e067-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="5e067-152">*Desabilitar a capacidade no local para se comunicar com o Office 365.*</span><span class="sxs-lookup"><span data-stu-id="5e067-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="5e067-153">O comando a seguir precisa ser feito a partir de uma janela do PowerShell local.</span><span class="sxs-lookup"><span data-stu-id="5e067-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="5e067-154">Se você importou uma sessão do Skype for Business online anteriormente, inicie uma nova sessão do PowerShell do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="5e067-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="5e067-155">Confira também</span><span class="sxs-lookup"><span data-stu-id="5e067-155">See also</span></span>

[<span data-ttu-id="5e067-156">Consolidação de nuvem para Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5e067-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
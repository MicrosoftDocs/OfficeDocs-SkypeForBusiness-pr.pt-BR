---
title: Desabilitar híbrido para concluir a migração para a nuvem
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui as etapas detalhadas para desativando híbrida como parte da consolidação de nuvem para equipes e Skype para negócios.
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247602"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="ef69f-103">Desabilitar híbrido para concluir a migração para a nuvem</span><span class="sxs-lookup"><span data-stu-id="ef69f-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="ef69f-104">Depois que tiver movido todos os usuários no local para a nuvem, você poderá encerrar o Skype local para implantação de negócios.</span><span class="sxs-lookup"><span data-stu-id="ef69f-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="ef69f-105">Além dos removendo qualquer hardware, uma etapa importante é separar logicamente essa implantação local do Office 365, desativando híbrida.</span><span class="sxs-lookup"><span data-stu-id="ef69f-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="ef69f-106">Desabilitando híbrida consiste em 3 etapas:</span><span class="sxs-lookup"><span data-stu-id="ef69f-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="ef69f-107">Atualize registros DNS para apontar para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ef69f-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="ef69f-108">Desabilite a divisão de domínios no Office 365 inquilino.</span><span class="sxs-lookup"><span data-stu-id="ef69f-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="ef69f-109">Desabilite a capacidade em prem de se comunicar com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ef69f-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="ef69f-110">Estas etapas devem ser feitas juntos como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="ef69f-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="ef69f-111">Detalhes são fornecidas abaixo.</span><span class="sxs-lookup"><span data-stu-id="ef69f-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="ef69f-112">Em casos raros, a mudança do DNS de apontando no local para o Office 365 para sua organização pode causar federação com outras organizações parem de funcionar até que a outra organização atualiza sua configuração de Federação:</span><span class="sxs-lookup"><span data-stu-id="ef69f-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="ef69f-113">Qualquer organizações federadas que estiver usando o modelo de Federação direta mais antigo (também conhecido como servidor de parceiro permitido) serão necessário atualizar suas entradas de domínios permitidos para sua organização remover o FQDN do proxy.</span><span class="sxs-lookup"><span data-stu-id="ef69f-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="ef69f-114">Este modelo de Federação herdada não é baseado em registros SRV de DNS, portanto, tal configuração se tornará desatualizada depois que a sua organização se move para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="ef69f-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="ef69f-115">Qualquer organização federada que não tem um provedor de hospedagem habilitado para sipfed.online.lync. <span>com precisará atualizem sua configuração para permitir que.</span><span class="sxs-lookup"><span data-stu-id="ef69f-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="ef69f-116">Essa situação é possível apenas se a organização federada é puramente no local e nunca tiver federado com qualquer híbrido ou Locatário online.</span><span class="sxs-lookup"><span data-stu-id="ef69f-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="ef69f-117">Nesse caso, a federação com essas organizações não funcionará até que eles permitem que o seu provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="ef69f-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="ef69f-118">Se você suspeitar de que qualquer um dos seus parceiros federados podem estar usando a federação direta ou tenham federado com qualquer online ou organização híbrida, sugerimos que você envia-lhes uma comunicação sobre isso conforme você prepara para completar sua migração para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="ef69f-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="ef69f-119">*Atualize o DNS para apontar para o Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ef69f-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="ef69f-120">O DNS externo para a organização local da organização precisa ser atualizada para que Skype para registros de negócios apontem para o Office 365, em vez de implantação no local.</span><span class="sxs-lookup"><span data-stu-id="ef69f-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="ef69f-121">Especificamente:</span><span class="sxs-lookup"><span data-stu-id="ef69f-121">Specifically:</span></span>

    |<span data-ttu-id="ef69f-122">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="ef69f-122">Record type</span></span>|<span data-ttu-id="ef69f-123">Nome</span><span class="sxs-lookup"><span data-stu-id="ef69f-123">Name</span></span>|<span data-ttu-id="ef69f-124">TTL</span><span class="sxs-lookup"><span data-stu-id="ef69f-124">TTL</span></span>|<span data-ttu-id="ef69f-125">Valor</span><span class="sxs-lookup"><span data-stu-id="ef69f-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="ef69f-126">SRV</span><span class="sxs-lookup"><span data-stu-id="ef69f-126">SRV</span></span>|<span data-ttu-id="ef69f-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="ef69f-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="ef69f-128">3600</span><span class="sxs-lookup"><span data-stu-id="ef69f-128">3600</span></span>|<span data-ttu-id="ef69f-129">100 1 5061 sipfed.online.lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ef69f-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ef69f-130">SRV</span><span class="sxs-lookup"><span data-stu-id="ef69f-130">SRV</span></span>|<span data-ttu-id="ef69f-131">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="ef69f-131">_sip._tls</span></span>|<span data-ttu-id="ef69f-132">3600</span><span class="sxs-lookup"><span data-stu-id="ef69f-132">3600</span></span>|<span data-ttu-id="ef69f-133">100 1 443 sipdir.online.lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ef69f-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ef69f-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef69f-134">CNAME</span></span>| <span data-ttu-id="ef69f-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ef69f-135">lyncdiscover</span></span>|   <span data-ttu-id="ef69f-136">3600</span><span class="sxs-lookup"><span data-stu-id="ef69f-136">3600</span></span>|   <span data-ttu-id="ef69f-137">WebDir.online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ef69f-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ef69f-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef69f-138">CNAME</span></span>| <span data-ttu-id="ef69f-139">SIP</span><span class="sxs-lookup"><span data-stu-id="ef69f-139">sip</span></span>|    <span data-ttu-id="ef69f-140">3600</span><span class="sxs-lookup"><span data-stu-id="ef69f-140">3600</span></span>|   <span data-ttu-id="ef69f-141">sipdir.online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ef69f-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ef69f-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef69f-142">CNAME</span></span>| <span data-ttu-id="ef69f-143">reunir</span><span class="sxs-lookup"><span data-stu-id="ef69f-143">meet</span></span>|   <span data-ttu-id="ef69f-144">3600</span><span class="sxs-lookup"><span data-stu-id="ef69f-144">3600</span></span>|   <span data-ttu-id="ef69f-145">WebDir.online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ef69f-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ef69f-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="ef69f-146">CNAME</span></span>| <span data-ttu-id="ef69f-147">Dialin</span><span class="sxs-lookup"><span data-stu-id="ef69f-147">dialin</span></span>  |<span data-ttu-id="ef69f-148">3600</span><span class="sxs-lookup"><span data-stu-id="ef69f-148">3600</span></span>|  <span data-ttu-id="ef69f-149">WebDir.online.Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="ef69f-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="ef69f-150">*Desabilite o espaço de endereçamento SIP compartilhado no locatário do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ef69f-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="ef69f-151">O comando a seguir deve ser feito a partir de um Skype para negócios Online PowerShell janela.</span><span class="sxs-lookup"><span data-stu-id="ef69f-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="ef69f-152">*Desabilite a capacidade em prem de se comunicar com o Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ef69f-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="ef69f-153">O comando a seguir deve ser feito a partir de uma janela do PowerShell no local.</span><span class="sxs-lookup"><span data-stu-id="ef69f-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="ef69f-154">Se você importou anteriormente um Skype para sessão Business Online, inicie um novo Skype para a sessão do PowerShell de negócios.</span><span class="sxs-lookup"><span data-stu-id="ef69f-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="ef69f-155">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ef69f-155">See also</span></span>

[<span data-ttu-id="ef69f-156">Consolidação de nuvem para equipes e Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="ef69f-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
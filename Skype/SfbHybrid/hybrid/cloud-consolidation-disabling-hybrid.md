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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Este apêndice inclui etapas detalhadas para desabilitar o híbrido como parte da consolidação em nuvem para o Teams e o Skype for Business.
ms.openlocfilehash: 053d632b5a07b7ce7cca8ef7a1ddf45a673bcf59
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780140"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="33f3a-103">Desabilitar a migração híbrida para concluir a nuvem</span><span class="sxs-lookup"><span data-stu-id="33f3a-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="33f3a-104">Depois de mover todos os usuários do local para a nuvem, você poderá desativar a implantação do Skype for Business local.</span><span class="sxs-lookup"><span data-stu-id="33f3a-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="33f3a-105">Além de remover qualquer hardware, uma etapa crítica é separar logicamente essa implantação local do Office 365, desativando a configuração híbrida.</span><span class="sxs-lookup"><span data-stu-id="33f3a-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="33f3a-106">A desabilitação híbrida consiste em três etapas:</span><span class="sxs-lookup"><span data-stu-id="33f3a-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="33f3a-107">Atualização dos registros DNS para apontar para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="33f3a-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="33f3a-108">Desabilite o domínio dividido na organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="33f3a-108">Disable split domain in the Office 365 organization.</span></span>

3. <span data-ttu-id="33f3a-109">Desabilite a capacidade no local para se comunicar com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="33f3a-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="33f3a-110">Essas etapas devem ser feitas juntas como uma unidade.</span><span class="sxs-lookup"><span data-stu-id="33f3a-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="33f3a-111">Os detalhes são fornecidos abaixo.</span><span class="sxs-lookup"><span data-stu-id="33f3a-111">Details are provided below.</span></span> <span data-ttu-id="33f3a-112">Além disso, as diretrizes são fornecidas para o gerenciamento de números de telefone para usuários migrados depois que a implantação local é desconectada.</span><span class="sxs-lookup"><span data-stu-id="33f3a-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="33f3a-113">Em casos raros, alterar o DNS de apontar para local para o Office 365 para sua organização pode fazer com que a Federação com algumas outras organizações pare de funcionar até que outra organização Atualize sua configuração de Federação:</span><span class="sxs-lookup"><span data-stu-id="33f3a-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="33f3a-114">Todas as organizações federadas que usam o modelo de Federação direta mais antigo (também conhecido como servidor parceiro permitido) precisarão atualizar suas entradas de domínio permitidas para sua organização para remover o FQDN do proxy.</span><span class="sxs-lookup"><span data-stu-id="33f3a-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="33f3a-115">Esse modelo de Federação herdado não é baseado nos registros SRV DNS, portanto, essa configuração se tornará desatualizada quando sua organização for movida para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="33f3a-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="33f3a-116">Qualquer organização federada que não tenha um provedor de hospedagem habilitado para sipfed. online. Lync. <span>com precisará atualizar sua configuração para habilitar isso.</span><span class="sxs-lookup"><span data-stu-id="33f3a-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="33f3a-117">Essa situação só é possível se a organização federada estiver exclusivamente local e nunca federada com nenhum locatário híbrido ou online.</span><span class="sxs-lookup"><span data-stu-id="33f3a-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="33f3a-118">Nesse caso, a Federação com essas organizações não funcionará até que o provedor de hospedagem seja habilitado.</span><span class="sxs-lookup"><span data-stu-id="33f3a-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="33f3a-119">Se você suspeita que qualquer um dos seus parceiros federados pode usar Federação direta ou federado com qualquer organização online ou híbrida, sugerimos que você envie uma comunicação sobre isso ao se preparar para concluir a migração para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="33f3a-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="33f3a-120">*Atualize o DNS para apontar para o Office 365.*</span><span class="sxs-lookup"><span data-stu-id="33f3a-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="33f3a-121">O DNS externo da organização para a organização local precisa ser atualizado para que os registros do Skype for Business apontem para o Office 365 em vez da implantação local.</span><span class="sxs-lookup"><span data-stu-id="33f3a-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="33f3a-122">Especificamente:</span><span class="sxs-lookup"><span data-stu-id="33f3a-122">Specifically:</span></span>

    |<span data-ttu-id="33f3a-123">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="33f3a-123">Record type</span></span>|<span data-ttu-id="33f3a-124">Nome</span><span class="sxs-lookup"><span data-stu-id="33f3a-124">Name</span></span>|<span data-ttu-id="33f3a-125">TTL</span><span class="sxs-lookup"><span data-stu-id="33f3a-125">TTL</span></span>|<span data-ttu-id="33f3a-126">Valor</span><span class="sxs-lookup"><span data-stu-id="33f3a-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="33f3a-127">SRV</span><span class="sxs-lookup"><span data-stu-id="33f3a-127">SRV</span></span>|<span data-ttu-id="33f3a-128">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="33f3a-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="33f3a-129">3600</span><span class="sxs-lookup"><span data-stu-id="33f3a-129">3600</span></span>|<span data-ttu-id="33f3a-130">100 1 5061 sipfed. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="33f3a-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="33f3a-131">SRV</span><span class="sxs-lookup"><span data-stu-id="33f3a-131">SRV</span></span>|<span data-ttu-id="33f3a-132">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="33f3a-132">_sip._tls</span></span>|<span data-ttu-id="33f3a-133">3600</span><span class="sxs-lookup"><span data-stu-id="33f3a-133">3600</span></span>|<span data-ttu-id="33f3a-134">100 1 443 sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="33f3a-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="33f3a-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="33f3a-135">CNAME</span></span>| <span data-ttu-id="33f3a-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="33f3a-136">lyncdiscover</span></span>|   <span data-ttu-id="33f3a-137">3600</span><span class="sxs-lookup"><span data-stu-id="33f3a-137">3600</span></span>|   <span data-ttu-id="33f3a-138">Webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="33f3a-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="33f3a-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="33f3a-139">CNAME</span></span>| <span data-ttu-id="33f3a-140">sip</span><span class="sxs-lookup"><span data-stu-id="33f3a-140">sip</span></span>|    <span data-ttu-id="33f3a-141">3600</span><span class="sxs-lookup"><span data-stu-id="33f3a-141">3600</span></span>|   <span data-ttu-id="33f3a-142">sipdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="33f3a-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="33f3a-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="33f3a-143">CNAME</span></span>| <span data-ttu-id="33f3a-144">cumpra</span><span class="sxs-lookup"><span data-stu-id="33f3a-144">meet</span></span>|   <span data-ttu-id="33f3a-145">3600</span><span class="sxs-lookup"><span data-stu-id="33f3a-145">3600</span></span>|   <span data-ttu-id="33f3a-146">Webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="33f3a-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="33f3a-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="33f3a-147">CNAME</span></span>| <span data-ttu-id="33f3a-148">Dialin</span><span class="sxs-lookup"><span data-stu-id="33f3a-148">dialin</span></span>  |<span data-ttu-id="33f3a-149">3600</span><span class="sxs-lookup"><span data-stu-id="33f3a-149">3600</span></span>|  <span data-ttu-id="33f3a-150">Webdir. online. Lync. <span>com</span><span class="sxs-lookup"><span data-stu-id="33f3a-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="33f3a-151">*Desabilitar o espaço de endereçamento SIP compartilhado na organização do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="33f3a-151">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="33f3a-152">O comando a seguir precisa ser feito de uma janela do PowerShell do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="33f3a-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="33f3a-153">*Desabilitar a capacidade no local para se comunicar com o Office 365.*</span><span class="sxs-lookup"><span data-stu-id="33f3a-153">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="33f3a-154">O comando abaixo precisa ser feito de uma janela do PowerShell local:</span><span class="sxs-lookup"><span data-stu-id="33f3a-154">The command below needs to be done from an on-premises PowerShell window:</span></span>
```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="33f3a-155">Gerenciar números de telefone para usuários que foram migrados do local</span><span class="sxs-lookup"><span data-stu-id="33f3a-155">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="33f3a-156">Os administradores podem gerenciar os usuários que foram movidos anteriormente de um Skype for Business Server local para a nuvem, mesmo depois que a implantação local é descomissionada.</span><span class="sxs-lookup"><span data-stu-id="33f3a-156">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="33f3a-157">Há duas possibilidades diferentes:</span><span class="sxs-lookup"><span data-stu-id="33f3a-157">There are two different possibilities:</span></span>

- <span data-ttu-id="33f3a-158">O usuário não tinha um valor para LineURI no local antes da movimentação.</span><span class="sxs-lookup"><span data-stu-id="33f3a-158">The user did not have a value for LineURI on-premises before the move.</span></span> 

  <span data-ttu-id="33f3a-159">Nesse caso, você pode modificar o LineURI usando os parâmetros-onpremLineUri no [cmdlet Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) no módulo PowerShell do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="33f3a-159">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

- <span data-ttu-id="33f3a-160">O usuário tinha um LineURI local antes da movimentação (supostamente porque o usuário foi habilitado para o Enterprise Voice).</span><span class="sxs-lookup"><span data-stu-id="33f3a-160">The user had a LineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="33f3a-161">Se quiser alterar o LineURI, você deve fazer isso no Active Directory local e deixar o valor fluir para o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="33f3a-161">If you want to change the LineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="33f3a-162">Isso não requer o Skype for Business Server local.</span><span class="sxs-lookup"><span data-stu-id="33f3a-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="33f3a-163">Em vez disso, esse atributo, msRTCSIP, pode ser editado diretamente no Active Directory local, usando o snap-in usuários e computadores do Active Directory do MMC ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33f3a-163">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="33f3a-164">Se você estiver usando o snap-in do MMC, abra na página de propriedades do usuário, clique na guia Editor de atributo e encontre msRTCSIP.</span><span class="sxs-lookup"><span data-stu-id="33f3a-164">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Ferramenta usuários e computadores do Active Directory](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="33f3a-166">Confira também</span><span class="sxs-lookup"><span data-stu-id="33f3a-166">See also</span></span>

[<span data-ttu-id="33f3a-167">Consolidação de nuvem para Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="33f3a-167">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

---
title: Configurar um controlador de borda da sessão para vários locatários
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Saiba como configurar um SBC (controlador de borda de sessão) para atender a vários locatários.
ms.openlocfilehash: 5392359307d97e010f86d3bb71f2f7c3f3d1ffb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290465"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="ce698-103">Configurar um controlador de borda da sessão para vários locatários</span><span class="sxs-lookup"><span data-stu-id="ce698-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="ce698-104">O roteamento direto suporta a configuração de um SBC (controlador de borda de sessão) para atender a vários locatários.</span><span class="sxs-lookup"><span data-stu-id="ce698-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="ce698-105">Esse cenário foi projetado para operadoras de parceiros da Microsoft e/ou PSTN, conhecidos como transportadoras mais adiante neste documento.</span><span class="sxs-lookup"><span data-stu-id="ce698-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="ce698-106">Uma operadora vende serviços de telefonia entregues ao Microsoft Teams para seus clientes.</span><span class="sxs-lookup"><span data-stu-id="ce698-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="ce698-107">Uma operadora:</span><span class="sxs-lookup"><span data-stu-id="ce698-107">A carrier:</span></span>
- <span data-ttu-id="ce698-108">Implanta e gerencia um SBC em seu datacenter (os clientes não precisam implementar um SBC e eles recebem serviços de telefonia da operadora no cliente do Teams).</span><span class="sxs-lookup"><span data-stu-id="ce698-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="ce698-109">Interconecta o SBC a vários locatários.</span><span class="sxs-lookup"><span data-stu-id="ce698-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="ce698-110">Fornece serviços PSTN aos clientes.</span><span class="sxs-lookup"><span data-stu-id="ce698-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="ce698-111">Gerencia a qualidade da chamada de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="ce698-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="ce698-112">Cobranças separadamente para serviços PSTN.</span><span class="sxs-lookup"><span data-stu-id="ce698-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="ce698-113">A Microsoft não gerencia operadoras.</span><span class="sxs-lookup"><span data-stu-id="ce698-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="ce698-114">A Microsoft oferece um PBX (Microsoft Phone System) e um cliente do Teams, certifica telefones e certifica SBCs que podem ser usados com o sistema telefônico da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ce698-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="ce698-115">Antes de escolher uma operadora, certifique-se de que sua escolha tem um SBC certificado e pode gerenciar a qualidade de voz de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="ce698-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="ce698-116">Veja a seguir as etapas de implementação técnica para configurar o cenário.</span><span class="sxs-lookup"><span data-stu-id="ce698-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="ce698-117">**Somente portadora:**</span><span class="sxs-lookup"><span data-stu-id="ce698-117">**Carrier only:**</span></span>
1. <span data-ttu-id="ce698-118">Implante o SBC e configure-o para o cenário de Hospedagem de acordo com as [instruções dos fornecedores de SBC certificados](#deploy-and-configure-the-sbc).</span><span class="sxs-lookup"><span data-stu-id="ce698-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="ce698-119">Registre um nome de domínio base no locatário da operadora e solicite um certificado curinga.</span><span class="sxs-lookup"><span data-stu-id="ce698-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="ce698-120">Registre um subdomínio para cada cliente, que faz parte do domínio base.</span><span class="sxs-lookup"><span data-stu-id="ce698-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="ce698-121">**Operadora com um administrador global do cliente:**</span><span class="sxs-lookup"><span data-stu-id="ce698-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="ce698-122">Adicione o nome de subdomínio ao locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="ce698-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="ce698-123">Ativar o nome do subdomínio.</span><span class="sxs-lookup"><span data-stu-id="ce698-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="ce698-124">Configure o tronco da transportadora para o locatário do cliente e provisionar usuários.</span><span class="sxs-lookup"><span data-stu-id="ce698-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="ce698-125">*Certifique-se de compreender noções básicas de DNS e como o nome de domínio é gerenciado no Office 365. Examine [a ajuda para obter ajuda com os domínios do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) antes de continuar.*</span><span class="sxs-lookup"><span data-stu-id="ce698-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="ce698-126">Implantar e configurar o SBC</span><span class="sxs-lookup"><span data-stu-id="ce698-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="ce698-127">Para ver as etapas detalhadas sobre como implantar e configurar o SBCs para um cenário de hospedagem SBC, consulte a documentação do fornecedor do SBC.</span><span class="sxs-lookup"><span data-stu-id="ce698-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="ce698-128">**AudioCodes:** [Rotas diretas de configuração de roteamento](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), a configuração do cenário de Hospedagem de SBC descrito em "conectando AudioCodes SBC para a Microsoft Teams Direct Routing Host Configuration model observação".</span><span class="sxs-lookup"><span data-stu-id="ce698-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="ce698-129">**Comunicações da faixa** de opções:  Consulte o guia de [configuração do Microsoft Teams SBC da faixa](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) de opções do Microsoft Teams para obter a documentação sobre como configurar a faixa de opções da faixa de opções SBCS e para esta página de [práticas recomendadas-configurando as operadoras do Microsoft Teams Direct Margem](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="ce698-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>

> [!NOTE]
> <span data-ttu-id="ce698-130">Preste atenção em como configurar o cabeçalho "contato".</span><span class="sxs-lookup"><span data-stu-id="ce698-130">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="ce698-131">O cabeçalho do contato é usado para localizar o locatário do cliente na mensagem de convite de entrada.</span><span class="sxs-lookup"><span data-stu-id="ce698-131">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="ce698-132">Registrar um domínio base e subdomínios</span><span class="sxs-lookup"><span data-stu-id="ce698-132">Register a base domain and subdomains</span></span>

<span data-ttu-id="ce698-133">Para o cenário de hospedagem, você precisa criar:</span><span class="sxs-lookup"><span data-stu-id="ce698-133">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="ce698-134">Um nome de domínio base pertencente à transportadora.</span><span class="sxs-lookup"><span data-stu-id="ce698-134">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="ce698-135">Um subdomínio que faz parte do nome do domínio base em cada locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="ce698-135">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="ce698-136">No exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="ce698-136">In the following example:</span></span>
- <span data-ttu-id="ce698-137">Adatum é uma operadora que atende vários clientes fornecendo serviços de telefonia e de Internet.</span><span class="sxs-lookup"><span data-stu-id="ce698-137">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="ce698-138">Woodgrove Bank, contoso e Adventure Works são três clientes que têm domínios do Office 365, mas recebem os serviços de telefonia do adatum.</span><span class="sxs-lookup"><span data-stu-id="ce698-138">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="ce698-139">Subdomínios **devem** coincidir com o nome FQDN do tronco que será configurado para o cliente e o FQDN no cabeçalho do contato ao enviar o convite para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce698-139">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="ce698-140">Quando chega uma chamada na interface de roteamento direto do Office 365, a interface usa o cabeçalho do contato para localizar o locatário onde o usuário deve ser pesquisado.</span><span class="sxs-lookup"><span data-stu-id="ce698-140">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="ce698-141">O roteamento direto não usa a pesquisa de número de telefone no convite, pois alguns clientes podem ter números não-participantes que podem sobrepor-se a vários locatários.</span><span class="sxs-lookup"><span data-stu-id="ce698-141">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="ce698-142">Portanto, o nome FQDN no cabeçalho do contato é necessário para identificar o locatário exato para pesquisar o usuário pelo número de telefone.</span><span class="sxs-lookup"><span data-stu-id="ce698-142">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="ce698-143">*Consulte [obter ajuda com os domínios do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre como criar nomes de domínio nos locatários do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ce698-143">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="ce698-144">O diagrama a seguir resume os requisitos para o domínio base, subdomínios e cabeçalho de contato.</span><span class="sxs-lookup"><span data-stu-id="ce698-144">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![Requisitos para domínio base, subdomínios e cabeçalho de contato](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="ce698-146">O SBC exige um certificado para autenticar as conexões.</span><span class="sxs-lookup"><span data-stu-id="ce698-146">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="ce698-147">Para o cenário de hospedagem SBC, a transportadora precisa solicitar um certificado com San \* \*. base_domain (por \*exemplo, Customers.adatum.biz)\*.</span><span class="sxs-lookup"><span data-stu-id="ce698-147">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="ce698-148">Esse certificado pode ser usado para autenticar conexões para vários locatários servidos a partir de um único SBC.</span><span class="sxs-lookup"><span data-stu-id="ce698-148">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="ce698-149">A tabela a seguir é um exemplo de uma configuração.</span><span class="sxs-lookup"><span data-stu-id="ce698-149">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="ce698-150">Novo nome de domínio</span><span class="sxs-lookup"><span data-stu-id="ce698-150">New domain name</span></span> |<span data-ttu-id="ce698-151">Tipo</span><span class="sxs-lookup"><span data-stu-id="ce698-151">Type</span></span>|<span data-ttu-id="ce698-152">Removido</span><span class="sxs-lookup"><span data-stu-id="ce698-152">Registered</span></span>  |<span data-ttu-id="ce698-153">SAN de certificado para SBC</span><span class="sxs-lookup"><span data-stu-id="ce698-153">Certificate SAN for SBC</span></span>  |<span data-ttu-id="ce698-154">Domínio padrão do locatário no exemplo</span><span class="sxs-lookup"><span data-stu-id="ce698-154">Tenant default domain in the example</span></span>  |<span data-ttu-id="ce698-155">Nome FQDN que o SBC deve apresentar no cabeçalho do contato ao enviar chamadas para usuários</span><span class="sxs-lookup"><span data-stu-id="ce698-155">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="ce698-156">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-156">customers.adatum.biz</span></span>|    <span data-ttu-id="ce698-157">Polybase</span><span class="sxs-lookup"><span data-stu-id="ce698-157">Base</span></span>     |     <span data-ttu-id="ce698-158">No locatário da operadora</span><span class="sxs-lookup"><span data-stu-id="ce698-158">In carrier tenant</span></span>  |    <span data-ttu-id="ce698-159">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-159">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="ce698-160">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-160">adatum.biz</span></span>      |<span data-ttu-id="ce698-161">No, este é um locatário de serviço, nenhum usuário</span><span class="sxs-lookup"><span data-stu-id="ce698-161">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="ce698-162">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-162">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="ce698-163">Subdomínio</span><span class="sxs-lookup"><span data-stu-id="ce698-163">Subdomain</span></span>  |    <span data-ttu-id="ce698-164">Em um locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="ce698-164">In a customer tenant</span></span>  |    <span data-ttu-id="ce698-165">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-165">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="ce698-166">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="ce698-166">woodgrovebank.us</span></span>  |  <span data-ttu-id="ce698-167">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-167">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="ce698-168">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-168">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="ce698-169">Subdomínio</span><span class="sxs-lookup"><span data-stu-id="ce698-169">Subdomain</span></span> | <span data-ttu-id="ce698-170">Em um locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="ce698-170">In a customer tenant</span></span>   |   <span data-ttu-id="ce698-171">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-171">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="ce698-172">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce698-172">contoso.com</span></span>   |<span data-ttu-id="ce698-173">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-173">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="ce698-174">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-174">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="ce698-175">Subdomínio</span><span class="sxs-lookup"><span data-stu-id="ce698-175">Subdomain</span></span> | <span data-ttu-id="ce698-176">Em um locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="ce698-176">In a customer tenant</span></span> |   <span data-ttu-id="ce698-177">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-177">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="ce698-178">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="ce698-178">adventureworks.com</span></span> | <span data-ttu-id="ce698-179">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-179">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="ce698-180">Para configurar a base e subdomínios, siga as etapas descritas abaixo.</span><span class="sxs-lookup"><span data-stu-id="ce698-180">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="ce698-181">No exemplo, configuraremos um nome de domínio base (customers.adatum.biz) e um subdomínio para um cliente (sbc1.customers.adatum.biz no locatário do Woodgrove Bank).</span><span class="sxs-lookup"><span data-stu-id="ce698-181">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="ce698-182">Registrar um nome de domínio base no locatário da operadora</span><span class="sxs-lookup"><span data-stu-id="ce698-182">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="ce698-183">**Essas ações são executadas no locatário da operadora.**</span><span class="sxs-lookup"><span data-stu-id="ce698-183">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="ce698-184">Certifique-se de ter os direitos apropriados no locatário da operadora</span><span class="sxs-lookup"><span data-stu-id="ce698-184">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="ce698-185">Você só poderá adicionar novos domínios se tiver entrado no centro de administração do Microsoft 365 como administrador global.</span><span class="sxs-lookup"><span data-stu-id="ce698-185">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="ce698-186">Para validar a função que você tem, entre no centro de administração do Microsoft 365 (https://portal.office.com), vá para \*\*\*\* > usuários**ativos**do Microsoft e verifique se você tem uma função de administrador global.</span><span class="sxs-lookup"><span data-stu-id="ce698-186">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="ce698-187">Para obter mais informações sobre funções de administrador e como atribuir uma função no Office 365, consulte [sobre as funções de administrador do office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="ce698-187">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="ce698-188">Adicionar um domínio base ao locatário e verificá-lo</span><span class="sxs-lookup"><span data-stu-id="ce698-188">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="ce698-189">No centro de administração do Microsoft 365, vá para **Configurar** > **domínios** > **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="ce698-189">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="ce698-190">Na caixa **Insira um domínio que você possui** , digite o FQDN do domínio base.</span><span class="sxs-lookup"><span data-stu-id="ce698-190">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="ce698-191">No exemplo a seguir, o domínio base é *Customers.adatum.biz*.</span><span class="sxs-lookup"><span data-stu-id="ce698-191">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![Adicionando um domínio base](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="ce698-193">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="ce698-193">Click **Next**.</span></span>
4. <span data-ttu-id="ce698-194">No exemplo, o locatário já tem adatum.biz como um nome de domínio verificado.</span><span class="sxs-lookup"><span data-stu-id="ce698-194">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="ce698-195">O assistente não solicitará verificação adicional, pois customers.adatum.biz é um subdomínio para o nome já registrado.</span><span class="sxs-lookup"><span data-stu-id="ce698-195">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="ce698-196">No entanto, se você adicionar um FQDN que não tenha sido verificado antes, será necessário passar pelo processo de verificação.</span><span class="sxs-lookup"><span data-stu-id="ce698-196">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="ce698-197">O processo de verificação está [descrito abaixo](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span><span class="sxs-lookup"><span data-stu-id="ce698-197">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![Confirmação de um nome de domínio verificado](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="ce698-199">Clique em **Avançar**e, na página **Atualizar configurações de DNS** , selecione **eu mesmo adiciono os registros DNS** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ce698-199">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="ce698-200">Na próxima página, desmarque todos os valores (a menos que você queira usar o nome do domínio do Exchange, do SharePoint ou do teams/Skype for Business), clique em **Avançar**e, em seguida, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="ce698-200">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="ce698-201">Verifique se o novo domínio está no status de configuração concluída.</span><span class="sxs-lookup"><span data-stu-id="ce698-201">Make sure your new domain is in the Setup complete status.</span></span>

    ![Domínios mostrando o status de configuração concluída](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="ce698-203">Ativar o nome de domínio</span><span class="sxs-lookup"><span data-stu-id="ce698-203">Activate the domain name</span></span>

<span data-ttu-id="ce698-204">Depois de registrar um nome de domínio, você precisa ativá-lo adicionando pelo menos um usuário licenciado E1, E3 ou E5 e atribuindo um endereço SIP à parte FQDN do endereço SIP correspondente ao domínio base criado.</span><span class="sxs-lookup"><span data-stu-id="ce698-204">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="ce698-205">*Consulte [obter ajuda com os domínios do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre como adicionar usuários nos locatários do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ce698-205">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="ce698-206">Por exemplo: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-206">For example: test@customers.adatum.biz</span></span>

![Página de ativação de domínio base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="ce698-208">Registrar um nome de subdomínio em um locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="ce698-208">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="ce698-209">Será necessário criar um nome de subdomínio exclusivo para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="ce698-209">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="ce698-210">Neste exemplo, criaremos um subdomínio sbc1.customers.adatum.biz em um locatário com o nome de domínio padrão woodgrovebank.us.</span><span class="sxs-lookup"><span data-stu-id="ce698-210">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="ce698-211">**Todas as ações abaixo estão no locatário do cliente.**</span><span class="sxs-lookup"><span data-stu-id="ce698-211">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="ce698-212">Certifique-se de ter os direitos apropriados no locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="ce698-212">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="ce698-213">Você só poderá adicionar novos domínios se tiver entrado no centro de administração do Microsoft 365 como administrador global.</span><span class="sxs-lookup"><span data-stu-id="ce698-213">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="ce698-214">Para validar a função que você tem, entre no centro de administração do Microsoft 365 (https://portal.office.com), vá para \*\*\*\* > usuários**ativos**do Microsoft e verifique se você tem uma função de administrador global.</span><span class="sxs-lookup"><span data-stu-id="ce698-214">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="ce698-215">Para obter mais informações sobre funções de administrador e como atribuir uma função no Office 365, consulte [sobre as funções de administrador do office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="ce698-215">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="ce698-216">Adicionar um subdomínio ao locatário do cliente e verificá-lo</span><span class="sxs-lookup"><span data-stu-id="ce698-216">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="ce698-217">No centro de administração do Microsoft 365, vá para **Configurar** > **domínios** > **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="ce698-217">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="ce698-218">Na caixa **Insira um domínio que você possui** , digite o FQDN do subdomínio para esse locatário.</span><span class="sxs-lookup"><span data-stu-id="ce698-218">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="ce698-219">No exemplo a seguir, o subdomínio é sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="ce698-219">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![Adicionando um subdomínio do cliente](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="ce698-221">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="ce698-221">Click **Next**.</span></span>
4. <span data-ttu-id="ce698-222">O FQDN nunca foi registrado no locatário.</span><span class="sxs-lookup"><span data-stu-id="ce698-222">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="ce698-223">Na próxima etapa, será necessário verificar o domínio.</span><span class="sxs-lookup"><span data-stu-id="ce698-223">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="ce698-224">**Em vez disso, selecione Adicionar um registro txt**.</span><span class="sxs-lookup"><span data-stu-id="ce698-224">Select **Add a TXT record instead**.</span></span> 

    ![Opções na página verificar domínio](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="ce698-226">Clique em **Avançar**e observe o valor txt gerado para verificar o nome do domínio.</span><span class="sxs-lookup"><span data-stu-id="ce698-226">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![Registros de texto na página verificar domínio](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="ce698-228">Crie o registro TXT com o valor da etapa anterior no provedor de Hospedagem de DNS da transportadora.</span><span class="sxs-lookup"><span data-stu-id="ce698-228">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![Criando o registro TXT no provedor de hospedagem DNS da operadora](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="ce698-230">Para obter mais informações, consulte [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span><span class="sxs-lookup"><span data-stu-id="ce698-230">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="ce698-231">Volte para o centro de administração do Microsoft 365 do cliente e clique em **verificar**.</span><span class="sxs-lookup"><span data-stu-id="ce698-231">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="ce698-232">Na próxima página, selecione **adicionarei os registros de DNS** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ce698-232">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![Opções na página atualizar configurações de DNS](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="ce698-234">Na página **escolher seus serviços online** , desmarque todas as opções e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ce698-234">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![A página escolher seus serviços online](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="ce698-236">Clique em **concluir** na página **Atualizar configurações de DNS** .</span><span class="sxs-lookup"><span data-stu-id="ce698-236">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![A página atualizar configurações de DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="ce698-238">Certifique-se de que o status seja **configuração concluído**.</span><span class="sxs-lookup"><span data-stu-id="ce698-238">Ensure that the status is **Setup complete**.</span></span> 
    
    ![Página mostrando o status da configuração concluída](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="ce698-240">Ativar o nome do subdomínio</span><span class="sxs-lookup"><span data-stu-id="ce698-240">Activate the subdomain name</span></span>

<span data-ttu-id="ce698-241">Depois de registrar um nome de domínio, você precisa ativá-lo adicionando pelo menos um usuário e atribuir um endereço SIP à parte FQDN do endereço SIP correspondente ao subdomínio criado no locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="ce698-241">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="ce698-242">*Consulte [obter ajuda com os domínios do Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre como adicionar usuários nos locatários do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ce698-242">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="ce698-243">Por exemplo: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ce698-243">For example: test@sbc1.customers.adatum.biz</span></span>

![Ativação da página de subdomínio](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="ce698-245">Criar um tronco e provisionar usuários</span><span class="sxs-lookup"><span data-stu-id="ce698-245">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="ce698-246">Com base nos comentários que recebemos no programa de adoção técnica, a Microsoft pode alterar o processo de criação de troncos nos locatários do cliente para simplificar o processo.</span><span class="sxs-lookup"><span data-stu-id="ce698-246">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="ce698-247">Assista às atualizações da documentação nesta página e siga os Blogs da comunidade técnica da Microsoft para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ce698-247">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="ce698-248">Crie um tronco no domínio do cliente usando o comando New-CSonlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="ce698-248">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="ce698-249">O FQDN do tronco **deve** corresponder ao subdomínio criado para o cliente.</span><span class="sxs-lookup"><span data-stu-id="ce698-249">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="ce698-250">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ce698-250">For example:</span></span>

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

<span data-ttu-id="ce698-251">Ao criar o tronco, você pode receber a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="ce698-251">When creating the trunk, you may receive the following error message:</span></span>

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

<span data-ttu-id="ce698-252">Aguarde algum tempo para que o registro e a ativação do domínio se repliquem e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="ce698-252">Please allow some time for domain registration and activation to replicate and try again.</span></span>

<span data-ttu-id="ce698-253">Provisione usuários com os números de telefone e configure o roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="ce698-253">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="ce698-254">Para obter mais informações sobre o novo-CSOnlinePSTNGateway, os usuários de provisionamento e a configuração do roteamento de voz, consulte [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="ce698-254">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="ce698-255">Consulte as instruções do [fornecedor do SBC](#deploy-and-configure-the-sbc) sobre como configurar o envio do nome FQDN dos subdomínios no cabeçalho do contato.</span><span class="sxs-lookup"><span data-stu-id="ce698-255">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>


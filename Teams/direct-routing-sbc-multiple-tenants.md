---
title: Configurar um controlador de borda de sessão para vários locatários
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: ''
description: Saiba como configurar uma borda controlador sessão (SBC) para atender a vários locatários.
ms.openlocfilehash: 3073800a6c200bcaeffafb557d6ea149dee598cd
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23866455"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="57502-103">Configurar um controlador de borda de sessão para vários locatários</span><span class="sxs-lookup"><span data-stu-id="57502-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="57502-104">Roteamento direto suporta Configurando uma borda controlador sessão (SBC) para atender a vários locatários.</span><span class="sxs-lookup"><span data-stu-id="57502-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="57502-105">Este cenário foi projetado para parceiros da Microsoft e/ou operadoras PSTN, conhecidas como operadoras posteriormente contidas neste documento.</span><span class="sxs-lookup"><span data-stu-id="57502-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="57502-106">Uma operadora de telefonia vende entregues a Microsoft Teams aos clientes de serviços de telefonia.</span><span class="sxs-lookup"><span data-stu-id="57502-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="57502-107">Uma operadora de telefonia:</span><span class="sxs-lookup"><span data-stu-id="57502-107">A carrier:</span></span>
- <span data-ttu-id="57502-108">Implanta e gerencia um SBC em datacenters (os clientes não precisam implementar um SBC e recebem serviços de telefonia da operadora no cliente equipes).</span><span class="sxs-lookup"><span data-stu-id="57502-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="57502-109">Interconexão o SBC para vários locatários.</span><span class="sxs-lookup"><span data-stu-id="57502-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="57502-110">Fornece serviços PSTN para os clientes.</span><span class="sxs-lookup"><span data-stu-id="57502-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="57502-111">Gerencia a qualidade da chamada ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="57502-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="57502-112">Encargos separadamente para serviços PSTN.</span><span class="sxs-lookup"><span data-stu-id="57502-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="57502-113">Microsoft não gerencia operadoras.</span><span class="sxs-lookup"><span data-stu-id="57502-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="57502-114">Microsoft oferece um PBX (sistema de telefone da Microsoft) e um cliente de equipes, certifica telefones e certifica SBCs que podem ser usados com o sistema de telefone da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="57502-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="57502-115">Antes de escolher uma operadora de telefonia, verifique se sua escolha tem um SBC certificado e pode gerenciar a qualidade de voz ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="57502-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="57502-116">A seguir estão as etapas de implementação técnica para configurar o cenário.</span><span class="sxs-lookup"><span data-stu-id="57502-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="57502-117">**Operadora:**</span><span class="sxs-lookup"><span data-stu-id="57502-117">**Carrier only:**</span></span>
1. <span data-ttu-id="57502-118">Implante o SBC e configurá-lo para o cenário de hospedagem de acordo com as [instruções dos fornecedores certificados SBC](#deploy-and-configure-the-sbc).</span><span class="sxs-lookup"><span data-stu-id="57502-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="57502-119">Registrar um nome de domínio base no locatário operadora e solicitar um certificado curinga.</span><span class="sxs-lookup"><span data-stu-id="57502-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="57502-120">Registre um subdomínio para cada cliente, que é parte do domínio base.</span><span class="sxs-lookup"><span data-stu-id="57502-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="57502-121">**Operadora com um Administrador Global do cliente:**</span><span class="sxs-lookup"><span data-stu-id="57502-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="57502-122">Adicione o nome do subdomínio para o locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="57502-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="57502-123">Ative o nome do subdomínio.</span><span class="sxs-lookup"><span data-stu-id="57502-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="57502-124">Configure o tronco da operadora para os usuários de locatário e provisionar do cliente.</span><span class="sxs-lookup"><span data-stu-id="57502-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="57502-125">*Verifique se que você entendeu os fundamentos DNS e como o nome de domínio é gerenciado no Office 365. Revise a [obter ajuda com o Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) antes de continuar.*</span><span class="sxs-lookup"><span data-stu-id="57502-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="57502-126">Implantar e configurar o SBC</span><span class="sxs-lookup"><span data-stu-id="57502-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="57502-127">Para obter as etapas detalhadas sobre como implantar e configurar SBCs para um cenário de hospedagem de SBC, consulte a documentação do fornecedor SBC.</span><span class="sxs-lookup"><span data-stu-id="57502-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="57502-128">**AudioCodes:** [Notas de configuração de roteamento direto](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), a configuração do SBC hospedando o cenário descrito em "Connecting AudioCodes SBC à Microsoft Teams direto roteamento Hosting modelo configuração nota".</span><span class="sxs-lookup"><span data-stu-id="57502-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="57502-129">**Communications da faixa de opções:** Para cenários de hospedagem de SBC, somente a série de núcleo é suportada.</span><span class="sxs-lookup"><span data-stu-id="57502-129">**Ribbon Communications:** For SBC hosting scenarios, only the core series is supported.</span></span> <span data-ttu-id="57502-130">Consulte o [Guia de configuração da faixa de opções Communications SBC Core Microsoft equipes](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe).</span><span class="sxs-lookup"><span data-stu-id="57502-130">Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe).</span></span>

> [!NOTE]
> <span data-ttu-id="57502-131">Por favor, preste atenção como configurar o cabeçalho "Contato".</span><span class="sxs-lookup"><span data-stu-id="57502-131">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="57502-132">O cabeçalho de contato é usado para localizar o locatário do cliente na mensagem de entrada de convidar.</span><span class="sxs-lookup"><span data-stu-id="57502-132">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="57502-133">Registrar um domínio base e subdomínios</span><span class="sxs-lookup"><span data-stu-id="57502-133">Register a base domain and subdomains</span></span>

<span data-ttu-id="57502-134">Para o cenário de hospedagem, você precisa criar:</span><span class="sxs-lookup"><span data-stu-id="57502-134">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="57502-135">Um nome de domínio base pertencente a operadora.</span><span class="sxs-lookup"><span data-stu-id="57502-135">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="57502-136">Um subdomínio que faz parte do nome do domínio base em cada locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="57502-136">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="57502-137">No exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="57502-137">In the following example:</span></span>
- <span data-ttu-id="57502-138">Adatum é uma operadora de telefonia que serve de vários clientes fornecendo serviços de Internet e telefonia.</span><span class="sxs-lookup"><span data-stu-id="57502-138">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="57502-139">Woodgrove Bank, Contoso e Adventure Works são três clientes que tenham domínios do Office 365, mas recebem os serviços de telefonia de Adatum.</span><span class="sxs-lookup"><span data-stu-id="57502-139">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="57502-140">Subdomínios **deve** correspondem ao nome do FQDN do tronco que será configurado para o cliente e o FQDN no cabeçalho contato ao enviar o convite para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="57502-140">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="57502-141">Quando uma chamada chega a interface do roteamento direto do Office 365, a interface usa o cabeçalho de contato para encontrar o locatário onde o usuário deve ser consultado.</span><span class="sxs-lookup"><span data-stu-id="57502-141">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="57502-142">Roteamento direta não usa pesquisa de número de telefone no convite da, como alguns clientes podem ter não-números que podem sobrepor-se em vários locatários.</span><span class="sxs-lookup"><span data-stu-id="57502-142">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="57502-143">Portanto, o nome FQDN no cabeçalho do contato é necessária para identificar o locatário exato para consultar o usuário pelo número de telefone.</span><span class="sxs-lookup"><span data-stu-id="57502-143">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="57502-144">*Analise a [obter ajuda com o Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre como criar nomes de domínio em locatários do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="57502-144">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="57502-145">O diagrama a seguir resume os requisitos de domínio base, subdomínios e cabeçalho de contato.</span><span class="sxs-lookup"><span data-stu-id="57502-145">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![Requisitos de domínio base, subdomínios e cabeçalho de contato](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="57502-147">O SBC requer um certificado para autenticar as conexões.</span><span class="sxs-lookup"><span data-stu-id="57502-147">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="57502-148">Para o cenário de hospedagem de SBC, a operadora precisa solicitar um certificado com SAN \* \*.base_domain (por exemplo, \*customers.adatum.biz)\*.</span><span class="sxs-lookup"><span data-stu-id="57502-148">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="57502-149">Este certificado pode ser usado para autenticar conexões com vários locatários servidos de um único SBC.</span><span class="sxs-lookup"><span data-stu-id="57502-149">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="57502-150">A tabela a seguir está um exemplo de uma configuração.</span><span class="sxs-lookup"><span data-stu-id="57502-150">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="57502-151">Novo nome de domínio</span><span class="sxs-lookup"><span data-stu-id="57502-151">New domain name</span></span> |<span data-ttu-id="57502-152">Tipo</span><span class="sxs-lookup"><span data-stu-id="57502-152">Type</span></span>|<span data-ttu-id="57502-153">Registrado</span><span class="sxs-lookup"><span data-stu-id="57502-153">Registered</span></span>  |<span data-ttu-id="57502-154">Certificado SAN para SBC</span><span class="sxs-lookup"><span data-stu-id="57502-154">Certificate SAN for SBC</span></span>  |<span data-ttu-id="57502-155">Domínio de padrão de Inquilino no exemplo</span><span class="sxs-lookup"><span data-stu-id="57502-155">Tenant default domain in the example</span></span>  |<span data-ttu-id="57502-156">Nome do FQDN que SBC deve apresentar no cabeçalho contato ao enviar chamadas para usuários</span><span class="sxs-lookup"><span data-stu-id="57502-156">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="57502-157">Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-157">customers.adatum.biz</span></span>|    <span data-ttu-id="57502-158">Base</span><span class="sxs-lookup"><span data-stu-id="57502-158">Base</span></span>     |     <span data-ttu-id="57502-159">No locatário operadora</span><span class="sxs-lookup"><span data-stu-id="57502-159">In carrier tenant</span></span>  |    <span data-ttu-id="57502-160">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-160">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="57502-161">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-161">adatum.biz</span></span>      |<span data-ttu-id="57502-162">NA, este é um locatário de serviço, nenhum usuário</span><span class="sxs-lookup"><span data-stu-id="57502-162">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="57502-163">sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-163">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="57502-164">Subdomínio</span><span class="sxs-lookup"><span data-stu-id="57502-164">Subdomain</span></span>  |    <span data-ttu-id="57502-165">Em um locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="57502-165">In a customer tenant</span></span>  |    <span data-ttu-id="57502-166">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-166">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="57502-167">woodgrovebank.US</span><span class="sxs-lookup"><span data-stu-id="57502-167">woodgrovebank.us</span></span>  |  <span data-ttu-id="57502-168">sbc1.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-168">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="57502-169">sbc2.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-169">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="57502-170">Subdomínio</span><span class="sxs-lookup"><span data-stu-id="57502-170">Subdomain</span></span> | <span data-ttu-id="57502-171">Em um locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="57502-171">In a customer tenant</span></span>   |   <span data-ttu-id="57502-172">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-172">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="57502-173">Contoso.com</span><span class="sxs-lookup"><span data-stu-id="57502-173">contoso.com</span></span>   |<span data-ttu-id="57502-174">sbc2.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-174">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="57502-175">sbc3.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-175">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="57502-176">Subdomínio</span><span class="sxs-lookup"><span data-stu-id="57502-176">Subdomain</span></span> | <span data-ttu-id="57502-177">Em um locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="57502-177">In a customer tenant</span></span> |   <span data-ttu-id="57502-178">\*. customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-178">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="57502-179">AdventureWorks.com</span><span class="sxs-lookup"><span data-stu-id="57502-179">adventureworks.com</span></span> | <span data-ttu-id="57502-180">sbc3.Customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-180">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="57502-181">Para configurar a base e os subdomínios, siga as etapas descritas abaixo.</span><span class="sxs-lookup"><span data-stu-id="57502-181">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="57502-182">No exemplo, podemos configurar um nome de domínio básico (customers.adatum.biz) e um subdomínio para um cliente (sbc1.customers.adatum.biz no locatário Woodgrove Bank).</span><span class="sxs-lookup"><span data-stu-id="57502-182">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="57502-183">Registrar um nome de domínio base no locatário operadora</span><span class="sxs-lookup"><span data-stu-id="57502-183">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="57502-184">**Essas ações são executadas no locatário operadora.**</span><span class="sxs-lookup"><span data-stu-id="57502-184">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="57502-185">Certifique-se de que você tenha os direitos apropriados no locatário operadora</span><span class="sxs-lookup"><span data-stu-id="57502-185">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="57502-186">Você só pode adicionar novos domínios se você entrou no Centro de administração do Office 365, como um Administrador Global.</span><span class="sxs-lookup"><span data-stu-id="57502-186">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="57502-187">Para validar a função que você tiver, conecte-se ao centro de administração do Microsoft 365 (https://portal.office.com), vá para **usuários** > **Usuários ativos**e, em seguida, verifique se você possui uma função de Administrador Global.</span><span class="sxs-lookup"><span data-stu-id="57502-187">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="57502-188">Para obter mais informações sobre funções de administração e como atribuir uma função no Office 365, consulte [funções de administrador do Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="57502-188">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="57502-189">Adicionar um domínio de base para o inquilino e verifique se ele</span><span class="sxs-lookup"><span data-stu-id="57502-189">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="57502-190">No Centro de administração do Microsoft 365, vá para a **instalação** > **domínios** > **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="57502-190">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="57502-191">Na caixa **Digite um domínio em que você é proprietário** , digite o FQDN do domínio base.</span><span class="sxs-lookup"><span data-stu-id="57502-191">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="57502-192">No exemplo a seguir, o domínio de base é *customers.adatum.biz*.</span><span class="sxs-lookup"><span data-stu-id="57502-192">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![Adicionando um domínio de base](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="57502-194">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="57502-194">Click **Next**.</span></span>
4. <span data-ttu-id="57502-195">No exemplo, o locatário já tiver adatum.biz como um nome de domínio verificado.</span><span class="sxs-lookup"><span data-stu-id="57502-195">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="57502-196">O assistente não pedirá para verificação adicional porque customers.adatum.biz é um subdomínio para o nome já está registrado.</span><span class="sxs-lookup"><span data-stu-id="57502-196">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="57502-197">No entanto, se você adicionar um FQDN que não foi verificado antes, você precisará percorrer o processo de verificação.</span><span class="sxs-lookup"><span data-stu-id="57502-197">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="57502-198">O processo de verificação é [descrito abaixo](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span><span class="sxs-lookup"><span data-stu-id="57502-198">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![Confirmação de nome de domínio verfied](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="57502-200">Clique em **Avançar**e na página **Configurações de DNS de atualização** , selecione **eu adicionará os registros DNS irei** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="57502-200">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="57502-201">Na próxima página, limpe todos os valores (a menos que você deseja usar o nome de domínio para o Exchange, SharePoint ou equipes/Skype for Business), clique em **Avançar**e, em seguida, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="57502-201">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="57502-202">Certifique-se de que seu novo domínio se situa o status de instalação completo.</span><span class="sxs-lookup"><span data-stu-id="57502-202">Make sure your new domain is in the Setup complete status.</span></span>

    ![Domínios mostrando o status da instalação completa](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="57502-204">Ativar o nome de domínio</span><span class="sxs-lookup"><span data-stu-id="57502-204">Activate the domain name</span></span>

<span data-ttu-id="57502-205">Depois que você registrou um nome de domínio, você precisa ativá-lo adicionando pelo menos um usuário e atribuir um endereço SIP com a parte do FQDN do endereço SIP correspondente do domínio base criado.</span><span class="sxs-lookup"><span data-stu-id="57502-205">After you have registered a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span>

<span data-ttu-id="57502-206">*Analise a [obter ajuda com o Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre a adição de usuários em locatários do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="57502-206">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="57502-207">Por exemplo: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-207">For example: test@customers.adatum.biz</span></span>

![Página de ativação de domínio base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="57502-209">Registrar um nome de subdomínio em um locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="57502-209">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="57502-210">Você precisará criar um nome de subdomínio exclusivo para cada cliente.</span><span class="sxs-lookup"><span data-stu-id="57502-210">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="57502-211">Neste exemplo, criaremos um sbc1.customers.adatum.biz subdomínio em um locatário com o woodgrovebank.us de nome de domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="57502-211">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="57502-212">**Todas as ações a seguir estão no locatário do cliente.**</span><span class="sxs-lookup"><span data-stu-id="57502-212">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="57502-213">Certifique-se de que você tenha os direitos apropriados no locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="57502-213">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="57502-214">Você só pode adicionar novos domínios se você entrou no Centro de administração do Office 365, como um Administrador Global.</span><span class="sxs-lookup"><span data-stu-id="57502-214">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="57502-215">Para validar a função que você tiver, conecte-se ao centro de administração do Microsoft 365 (https://portal.office.com), vá para **usuários** > **Usuários ativos**e, em seguida, verifique se você possui uma função de Administrador Global.</span><span class="sxs-lookup"><span data-stu-id="57502-215">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="57502-216">Para obter mais informações sobre funções de administração e como atribuir uma função no Office 365, consulte [funções de administrador do Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span><span class="sxs-lookup"><span data-stu-id="57502-216">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="57502-217">Adicionar um subdomínio para o locatário do cliente e verifique se ele</span><span class="sxs-lookup"><span data-stu-id="57502-217">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="57502-218">No Centro de administração do Microsoft 365, vá para a **instalação** > **domínios** > **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="57502-218">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="57502-219">Na caixa **Digite um domínio em que você é proprietário** , digite o FQDN do subdomínio para este locatário.</span><span class="sxs-lookup"><span data-stu-id="57502-219">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="57502-220">No exemplo a seguir, o subdomínio é sbc1.customers.adatum.biz.</span><span class="sxs-lookup"><span data-stu-id="57502-220">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![Adicionando um subdomínio do cliente](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="57502-222">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="57502-222">Click **Next**.</span></span>
4. <span data-ttu-id="57502-223">O FQDN nunca foi registrado no inquilino.</span><span class="sxs-lookup"><span data-stu-id="57502-223">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="57502-224">Na próxima etapa, você precisará verificar o domínio.</span><span class="sxs-lookup"><span data-stu-id="57502-224">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="57502-225">Selecione **Adicionar um registro TXT em vez disso**.</span><span class="sxs-lookup"><span data-stu-id="57502-225">Select **Add a TXT record instead**.</span></span> 

    ![Opções na página verificar domínio](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="57502-227">Clique em **Avançar**e observe o valor do TXT gerado para verificar o nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="57502-227">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![Registros de texto na página verificar domínio](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="57502-229">Crie o registro TXT com o valor da etapa anterior no provedor de hospedagem de DNS da operadora.</span><span class="sxs-lookup"><span data-stu-id="57502-229">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![Criando o registro TXT no provedor de hospedagem de DNS da operadora](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="57502-231">Para obter mais informações, consulte [criar registros DNS em qualquer provedor de hospedagem de DNS para o Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span><span class="sxs-lookup"><span data-stu-id="57502-231">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="57502-232">Voltar ao centro de administração do Microsoft 365 do cliente e clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="57502-232">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="57502-233">Na página seguinte, selecione **eu adicionará os registros DNS irei** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="57502-233">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![Opções da página de configurações de DNS de atualização](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="57502-235">Na página **Escolher seus serviços online** , desmarque todas as opções e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="57502-235">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![Escolha sua página de serviços online](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="57502-237">Na página **configurações de atualização de DNS** , clique em **Concluir** .</span><span class="sxs-lookup"><span data-stu-id="57502-237">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![A página de configurações de DNS de atualização](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="57502-239">Certifique-se de que o status é **Concluir a instalação**.</span><span class="sxs-lookup"><span data-stu-id="57502-239">Ensure that the status is **Setup complete**.</span></span> 
    
    ![Página mostrando o status da instalação completa](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="57502-241">Ativar o nome do subdomínio</span><span class="sxs-lookup"><span data-stu-id="57502-241">Activate the subdomain name</span></span>

<span data-ttu-id="57502-242">Após registrar um nome de domínio, você precisa ativá-lo adicionando pelo menos um usuário e atribuir um endereço SIP com a parte do FQDN do endereço SIP correspondente ao subdomínio criado no locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="57502-242">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="57502-243">*Analise a [obter ajuda com o Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) para obter mais informações sobre a adição de usuários em locatários do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="57502-243">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="57502-244">Por exemplo: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="57502-244">For example: test@sbc1.customers.adatum.biz</span></span>

![Ativação da página subdomínio](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="57502-246">Criar um tronco e provisionar usuários</span><span class="sxs-lookup"><span data-stu-id="57502-246">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="57502-247">Com base nos comentários que recebemos no programa de adoção técnicos, Microsoft pode alterar o processo de criação de troncos em Inquilinos do cliente para simplificar o processo.</span><span class="sxs-lookup"><span data-stu-id="57502-247">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="57502-248">Por favor, assista as atualizações de documentação nesta página e siga os blogs de comunidade técnica da Microsoft para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="57502-248">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="57502-249">Crie um tronco no domínio do cliente usando o comando New-CSonlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="57502-249">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="57502-250">O tronco FQDN **deve** corresponder ao subdomínio criado para o cliente.</span><span class="sxs-lookup"><span data-stu-id="57502-250">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="57502-251">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="57502-251">For example:</span></span>

<span data-ttu-id="57502-252">*New-CSOnlinePSTNGateway – FQDN sbc1.customers.adatum.biz - SipSignallingPort 5068*</span><span class="sxs-lookup"><span data-stu-id="57502-252">*New-CSOnlinePSTNGateway – FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068*</span></span>

<span data-ttu-id="57502-253">Provisionar usuários com os números de telefone e configurar o roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="57502-253">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="57502-254">Para obter mais informações sobre o New-CSOnlinePSTNGateway, provisionamento de usuários e configurando o roteamento de voz, consultem [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="57502-254">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="57502-255">Consulte as [instruções do fornecedor SBC](#deploy-and-configure-the-sbc) sobre como configurar enviando o nome FQDN subdomínios no cabeçalho do contato.</span><span class="sxs-lookup"><span data-stu-id="57502-255">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>


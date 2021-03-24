---
title: Configurar a integração do Cloud Connector com sua organização do Microsoft 365 ou Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Saiba como configurar a integração do Cloud Connector com sua organização do Microsoft 365 ou Office 365.
ms.openlocfilehash: 74696023dcffbc91641bb4e9950f2988a89abbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095085"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="4cef4-103">Configurar a integração do Cloud Connector com sua organização do Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="4cef4-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>

> [!Important] 
> <span data-ttu-id="4cef4-104">O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="4cef4-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="4cef4-105">Depois que sua organização tiver atualizado para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="4cef4-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="4cef4-106">Saiba como configurar a integração do Cloud Connector com sua organização do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="4cef4-106">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="4cef4-107">Depois que a instalação do Skype for Business Cloud Connector Edition for concluída, execute as etapas nesta seção para configurar sua implantação e conectá-la à sua organização do Microsoft 365 ou office 365.</span><span class="sxs-lookup"><span data-stu-id="4cef4-107">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="4cef4-108">Configurar configurações de firewall</span><span class="sxs-lookup"><span data-stu-id="4cef4-108">Configure firewall settings</span></span>

<span data-ttu-id="4cef4-109">Configure as configurações de firewall para suas configurações internas e externas de firewall para que você perímetro a rede para abrir as portas necessárias, conforme descrito em Portas e [protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) em [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="4cef4-109">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="4cef4-110">Configurar gateways PSTN (Rede Telefônica Pública Comutado)</span><span class="sxs-lookup"><span data-stu-id="4cef4-110">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="4cef4-111">Configurar troncos em cada gateway PSTN para apontar de volta para Servidores de Mediação para todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4cef4-111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="4cef4-112">Como o FQDN do pool é o mesmo para todos os servidores no pool, cada tronco deve apontar para um FQDN do Servidor de Mediação ou um endereço IP em vez do FQDN do pool do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="4cef4-112">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="4cef4-113">Os troncos devem ser definidos na mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="4cef4-113">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="4cef4-114">Se você estiver usando TLS entre servidores de mediação e gateways, será necessário configurar os gateways e servidores de mediação para dar suporte a MTLS da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4cef4-114">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="4cef4-115">Exporte a CA raiz do computador do Active Directory do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4cef4-115">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="4cef4-116">Siga as instruções do fornecedor de gateway PSTN para importar a AC raiz.</span><span class="sxs-lookup"><span data-stu-id="4cef4-116">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="4cef4-117">Importe o certificado de AC raiz do certificado emitido para o gateway nos Servidores de Mediação.</span><span class="sxs-lookup"><span data-stu-id="4cef4-117">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="4cef4-118">Se você precisar obter um certificado SSL para o gateway, pode fazer isso usando o serviço autoridade de certificado em execução no computador do Cloud Connector Active Directory da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4cef4-118">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="4cef4-119">Modifique o modelo de Servidor Web existente para permitir que usuários autenticados se inscrevam ou criem um novo modelo de Servidor Web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam.</span><span class="sxs-lookup"><span data-stu-id="4cef4-119">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="4cef4-120">Para obter instruções detalhadas, consulte [Modelos de Certificados](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="4cef4-120">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="4cef4-121">Solicite um certificado usando o snap-in certificado selecionando o modelo do Servidor Web habilitado.</span><span class="sxs-lookup"><span data-stu-id="4cef4-121">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="4cef4-122">Certifique-se de adicionar Nome comum em Assunto e nome DNS em Nome alternativo com FQDN do gateway e confirme na Chave Privada que Tornar chave privada exportável está selecionada em opções de chave.</span><span class="sxs-lookup"><span data-stu-id="4cef4-122">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="4cef4-123">Exporte o certificado SSL com chave privada e siga as instruções do fornecedor de gateway PSTN para importar o certificado.</span><span class="sxs-lookup"><span data-stu-id="4cef4-123">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="4cef4-124">Atualizar o domínio para seu locatário</span><span class="sxs-lookup"><span data-stu-id="4cef4-124">Update the domain for your tenant</span></span>

<span data-ttu-id="4cef4-125">Certifique-se de que você concluiu as etapas para atualizar seu domínio no Microsoft 365 ou No Office 365 e ter a capacidade de adicionar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="4cef4-125">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="4cef4-126">Para obter mais informações sobre como configurar seu domínio no Microsoft 365 ou No Office 365, consulte Adicionar um domínio ao [Microsoft 365 ou Ao Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="4cef4-126">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="4cef4-127">Adicionar registros DNS para seu Edge</span><span class="sxs-lookup"><span data-stu-id="4cef4-127">Add DNS records for your Edge</span></span>

<span data-ttu-id="4cef4-128">Adicione os seguintes registros DNS à sua organização do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="4cef4-128">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="4cef4-129">Para obter informações sobre como adicionar registros DNS, consulte [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="4cef4-129">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="4cef4-130">Adicione um registro DNS A para Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="4cef4-130">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="4cef4-131">Os registros SRV serão criados automaticamente pelo Microsoft 365 ou Office 365 e pelos scripts de implantação.</span><span class="sxs-lookup"><span data-stu-id="4cef4-131">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="4cef4-132">Confirme se você pode procurar os dois seguintes serviços SIP na Borda: \_ sip e \_ sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="4cef4-132">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![Confirmação de Registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="4cef4-134">Configurar a conectividade híbrida entre o Cloud Connector Edition e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="4cef4-134">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="4cef4-135">Para configurar a conectividade híbrida entre sua implantação do Skype for Business Cloud Connector Edition e sua organização do Microsoft 365 ou office 365, execute o seguinte cmdlet em uma sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4cef4-135">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="4cef4-136">Para saber como estabelecer uma sessão remota do PowerShell, consulte: [Configurar o computador para](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell .</span><span class="sxs-lookup"><span data-stu-id="4cef4-136">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
<span data-ttu-id="4cef4-137">O cmdlet define o FQDN externo de Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="4cef4-137">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="4cef4-138">No primeiro dos comandos, o deve ser o da função de Borda de \<External Access Edge FQDN\> Acesso SIP.</span><span class="sxs-lookup"><span data-stu-id="4cef4-138">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="4cef4-139">Por padrão, isso deve ser ap. \<Domain Name\> .</span><span class="sxs-lookup"><span data-stu-id="4cef4-139">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="4cef4-140">O FQDN de Borda de Acesso Externo usado para Destino Par deve ser definido como um site PSTN que só será usado como fallback caso um usuário não seja atribuído a um site PSTN.</span><span class="sxs-lookup"><span data-stu-id="4cef4-140">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="4cef4-141">Para obter mais informações, [consulte Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and Deploy multiple sites in Cloud [Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="4cef4-141">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="4cef4-142">Configurar gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="4cef4-142">Set up PSTN gateways</span></span>

<span data-ttu-id="4cef4-143">Configurar troncos em cada gateway PSTN para apontar de volta para Servidores de Mediação para todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4cef4-143">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="4cef4-144">Cada tronco deve apontar para um FQDN do Servidor de Mediação ou um endereço IP em vez do FQDN do pool do Servidor de Mediação porque o FQDN do pool é o mesmo para todos os servidores no pool.</span><span class="sxs-lookup"><span data-stu-id="4cef4-144">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="4cef4-145">Os troncos devem ser definidos na mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="4cef4-145">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="4cef4-146">Se você estiver usando TLS entre servidores de mediação e gateways, será necessário configurar os gateways e servidores de mediação para dar suporte a MTLS da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4cef4-146">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="4cef4-147">Exporte a CA raiz do computador do Active Directory do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4cef4-147">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="4cef4-148">Siga as instruções do fornecedor de gateway PSTN para importar a AC raiz.</span><span class="sxs-lookup"><span data-stu-id="4cef4-148">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="4cef4-149">Importe o certificado de AC raiz do certificado emitido para o gateway nos Servidores de Mediação.</span><span class="sxs-lookup"><span data-stu-id="4cef4-149">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="4cef4-150">Se você precisar obter um certificado SSL para o gateway, pode fazer isso usando o serviço autoridade de certificado em execução no computador do Cloud Connector Active Directory da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="4cef4-150">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="4cef4-151">Modifique o modelo de Servidor Web existente para permitir que usuários autenticados se inscrevam ou criem um novo modelo de Servidor Web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam.</span><span class="sxs-lookup"><span data-stu-id="4cef4-151">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="4cef4-152">Para obter instruções detalhadas, consulte [Modelos de Certificados](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="4cef4-152">For detailed instructions, see [Certificate Templates](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).</span></span>
    
   - <span data-ttu-id="4cef4-153">Solicite um certificado usando o snap-in certificado selecionando o modelo do Servidor Web habilitado.</span><span class="sxs-lookup"><span data-stu-id="4cef4-153">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="4cef4-154">Certifique-se de adicionar Nome comum em Assunto e nome DNS em Nome alternativo com FQDN do gateway e confirme na Chave Privada que Tornar chave privada exportável está selecionada em opções de chave.</span><span class="sxs-lookup"><span data-stu-id="4cef4-154">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="4cef4-155">Exporte o certificado SSL com chave privada e siga as instruções do fornecedor de gateway PSTN para importar o certificado.</span><span class="sxs-lookup"><span data-stu-id="4cef4-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="4cef4-156">Os gateways PSTN em um site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site.</span><span class="sxs-lookup"><span data-stu-id="4cef4-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="4cef4-157">Configurar seus usuários</span><span class="sxs-lookup"><span data-stu-id="4cef4-157">Set up your users</span></span>

<span data-ttu-id="4cef4-158">Faça logoff no Centro de administração do Microsoft 365, adicione os usuários que serão habilitados para serviços de voz online e atribua uma licença E5 ou um complemento do Sistema de Telefonia à licença do E3 a esses usuários.</span><span class="sxs-lookup"><span data-stu-id="4cef4-158">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="4cef4-159">Para obter informações sobre como adicionar usuários, consulte [Adicionar usuários ao Microsoft 365 para empresas.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)</span><span class="sxs-lookup"><span data-stu-id="4cef4-159">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="4cef4-160">Habilitar usuários para serviços de voz e caixa postal do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="4cef4-160">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="4cef4-161">Depois de adicionar seus usuários ao Microsoft 365 ou Office 365, habilita suas contas para serviços de voz do Sistema de Telefonia, incluindo caixa postal.</span><span class="sxs-lookup"><span data-stu-id="4cef4-161">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="4cef4-162">Para habilitar esses recursos, você deve fazer logoff na sua organização do Microsoft 365 ou office 365 com uma conta que seja uma função de Administrador Global e poder executar o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="4cef4-162">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="4cef4-163">Para saber como estabelecer uma sessão remota do PowerShell, consulte: [Configurar seu computador para](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4cef4-163">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
- <span data-ttu-id="4cef4-164">Atribua a política ao usuário e configure o número de telefone de voz comercial do usuário, que você especificará com o valor do parâmetro **Identity:**</span><span class="sxs-lookup"><span data-stu-id="4cef4-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="4cef4-165">Uma identidade de usuário pode ser especificada usando o endereço SIP do usuário, o nome principal do usuário (UPN) ou o nome de exibição do Active Directory do usuário (por exemplo, "Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="4cef4-165">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="4cef4-166">O caractere asterisco ( \* ) também pode ser usado com o Nome de Exibição como a Identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="4cef4-166">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="4cef4-167">Por exemplo, a Identidade " Smith" retorna todos os usuários que têm um nome de exibição que termina com o valor \* de cadeia de caracteres "Smith".</span><span class="sxs-lookup"><span data-stu-id="4cef4-167">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="4cef4-168">Em seguida, você pode verificar se os usuários foram adicionados e habilitados usando o seguinte script:</span><span class="sxs-lookup"><span data-stu-id="4cef4-168">You can then verify that the users were added and enabled using the following script:</span></span>
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="4cef4-169">Você precisará decidir se seus usuários devem ser capazes de fazer chamadas internacionais.</span><span class="sxs-lookup"><span data-stu-id="4cef4-169">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="4cef4-170">Por padrão, a chamada internacional está habilitada.</span><span class="sxs-lookup"><span data-stu-id="4cef4-170">By default, international calling is enabled.</span></span> <span data-ttu-id="4cef4-171">Você pode desabilitar ou habilitar usuários para discagem internacional usando o Centro de administração do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="4cef4-171">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="4cef4-172">Para desabilitar a chamada internacional por usuário, execute o seguinte cmdlet no Skype for Business Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4cef4-172">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="4cef4-173">Para habilitar a chamada internacional por usuário depois de desabilitada, execute o mesmo cmdlet, mas altere o valor de **PolicyName** para *InternationalCallsAllowed*  .</span><span class="sxs-lookup"><span data-stu-id="4cef4-173">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="4cef4-174">Atribuir usuários a sites PSTN</span><span class="sxs-lookup"><span data-stu-id="4cef4-174">Assign users to PSTN sites</span></span>

<span data-ttu-id="4cef4-175">Use o PowerShell remoto do locatário para atribuir um site aos usuários, mesmo que você só implantou um único site.</span><span class="sxs-lookup"><span data-stu-id="4cef4-175">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="4cef4-176">Para saber como estabelecer uma sessão remota do PowerShell, consulte: [Configurar o computador para](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell .</span><span class="sxs-lookup"><span data-stu-id="4cef4-176">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="4cef4-177">Se nenhum site PSTN for atribuído a um usuário, a conectividade híbrida entre sua implantação do Skype for Business Cloud Connector Edition e sua organização do Microsoft 365 ou Do Office 365 irá voltar a usar o nível de locatário padrão um (Destino Par) para que as chamadas possam ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="4cef4-177">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="4cef4-178">Configurar configurações do servidor de mediação híbrido online</span><span class="sxs-lookup"><span data-stu-id="4cef4-178">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="4cef4-179"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="4cef4-179"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="4cef4-180">Quando uma chamada P2P é escalonada para uma conferência PSTN, o servidor de conferência do Skype for Business Online enviará um convite para o Servidor de Mediação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="4cef4-180">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="4cef4-181">Para garantir que o Microsoft 365 ou o Office 365 possa rotear esse convite com êxito, você precisa configurar uma configuração em seu locatário online para cada Servidor de Mediação do Cloud Connector da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4cef4-181">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="4cef4-182">Crie um usuário no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cef4-182">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4cef4-183">Use qualquer nome de usuário que quiser, como "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="4cef4-183">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="4cef4-184">Use o domínio SIP padrão do Cloud Connector (o primeiro domínio SIP no arquivo .ini) como o domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="4cef4-184">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="4cef4-185">Observe que a atribuição de licença só é necessária para a propagação do usuário no diretório online do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4cef4-185">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="4cef4-186">Atribua uma licença do Microsoft 365 ou office 365 (como o E5) à conta que você criar, permita até uma hora para que as alterações se propaguem, verifique se as contas de usuário foram provisionadas corretamente para o diretório online do Skype for Business executando o seguinte cmdlet e remova a licença dessa conta.</span><span class="sxs-lookup"><span data-stu-id="4cef4-186">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="4cef4-187">Inicie uma sessão remota do PowerShell do Azure AD de locatário usando suas credenciais de administrador global ou de usuário e execute o seguinte cmdlet para definir o departamento para a conta de usuário do Azure AD configurada na etapa 1 como "HybridMediationServer":</span><span class="sxs-lookup"><span data-stu-id="4cef4-187">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="4cef4-188">Inicie uma sessão remota do PowerShell do Skype for Business de locatário usando suas credenciais de administrador de locatário do Skype for Business e execute o cmdlet a seguir para definir o FQDN do Servidor de Mediação e do Servidor de Borda para essa conta de usuário, substituindo pelo Nome de Exibição do usuário para a conta que você criou na etapa \<DisplayName\> 1:</span><span class="sxs-lookup"><span data-stu-id="4cef4-188">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="4cef4-189">Para Identidade, use o Nome de Exibição da conta de usuário que você criou para este Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="4cef4-189">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="4cef4-190">Para  *MediationServerFQDN*  , use o FQDN interno definido para seu Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="4cef4-190">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="4cef4-191">Para  *EdgeServerExternalFQDN,*  use o FQDN externo definido para Proxy de Acesso para Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="4cef4-191">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="4cef4-192">Se houver vários sites PSTN do Cloud Connector, escolha o FQDN do Proxy de Acesso para Servidor de Borda atribuído ao site onde o Servidor de Mediação está localizado.</span><span class="sxs-lookup"><span data-stu-id="4cef4-192">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="4cef4-193">Se houver vários Servidores de Mediação do Cloud Connector (vários sites, HA), repita as etapas anteriores para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="4cef4-193">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>

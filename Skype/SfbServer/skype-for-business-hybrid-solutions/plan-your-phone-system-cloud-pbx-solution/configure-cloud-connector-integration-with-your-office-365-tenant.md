---
title: Configurar a integração do Cloud Connector com seu locatário do Office 365
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
description: Saiba como configurar a integração do Cloud Connector com seu locatário do Office 365.
ms.openlocfilehash: cf683743064ec377c827fe0c52a59e464f65ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050203"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="1eeca-103">Configurar a integração do Cloud Connector com seu locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="1eeca-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="1eeca-104">Saiba como configurar a integração do Cloud Connector com seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="1eeca-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="1eeca-105">Depois que a instalação do Skype for Business Cloud Connector Edition estiver concluída, execute as etapas desta seção para configurar sua implantação e conectá-la ao seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="1eeca-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="1eeca-106">Configurar definições de firewall</span><span class="sxs-lookup"><span data-stu-id="1eeca-106">Configure firewall settings</span></span>

<span data-ttu-id="1eeca-107">Defina as configurações de firewall para suas configurações de firewall internas e externas para sua rede de perímetro para abrir as portas necessárias descritas em [portas e protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) em [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="1eeca-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="1eeca-108">Configurar gateways PSTN (rede telefônica pública comutada)</span><span class="sxs-lookup"><span data-stu-id="1eeca-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="1eeca-109">Configure troncos em cada gateway PSTN para apontar de volta para servidores de mediação para todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1eeca-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="1eeca-110">Como o FQDN do pool é o mesmo para todos os servidores no pool, cada tronco deve apontar para um FQDN do servidor de mediação ou endereço IP em vez do FQDN do pool do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="1eeca-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="1eeca-111">Os troncos devem ser definidos com a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="1eeca-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="1eeca-112">Se você estiver usando o TLS entre servidores de mediação e gateways, será necessário configurar os gateways e os servidores de mediação para suportar MTLS da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1eeca-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="1eeca-113">Exporte a autoridade de certificação raiz do computador do Active Directory do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1eeca-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="1eeca-114">Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.</span><span class="sxs-lookup"><span data-stu-id="1eeca-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="1eeca-115">Importe o certificado de autoridade de certificação raiz do certificado emitido para o seu gateway nos servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="1eeca-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="1eeca-116">Se for necessário obter um certificado SSL para o gateway, você poderá fazer isso usando o serviço da autoridade de certificação em execução no computador do Active Directory do Cloud Connector, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1eeca-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="1eeca-117">Modifique o modelo de servidor Web existente para permitir que os usuários autenticados se inscrevam ou criem um novo modelo de servidor Web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam.</span><span class="sxs-lookup"><span data-stu-id="1eeca-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="1eeca-118">Para obter instruções detalhadas, consulte [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="1eeca-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="1eeca-119">Solicitar um certificado usando snap-in de certificado selecionando o modelo de servidor Web que você habilitou.</span><span class="sxs-lookup"><span data-stu-id="1eeca-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="1eeca-120">Certifique-se de adicionar o nome comum ao nome de entidade e DNS em nome alternativo com FQDN do gateway e confirme se a chave privada que torna a chave privada exportável está selecionada em opções de chave.</span><span class="sxs-lookup"><span data-stu-id="1eeca-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="1eeca-121">Exporte o certificado SSL com a chave privada e siga as instruções do seu fornecedor de gateway PSTN para importar o certificado.</span><span class="sxs-lookup"><span data-stu-id="1eeca-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="1eeca-122">Atualizar o domínio para o locatário</span><span class="sxs-lookup"><span data-stu-id="1eeca-122">Update the domain for your tenant</span></span>

<span data-ttu-id="1eeca-123">Certifique-se de ter concluído as etapas para atualizar seu domínio no Office 365 e ter a capacidade de adicionar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="1eeca-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="1eeca-124">Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [Adicionar um domínio ao office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="1eeca-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="1eeca-125">Adicionar registros DNS no Office 365 para sua borda</span><span class="sxs-lookup"><span data-stu-id="1eeca-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="1eeca-126">Adicione os seguintes registros DNS ao seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="1eeca-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="1eeca-127">Para obter informações sobre como adicionar registros DNS ao seu locatário do Office 365, consulte [Adicionar ou editar registros DNS personalizados no Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="1eeca-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="1eeca-128">Adicionar um registro DNS A para borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="1eeca-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="1eeca-129">Os registros SRV serão criados automaticamente pelo Office 365 e os scripts de implantação.</span><span class="sxs-lookup"><span data-stu-id="1eeca-129">SRV records will automatically be created by Office 365 and the deployment scripts.</span></span> <span data-ttu-id="1eeca-130">Confirme que você pode pesquisar os dois serviços SIP a seguir na borda: _sip e _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="1eeca-130">Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Confirmação de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="1eeca-132">Configurar a conectividade híbrida entre o Cloud Connector Edition e o Office 365</span><span class="sxs-lookup"><span data-stu-id="1eeca-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="1eeca-133">Para configurar a conectividade híbrida entre sua implantação do Skype for Business Cloud Connector Edition e seu locatário do Office 365, execute o cmdlet a seguir em uma sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1eeca-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="1eeca-134">Para saber como estabelecer uma sessão remota do PowerShell, consulte: [configurar seu computador para o Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1eeca-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="1eeca-135">O cmdlet define o FQDN externo da borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="1eeca-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="1eeca-136">No primeiro dos comandos, o \<FQDN\> de borda de acesso externo deve ser aquele para a função de borda de acesso SIP.</span><span class="sxs-lookup"><span data-stu-id="1eeca-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="1eeca-137">Por padrão, isso deve ser AP.\<nome\>do domínio.</span><span class="sxs-lookup"><span data-stu-id="1eeca-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="1eeca-138">O FQDN de borda de acesso externo usado para o destino de par deve ser definido como um site PSTN que será usado apenas como fallback, caso um usuário não esteja atribuído a um site PSTN.</span><span class="sxs-lookup"><span data-stu-id="1eeca-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="1eeca-139">Para obter mais informações, consulte [implantar um único site no Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [implantar vários sites no Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1eeca-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="1eeca-140">Configurar gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="1eeca-140">Set up PSTN gateways</span></span>

<span data-ttu-id="1eeca-141">Configure troncos em cada gateway PSTN para apontar de volta para servidores de mediação para todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1eeca-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="1eeca-142">Cada tronco deve apontar para um FQDN do servidor de mediação ou endereço IP em vez do FQDN do pool do servidor de mediação porque o FQDN do pool é o mesmo para todos os servidores do pool.</span><span class="sxs-lookup"><span data-stu-id="1eeca-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="1eeca-143">Os troncos devem ser definidos com a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="1eeca-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="1eeca-144">Se você estiver usando o TLS entre servidores de mediação e gateways, será necessário configurar os gateways e os servidores de mediação para suportar MTLS da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1eeca-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="1eeca-145">Exporte a autoridade de certificação raiz do computador do Active Directory do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1eeca-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="1eeca-146">Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.</span><span class="sxs-lookup"><span data-stu-id="1eeca-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="1eeca-147">Importe o certificado de autoridade de certificação raiz do certificado emitido para o seu gateway nos servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="1eeca-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="1eeca-148">Se for necessário obter um certificado SSL para o gateway, você poderá fazer isso usando o serviço da autoridade de certificação em execução no computador do Active Directory do Cloud Connector, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1eeca-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="1eeca-149">Modifique o modelo de servidor Web existente para permitir que os usuários autenticados se inscrevam ou criem um novo modelo de servidor Web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam.</span><span class="sxs-lookup"><span data-stu-id="1eeca-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="1eeca-150">Para obter instruções detalhadas, consulte [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="1eeca-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="1eeca-151">Solicitar um certificado usando snap-in de certificado selecionando o modelo de servidor Web que você habilitou.</span><span class="sxs-lookup"><span data-stu-id="1eeca-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="1eeca-152">Certifique-se de adicionar o nome comum ao nome de entidade e DNS em nome alternativo com FQDN do gateway e confirme se a chave privada que torna a chave privada exportável está selecionada em opções de chave.</span><span class="sxs-lookup"><span data-stu-id="1eeca-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="1eeca-153">Exporte o certificado SSL com a chave privada e siga as instruções do seu fornecedor de gateway PSTN para importar o certificado.</span><span class="sxs-lookup"><span data-stu-id="1eeca-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="1eeca-154">Os gateways PSTN em um site PSTN só devem se conectar ao (s) servidor (es) de mediação no mesmo site.</span><span class="sxs-lookup"><span data-stu-id="1eeca-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="1eeca-155">Configurar seus usuários no Office 365</span><span class="sxs-lookup"><span data-stu-id="1eeca-155">Set up your users in Office 365</span></span>

<span data-ttu-id="1eeca-156">Faça logon no portal de administração do Office 365, adicione os usuários que serão habilitados para serviços de voz online e atribua uma licença E5 ou sistema de telefonia no Office 365 complemento à licença E3 para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="1eeca-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="1eeca-157">Para obter informações sobre como adicionar usuários, consulte [Adicionar usuários ao Office 365 for Business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="1eeca-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="1eeca-158">Habilitar usuários para o sistema de telefonia no Office 365 voz e serviços de caixa postal</span><span class="sxs-lookup"><span data-stu-id="1eeca-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="1eeca-159">Depois de adicionar os usuários ao Office 365, habilite suas contas de sistema de telefonia no Office 365 Voice Services, incluindo a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="1eeca-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="1eeca-160">Para habilitar esses recursos, você deve fazer logon no locatário do Office 365 com uma conta que seja uma função de administrador global do Office 365 e poder executar o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="1eeca-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="1eeca-161">Para saber como estabelecer uma sessão remota do PowerShell, consulte: [configurar seu computador para o Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1eeca-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="1eeca-162">Atribua a política ao usuário e configure o número de telefone comercial do usuário, que você especifica com o valor do parâmetro **Identity** :</span><span class="sxs-lookup"><span data-stu-id="1eeca-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="1eeca-163">Uma identidade de usuário pode ser especificada usando o endereço SIP do usuário, o nome do usuário principal (UPN) ou o nome de exibição do Active Directory do usuário (por exemplo, "Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="1eeca-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="1eeca-164">O caractere asterisco\*() também pode ser usado com o nome de exibição como a identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="1eeca-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="1eeca-165">Por exemplo, a identidade "\*Smith" retorna todos os usuários que têm um nome de exibição que termina com o valor de cadeia de caracteres "Smith".</span><span class="sxs-lookup"><span data-stu-id="1eeca-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="1eeca-166">Em seguida, você pode verificar se os usuários foram adicionados e habilitados usando o seguinte script:</span><span class="sxs-lookup"><span data-stu-id="1eeca-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="1eeca-167">Você precisará decidir se seus usuários devem ser capazes de fazer chamadas internacionais.</span><span class="sxs-lookup"><span data-stu-id="1eeca-167">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="1eeca-168">Por padrão, a chamada internacional está habilitada.</span><span class="sxs-lookup"><span data-stu-id="1eeca-168">By default, international calling is enabled.</span></span> <span data-ttu-id="1eeca-169">Você pode desabilitar ou habilitar usuários para discagem internacional usando o centro de administração do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="1eeca-169">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="1eeca-170">Para desabilitar a chamada internacional em uma base por usuário, execute o seguinte cmdlet no PowerShell do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="1eeca-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="1eeca-171">Para habilitar novamente a chamada internacional por usuário depois que ela tiver sido desabilitada, execute o mesmo cmdlet, mas altere o valor de **PolicyName** para *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="1eeca-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="1eeca-172">Atribuir usuários a sites PSTN</span><span class="sxs-lookup"><span data-stu-id="1eeca-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="1eeca-173">Use o PowerShell remoto do locatário para atribuir um site aos usuários, mesmo se você implantou apenas um único site.</span><span class="sxs-lookup"><span data-stu-id="1eeca-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="1eeca-174">Para saber como estabelecer uma sessão remota do PowerShell, consulte: [configurar seu computador para o Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1eeca-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="1eeca-175">Se nenhum site PSTN for atribuído a um usuário, a conectividade híbrida entre sua implantação do Skype for Business Cloud Connector Edition e seu locatário do Office 365 será revertida para usar o padrão de nível de locatário (destino de par) para que as chamadas possam ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="1eeca-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="1eeca-176">Definir configurações do servidor de mediação híbrida online</span><span class="sxs-lookup"><span data-stu-id="1eeca-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="1eeca-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="1eeca-177"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="1eeca-178">Quando uma chamada P2P é escalonada para uma conferência PSTN, o servidor de conferência do Skype for Business online enviará um convite para o servidor de mediação do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1eeca-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="1eeca-179">Para garantir que o Office 365 possa encaminhar esse convite com êxito, você precisa definir uma configuração no seu locatário online para cada servidor de mediação do Cloud Connector da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1eeca-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="1eeca-180">Crie um usuário no portal de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="1eeca-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="1eeca-181">Use o nome de usuário desejado, como "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="1eeca-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="1eeca-182">Use o domínio SIP padrão do Cloud Connector (o primeiro domínio SIP no arquivo. ini) como o domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="1eeca-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="1eeca-183">Observe que a atribuição de licenças só é necessária para a propagação do usuário no diretório do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="1eeca-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="1eeca-184">Atribuir licenças do Office 365 (como E5) à conta criada, permitir até uma hora para que as alterações sejam propagadas, verifique se as contas de usuário foram provisionadas corretamente para o diretório do Skype for Business online executando o cmdlet a seguir e remova o licença dessa conta.</span><span class="sxs-lookup"><span data-stu-id="1eeca-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="1eeca-185">Inicie uma sessão do PowerShell remoto do Azure AD do locatário usando suas credenciais de administrador global ou de usuário e execute o seguinte cmdlet para definir o departamento da conta de usuário do Azure AD configurada na etapa 1 como "HybridMediationServer":</span><span class="sxs-lookup"><span data-stu-id="1eeca-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="1eeca-186">Inicie uma sessão do PowerShell remoto do Skype for Business locatário usando suas credenciais de administrador de locatário do Skype for Business e, em seguida, execute o seguinte cmdlet para definir o servidor de mediação e \<o\> FQDN do servidor de borda para essa conta de usuário, substituindo DisplayName pelo nome de exibição do usuário para a conta que você criou na etapa 1:</span><span class="sxs-lookup"><span data-stu-id="1eeca-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="1eeca-187">Para identidade, use o nome de exibição da conta de usuário do Office 365 que você criou para este servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="1eeca-187">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="1eeca-188">Para o *MediationServerFQDN* , use o FQDN interno definido para o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="1eeca-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="1eeca-189">Para o *EdgeServerExternalFQDN* , use o FQDN externo definido para o proxy de acesso do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1eeca-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="1eeca-190">Se houver vários sites PSTN do Cloud Connector, escolha o FQDN do proxy de acesso do servidor de borda atribuído ao site onde o servidor de mediação está localizado.</span><span class="sxs-lookup"><span data-stu-id="1eeca-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="1eeca-191">Se houver vários servidores de mediação do Cloud Connector (vários sites, alta disponibilidade), repita as etapas anteriores para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="1eeca-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    


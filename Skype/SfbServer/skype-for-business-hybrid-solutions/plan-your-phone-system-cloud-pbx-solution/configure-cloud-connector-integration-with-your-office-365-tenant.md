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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Saiba como configurar a integração do Cloud Connector com seu locatário do Office 365.
ms.openlocfilehash: b4c70c5698601a2aa69669da3384b6806af98110
ms.sourcegitcommit: 0d7f3c7a84584ec25a23190187215109c8756189
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37508806"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="5c6bd-103">Configurar a integração do Cloud Connector com seu locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="5c6bd-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="5c6bd-104">Saiba como configurar a integração do Cloud Connector com seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="5c6bd-105">Ao concluir a instalação do Skype for Business Cloud Connector Edition, realize o procedimento apresentado nesta seção para configurar sua implantação e conectá-la a seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="5c6bd-106">Definir as configurações do firewall</span><span class="sxs-lookup"><span data-stu-id="5c6bd-106">Configure firewall settings</span></span>

<span data-ttu-id="5c6bd-107">Defina as configurações de firewall para as suas configurações de firewall internas e externas para a sua rede de perímetro para abrir as portas necessárias, conforme descrito em [portas e protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) em [plano para o Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="5c6bd-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="5c6bd-108">Gateways de PSTN (Rede Telefônica Pública Comutada)</span><span class="sxs-lookup"><span data-stu-id="5c6bd-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="5c6bd-p101">Configure os troncos em cada gateway PSTN para que eles apontem para os Servidores de Mediação de todos os aplicativos. Como o FQDN do pool é o mesmo para todos os servidores no pool, cada tronco deve apontar para o endereço IP ou FQDN do Servidor de Mediação e não para o FQDN do pool do Servidor de Mediação. Os troncos devem ser definidos com a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="5c6bd-112">Se você usa o protocolo TLS entre os Servidores de Mediação e os gateways, é necessário configurá-los para dar suporte a MTLS, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5c6bd-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="5c6bd-113">Exporte a Autoridade de Certificação raiz do computador que executa o Active Directory do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="5c6bd-114">Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="5c6bd-p102">Importe o Certificado de Autoridade de Certificação raiz emitido para seu gateway nos Servidores de Mediação. Para obter um certificado SSL para o gateway, use o serviço da Autoridade de Certificação em execução no computador do Active Directory do Cloud Connector, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5c6bd-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="5c6bd-117">Modifique o modelo do servidor web existente para permitir que os usuários autenticados se inscrevam ou crie um novo modelo de servidor web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="5c6bd-118">Para obter instruções detalhadas, consulte [modelos de certificado](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c6bd-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="5c6bd-119">Solicitar um certificado usando o snap-in de certificado selecionando o modelo de servidor Web que você habilitou.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="5c6bd-120">Certifique-se de adicionar nome comum em assunto e nome DNS em nome alternativo com FQDN do gateway e confirme se a chave privada que torna a chave privada exportável está selecionada em opções de chave.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="5c6bd-121">Exporte o certificado SSL com a chave privada e siga as instruções do fornecedor do gateway PSTN para importar o certificado.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="5c6bd-122">Atualizar o domínio do locatário</span><span class="sxs-lookup"><span data-stu-id="5c6bd-122">Update the domain for your tenant</span></span>

<span data-ttu-id="5c6bd-123">Confira se você concluiu as etapas de atualização de seu domínio no Office 365 e se é capaz de adicionar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="5c6bd-124">Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [Adicionar um domínio ao office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="5c6bd-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="5c6bd-125">Adicionar registros DNS ao Office 365 para borda</span><span class="sxs-lookup"><span data-stu-id="5c6bd-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="5c6bd-126">Adicione os seguintes registros DNS a seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="5c6bd-127">Para obter informações sobre como adicionar registros DNS ao seu locatário do Office 365, consulte [Adicionar ou editar registros DNS personalizados no Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="5c6bd-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="5c6bd-128">Adicionar um registro DNS A à Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="5c6bd-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="5c6bd-p107">Os registros SRV serão criados automaticamente pelo Office 365 e os scripts de implantação. Confira se é possível pesquisar os dois serviços SIP a seguir na Borda: _sip and _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Confirmação de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="5c6bd-132">Configure a conectividade híbrida entre o Cloud Connector Edition e o Office 365</span><span class="sxs-lookup"><span data-stu-id="5c6bd-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="5c6bd-133">Para configurar a conectividade híbrida entre a implantação do Skype for Business Cloud Connector Edition e seu locatário do Office 365, execute o cmdlet a seguir em uma sessão remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="5c6bd-134">Para saber como estabelecer uma sessão remota do PowerShell, consulte: [configurar seu computador para Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c6bd-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="5c6bd-135">O cmdlet define o FQDN externo da Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="5c6bd-136">No primeiro dos comandos, o \<FQDN\> de borda de acesso externo deve ser aquele da função de borda de acesso SIP.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="5c6bd-137">Por padrão, isso deve ser AP.\<nome\>do domínio.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="5c6bd-138">A borda de acesso externo FQDN usada para destino de par deve ser definida como um site PSTN que só será usado como um fallback caso um usuário não seja atribuído a um site PSTN.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="5c6bd-139">Para obter mais informações, consulte [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="5c6bd-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="5c6bd-140">Configurar gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="5c6bd-140">Set up PSTN gateways</span></span>

<span data-ttu-id="5c6bd-p111">Configure os troncos em cada gateway PSTN para que eles apontem para os Servidores de Mediação de todos os dispositivos. Cada tronco deve apontar para o endereço IP ou FQDN do Servidor de Mediação e não para o FQDN do pool do Servidor de Mediação, pois o FQDN do pool é o mesmo para todos os servidores no pool. Os troncos devem ser definidos com a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="5c6bd-144">Se você usa o protocolo TLS entre os Servidores de Mediação e os gateways, é necessário configurá-los para dar suporte a MTLS, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5c6bd-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="5c6bd-145">Exporte a Autoridade de Certificação raiz do computador que executa o Active Directory do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="5c6bd-146">Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="5c6bd-p112">Importe o Certificado de Autoridade de Certificação raiz emitido para seu gateway nos Servidores de Mediação. Para obter um certificado SSL para o gateway, use o serviço da Autoridade de Certificação em execução no computador do Active Directory do Cloud Connector, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5c6bd-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="5c6bd-149">Modifique o modelo de servidor Web existente para habilitar os usuários autenticados a se inscrever ou criar um novo modelo de servidor Web para configurar outras propriedades e habilitar o registro de usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="5c6bd-150">Para obter instruções detalhadas, consulte [modelos de certificado](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c6bd-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="5c6bd-151">Solicitar um certificado usando o snap-in de certificado selecionando o modelo de servidor Web que você habilitou.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="5c6bd-152">Certifique-se de adicionar nome comum em assunto e nome DNS em nome alternativo com FQDN do gateway e confirme se a chave privada que torna a chave privada exportável está selecionada em opções de chave.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="5c6bd-153">Exporte o certificado SSL com a chave privada e siga as instruções do fornecedor do gateway PSTN para importar o certificado.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="5c6bd-154">Os gateways PSTN em cada site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="5c6bd-155">Configurar usuários no Office 365</span><span class="sxs-lookup"><span data-stu-id="5c6bd-155">Set up your users in Office 365</span></span>

<span data-ttu-id="5c6bd-156">Faça logon no portal de administração do Office 365, adicione os usuários que serão habilitados para serviços de voz online e atribua a licença E5 ou o complemento do Sistema de Telefonia do Office 365 à licença E3 para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="5c6bd-157">Para obter informações sobre como adicionar usuários, consulte [Adicionar usuários ao Office 365 para empresas](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="5c6bd-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="5c6bd-158">Habilitar usuários para os serviços de voz e de caixa postal do Sistema de Telefonia do Office 365</span><span class="sxs-lookup"><span data-stu-id="5c6bd-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="5c6bd-159">Depois de adicionar os usuários ao Office 365, habilite suas contas para os serviços de voz do Sistema de Telefonia do Office 365, incluindo a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="5c6bd-160">Para habilitar essas funcionalidades, faça logon no locatário do Office 365 usando uma conta com função de Administrador Global do Office 365 e que seja capaz de executar o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="5c6bd-161">Para saber como estabelecer uma sessão remota do PowerShell, consulte: [configurar seu computador para Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5c6bd-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="5c6bd-162">Atribua a política ao seu usuário e configure o número de telefone comercial do usuário, que você especifica com o valor do parâmetro de **identidade** :</span><span class="sxs-lookup"><span data-stu-id="5c6bd-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="5c6bd-163">Uma identidade de usuário pode ser especificada usando o endereço SIP do usuário, o nome de usuário principal (UPN) ou o nome de exibição do Active Directory do usuário (por exemplo, "Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="5c6bd-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="5c6bd-164">O caractere asterisco\*() também pode ser usado com o nome para exibição como a identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="5c6bd-165">Por exemplo, a identidade "\*Smith" retorna todos os usuários que têm um nome de exibição que termina com o valor de cadeia de caracteres "Smith".</span><span class="sxs-lookup"><span data-stu-id="5c6bd-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="5c6bd-166">Em seguida, é possível verificar se os usuários foram adicionados e habilitados usando o seguinte script:</span><span class="sxs-lookup"><span data-stu-id="5c6bd-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="5c6bd-p118">Você deverá decidir se os usuários poderão ou não fazer chamadas internacionais. Por padrão, as chamadas internacionais são permitidas. As chamadas internacionais podem ser habilitadas ou desabilitadas para os usuários no Centro de Administração online do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-p118">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="5c6bd-170">Para desabilitar as chamadas internacionais por usuário, execute o seguinte cmdlet no Powershell do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="5c6bd-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="5c6bd-171">Para reativar a chamada internacional a cada usuário depois que ela tiver sido desabilitada, execute o mesmo cmdlet, mas altere o valor de **PolicyName** para *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="5c6bd-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="5c6bd-172">Atribuir usuários a sites PSTN</span><span class="sxs-lookup"><span data-stu-id="5c6bd-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="5c6bd-173">Use o PowerShell remoto do locatário para atribuir o site aos usuários, mesmo que você tenha implantado um único site.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="5c6bd-174">Para saber como estabelecer uma sessão remota do PowerShell, consulte: [configurar seu computador para Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c6bd-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="5c6bd-175">Se nenhum site PSTN estiver atribuído a um usuário, será feito fallback da conectividade híbrida entre a implantação do Skype for Business Cloud Connector Edition e seu locatário do Office 365 para usar o nível de locatário padrão um (destino par) de modo a possibilitar a realização de chamadas.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="5c6bd-176">Definir configurações do servidor de mediação híbrido online</span><span class="sxs-lookup"><span data-stu-id="5c6bd-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="5c6bd-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="5c6bd-177"></span></span>

<span data-ttu-id="5c6bd-178">Quando uma chamada ponto a ponto é escalonada para uma conferência PSTN, o servidor de conferência do Skype for Business online enviará um convite para o servidor de mediador do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="5c6bd-179">Para garantir que o Office 365 possa direcionar esse convite com êxito, você precisa definir uma configuração em seu locatário online para cada servidor de mediador de nuvem da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5c6bd-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="5c6bd-180">Crie um usuário no portal de administração do O365.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="5c6bd-181">Use o nome de usuário desejado, como "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="5c6bd-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="5c6bd-182">Use o domínio SIP padrão do conector de nuvem (o primeiro domínio SIP no arquivo. ini) como o domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="5c6bd-183">Observe que a atribuição de licenças só é necessária para a propagação do usuário no diretório do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="5c6bd-184">Atribua as licenças do Office 365 (como E5) à conta que você criar, aguarde até uma hora para que as alterações sejam propagadas, verifique se as contas de usuário foram provisionadas corretamente para o diretório do Skype for Business online executando o cmdlet a seguir e, em seguida, remova o licença desta conta.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-184">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="5c6bd-185">Inicie uma sessão de locatário do PowerShell remoto do Azure AD usando suas credenciais de administrador global ou de usuário e execute o cmdlet a seguir para definir o departamento da conta de usuário do Azure AD configurada na etapa 1 para "HybridMediationServer":</span><span class="sxs-lookup"><span data-stu-id="5c6bd-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="5c6bd-186">Inicie uma sessão do PowerShell remoto do Skype for Business locatário usando suas credenciais de administrador de locatário do Skype for Business e execute o cmdlet a seguir para definir o servidor de mediação e o FQDN do \<servidor\> de borda para essa conta de usuário, substituindo DisplayName com o nome de exibição do usuário da conta que você criou na etapa 1:</span><span class="sxs-lookup"><span data-stu-id="5c6bd-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="5c6bd-187">Para identificação, use o Nome de Exibição da conta do usuário do Office 365 criada para este Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-187">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="5c6bd-188">Para o *MediationServerFQDN* , use o FQDN interno definido para o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="5c6bd-189">Para o *EdgeServerExternalFQDN* , use o FQDN externo definido para proxy de acesso do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="5c6bd-190">Se houver vários sites PSTN do Cloud Connector, escolha o FQDN do Proxy de Acesso do Servidor de Borda atribuído ao site que contém a localização do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="5c6bd-191">Se houver vários Servidores de Mediação do Cloud Connector (vários sites, alta disponibilidade), repita as etapas anteriores para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="5c6bd-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    


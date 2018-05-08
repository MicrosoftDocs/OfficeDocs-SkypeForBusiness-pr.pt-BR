---
title: Configurar a integração do Cloud Connector com seu locatário do Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Saiba como configurar a integração do Cloud Connector com seu locatário do Office 365.
ms.openlocfilehash: 62caf2cd70b16f0a8e85a38b381478d49e4ee37c
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2018
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="c27e2-103">Configurar a integração do Cloud Connector com seu locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="c27e2-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="c27e2-104">Saiba como configurar a integração do Cloud Connector com seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c27e2-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="c27e2-105">Ao concluir a instalação do Skype for Business Cloud Connector Edition, realize o procedimento apresentado nesta seção para configurar sua implantação e conectá-la a seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c27e2-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="c27e2-106">Definir as configurações do firewall</span><span class="sxs-lookup"><span data-stu-id="c27e2-106">Configure firewall settings</span></span>

<span data-ttu-id="c27e2-107">Defina as configurações de firewall para as suas configurações de firewall interno e externo para a rede de perímetro abrir as portas necessárias, conforme descrito em [portas e protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) no [Planejar Skype para o conector de nuvem Business Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="c27e2-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="c27e2-108">Gateways de PSTN (Rede Telefônica Pública Comutada)</span><span class="sxs-lookup"><span data-stu-id="c27e2-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="c27e2-p101">Configure os troncos em cada gateway PSTN para que eles apontem para os Servidores de Mediação de todos os aplicativos. Como o FQDN do pool é o mesmo para todos os servidores no pool, cada tronco deve apontar para o endereço IP ou FQDN do Servidor de Mediação e não para o FQDN do pool do Servidor de Mediação. Os troncos devem ser definidos com a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="c27e2-p101">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="c27e2-112">Se você usa o protocolo TLS entre os Servidores de Mediação e os gateways, é necessário configurá-los para dar suporte a MTLS, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c27e2-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="c27e2-113">Exporte a Autoridade de Certificação raiz do computador que executa o Active Directory do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c27e2-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="c27e2-114">Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.</span><span class="sxs-lookup"><span data-stu-id="c27e2-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="c27e2-p102">Importe o Certificado de Autoridade de Certificação raiz emitido para seu gateway nos Servidores de Mediação. Para obter um certificado SSL para o gateway, use o serviço da Autoridade de Certificação em execução no computador do Active Directory do Cloud Connector, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c27e2-p102">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="c27e2-117">Modifique o modelo do servidor web existente para permitir que os usuários autenticados se inscrevam ou crie um novo modelo de servidor web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam.</span><span class="sxs-lookup"><span data-stu-id="c27e2-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="c27e2-118">Para obter instruções detalhadas, consulte [Modelos de certificado](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="c27e2-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="c27e2-119">Solicite um certificado usando o snap-in certificado selecionando o modelo de servidor Web que você habilitou.</span><span class="sxs-lookup"><span data-stu-id="c27e2-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="c27e2-120">Certifique-se de adicionar o nome comum no assunto e o nome DNS no nome alternativo com o FQDN do gateway e confirmar a chave privada que tornam a chave privada exportável está selecionada em Opções de chave.</span><span class="sxs-lookup"><span data-stu-id="c27e2-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> <span data-ttu-id="c27e2-121">Para obter instruções detalhadas, consulte [solicitar um certificado](https://technet.microsoft.com/en-us/library/cc730689.aspx).</span><span class="sxs-lookup"><span data-stu-id="c27e2-121">For detailed instructions, see [Request a Certificate](https://technet.microsoft.com/en-us/library/cc730689.aspx).</span></span>
    
4. <span data-ttu-id="c27e2-122">Exporte o certificado SSL com a chave privada e siga as instruções do fornecedor do gateway PSTN para importar o certificado.</span><span class="sxs-lookup"><span data-stu-id="c27e2-122">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="c27e2-123">Atualizar o domínio do locatário</span><span class="sxs-lookup"><span data-stu-id="c27e2-123">Update the domain for your tenant</span></span>

<span data-ttu-id="c27e2-124">Confira se você concluiu as etapas de atualização de seu domínio no Office 365 e se é capaz de adicionar registros DNS.</span><span class="sxs-lookup"><span data-stu-id="c27e2-124">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="c27e2-125">Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [vídeo: configurar seu domínio no Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="c27e2-125">For more information about how to set up your domain in Office 365, see [Video: Set up your domain in Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="c27e2-126">Adicionar registros DNS ao Office 365 para borda</span><span class="sxs-lookup"><span data-stu-id="c27e2-126">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="c27e2-127">Adicione os seguintes registros DNS a seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c27e2-127">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="c27e2-128">Para obter informações sobre como adicionar registros DNS para seu locatário do Office 365, consulte [Adicionar ou editar registros DNS personalizados no Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="c27e2-128">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="c27e2-129">Adicionar um registro DNS A à Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="c27e2-129">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="c27e2-p107">Os registros SRV serão criados automaticamente pelo Office 365 e os scripts de implantação. Confira se é possível pesquisar os dois serviços SIP a seguir na Borda: _sip and _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="c27e2-p107">SRV records will automatically be created by Office 365 and the deployment scripts. Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Confirmação de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="c27e2-133">Configure a conectividade híbrida entre o Cloud Connector Edition e o Office 365</span><span class="sxs-lookup"><span data-stu-id="c27e2-133">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="c27e2-134">Para configurar a conectividade híbrida entre seu Skype para implantação do conector de nuvem Business Edition e seu locatário do Office 365, execute o seguinte cmdlet em uma sessão PowerShell remota.</span><span class="sxs-lookup"><span data-stu-id="c27e2-134">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="c27e2-135">Para saber como estabelecer uma sessão PowerShell remota, consulte: [Using Windows PowerShell para gerenciar Skype para negócios Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c27e2-135">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="c27e2-136">O cmdlet define o FQDN externo da Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="c27e2-136">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="c27e2-137">No primeiro dos comandos, o \<FQDN de borda de acesso externo\> deve ser um para a função de borda de acesso SIP.</span><span class="sxs-lookup"><span data-stu-id="c27e2-137">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="c27e2-138">Por padrão, este deve ser ap.\<nome de domínio\>.</span><span class="sxs-lookup"><span data-stu-id="c27e2-138">By default, this should be ap.\<Domain Name\>.</span></span>
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="c27e2-139">O FQDN de borda de acesso externo usados para o destino de ponto deve ser definido como um site PSTN que será usado apenas como fallback no caso de um usuário não for atribuído a um site PSTN.</span><span class="sxs-lookup"><span data-stu-id="c27e2-139">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="c27e2-140">Para obter mais informações, consulte [implantar um único site no conector de nuvem](deploy-a-single-site-in-cloud-connector.md) e [implantar vários sites em nuvem de conector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="c27e2-140">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="c27e2-141">Configurar gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="c27e2-141">Set up PSTN gateways</span></span>

<span data-ttu-id="c27e2-p111">Configure os troncos em cada gateway PSTN para que eles apontem para os Servidores de Mediação de todos os dispositivos. Cada tronco deve apontar para o endereço IP ou FQDN do Servidor de Mediação e não para o FQDN do pool do Servidor de Mediação, pois o FQDN do pool é o mesmo para todos os servidores no pool. Os troncos devem ser definidos com a mesma prioridade.</span><span class="sxs-lookup"><span data-stu-id="c27e2-p111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances. Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool. Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="c27e2-145">Se você usa o protocolo TLS entre os Servidores de Mediação e os gateways, é necessário configurá-los para dar suporte a MTLS, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c27e2-145">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="c27e2-146">Exporte a Autoridade de Certificação raiz do computador que executa o Active Directory do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="c27e2-146">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="c27e2-147">Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.</span><span class="sxs-lookup"><span data-stu-id="c27e2-147">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="c27e2-p112">Importe o Certificado de Autoridade de Certificação raiz emitido para seu gateway nos Servidores de Mediação. Para obter um certificado SSL para o gateway, use o serviço da Autoridade de Certificação em execução no computador do Active Directory do Cloud Connector, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c27e2-p112">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers. If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
  - <span data-ttu-id="c27e2-150">Modificar o modelo de servidor Web existente para permitir que os usuários autenticados registrar ou criar um novo modelo de servidor Web para configurar outras propriedades e permitir que os usuários autenticados que se inscrevam.</span><span class="sxs-lookup"><span data-stu-id="c27e2-150">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="c27e2-151">Para obter instruções detalhadas, consulte [Modelos de certificado](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="c27e2-151">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
  - <span data-ttu-id="c27e2-152">Solicite um certificado usando o snap-in certificado selecionando o modelo de servidor Web que você habilitou.</span><span class="sxs-lookup"><span data-stu-id="c27e2-152">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="c27e2-153">Certifique-se de adicionar o nome comum no assunto e o nome DNS no nome alternativo com o FQDN do gateway e confirmar a chave privada que tornam a chave privada exportável está selecionada em Opções de chave.</span><span class="sxs-lookup"><span data-stu-id="c27e2-153">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> <span data-ttu-id="c27e2-154">Para obter instruções detalhadas, consulte [solicitar um certificado](https://technet.microsoft.com/library/cc730689.aspx).</span><span class="sxs-lookup"><span data-stu-id="c27e2-154">For detailed instructions, see [Request a Certificate](https://technet.microsoft.com/library/cc730689.aspx).</span></span>
    
4. <span data-ttu-id="c27e2-155">Exporte o certificado SSL com a chave privada e siga as instruções do fornecedor do gateway PSTN para importar o certificado.</span><span class="sxs-lookup"><span data-stu-id="c27e2-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="c27e2-156">Os gateways PSTN em cada site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site.</span><span class="sxs-lookup"><span data-stu-id="c27e2-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="c27e2-157">Configurar usuários no Office 365</span><span class="sxs-lookup"><span data-stu-id="c27e2-157">Set up your users in Office 365</span></span>

<span data-ttu-id="c27e2-158">Faça logon no portal de administração do Office 365, adicione os usuários que serão habilitados para serviços de voz online e atribua a licença E5 ou o complemento do Sistema de Telefonia do Office 365 à licença E3 para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="c27e2-158">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="c27e2-159">Para obter informações sobre como adicionar usuários, consulte [Adicionar usuários para o Office 365 para empresas](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="c27e2-159">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="c27e2-160">Habilitar usuários para os serviços de voz e de caixa postal do Sistema de Telefonia do Office 365</span><span class="sxs-lookup"><span data-stu-id="c27e2-160">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="c27e2-161">Depois de adicionar os usuários ao Office 365, habilite suas contas para os serviços de voz do Sistema de Telefonia do Office 365, incluindo a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="c27e2-161">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="c27e2-162">Para habilitar essas funcionalidades, faça logon no locatário do Office 365 usando uma conta com função de Administrador Global do Office 365 e que seja capaz de executar o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="c27e2-162">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="c27e2-163">Para saber como estabelecer uma sessão PowerShell remota, consulte: [Using Windows PowerShell para gerenciar Skype para negócios Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c27e2-163">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="c27e2-164">Atribuir a política ao usuário e configure voz número de telefone comercial do usuário, que você especificar com o valor do parâmetro **Identity** :</span><span class="sxs-lookup"><span data-stu-id="c27e2-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="c27e2-165">Você também pode especificar a identidade do usuário pelo endereço SIP, nome UPN, nome de domínio e nome de usuário (domínio\nome de usuário) e nome de exibição no Active Directory ("Diogo Martins"). </span><span class="sxs-lookup"><span data-stu-id="c27e2-165">You can also specify a user's Identity by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
<span data-ttu-id="c27e2-166">Em seguida, é possível verificar se os usuários foram adicionados e habilitados usando o seguinte script:</span><span class="sxs-lookup"><span data-stu-id="c27e2-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="c27e2-p117">Você deverá decidir se os usuários poderão ou não fazer chamadas internacionais. Por padrão, as chamadas internacionais são permitidas. As chamadas internacionais podem ser habilitadas ou desabilitadas para os usuários no Centro de Administração online do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c27e2-p117">You'll need to decide whether your users should be able to make international calls. By default, international calling is enabled. You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="c27e2-170">Para desabilitar as chamadas internacionais por usuário, execute o seguinte cmdlet no Powershell do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="c27e2-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="c27e2-171">Para reabilitar internacional chamar em uma base por usuário depois que ele tiver sido desabilitado, execute o cmdlet mesmo, mas altere o valor de **PolicyName** para *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="c27e2-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="c27e2-172">Atribuir usuários a sites PSTN</span><span class="sxs-lookup"><span data-stu-id="c27e2-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="c27e2-173">Use o PowerShell remoto do locatário para atribuir o site aos usuários, mesmo que você tenha implantado um único site.</span><span class="sxs-lookup"><span data-stu-id="c27e2-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="c27e2-174">Para saber como estabelecer uma sessão PowerShell remota, consulte: [Using Windows PowerShell para gerenciar Skype para negócios Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c27e2-174">To learn how to establish a remote PowerShell session, see: [Using Windows PowerShell to manage Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="c27e2-175">Se nenhum site PSTN estiver atribuído a um usuário, será feito fallback da conectividade híbrida entre a implantação do Skype for Business Cloud Connector Edition e seu locatário do Office 365 para usar o nível de locatário padrão um (destino par) de modo a possibilitar a realização de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c27e2-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="c27e2-176">Definir configurações do servidor de mediação híbrido online</span><span class="sxs-lookup"><span data-stu-id="c27e2-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="c27e2-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="c27e2-177"></span></span>

<span data-ttu-id="c27e2-178">Quando uma chamada de P2P será escalonada para uma conferência PSTN, o Skype para o servidor de conferência Business Online enviará um convite para o servidor de mediação do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="c27e2-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="c27e2-179">Para garantir que o Office 365 pode direcionar a esse convite com êxito, você precisa definir uma configuração no seu locatário online para cada servidor de mediação do conector de nuvem da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c27e2-179">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="c27e2-180">Crie um usuário no portal de administração do O365.</span><span class="sxs-lookup"><span data-stu-id="c27e2-180">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="c27e2-181">Usar qualquer nome de usuário que você deseja, como "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="c27e2-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="c27e2-182">Use o domínio SIP padrão do conector de nuvem (o primeiro domínio SIP do arquivo. ini) como o domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="c27e2-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="c27e2-p121">Não atribua nenhuma licença do O365 (como a E5) à conta criada. Espere a conclusão da sincronização do AD do O365.</span><span class="sxs-lookup"><span data-stu-id="c27e2-p121">Do not assign any Office 365 licenses (such as E5) to the account you create. Wait for Office 365 AD sync to complete.</span></span>
    
2. <span data-ttu-id="c27e2-185">Iniciar uma sessão de PowerShell remota do inquilino usando suas credenciais de administrador de locatário e execute o seguinte cmdlet para definir o servidor de mediação e o FQDN do servidor de borda para o usuário da conta, substituir \<DisplayName\> com o nome de exibição do usuário para o conta criada:</span><span class="sxs-lookup"><span data-stu-id="c27e2-185">Start a tenant remote PowerShell session using your tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created:</span></span>
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    <span data-ttu-id="c27e2-186">Para identificação, use o Nome de Exibição da conta do usuário do Office 365 criada para este Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="c27e2-186">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="c27e2-187">Para *MediationServerFQDN* , use o FQDN interno definido para seu servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="c27e2-187">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="c27e2-188">Para *EdgeServerExternalFQDN* , use o FQDN externo definido para o Proxy de acesso do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c27e2-188">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="c27e2-189">Se houver vários sites PSTN do Cloud Connector, escolha o FQDN do Proxy de Acesso do Servidor de Borda atribuído ao site que contém a localização do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="c27e2-189">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
3. <span data-ttu-id="c27e2-190">Se houver vários Servidores de Mediação do Cloud Connector (vários sites, alta disponibilidade), repita as etapas anteriores para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="c27e2-190">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    


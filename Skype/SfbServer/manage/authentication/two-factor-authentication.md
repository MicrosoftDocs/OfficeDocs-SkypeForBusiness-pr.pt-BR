---
title: Gerenciar autenticação de dois fatores no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumo: Gerencie a autenticação de dois fatores no Skype for Business Server.'
ms.openlocfilehash: 8e8f665d824cd5f21cc2ca874668eba90bc97c4b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119540"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="b511c-103">Gerenciar autenticação de dois fatores no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b511c-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="b511c-104">**Resumo:** Gerenciar a autenticação de dois fatores no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b511c-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="b511c-105">A autenticação de dois fatores fornece segurança aprimorada, exigindo que os usuários forneçam duas formas de autenticação ou identificação, ou seja, uma combinação de nome de usuário/senha e um token ou certificado.</span><span class="sxs-lookup"><span data-stu-id="b511c-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="b511c-106">Isso também é conhecido como "algo que você tem, algo que você sabe".</span><span class="sxs-lookup"><span data-stu-id="b511c-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="b511c-107">Um exemplo típico de autenticação de dois fatores com um certificado é o uso de cartões inteligentes.</span><span class="sxs-lookup"><span data-stu-id="b511c-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="b511c-108">Um cartão inteligente contém um certificado associado à conta de usuário e pode ser validado em relação às informações de usuário e certificado armazenadas em um servidor.</span><span class="sxs-lookup"><span data-stu-id="b511c-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="b511c-109">Comparando as informações do usuário (nome de usuário e senha) com o certificado fornecido, o servidor valida as credenciais e autentica o usuário.</span><span class="sxs-lookup"><span data-stu-id="b511c-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="b511c-110">Considere os seguintes assuntos ao configurar um ambiente do Skype for Business Server para dar suporte à autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b511c-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="b511c-111">Suporte para Cliente</span><span class="sxs-lookup"><span data-stu-id="b511c-111">Client Support</span></span>

<span data-ttu-id="b511c-112">As Atualizações Cumulativas do Lync Server 2013: cliente de área de trabalho de julho de 2013 e o cliente skype for Business são os únicos clientes que atualmente suportam a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b511c-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="b511c-113">Requisitos de topologia</span><span class="sxs-lookup"><span data-stu-id="b511c-113">Topology Requirements</span></span>

<span data-ttu-id="b511c-114">Os clientes são incentivados a implantar a autenticação de dois fatores usando o Skype for Business Server dedicado com Pools de Borda, Diretor e Usuário.</span><span class="sxs-lookup"><span data-stu-id="b511c-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="b511c-115">Para habilitar a autenticação passiva para usuários, outros métodos de autenticação devem ser desabilitados para outras funções e serviços, incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b511c-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="b511c-116">**Tipo de configuração**</span><span class="sxs-lookup"><span data-stu-id="b511c-116">**Configuration Type**</span></span>|<span data-ttu-id="b511c-117">**Tipo de serviço**</span><span class="sxs-lookup"><span data-stu-id="b511c-117">**Service Type**</span></span>|<span data-ttu-id="b511c-118">**Função de servidor**</span><span class="sxs-lookup"><span data-stu-id="b511c-118">**Server Role**</span></span>|<span data-ttu-id="b511c-119">**Tipo de autenticação a ser desabilitado**</span><span class="sxs-lookup"><span data-stu-id="b511c-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b511c-120">Serviço Web</span><span class="sxs-lookup"><span data-stu-id="b511c-120">Web Service</span></span>  <br/> |<span data-ttu-id="b511c-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="b511c-121">WebServer</span></span>  <br/> |<span data-ttu-id="b511c-122">Diretor</span><span class="sxs-lookup"><span data-stu-id="b511c-122">Director</span></span>  <br/> |<span data-ttu-id="b511c-123">Kerberos, NTLM e Certificate</span><span class="sxs-lookup"><span data-stu-id="b511c-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="b511c-124">Serviço Web</span><span class="sxs-lookup"><span data-stu-id="b511c-124">Web Service</span></span>  <br/> |<span data-ttu-id="b511c-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="b511c-125">WebServer</span></span>  <br/> |<span data-ttu-id="b511c-126">Front-end</span><span class="sxs-lookup"><span data-stu-id="b511c-126">Front End</span></span>  <br/> |<span data-ttu-id="b511c-127">Kerberos, NTLM e Certificate</span><span class="sxs-lookup"><span data-stu-id="b511c-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="b511c-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="b511c-128">Proxy</span></span>  <br/> |<span data-ttu-id="b511c-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="b511c-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="b511c-130">Borda</span><span class="sxs-lookup"><span data-stu-id="b511c-130">Edge</span></span>  <br/> |<span data-ttu-id="b511c-131">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="b511c-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="b511c-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="b511c-132">Proxy</span></span>  <br/> |<span data-ttu-id="b511c-133">Registrador</span><span class="sxs-lookup"><span data-stu-id="b511c-133">Registrar</span></span>  <br/> |<span data-ttu-id="b511c-134">Front-end</span><span class="sxs-lookup"><span data-stu-id="b511c-134">Front End</span></span>  <br/> |<span data-ttu-id="b511c-135">Kerberos e NTLM</span><span class="sxs-lookup"><span data-stu-id="b511c-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="b511c-136">A menos que esses tipos de autenticação sejam desabilitados no nível de serviço, todas as outras versões do cliente não poderão entrar com êxito depois que a autenticação de dois fatores for habilitada em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="b511c-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="b511c-137">Descoberta do Serviço do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b511c-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="b511c-138">Os registros DNS usados por clientes internos e/ou externos para descobrir os serviços do Skype for Business devem ser configurados para resolver para um servidor do Skype for Business que não está habilitado para autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b511c-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="b511c-139">Com essa configuração, os usuários dos Pools do Skype for Business que não estão habilitados para autenticação de dois fatores não serão necessários para inserir um PIN para autenticação, enquanto os usuários dos Pools do Skype for Business habilitados para autenticação de dois fatores serão obrigados a inserir seu PIN para autenticação.</span><span class="sxs-lookup"><span data-stu-id="b511c-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="b511c-140">Autenticação do Exchange</span><span class="sxs-lookup"><span data-stu-id="b511c-140">Exchange Authentication</span></span>

<span data-ttu-id="b511c-141">Os clientes que implantaram a autenticação de dois fatores para o Microsoft Exchange podem descobrir que determinados recursos no cliente estão indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="b511c-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="b511c-142">Isso é atualmente por design, pois o cliente skype for Business não dá suporte à autenticação de dois fatores para recursos que dependem da integração com o Exchange.</span><span class="sxs-lookup"><span data-stu-id="b511c-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="b511c-143">Contatos</span><span class="sxs-lookup"><span data-stu-id="b511c-143">Contacts</span></span>

<span data-ttu-id="b511c-144">Os usuários do Skype for Business que estão configurados para aproveitar o recurso de Armazenamento unificado de Contatos descobrirão que seus contatos não estão mais disponíveis depois de entrar com a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b511c-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="b511c-145">Você deve usar o cmdlet **Invoke-CsUcsRollback** para remover contatos de usuário existentes do Armazenamento unificado de contatos e armazená-los no Skype for Business Server antes de habilitá-los.</span><span class="sxs-lookup"><span data-stu-id="b511c-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="b511c-146">Pesquisa de Habilidades</span><span class="sxs-lookup"><span data-stu-id="b511c-146">Skill Search</span></span>

<span data-ttu-id="b511c-147">Os clientes que configuraram o recurso pesquisa de habilidades em seu ambiente do Skype for Business descobrirão que esse recurso não funciona quando o Skype for Business está habilitado para autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b511c-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="b511c-148">Isso é por design, pois o Microsoft SharePoint atualmente não dá suporte à autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b511c-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="b511c-149">Credenciais</span><span class="sxs-lookup"><span data-stu-id="b511c-149">Credentials</span></span>

<span data-ttu-id="b511c-150">Há várias considerações de implantação envolvendo credenciais salvas do Skype for Business que podem afetar os usuários configurados para usar a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b511c-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="b511c-151">Excluir credenciais salvas</span><span class="sxs-lookup"><span data-stu-id="b511c-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="b511c-152">Os usuários  devem usar a opção Excluir minhas informações de entrada no cliente skype for Business e excluir sua pasta de perfil SIP de %localappdata%\Microsoft\Office\15.0\Skype for Business antes de tentar entrar pela primeira vez usando a autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b511c-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="b511c-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="b511c-153">DisableNTCredentials</span></span>

<span data-ttu-id="b511c-154">Com o método de autenticação Kerberos ou NTLM, as credenciais do Windows do usuário são usadas automaticamente para autenticação.</span><span class="sxs-lookup"><span data-stu-id="b511c-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="b511c-155">Em uma implantação típica do Skype for Business Server em que Kerberos e/ou NTLM estão habilitados para autenticação, os usuários não devem ter que inserir suas credenciais sempre que entrarem.</span><span class="sxs-lookup"><span data-stu-id="b511c-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="b511c-156">Se os usuários não são solicitados intencionalmente a solicitar credenciais antes de serem solicitados a inserir seu PIN, a chave do Registro **DisableNTCredentials** pode ser configurada incorretamente em computadores cliente, possivelmente por meio da Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="b511c-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="b511c-157">Para impedir o prompt adicional de credenciais, crie a seguinte entrada do Registro na estação de trabalho local ou use o modelo administrativo do Skype for Business para aplicar a todos os usuários para um determinado pool usando a Política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="b511c-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="b511c-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="b511c-158">SavePassword</span></span>

<span data-ttu-id="b511c-159">Quando um usuário faz logor no Skype for Business pela primeira vez, o usuário é solicitado a salvar sua senha.</span><span class="sxs-lookup"><span data-stu-id="b511c-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="b511c-160">Se selecionada, essa opção permite que o certificado de cliente do usuário seja armazenado no armazenamento de certificados pessoais e as credenciais do Windows do usuário sejam armazenadas no Gerenciador de Credenciais do computador local.</span><span class="sxs-lookup"><span data-stu-id="b511c-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="b511c-161">A configuração do Registro **savePassword** deve ser desabilitada quando o Skype for Business estiver configurado para dar suporte à autenticação de dois fatores.</span><span class="sxs-lookup"><span data-stu-id="b511c-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="b511c-162">Para impedir que os usuários salvam suas senhas, altere a seguinte entrada do Registro na estação de trabalho local ou use o modelo administrativo do Skype for Business para aplicar a todos os usuários para um determinado pool usando a Política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="b511c-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="b511c-163">Reprodução de token do AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="b511c-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="b511c-164">O AD FS 2.0 fornece um recurso conhecido como detecção de repetição de token, pelo qual várias solicitações de token usando o mesmo token podem ser detectadas e descartadas.</span><span class="sxs-lookup"><span data-stu-id="b511c-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="b511c-165">Quando esse recurso está habilitado, a detecção de repetição de token protege a integridade das solicitações de autenticação no perfil passivo WS-Federation e no perfil SAML WebSSO, fazendo com que o mesmo token nunca seja usado mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="b511c-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="b511c-166">Esse recurso deve ser habilitado em situações em que a segurança é uma preocupação muito alta, como ao usar quiosques.</span><span class="sxs-lookup"><span data-stu-id="b511c-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="b511c-167">Para obter mais informações sobre a detecção de repetição de token, consulte [Best Practices for Secure Planning and Deployment of AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="b511c-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10)).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="b511c-168">Acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="b511c-168">External User Access</span></span>

<span data-ttu-id="b511c-169">A configuração de um Proxy ADFS ou Proxy Reverso para dar suporte à autenticação de dois fatores do Skype for Business de redes externas não é abordada nesses tópicos.</span><span class="sxs-lookup"><span data-stu-id="b511c-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b511c-170">Confira também</span><span class="sxs-lookup"><span data-stu-id="b511c-170">See also</span></span>

[<span data-ttu-id="b511c-171">Configurar a autenticação de dois fatores no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b511c-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
